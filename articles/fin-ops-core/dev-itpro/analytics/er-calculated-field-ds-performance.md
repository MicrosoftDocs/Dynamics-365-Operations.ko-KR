---
title: 매개 변수화된 CALCULATED FIELD 데이터 소스를 추가하여 ER 솔루션의 성능 향상
description: 이번에는 매개 변수화된 CALCULATED FIELD 데이터 소스를 추가하여 전자 보고(ER) 솔루션의 성능을 개선하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5fada2fc0b35e22da18f5d6a0505df077d5ada4e0221031d63c316d8c705bc79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460698"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>매개 변수화된 CALCULATED FIELD 데이터 소스를 추가하여 ER 솔루션의 성능 향상

[!include [banner](../includes/banner.md)]

이번에는 실행되는 [ER(전자 보고)](general-electronic-reporting.md) 형식의 [성능 추적](trace-execution-er-troubleshoot-perf.md)을 가져온 다음 해당 추적의 정보를 사용하여 매개 변수화된 **계산 필드** 데이터 원본을 구성하여 성능을 개선하는 방법에 대해 설명합니다.

비즈니스 문서를 생성하기 위해 ER 구성을 설계하는 프로세스의 일부로 애플리케이션에서 데이터를 검색하고 생성된 출력에 입력하는 데 사용되는 방법을 정의합니다. **계산된 필드** 유형의 매개 변수화된 ER 데이터 소스를 설계하여 데이터베이스 호출 수를 줄이고 ER 형식 실행의 세부 정보 수집과 관련된 시간과 비용을 크게 줄일 수 있습니다.

## <a name="prerequisites"></a>전제 조건

- 이 주제의 예를 완료하려면 다음 [역할](../sysadmin/tasks/assign-users-security-roles.md) 중 하나에 대한 액세스 권한이 있어야 합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 회사는 **DEMF** 로 설정되어야 합니다.
- 이 항목의 [부록 1](#appendix1)에 있는 단계에 따라 이 항목의 예시를 완료하는 데 필요한 샘플 Microsoft ER 솔루션의 구성 요소를 다운로드하십시오.
- 이 항목의 [부록 2](#appendix2)에 있는 단계에 따라 ER 프레임워크를 사용하여 샘플 Microsoft ER 솔루션의 성능을 향상시키는 데 필요한 최소한의 ER 매개 변수 집합을 구성하십시오.

## <a name="import-the-sample-er-solution"></a>샘플 ER 솔루션 가져오기

공급 업체 거래를 보여주는 새 보고서를 생성하기 위해 ER 솔루션을 설계해야 한다고 가정해 보십시오. 현재 **공급 업체 거래** 페이지에서 선택한 공급 업체에 대한 거래를 찾을 수 있습니다(**채무** \> **공급 업체** \> **모든 공급 업체** 로 이동하여 **공급 업체** 를 선택한 다음 작업 창의 공급 업체 탭, **거래** 그룹에서 **거래** 선택). . 그러나 모든 공급 업체 트랜잭션을 XML 형식의 하나의 전자 문서에 포함하려고 합니다. 이 솔루션은 필요한 데이터 모델, 모델 매핑 및 형식 구성 요소를 포함하는 여러 ER 구성으로 구성됩니다.

첫 번째 단계는 샘플 ER 솔루션을 가져와서 공급 업체 거래 보고서를 생성하는 것입니다.

1. 회사에 프로비저닝된 Microsoft Dynamics 365 Finance 인스턴스에 로그인합니다.
2. 이번에는 **Litware, Inc.** 샘플 회사에 대한 구성을 만들고 수정합니다. 이 구성 제공자가 Finance 인스턴스에 추가되었고 활성으로 표시되었는지 확인하십시오. 자세한 내용은 [구성 공급자 생성 및 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하십시오.
3. **전자 보고** 작업 영역에서 **보고 구성** 타일을 선택합니다.
4. **구성** 페이지에서 사전 요구 사항으로 다운로드한 ER 구성을 데이터 모델, 모델 매핑, 형식의 순서로 Finance로 가져옵니다. 각 구성에 대해 다음 단계를 따르십시오.

    1. 작업 창에서 **XML 파일에서** \> **Exchange 로드** 를 선택합니다.
    2. **찾아보기** 를 선택하고 XML 형식의 ER 구성에 적합한 파일을 선택합니다.
    3. **확인** 을 선택합니다.

![구성 페이지에서 가져온 구성.](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>샘플 ER 솔루션 검토

### <a name="review-the-model-mapping"></a>모델 매핑 검토

1. **구성** 페이지의 구성 트리에서 **성능 개선 모델** 을 펼치고 **성능 개선 맵핑** 을 선택하십시오.
2. 작업 창에서 **디자이너** 를 선택합니다.
3. **모델과 데이터 원본 간 매핑** 페이지의 작업 창에서 **디자이너** 를 선택합니다.

    이 ER 모델 매핑은 다음 작업을 수행하도록 설계되었습니다.

    - VendTrans 테이블(**Trans** 데이터 소스)에 저장된 공급 업체 트랜잭션 목록을 가져옵니다.
    - 모든 트랜잭션에 대해 VendTable 테이블에서 트랜잭션이 게시된 공급 업체의 기록(**\#Vend** 데이터 소스)를 가져옵니다.

    > [!NOTE]
    > **\#Vend** 데이터 소스는 기존의 다대일 관계인 **\@'\>Relations'.VendTable\_AccountNum** 을 사용하여 해당 공급 업체 기록을 가져오도록 구성됩니다.

    이 구성의 모델 매핑은 이 모델에 대해 생성되고 Finance에서 실행되는 모든 ER 형식에 대한 기본 데이터 모델을 구현합니다. 따라서 **Trans** 데이터 소스의 내용은 추상 **모델** 데이터 소스와 같은 ER 형식에 대해 노출됩니다.

    ![모델 매핑 디자이너 페이지의 트랜스 데이터 원본입니다.](media/er-calculated-field-ds-performance-mapping-1.png)

4. **모델 매핑 디자이너** 페이지를 닫습니다.
5. **데이터 소스 매핑 모델링** 페이지를 닫습니다.

### <a name="review-format"></a>검토 형식

1. **구성** 페이지의 구성 트리에서 **성능 개선 모델** 을 펼치고 **성능 개선 형식** 을 선택하십시오.
2. 작업 창에서 **디자이너** 를 선택합니다.
3. **형식 디자이너** 페이지의 **매핑** 탭에서 **확장/축소** 를 선택합니다.
4. **모델**, **데이터** 및 **트랜잭션** 항목을 확장합니다.

    이 ER 형식은 XML 형식의 공급 업체 트랜잭션 보고서를 생성하도록 설계되었습니다.

    ![형식 디자이너 페이지에서 형식 데이터 소스 및 형식 요소의 구성된 바인딩을 지정합니다.](media/er-calculated-field-ds-performance-format.png)

5. **형식 디자이너** 페이지를 닫습니다.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>샘플 ER 솔루션을 실행하여 실행 추적

ER 솔루션의 첫 번째 버전 설계를 마쳤다고 가정해 보십시오. 이제 Finance 인스턴스에서 솔루션을 테스트하고 실행 성능을 분석하려고 합니다.

### <a name="turn-on-the-er-performance-trace"></a>ER 성능 추적 켜기

1. **DEMF** 회사를 선택합니다.
2. [ER 성능 추적 켜기](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace)의 단계에 따라 ER 형식이 실행되는 동안 성능 추적을 생성하십시오.

    ![사용자 매개 변수 대화 상자.](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>ER 형식 실행

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **성능 개선 형식** 을 선택합니다.
3. 작업 창에서 **송장** 을 선택합니다.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>성능 추적을 사용하여 모델 매핑 성능 분석

1. **구성** 페이지의 구성 트리에서 **성능 개선 매핑** 을 선택합니다.
2. 작업 창에서 **디자이너** 를 선택합니다.
3. **모델 매핑** 페이지의 작업 창에서 **디자이너** 를 선택합니다.
4. **모델 매핑 디자이너** 페이지의 작업 창에서 **성능 추적** 을 선택합니다.
5. 가장 최근에 생성된 추적을 선택한 다음 **확인** 을 선택합니다.

현재 모델 매핑의 일부 데이터 소스 항목에 대한 새 정보를 사용할 수 있습니다.

- 데이터 소스를 사용하여 데이터를 가져오는 데 소요된 실제 시간
- 전체 모델 매핑을 실행하는 데 소요된 총 시간의 백분율로 표시되는 동일한 시간

![모델 매핑 디자이너 페이지의 실행 시간 세부 정보.](./media/er-calculated-field-ds-performance-mapping-2.png)

**성능 통계** 그리드는 **Trans** 데이터 소스가 VendTrans 테이블을 한 번 호출함을 보여줍니다. **Trans** 데이터 소스의 값 **\[265\]\[Q:265\]** 는 265개의 공급 업체 트랜잭션이 애플리케이션 테이블에서 가져와 데이터 모델로 반환되었음을 나타냅니다.

또한 **성능 통계** 그리드는 **\#Vend** 데이터 소스가 실행되는 동안 현재 모델 매핑이 데이터베이스 요청을 복제함을 보여줍니다. 이 중복은 다음과 같은 이유로 발생합니다.

- 공급 업체 테이블은 265회의 반복 공급 업체 트랜잭션 각각에 대해 두 번 호출되어 총 530회의 호출이 가능합니다.

    - 공급 업체 계정 번호를 입력하기 위해 한 번 호출됩니다.
    - 공급 업체 이름을 입력하기 위해 한 번 호출됩니다.

- 가져온 트랜잭션이 5개 공급 업체에 대해서만 게시된 경우에도 반복되는 각 공급 업체 트랜잭션에 대해 공급 업체 테이블이 호출됩니다. 530개 호출 중 525개가 중복됩니다. 다음 그림은 중복 호출(데이터베이스 요청)에 대해 수신하는 메시지를 보여줍니다.

![모델 매핑 디자이너 페이지의 중복 데이터베이스 요청에 대한 메시지입니다.](./media/er-calculated-field-ds-performance-mapping-2a.png)

총 모델 매핑 실행 시간(약 8초) 중 80% 이상(약 6초)이 VendTable 애플리케이션 테이블에서 값을 검색하는 데 사용되었습니다. 이 비율은 VendTrans 애플리케이션 테이블의 정보 양과 비교할 때 5개 공급 업체의 두 가지 속성에 대해 너무 큽니다.

모든 트랜잭션에 대한 공급 업체 세부 정보를 가져오기 위해 수행되는 호출 수를 줄이고 모델 매핑의 성능을 개선하기 위해 **\#Vend** 데이터 원본에 대한 캐싱을 사용할 수 있습니다.

> [!NOTE]
> **Trans\\\#Vend** 데이터 소스는 런타임 시 **Trans** 데이터 소스의 현재 트랜잭션 범위에서 캐시됩니다.

**\#Vend** 데이터 소스를 캐싱하여 중복 호출 수를 525개에서 260개로 줄이지만 중복을 완전히 제거하지는 못합니다. 중복을 완전히 제거하기 위해 **계산된 필드** 유형의 매개 변수가 있는 새 데이터 원본을 구성할 수 있습니다.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>실행 추적 정보를 기반으로 모델 매핑 개선

### <a name="change-the-logic-of-the-model-mapping"></a>모델 매핑의 논리 변경

데이터베이스에 대한 중복 호출을 방지하기 위해 다음 단계에 따라 **계산된 필드** 유형의 데이터 원본 및 캐싱을 사용합니다.

1. **구성** 페이지의 구성 트리에서 **성능 개선 매핑** 을 선택합니다.
2. 작업 창에서 **디자이너** 를 선택합니다.
3. **모델 매핑** 페이지의 작업 창에서 **디자이너** 를 선택합니다.
4. **모델 매핑 디자이너** 페이지에서 다음 단계에 따라 VendTable 애플리케이션 테이블의 기록에 액세스하기 위해 **테이블 기록** 유형의 데이터 원본을 추가합니다.

    1. **데이터 원본 유형** 창에서 **Dynamics 365 for Operations** 을 확장하고 **테이블 기록** 를 선택합니다.
    2. **루트 추가** 를 선택합니다.
    3. 대화 상자의 **이름** 필드에 **Vend** 를 입력합니다.
    4. **테이블** 필드에 **VendTable** 을 입력합니다.
    5. **확인** 을 선택합니다.

5. 데이터 원본이 컨테이너에 있는 경우에만 **계산된 필드** 유형의 데이터 원본에 대한 호출을 매개 변수화할 수 있습니다. 따라서 다음 단계에 따라 **빈 컨테이너** 유형의 데이터 소스를 추가하여 **계산된 필드** 유형의 매개 변수화된 새 데이터 소스를 보유하십시오.

    1. **데이터 원본 유형** 창에서 **일반** 을 확장하고 **빈 컨테이너** 를 선택합니다.
    2. **루트 추가** 를 선택합니다.
    3. 대화 상자의 **이름** 필드에 **Box** 를 입력합니다.
    3. **확인** 을 선택합니다.

    ![모델 매핑 디자이너 페이지의 상자 데이터 원본입니다.](./media/er-calculated-field-ds-performance-mapping-3.png)

6. 다음 단계에 따라 **계산된 필드** 유형의 매개 변수화된 데이터 소스를 추가하십시오.

    1. **데이터 원본** 창에서 **상자** 를 선택합니다.
    2. **데이터 원본 유형** 창에서 **함수** 를 확장하고 **계산된 필드** 를 선택합니다.
    3. **추가** 를 선택합니다.
    4. 대화 상자의 **이름** 필드에 **Vend** 를 입력합니다.
    5. **수식 편집** 을 선택합니다.
    6. **공식 디자이너** 페이지에서 **매개 변수** 를 선택하여 이 데이터 소스가 호출될 때 제공해야 하는 매개 변수를 지정합니다.
    7. **매개 변수** 대화 상자에서 **새로 만들기** 를 선택합니다.
    8. **이름** 필드에 **parmVendAccNumber** 를 입력합니다.
    9. **유형** 필드에서 **스트링** 을 선택하십시오.
    10. **확인** 을 선택합니다.
    11. **수식** 필드에 **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))** 을 입력합니다.
    12. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.
    13. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

7. 추가된 데이터 소스를 실행 중에 캐시된 것으로 표시하려면 다음 단계를 따르십시오.

    1. **데이터 원본** 창에서 **상\\자** 를 선택합니다.
    2. **캐시** 를 선택합니다.

    > [!NOTE]
    > **Box\\Vend** 데이터 소스는 런타임 시 **Trans** 데이터 소스의 모든 공급 업체 트랜잭션 범위에서 캐시됩니다.

8. **Box\\Vend** 데이터 소스를 사용하도록 중첩된 **Trans\\\#Vend** 데이터 소스를 업데이트하려면 다음 단계를 따르십시오.

    1. **데이터 원본** 창에서 **Trans** 를 확장합니다.
    2. **Trans\\\#Vend** 데이터 원본을 선택한 다음 **편집** \> **수식 편집** 을 선택합니다.
    3. **수식 디자이너** 페이지의 **수식** 필드에 **Box.Vend(\@.AccountNum)** 을 입력합니다.
    4. **저장** 을 선택한 다음 **수식 디자이너** 페이지를 닫습니다.
    5. **확인** 을 선택하여 선택한 데이터 원본에 대한 변경을 완료합니다.

9. **저장** 을 선택합니다.

    ![모델 매핑 디자이너 페이지에서 데이터 소스를 판매하십시오.](./media/er-calculated-field-ds-performance-mapping-4.png)

10. **모델 매핑 디자이너** 페이지를 닫습니다.
11. **모델 매핑** 페이지를 닫습니다.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>수정된 버전의 ER 모델 매핑 완료

1. **구성** 페이지의 FastTab **버전** 에서 **성능 개선 매핑** 구성의 버전 **1.2** 를 선택합니다.
2. **상태 변경** \> **완료** 를 선택한 다음 **확인** 을 선택합니다.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>수정된 ER 솔루션을 실행하여 실행 추적

이 항목 앞부분의 [ER 형식 실행](#run-format) 섹션에 있는 단계를 반복하여 새 성능 추적을 생성합니다.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>성능 추적을 사용하여 모델 매핑에 대한 조정 분석 

1. **구성** 페이지의 구성 트리에서 **성능 개선 매핑** 을 선택합니다.
2. 작업 창에서 **디자이너** 를 선택합니다.
3. **모델 매핑** 페이지의 작업 창에서 **디자이너** 를 선택합니다.
4. **모델 매핑 디자이너** 페이지의 작업 창에서 **성능 추적** 을 선택합니다.
5. 가장 최근에 생성된 추적을 선택한 다음 **확인** 을 선택합니다.

모델 매핑을 조정하면 데이터베이스에 대한 중복 쿼리가 제거됩니다. 이 모델 매핑에 대한 데이터베이스 테이블 및 데이터 소스에 대한 호출 수도 감소했습니다.

![모델 매핑 디자이너 페이지 1의 추적 정보.](./media/er-calculated-field-ds-performance-mapping-5.png)

총 실행 시간이 약 20배 단축되었습니다(약 8초에서 약 400밀리초로). 따라서 전체 ER 솔루션의 성능이 향상되었습니다.

![모델 매핑 디자이너 페이지 2의 추적 정보.](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>부록 1 샘플 Microsoft ER 솔루션의 구성 요소 다운로드

다음 파일을 다운로드하여 로컬에 저장해야 합니다.

| 파일                                        | 콘텐츠 |
|---------------------------------------------|---------|
| 성능 향상 model.version.1     | [샘플 ER 데이터 모델 구성](https://download.microsoft.com/download/4/6/f/46f0f3fa-782b-414a-8f7b-b6c64a388661/Performance_improvement_model.version.1.xml) |
| 성능 개선 mapping.version.1.1 | [샘플 ER 모델 매핑 구성](https://download.microsoft.com/download/8/9/1/8913a763-afb8-4bf4-aaf1-95ad793ffc5a/Performance_improvement_mapping.version.1.1.xml) |
| 성능 향상 형식.version.1.1  | [샘플 ER 형식 구성](https://download.microsoft.com/download/9/0/c/90c75963-bc78-4edc-9096-556bbe281f10/Performance_improvement_format.version.1.1.xml) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>부록 2 ER 프레임워크 구성

샘플 Microsoft ER 솔루션의 성능을 개선하기 위해 ER 프레임워크를 사용하기 시작하기 전에 최소한의 ER 매개 변수 집합을 구성해야 합니다.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>ER 매개 변수 구성

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.
3. **전자 보고 매개변수** 페이지의 **일반** 탭에서 **디자인 모드 활성화** 옵션을 **네** 로 설정합니다.
4. **첨부** 탭에서 다음 매개 변수를 설정합니다.

    - **구성** 필드에서 **DEMF** 회사의 **파일** 유형을 선택하십시오.
    - **작업 아카이브**, **임시**, **기준선** 및 **기타** 필드에서 **파일** 유형을 선택합니다.

ER 매개 변수에 대한 자세한 내용은 [ER 프레임워크 구성](electronic-reporting-er-configure-parameters.md)을 참조하세요.

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>ER 구성 공급자 활성화

추가된 모든 ER 구성은 ER 구성 공급자가 소유한 것으로 표시됩니다. 이 목적으로 **전자 보고** 작업 영역에서 활성화된 ER 구성 공급자가 사용됩니다. 따라서 ER 구성을 추가하거나 편집하기 전에 **전자 보고** 작업 영역에서 ER 구성 공급자를 활성화해야 합니다.

> [!NOTE]
> ER 구성의 소유자만 구성을 편집할 수 있습니다. 따라서 ER 구성을 편집하기 전에 **전자 보고** 작업 영역에서 적절한 ER 구성 공급자를 활성화해야 합니다.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>ER 구성 제공자 목록 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자 테이블** 페이지에서 각 공급자 레코드에는 고유한 이름과 URL이 있습니다. 이 페이지의 내용을 검토하세요. **Litware, Inc.** 에 대한 기록이 이미 있는 경우 다음 절차인 [새 ER 구성 공급자 추가](#ActivateProvider)를 건너뜁니다.

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>새 ER 구성 공급자 추가

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자** 페이지에서 **새로 만들기** 를 선택합니다.
4. **이름** 필드에서 **Litware, Inc.** 를 입력합니다.
5. **인터넷 주소** 필드에 `https://www.litware.com`을 입력합니다.
6. **저장** 을 선택합니다.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>ER 구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Litware, Inc.** 타일을 선택한 다음 **활성으로 설정** 을 선택합니다.

ER 구성 공급자에 대한 자세한 내용은 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하세요.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)
- [계산된 필드 유형의 ER 데이터 소스의 매개 변수화된 호출 지원](er-calculated-field-type.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
