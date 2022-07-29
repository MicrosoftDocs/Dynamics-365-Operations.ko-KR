---
title: ER 형식의 시퀀스 요소 실행 연기
description: 이번에는 전자 보고(ER) 형식에서 순번 요소의 실행을 연기하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 19d1cf0aa6e9b40a0e72a3a74acda6e2579d6ee2
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460863"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>ER 형식의 시퀀스 요소 실행 연기

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>개요

[전자 보고(ER)](general-electronic-reporting.md) 프레임워크의 작업 디자이너를 사용하여 아웃바운드 문서를 텍스트 형식으로 생성하는 데 사용되는 ER 솔루션의 형식 구성 요소를 [구성](tasks/er-format-configuration-2016-11.md)할 수 있습니다. 구성된 형식 구성 요소의 계층 구조는 다양한 형식의 형식 요소로 구성됩니다. 이러한 형식 요소는 생성된 문서를 런타임에 필요한 정보로 채우는 데 사용됩니다. 기본적으로 ER 형식을 실행할 때 형식 요소는 형식 계층에 표시되는 것과 같은 순서로 위에서 아래로 하나씩 실행됩니다. 그러나 디자인 타임에 구성된 형식 구성 요소의 모든 시퀀스 요소에 대한 실행 순서를 변경할 수 있습니다.

구성된 형식의 시퀀스 형식 요소에 대해 <a name="DeferredSequenceExecution"></a>**지연된 실행** 옵션을 켜면 해당 요소의 실행을 연기(연기)할 수 있습니다. 이 경우 요소는 상위 요소의 다른 모든 요소가 실행될 때까지 실행되지 않습니다.

이 기능에 대해 자세히 알아보려면 이 항목의 예시를 완료하십시오.

## <a name="limitations"></a>한계

**지연된 실행** 옵션은 텍스트 형식의 **아웃바운드** 문서를 생성하는 데 사용되는 ER 형식에 대해 구성된 시퀀스 요소에 대해서만 지원됩니다.

**지연된 실행** 옵션은 최대 길이가 제한된 잘린 시퀀스로 구성된 시퀀스에 적용할 수 없습니다.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>예:, ER 형식의 시퀀스 요소 실행 연기

다음 단계는 시스템 관리자 또는 전자 보고 함수 컨설턴트 [역할](../sysadmin/tasks/assign-users-security-roles.md)의 사용자가 실행 순서가 형식 계층의 순서와 다른 순서 요소를 포함하는 ER 형식을 구성하는 방법을 설명합니다.

이러한 단계는 Microsoft Dynamics 365 Finance의 **USMF** 회사에서 수행할 수 있습니다.

### <a name="prerequisites"></a>전제 조건

이 예를 완료하려면 다음 역할 중 하나에 대해 재무의 **USMF** 회사에 대한 액세스 권한이 있어야 합니다.

- 전자 보고 기능 컨설턴트
- 시스템 관리자

[ER 형식의 XML 요소 실행 연기 항목](er-defer-xml-element.md#Example)의 예시를 아직 완료하지 않은 경우 샘플 ER 솔루션의 다음 [구성](general-electronic-reporting.md#Configuration)을 다운로드하십시오.

| 콘텐츠 설명            | 파일 이름 |
|--------------------------------|-----------|
| ER 데이터 모델 구성    | [deferred elements.version.1.xml을 학습하는 모델](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| ER 모델 매핑 구성 | [deferred elements.version.1.1.xml 학습을 위한 매핑](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

시작하기 전에 샘플 ER 솔루션의 다음 구성도 다운로드하여 저장해야 합니다.

| 콘텐츠 설명     |파일 이름 |
|-------------------------|----------|
| ER 형식 구성 | [지연된 시퀀스를 학습하는 형식.version.1.1.xml](https://download.microsoft.com/download/0/f/5/0f55c341-8285-4d92-a46d-475d9a010927/Formattolearndeferredsequences.version.1.1.xml) |

### <a name="import-the-sample-er-configurations"></a>샘플 ER 구성 가져오기

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **보고 구성** 을 선택합니다.
3. **구성** 페이지에서 **지연된 요소 구성을 학습하는 모델** 을 구성 트리에서 사용할 수 없는 경우 ER 데이터 모델 구성을 가져옵니다.

    1. **Exchange** 를 선택한 다음 **XML 파일에서 로드** 를 선택합니다.
    2. **찾아보기** 를 선택하고 **지연된 elements.1.xml 파일을 학습할 모델** 을 찾아 선택한 다음 **확인** 을 선택합니다.

4. 구성 트리에서 **지연 요소 구성을 학습하기 위한 매핑** 을 사용할 수 없는 경우 ER 모델 매핑 구성을 가져옵니다.

    1. **Exchange** 를 선택한 다음 **XML 파일에서 로드** 를 선택합니다.
    2. **찾아보기** 를 선택하고 **Mapping to learning deferred elements.1.1.xml** 파일을 찾아 선택한 다음 **확인** 을 선택합니다.

5. ER 형식 구성 가져오기:

    1. **Exchange** 를 선택한 다음 **XML 파일에서 로드** 를 선택합니다.
    2. **찾아보기** 를 선택하고 **지연된 시퀀스를 학습할 형식.1.1.xml** 파일을 찾아 선택한 다음 **확인** 을 선택합니다.

6. 구성 트리에서 **모델을 확장하여 지연된 요소** 를 학습합니다.
7. 구성 트리에서 가져온 ER 구성 목록을 검토합니다.

    ![구성 페이지에서 가져온 ER 구성.](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 Litware, Inc. (`http://www.litware.com`) 샘플 회사의 [구성 공급자](general-electronic-reporting.md#Provider)가 나열되어 있고 활성으로 표시되어 있는지 확인합니다. 이 구성 공급자가 나열되지 않거나 활성으로 표시되지 않은 경우 [구성 공급자 만들기 및 활성으로 표시](./tasks/er-configuration-provider-mark-it-active-2016-11.md) 항목의 단계를 따르십시오.

    ![현지화 구성 페이지의 Litware, Inc. 샘플 회사.](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>가져온 모델 매핑 검토

세금 거래에 액세스하고 요청 시 액세스된 데이터를 노출하도록 구성된 ER 모델 매핑 구성 요소의 설정을 검토합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **보고 구성** 을 선택합니다.
3. **구성** 페이지의 구성 트리에서 **모델을 확장하여 지연된 요소** 를 학습합니다.
4. **매핑을 선택하여 지연된 요소** 구성을 학습합니다.
5. **디자이너** 를 선택하여 매핑 목록을 엽니다.
6. **디자이너** 를 선택하여 매핑 세부 정보를 검토합니다.
7. **세부 정보 표시** 를 선택합니다.
8. 세금 거래에 액세스하도록 구성된 데이터 소스를 검토합니다.

    - *테이블 기록* 유형의 **트랜잭션** 데이터 소스는 **TaxTrans** 애플리케이션 테이블의 기록에 액세스하도록 구성됩니다.
    - *계산 필드* 유형의 **상품권** 데이터 소스는 필수 상품권 코드(**INV-10000349** 및 **INV-10000350**)를 기록 목록으로 반환하도록 구성됩니다.
    - *계산된 필드* 유형의 **필터링된** 데이터 원본은 **거래** 데이터 원본에서 필요한 바우처의 세금 거래만 선택하도록 구성됩니다.
    - **필터링된** 데이터 원본에 대해 *계산된 필드* 유형의 **\$TaxAmount** 필드가 추가되어 부호가 반대인 세금 값을 표시합니다.
    - *Group By* 유형의 **Grouped** 데이터 소스는 Filtered 데이터 소스의 **필터링된** 세금 거래를 그룹화하도록 구성됩니다.
    - **그룹화된** 데이터 원본의 **TotalSum** 집계 필드는 해당 데이터 원본의 필터링된 모든 세금 거래에 대한 **필터링된** 데이터 원본의 **\$TaxAmount** 필드 값을 요약하도록 구성됩니다.

        !['GroupBy' 매개 변수 편집 페이지의 TotalSum 집계 필드.](./media/ER-DeferredSequence-GroupByParameters.png)

9. 구성된 데이터 소스가 데이터 모델에 바인딩되는 방법과 액세스된 데이터를 노출하여 ER 형식으로 사용할 수 있도록 하는 방법을 검토합니다.

    - **필터링된** 데이터 소스는 데이터 모델의 **Data.List** 필드에 바인딩됩니다.
    - **필터링된** 데이터 원본의 **\$TaxAmount** 필드는 데이터 모델의 **Data.List.Value** 필드에 바인딩됩니다.
    - **Grouped** 데이터 원본의 **TotalSum** 필드는 데이터 모델의 **Data.Summary.Total** 필드에 바인딩됩니다.

    ![모델 매핑 디자이너 페이지.](./media/ER-DeferredSequence-ModelMapping.png)

10. **모델 매핑 디자이너** 및 **모델 매핑** 페이지를 닫습니다.

### <a name="review-the-imported-format"></a>가져온 형식 검토

1. **구성** 페이지의 구성 트리에서 **지연된 시퀀스 구성** 을 학습하는 형식을 선택합니다.
2. 형식 세부 정보를 검토하려면 **디자이너** 를 선택합니다.
3. **세부 정보 표시** 를 선택합니다.
4. 세금 거래의 상세 기록을 포함하는 텍스트 형식의 아웃바운드 문서를 생성하도록 구성된 ER 형식 구성 요소의 설정을 검토합니다.

    - **Repor\\tLines** 시퀀스 형식 요소는 중첩된 시퀀스 요소(**헤더**, **기록** 및 **요약**)에서 생성된 단일 행으로 아웃바운드 문서를 채우도록 구성됩니다.

        ![형식 디자이너 페이지에서 줄 순서 형식 요소 및 중첩 요소.](./media/ER-DeferredSequence-Format.png)

    - **Report\\Lines\\Header** 시퀀스 형식 요소는 처리가 시작되는 날짜와 시간을 표시하는 단일 헤더 행으로 아웃바운드 문서를 채우도록 구성됩니다.
    - **Report \\Lines\\Record** 시퀀스 형식 요소는 아웃바운드 문서를 개별 세금 거래의 세부 사항을 표시하는 단일 라인으로 채우도록 구성됩니다. 이러한 세금 거래는 세미콜론으로 구분됩니다.

        ![세미콜론을 구분 기호로 사용하는 기록 시퀀스 형식 요소입니다.](./media/ER-DeferredSequence-Format1.png)

    - **Report\\Lines\\Summary** 시퀀스 형식 요소는 처리된 세금 거래의 세금 값 합계를 포함하는 단일 요약 라인으로 아웃바운드 문서를 채우도록 구성됩니다.

4. **매핑** 탭에서 다음 세부 정보를 검토합니다.

    - **Report\\Lines\\Header** 요소는 아웃바운드 문서에서 한 줄을 생성하기 위해 데이터 소스에 바인딩될 필요가 없습니다.
    - **Prefix1** 요소는 추가된 행이 보고서 헤더 행임을 나타내기 위해 **P1** 기호를 생성합니다.
    - **ExecutionDateTime** 요소는 헤더 행이 추가될 때 날짜와 시간(밀리초 포함)을 생성합니다.
    - **Report\\Lines\\Record** 요소는 **model.Data.List** 목록에 바인딩되어 바인딩된 목록의 모든 기록에 대해 한 줄을 생성합니다.
    - **Prefix2** 요소는 추가된 행이 세금 거래 세부 정보에 대한 것임을 나타내기 위해 **P2** 기호를 생성합니다.
    - **TaxAmount** 요소는 현재 세금 거래의 세금 값을 생성하기 위해 **model.Data.List.Value**(상대 경로 보기에서 **\@.Value** 로 표시됨)에 바인딩됩니다.
    - **RunningTotal** 요소는 세금 값의 누계에 대한 자리 표시자입니다. 현재 이 요소에는 바인딩이나 기본값이 구성되어 있지 않기 때문에 출력이 없습니다.
    - **ExecutionDateTime** 요소는 이 보고서에서 현재 트랜잭션이 처리될 때 날짜와 시간(밀리초 포함)을 생성합니다.
    - **Report\\Lines\\Header** 요소는 아웃바운드 문서에서 한 줄을 생성하기 위해 데이터 소스에 바인딩될 필요가 없습니다.
    - **Prefix3** 요소는 추가된 라인에 총 세금 값이 포함되어 있음을 나타내는 **P3** 기호를 생성합니다.
    - **TotalTaxAmount** 요소는 **model.Data.Summary.Total** 에 바인딩되어 처리된 세금 거래의 세금 값 합계를 생성합니다.
    - **ExecutionDateTime** 요소는 요약 줄이 추가될 때 날짜와 시간(밀리초 포함)을 생성합니다.

    ![형식 디자이너 페이지의 매핑 탭](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>가져온 형식 실행

1. **형식 디자이너** 페이지에서 **실행** 을 선택합니다.
2. 웹 브라우저에서 제공하는 파일을 다운로드하고 검토를 위해 엽니다.

    ![샘플 보고서 파일을 다운로드했습니다.](./media/ER-DeferredSequence-Run.png)

요약 라인 22는 처리된 거래에 대한 세금 가치의 합계를 나타냅니다. 이 합계를 반환하기 위해 **model.Data.Summary.Total** 바인딩을 사용하도록 형식이 구성되어 있기 때문에 합계는 모델 매핑을 사용하는 *GroupBy* 유형의 **Grouped** 데이터 소스의 **TotalSum** 집계를 호출하여 계산됩니다. 이 집계를 계산하기 위해 모델 매핑은 **필터링된** 데이터 원본에서 선택된 모든 트랜잭션을 반복합니다. 21행과 22행의 실행 시간을 비교하여 합계 계산에 10밀리초(ms)가 소요되었음을 확인할 수 있습니다. 2행과 21행의 실행 시간을 비교하면 모든 트랜잭션 행을 생성하는 데 7ms가 걸렸다는 것을 알 수 있습니다. 따라서 총 17ms가 필요했습니다.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>합계가 생성된 출력을 기반으로 하도록 형식을 수정합니다.

트랜잭션 볼륨이 현재 예시의 볼륨보다 훨씬 크면 합산 시간이 증가하여 성능 문제가 발생할 수 있습니다. 형식 설정을 변경하여 이러한 성능 문제를 방지할 수 있습니다. 생성된 보고서에 포함하기 위해 세금 값에 액세스하기 때문에 이 정보를 재사용하여 세금 값을 합산할 수 있습니다. 자세한 내용은 [계산 및 합산을 수행하도록 형식 구성](./tasks/er-format-counting-summing-1.md)을 참조하십시오.

1. **형식 디자이너** 페이지의 **형식** 탭에 있는 형식 트리에서 **보고서** 파일 요소를 선택합니다.
2. **출력 세부 정보 수집** 옵션을 **예** 로 설정합니다. 이제 기존 보고서의 내용을 [데이터 수집](er-functions-category-data-collection.md) 범주의 기본 제공 ER 함수를 사용하여 액세스할 수 있는 데이터 소스로 사용하여 이 형식을 구성할 수 있습니다.
3. **매핑** 탭에서 **Report\\Lines** 시퀀스 요소를 선택합니다.
4. **수집된 데이터 키 이름** 표현식을 `WsColumn`로 구성하십시오.
5. **수집된 데이터 키 값** 표현식을 `WsRow`로 구성하십시오.

    ![형식 디자이너 페이지의 라인 시퀀스 요소입니다.](./media/ER-DeferredSequence-Format3.png)

6. **Report\\Lines\\Record\\TaxAmount** 숫자 요소를 선택하십시오.
7. **수집된 데이터 키 이름** 표현식을 `SummingAmountKey`로 구성하십시오.

    ![형식 디자이너 페이지의 TaxAmount 숫자 요소입니다.](./media/ER-DeferredSequence-Format4.png)

    이 설정을 가상 워크시트의 이행으로 간주할 수 있습니다. 여기에서 셀 A1의 값에 처리된 모든 세금 거래의 세액 값이 추가됩니다.

8. **Report\\Lines\\Record\\RunningTotal** 숫자 요소를 선택한 다음 **수식 편집** 을 선택합니다.
9. 내장된 [SUMIF](er-functions-datacollection-sumif.md) ER 함수를 사용하여 `SUMIF(SummingAmountKey, WsColumn, WsRow)` 표현식을 구성합니다.
10. **저장** 을 선택합니다.

    ![SUMIF 식.](./media/ER-DeferredSequence-FormulaDesigner.png)

11. **수식 디자이너** 페이지를 닫습니다.
12. **저장** 을 선택한 다음 **실행** 을 선택합니다.
13. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![다운로드한 파일 - 세금 합계.](./media/ER-DeferredSequence-Run1.png)

    21행에는 생성된 출력을 데이터 소스로 사용하여 처리된 모든 거래에 대해 계산된 세금 값의 누계가 포함됩니다. 이 데이터 소스는 보고서 시작 부분에서 시작하여 마지막 세금 거래까지 계속됩니다. 22행에는 *GroupBy* 유형의 데이터 소스를 사용하여 모델 매핑에서 계산된 처리된 모든 거래에 대한 세금 값의 합계가 포함됩니다. 이 값은 동일합니다. 따라서 **GroupBy** 대신 출력 기반 합산을 사용할 수 있습니다. 2행과 21행의 실행 시간을 비교하면 모든 트랜잭션 행의 생성과 합산에 9ms가 걸렸다는 것을 알 수 있습니다. 따라서 세부 라인 생성 및 세금 값 합산에 관한 한 수정 된 형식은 원래 형식보다 약 2 배 빠릅니다.

14. **Report\\Lines\\Summary\\TotalTaxAmount** 숫자 요소를 선택한 다음 **수식 편집** 을 선택합니다.
15. 기존 표현식 대신 `SUMIF(SummingAmountKey, WsColumn, WsRow)` 표현식을 입력합니다.
16. **저장** 을 선택한 다음 **실행** 을 선택합니다.
17. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![편집된 수식으로 파일을 다운로드했습니다.](./media/ER-DeferredSequence-Run2.png)

    마지막 거래 세부 정보 라인의 세액 누계가 이제 요약 라인의 합계와 같습니다.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>보고서 헤더에 출력 기반 합산 값 입력

예를 들어, 보고서 헤더에 세금 값 합계를 표시해야 하는 경우 형식을 수정할 수 있습니다.

1. **형식 디자이너** 페이지의 **형식** 탭에서 **Report\\Lines\\Summary** 시퀀스 요소를 선택합니다.
2. **위로 이동** 을 선택합니다.
3. **저장** 을 선택한 다음 **실행** 을 선택합니다.
4. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![보고서 헤더에 합산하기 위해 다운로드한 파일입니다.](./media/ER-DeferredSequence-Run3.png)

    요약 라인 2의 세금 값 합계는 이제 생성된 출력을 기반으로 계산되기 때문에 0(영)과 같습니다. 라인 2가 생성될 때 생성된 출력에는 트랜잭션 세부 정보가 있는 라인이 아직 포함되지 않습니다. 모든 세금 거래에 대해 **Report\\Lines\\Summary** 시퀀스 요소가 실행될 때까지 **Report\\Lines\\Record** 시퀀스 요소의 실행을 연기하도록 이 형식을 구성할 수 있습니다.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>계산된 합계가 사용되도록 요약 시퀀스의 실행을 지연합니다.

1. **형식 디자이너** 페이지의 **형식** 탭에서 **Report\\Lines\\Summary** 시퀀스 요소를 선택합니다.
2. **지연된 실행** 옵션을 **예** 로 설정합니다.

    ![형식 디자이너 페이지에 있는 요약 시퀀스 요소의 지연된 실행 옵션입니다.](./media/ER-DeferredSequence-Format5.png)

3. **저장** 을 선택한 다음 **실행** 을 선택합니다.
4. 웹 브라우저에서 제공하는 파일을 다운로드하여 검토합니다.

    ![다운로드한 파일 - 실행이 지연되었습니다.](./media/ER-DeferredSequence-Run4.png)

    **Report\\Lines\\Summary** 시퀀스 요소는 이제 상위 요소인 **Report\\Lines** 아래에 중첩된 다른 모든 항목이 실행된 후에만 실행됩니다. 따라서 **model.Data.List** 데이터 소스의 모든 세금 거래에 대해 **Report\\Lines\\Record** 시퀀스 요소가 실행된 후에 실행됩니다. 1, 2, 3행과 마지막 22행의 실행 시간이 이를 말해준다.

## <a name="additional-resources"></a>추가 리소스

- [계산 및 합산을 수행하는 형식 구성](./tasks/er-format-counting-summing-1.md)
- [ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)
- [ER 형식의 XML 요소 실행 연기](er-defer-xml-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
