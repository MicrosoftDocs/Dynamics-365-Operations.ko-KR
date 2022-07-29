---
title: ER 형식의 실행을 추적하여 성능 문제 해결
description: 이 항목에서는 전자 보고(ER)의 성능 추적 기능을 사용하여 성능 문제를 해결하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 10eddf2f60db914e6451840d4d7aedb9dce7108874ea3ff45f375b85a55a694f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460747"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>ER 형식의 실행을 추적하여 성능 문제 해결

[!include[banner](../includes/banner.md)]

전자 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 프로세스의 일부로 애플리케이션에서 데이터를 가져오고 생성된 출력에 입력하는 데 사용되는 방법을 정의합니다. ER 성능 추적 기능은 ER 형식 실행의 세부 정보를 수집하고 성능 문제를 해결하는 데 사용하는 데 소요되는 시간과 비용을 크게 줄이는 데 도움이 됩니다. 이 자습서는 실행된 ER 형식에 대한 성능 추적을 수행하는 방법과 이러한 추적의 정보를 사용하여 성능을 개선하는 방법에 대한 지침을 제공합니다.

## <a name="prerequisites"></a>전제 조건

이 자습서의 예를 완료하려면 다음 액세스 권한이 있어야 합니다.

- 다음 역할 중 하나에 대한 액세스:

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 다음 역할 중 하나에 대해 애플리케이션과 동일한 테넌트에 프로비저닝된 Regulatory Configuration Services(RCS) 인스턴스에 대한 액세스:

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

다음 파일을 다운로드하여 로컬에 저장합니다.

| 파일                                  | 콘텐츠                               |
|---------------------------------------|---------------------------------------|
| 성능 추적 model.version.1     | [샘플 ER 데이터 모델 구성](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| 성능 추적 metadata.version.1  | [샘플 ER 메타데이터 구성](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| 성능 추적 mapping.version.1.1 | [샘플 ER 모델 매핑 구성](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| 성능 추적 format.version.1.1  | [샘플 ER 형식 구성](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>ER 매개 변수 구성

애플리케이션에서 생성된 각 ER 성능 추적은 실행 로그 레코드의 첨부 파일로 저장됩니다. 문서 관리(DM) 프레임워크는 이러한 첨부 파일을 관리하는 데 사용됩니다. 성능 추적을 첨부하는 데 사용해야 하는 DM 문서 유형을 지정하려면 ER 매개변수를 미리 구성해야 합니다. **전자 보고** 작업 영역에서 **전자 보고 매개 변수** 를 선택합니다. 그런 다음 **전자 보고 매개변수** 페이지에서 **첨부 파일** 탭의 **기타** 필드에서 성능 추적에 사용할 DM 문서 유형을 선택합니다.

![전자 보고 매개 변수 페이지.](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

**기타** 조회 필드에서 사용할 수 있게 하려면 **문서 유형** 페이지에서 DM 문서 유형이 다음과 같은 방식으로 구성되어야 합니다(**조직 관리 \> 문서 관리 \> 문서 유형**).

- **클래스:** 파일 첨부
- **그룹:** 파일

![문서 유형 페이지.](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> DM 첨부 파일은 회사별로 다르기 때문에 선택한 문서 유형은 현재 인스턴스의 모든 회사에서 사용할 수 있어야 합니다.

### <a name="configure-rcs-parameters"></a>RCS 매개 변수 구성

생성된 ER 성능 추적은 ER 형식 디자이너와 ER 매핑 디자이너를 사용하여 분석을 위해 RCS로 가져옵니다. ER 성능 추적은 ER 형식과 관련된 실행 로그 레코드의 첨부 파일로 저장되기 때문에 성능 추적을 첨부하는 데 사용해야 하는 DM 문서 유형을 지정하려면 사전에 RCS 매개변수를 구성해야 합니다. 귀사에 프로비저닝된 RCS의 경우 **전자 보고** 작업 공간에서 **전자 보고 매개변수** 를 선택합니다. 그런 다음 **전자 보고 매개변수** 페이지에서 **첨부 파일** 탭의 **기타** 필드에서 성능 추적에 사용할 DM 문서 유형을 선택합니다.

![RCS의 전자 보고 매개 변수 페이지.](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

**기타** 조회 필드에서 사용할 수 있게 하려면 **문서 유형** 페이지에서 DM 문서 유형이 다음과 같은 방식으로 구성되어야 합니다(**조직 관리 \> 문서 관리 \> 문서 유형**).

- **클래스:** 파일 첨부
- **그룹:** 파일

## <a name="design-an-er-solution"></a>ER 솔루션 설계

공급업체 트랜잭션을 표시하는 새 보고서를 생성하기 위해 새 ER 솔루션을 설계하기 시작했다고 가정합니다. **공급업체 페이지** 에서 현재 선택한 공급업체에 대한 거래를 찾을 수 있습니다(**지불 계정 \> 공급업체 \> 모든 공급업체** 로 이동하고 공급업체를 선택한 다음 작업 창의 **공급 업체** 탭에서 **트랜잭션** 그룹의 **트랜잭션** 선택). 그러나 XML 형식의 하나의 전자 문서에서 모든 벤더 트랜잭션을 동시에 갖고 싶어합니다. 이 솔루션은 필요한 데이터 모델, 메타데이터, 모델 매핑 및 형식 구성 요소를 포함하는 여러 ER 구성으로 구성됩니다.

1. 회사에 프로비저닝된 RCS 인스턴스에 로그인합니다.
2. 이 자습서에서는 샘플 회사 **Litware, Inc.** 에 대한 구성을 만들고 수정합니다. 따라서 이 구성 제공자가 RCS에 추가되었고 활성으로 선택되었는지 확인합니다. 안내는 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md) 절차를 참조하세요.
3. **전자 보고** 작업 영역에서 **보고 구성** 타일을 선택합니다.
4. **구성** 페이지에서 전제 조건으로 다운로드한 ER 구성을 데이터 모델, 메타데이터, 모델 매핑, 형식의 순서로 RCS로 가져옵니다. 각 구성에 대해 다음 단계를 따르십시오.

    1. 작업 창에서 **교환 \> XML 파일에서 로드** 를 선택합니다.
    2. **검색** 을 선택하여 XML 형식의 필수 ER 구성에 적합한 파일을 선택합니다.
    3. **확인** 을 선택합니다.

    ![RCS의 구성 페이지.](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>ER 솔루션을 실행하여 실행 추적

ER 솔루션의 첫 번째 버전 설계를 완료했다고 가정합니다. 이제 인스턴스에서 테스트하고 실행 성능을 분석하려고 합니다.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>RCS에서 재무 및 운영으로 ER 구성 가져오기

1. 애플리케이션 인스턴스에 로그인합니다.
2. 이 자습서에서는 RCS 인스턴스(ER 구성 요소를 디자인하는 위치)에서 인스턴스(테스트하고 마지막으로 사용하는 위치)로 구성을 가져옵니다. 따라서 필요한 모든 아티팩트가 준비되었는지 확인해야 합니다. 안내는 [Regulatory Configuration Services(RCS)에서 전자 보고(ER) 구성 가져오기](rcs-download-configurations.md) 절차를 참조하세요.
3. RCS에서 애플리케이션으로 구성을 가져오려면 다음 단계를 따르세요.

    1. **전자 보고** 작업 영역의 **Litware, Inc.** 구성 공급자 타일에서 **리포지토리** 를 선택합니다.
    2. **구성 리포지토리** 페이지에서 **RCS** 유형의 저장소를 선택한 다음 **열기** 를 선택합니다.
    3. **구성** 빠른 탭에서 **성능 추적 형식** 구성을 선택합니다.
    4. **버전** 빠른 탭에서 선택한 형식 구성의 초안 버전 **1.1** 을 선택한 다음 **가져오기** 를 선택합니다.

    ![구성 리포지토리 페이지.](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

데이터 모델 및 모델 매핑 구성의 해당 버전은 가져온 ER 형식 구성의 전제 조건으로 자동으로 가져옵니다.

### <a name="turn-on-the-er-performance-trace"></a>ER 성능 추적 켜기

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개변수** 대화 상자에서 **실행 추적** 섹션에서 다음 단계를 따르세요.

    1. **실행 추적 형식** 필드에서 ER 형식 및 매핑 요소에 대해 실행 세부 정보를 저장해야 하는 생성된 성능 추적 형식을 지정합니다.

        - **디버그 추적 형식** – 실행 시간이 짧은 ER 형식을 대화식으로 실행하려는 경우 이 값을 선택합니다. 그런 다음 ER 형식 실행에 대한 세부 정보 수집이 시작됩니다. 이 값을 선택하면 성능 추적은 다음 작업에 소요된 시간에 대한 정보를 수집합니다.

            - 데이터를 가져오기 위해 호출되는 모델 매핑에서 각 데이터 소스 실행
            - 각 형식 항목을 처리하여 생성된 출력에 데이터 입력

            **디버그 추적 형식** 값을 선택하면 ER Operation Designer에서 추적 내용을 분석할 수 있습니다. 거기에서 추적에 언급된 ER 형식 또는 매핑 요소를 볼 수 있습니다.

        - **집계된 추적 형식** – 배치 모드에서 실행 시간이 긴 ER 형식을 실행하려는 경우 이 값을 선택합니다. 그런 다음 ER 형식 실행에 대한 집계된 세부 정보 수집이 시작됩니다. 이 값을 선택하면 성능 추적은 다음 작업에 소요된 시간에 대한 정보를 수집합니다.

            - 데이터를 가져오기 위해 호출되는 모델 매핑에서 각 데이터 소스 실행
            - 데이터를 가져오기 위해 호출되는 형식 매핑에서 각 데이터 소스 실행
            - 각 형식 항목을 처리하여 생성된 출력에 데이터 입력

            **집계된 추적 형식** 값은 Microsoft Dynamics 365 Finance 버전 10.0.20 이상에서 사용할 수 있습니다.

            ER 형식 디자이너와 ER 모델 매핑 디자이너에서 단일 구성 요소에 대한 총 실행 시간을 볼 수 있습니다. 또한 추적에는 실행 횟수, 단일 실행의 최소 및 최대 시간과 같은 실행에 대한 세부 정보가 포함됩니다.

            > [!NOTE]
            > 이 추적은 추적된 구성 요소 경로를 기반으로 수집됩니다. 따라서 단일 상위 구성 요소에 이름이 지정되지 않은 여러 하위 구성 요소가 포함되어 있거나 여러 하위 구성 요소에 동일한 이름이 있는 경우 통계가 정확하지 않을 수 있습니다.

    2. 다음 옵션을 **네** 로 설정하여 ER 모델 매핑 및 ER 형식 구성 요소 실행에 대한 특정 세부 정보를 수집합니다.

        - **쿼리 통계 수집** – 이 옵션을 켜면 성능 추적에서 다음 정보를 수집합니다.

            - 데이터 소스에서 수행한 데이터베이스 호출 수
            - 데이터베이스로의 중복 호출 횟수
            - 데이터베이스 호출에 사용된 SQL 문의 세부 정보

        - **캐싱 액세스 추적** – 이 옵션이 켜져 있으면 성능 추적이 ER 모델 매핑의 캐시 사용에 대한 정보를 수집합니다.
        - **추적 데이터 액세스** – 이 옵션이 켜져 있으면 성능 추적은 레코드 목록 유형의 실행된 데이터 소스에 대해 데이터베이스에 대한 호출 수에 대한 정보를 수집합니다.
        - **추적 목록 열거형** – 이 옵션이 켜져 있으면 성능 추적은 레코드 목록 유형의 데이터 원본에서 요청되는 레코드 수에 대한 정보를 수집합니다.

    > [!NOTE]
    > **사용자 매개변수** 대화 상자의 매개 변수는 사용자와 현재 회사에 따라 다릅니다.

    ![사용자 매개 변수 대화 상자.](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>ER 형식 실행

1. **DEMF** 회사를 선택합니다.
2. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
3. **구성** 페이지의 구성 트리에서 **성능 추적 형식** 항목을 선택합니다.
4. 작업 창에서 **송장** 을 선택합니다.

생성된 파일에는 6개 공급업체의 265개 트랜잭션에 대한 정보가 표시됩니다.

## <a name="review-the-execution-trace"></a>실행 추적 검토

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>애플리케이션에서 생성된 추적 내보내기

성능 추적은 소스 ER 형식에서 분리되며 외부 zip 파일로 직렬화할 수 있습니다.

1. **조직 관리 \> 전자 보고 \> 구성 디버그 로그** 로 이동합니다.
2. **전자 보고 실행 로그** 페이지의 왼쪽 창에서 **구성 이름** 필드에 있는 **성능 추적 형식** 을 선택하여 **성능 추적 형식** 구성의 실행에 의해 생성된 로그 레코드를 찾습니다.
3. 페이지의 오른쪽 상단 모서리에 있는 **첨부** 버튼(종이 클립 기호)을 선택하거나 **Ctrl+Shift+A** 를 누릅니다.

    ![전자 보고 실행 로그 페이지의 첨부 파일 버튼.](./media/GER-PerfTrace-GER-DebugLog.png)

4. **전자 보고 실행 로그에 대한 첨부 파일** 페이지의 작업 창에서 **열기** 를 선택하여 성능 추적을 zip 파일로 가져와 로컬에 저장합니다.

    ![전자 보고 실행 로그에 대한 첨부 파일입니다.](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> 생성된 추적에는 **GUID** 형식의 고유 보고서 식별자를 통해 소스 ER 보고서에 대한 참조가 있습니다. 형식의 버전 번호는 고려되지 않습니다.

실행된 ER 형식에 대해 생성된 성능 추적과 ER 모델 매핑 간의 연결은 사용된 루트 설명자와 공통 데이터 모델을 기반으로 합니다. 형식의 버전 번호 및 모델 매핑은 고려되지 않습니다. 모델 매핑에 대한 **모델 매핑의 기본값** 플래그 설정도 고려되지 않습니다.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>생성된 추적을 RCS로 가져오기

1. RCS의 **전자 보고** 작업 공간에서 **보고 구성** 타일을 선택합니다.
2. **구성** 페이지의 구성 트리에서 **성능 추적 모델** 항목을 확장하고 **성능 추적 형식** 항목을 선택합니다.
3. 작업 창에서 **디자이너** 를 선택합니다.
4. **형식 디자이너** 페이지의 작업 창에서 **성능 추적** 을 선택합니다.
5. **성능 추적 결과 설정** 대화 상자에서 **성능 추적 가져오기** 를 선택합니다.
6. **검색** 을 선택하여 이전에 내보낸 .Zip 파일을 선택합니다.
7. **확인** 을 선택합니다.

    ![RCS의 성능 추적 결과 설정 대화 상자.](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>RCS에서 분석을 위해 성능 추적 사용 – 형식 실행

1. RCS의 **형식 디자이너** 페이지에서 **펼치기/접기** 를 선택하여 모든 형식 항목의 내용을 확장합니다.

    현재 형식의 일부 항목에 대한 추가 정보가 표시됩니다.

    - 형식 항목을 사용하여 생성된 출력에 데이터를 입력하는 데 소요된 실제 시간
    - 전체 출력을 생성하는 데 소요된 총 시간의 백분율로 표시되는 동일한 시간

    ![RCS의 형식 디자이너 페이지.](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. **형식 디자이너** 페이지를 닫습니다.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>RCS에서 분석을 위해 성능 추적 사용 – 모델 매핑

1. RCS의 **구성** 페이지의 구성 트리에서 **성능 추적 매핑** 항목을 선택합니다.
2. 작업 창에서 **디자이너** 를 선택합니다.
3. **디자이너** 를 선택합니다.
4. **모델 매핑 디자이너** 페이지의 작업 창에서 **성능 추적** 을 선택합니다.
5. 이전에 가져온 추적을 선택합니다.
6. **확인** 을 선택합니다.

현재 모델 매핑의 일부 데이터 소스 항목에 대해 새 정보를 사용할 수 있습니다.

- 데이터 소스를 사용하여 데이터를 가져오는 데 소요된 실제 시간
- 전체 모델 매핑을 실행하는 데 소요된 총 시간의 백분율로 표시되는 동일한 시간

ER에서 VendTable/\<Relations/VendTrans.VendTable\_AccountNum 데이터 원본이 실해오디는 동안 현재 모델 매핑이 데이터베이스 요청을 복제함을 알립니다. 이 중복은 공급업체 트랜잭션 목록이 반복되는 각 공급업체 레코드에 대해 두 번 호출되기 때문에 발생합니다.

- 구성된 바인딩을 기반으로 데이터 모델의 각 트랜잭션에 대한 세부 정보를 입력하기 위해 한 번의 호출이 수행됩니다.
- 데이터 모델에서 공급업체당 계산된 트랜잭션 수를 입력하기 위해 한 번의 호출이 수행됩니다.

![RCS의 모델 매핑 디자이너 페이지에 있는 중복 데이터베이스 요청에 대한 메시지입니다.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

값 **\[Q:530\]** 은 VendTrans 테이블이 530번 호출되어 해당 테이블의 레코드를 VendTable/\<Relations/VendTrans.VendTable\_AccountNum 데이터 원본으로 반환함을 나타냅니다. 값 **\[530\]** 은 VendTable/\<Relations/VendTrans.VendTable\_AccountNum 데이터 소스는 해당 데이터 소스에서 레코드를 반환하고 데이터 모델에 세부 정보를 입력하기 위해 530번 호출되었음을 나타냅니다.

VendTable/\<Relations/VendTrans.VendTable\_AccountNum 데이터 원본은 265개 트랜잭션에 대한 세부 정보를 가져오고 모델 매핑의 성능을 개선하기 위해 수행되는 호출 수를 줄입니다.

LedgerTransTypeList 데이터 소스에 대한 호출 수를 줄이는 것도 유용할 수 있습니다. 이 데이터 소스는 **LedgerTransType** 열거형의 각 값을 레이블과 연결하는 데 사용됩니다. 이 데이터 소스를 사용하여 적절한 레이블을 찾아 각 공급업체 트랜잭션에 대한 데이터 모델에 입력할 수 있습니다. 이 데이터 소스에 대한 현재 호출 수(9,027)는 265 트랜잭션에 대해 상당히 높습니다.

![데이터 소스에 대한 9,027 호출을 보여주는 RCS의 모델 매핑 디자이너 페이지.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>실행 추적 정보를 기반으로 모델 매핑 개선

### <a name="modify-the-logic-of-the-model-mapping"></a>모델 매핑의 논리 수정

1. 다음 단계에 따라 캐싱을 사용하여 데이터베이스에 대한 중복 호출을 방지하세요.

    1. RCS의 **모델 매핑 디자이너** 페이지에 있는 **데이터 원본** 창에서 **VendTable** 항목을 선택합니다.
    2. **캐시** 를 선택합니다.
    3. **VendTable** 항목을 확장하고 VendTable 데이터 소스에 대한 일대다 관계 목록을 확장(**\<Relations** 항목)하고 **VendTrans.VendTable\_AccountNum** 항목을 선택합니다.
    4. **캐시** 를 선택합니다.

    ![중복 호출을 방지하기 위한 캐싱 설정.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. LedgerTransTypeList 데이터 소스를 VendTable 데이터 소스의 범위로 가져오려면 다음 단계를 따르세요.

    1. **데이터 소스 유형** 창에서 **기능** 항목을 확장하고 **계산된 필드** 항목을 선택합니다.
    2. **데이터 소스** 창에서 **VendTable** 항목을 선택합니다.
    3. **추가** 를 선택합니다.
    4. **이름** 필드에 **\$TransType** 을 입력합니다.
    5. **수식 편집** 을 선택합니다.
    6. **공식** 필드에 **LedgerTransTypeList** 를 입력합니다.
    7. **저장** 을 선택합니다.
    8. **수식 편집기** 페이지를 닫습니다.
    9. **확인** 을 클릭합니다.

3. **\$TransType** 필드의 캐싱을 수행하려면 다음 단계를 따르세요.

    1. **LedgerTransTypeList** 항목을 선택합니다.
    2. **캐시** 를 선택합니다.
    3. **VendTable.\$TransType** 항목을 선택합니다.
    4. **캐시** 를 선택합니다.

    ![$TransType 필드에 대한 캐싱 설정입니다.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. 다음 단계를 따라 **\$TransTypeRecord** 필드를 변경하여 캐시된 **\$TransType** 필드를 사용하기 시작합니다.

    1. **데이터 소스** 창에서 **VendTable** 항목을 확장하고 **\<Relations** 항목을 확장하고 **VendTrans.VendTable\_AccountNum** 항목을 확장하고 **VendTable.VendTrans.VendTable\_AccountNum.\$TransTypeRecord** 항목을 선택합니다.
    2. **편집** 을 선택합니다.
    3. **수식 편집** 을 선택합니다.
    4. **공식** 필드에서 다음 표현식을 찾습니다.

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. **수식** 필드에 다음 표현식을 입력합니다.

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. **저장** 을 선택합니다.
    7. **수식 편집기** 페이지를 닫습니다.
    8. **확인** 을 선택합니다.

5. **저장** 을 선택합니다.
6. **모델 매핑 디자이너** 페이지를 닫습니다.
7. **모델 매핑** 페이지를 닫습니다.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>수정된 버전의 ER 모델 매핑 완료

1. RCS의 **구성** 페이지에 있는 **버전** 빠른 탭에서 버전 **1.2** 의 **성능 추적 매핑** 구성을 선택합니다.
2. **상태 변경** 을 선택합니다.
3. **완료** 를 선택합니다.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>수정된 ER 모델 매핑 구성을 RCS에서 애플리케이션으로 가져오기

이 토픽 앞부분의 [RCS에서 재무 및 운영으로 ER 구성 가져오기](#import-configuration) 센션의 단계를 반복하여 버전 1.2의 **성능 추적 매핑** 구성을 가져옵니다.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>수정된 ER 솔루션을 실행하여 실행 추적

### <a name="run-the-er-format"></a>ER 형식 실행

이 항목 앞부분의 [ER 형식 실행](#run-format) 섹션에 있는 단계를 반복하여 새 성능 추적을 생성합니다.

## <a name="work-with-the-execution-trace"></a>실행 추적 작업

### <a name="export-the-generated-trace-from-the-application"></a>애플리케이션에서 생성된 추적 내보내기

이 항목 앞부분의 [애플리케이션에서 생성된 추적 내보내기](#export-trace) 섹션의 단계를 반복하여 새 성능 추적을 로컬로 저장합니다.

### <a name="import-the-generated-trace-into-rcs"></a>생성된 추적을 RCS로 가져오기

이 항목 앞부분의 [RCS로 생성된 추적 가져오기](#import-trace) 섹션의 단계를 반복하여 새 성능 추적을 RCS로 가져옵니다.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>RCS에서 분석을 위해 성능 추적 사용 – 모델 매핑

이 토픽 앞부분의 [RCS – 모델 매핑에서 분석을 위해 성능 추적 사용](#use-trace) 섹션의 단계를 반복하여 최신 성능 추적을 분석합니다.

모델 매핑을 조정하면 데이터베이스에 대한 중복 쿼리가 제거됩니다. 이 모델 매핑에 대한 데이터베이스 테이블 및 데이터 원본에 대한 호출 수도 감소했습니다. 따라서 전체 ER 솔루션의 성능이 향상되었습니다.

![RCS의 모델 매핑 디자이너 페이지에 있는 VendTable 데이터 원본에서 정보를 추적합니다.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

추적 정보에서 VendTable 데이터 원본의 값 **\[12\]** 는 이 데이터 원본이 12번 호출되었음을 나타냅니다. 값 **\[Q:6\]** 은 6개의 호출이 VendTable 테이블에 대한 데이터베이스 호출로 변환되었음을 나타냅니다. 값 **\[C:6\]** 은 데이터베이스에서 가져온 레코드가 캐시되었고 다른 6개의 호출이 캐시를 사용하여 처리되었음을 나타냅니다.

LedgerTransTypeList 데이터 소스에 대한 호출 수가 9,027에서 240으로 줄었습니다.

![RCS의 모델 매핑 디자이너 페이지에 있는 LedgerTransTypeList 데이터 원본에서 정보를 추적합니다.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>애플리케이션에서 실행 추적 검토

RCS 외에도 일부 버전은 ER 프레임워크 디자이너 경험을 위한 기능을 제공할 수 있습니다. 이러한 버전에는 **디자인 모드 활성화** 옵션을 켤 수 있습니다. 이 옵션은 **전자 보고 매개변수** 페이지의 **일반** 탭에서 찾을 수 있고, **전자 보고** 작업 공간에서 열 수 있습니다.

![전자 보고 매개변수 페이지에서 디자인 모드 옵션을 활성화합니다.](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

이러한 버전 중 하나를 사용하는 경우 애플리케이션에서 직접 생성된 성능 추적의 세부 정보를 분석할 수 있습니다. 응용 프로그램에서 내보내고 RCS로 가져올 필요가 없습니다.

## <a name="review-the-execution-trace-by-using-external-tools"></a>외부 도구를 사용하여 실행 추적 검토

### <a name="configure-user-parameters"></a>사용자 매개 변수 구성

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개 변수** 대화 상자에서 **실행 추적** 섹션의 **실행 추적 형식** 필드에서 **PerfView XML** 을 선택합니다.

### <a name="run-the-er-format"></a>ER 형식 실행

이 항목 앞부분의 [ER 형식 실행](#run-format) 섹션에 있는 단계를 반복하여 새 성능 추적을 생성합니다.

웹 브라우저는 다운로드용 zip 파일을 제공합니다. 이 파일에는 PerfView 형식의 성능 추적이 포함되어 있습니다. 그런 다음 PerfView 성능 분석 도구를 사용하여 ER 형식 실행의 세부 정보를 분석할 수 있습니다.

![PerfView 형식의 성능 추적 정보입니다.](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>외부 도구를 사용하여 데이터베이스 쿼리가 포함된 실행 추적 검토

ER 프레임워크에 대한 개선 사항으로 인해 PerfView 형식으로 생성된 성능 추적은 이제 ER 형식 실행에 대한 자세한 정보를 제공합니다. Microsoft Dynamics 365 for Finance and Operations 버전 10.0.4(2019년 7월)부터 이 추적에는 애플리케이션 데이터베이스에 대해 실행된 SQL 쿼리의 세부 정보도 포함될 수 있습니다.

### <a name="configure-user-parameters"></a>사용자 매개 변수 구성

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개변수** 대화 상자에서 **실행 추적** 섹션에서 다음 매개 변수를 설정하세요.

    - **실행 추적 형식** 필드에서 **PerfView XML** 을 선택합니다.
    - **쿼리 통계 수집** 옵션을 **네** 로 설정합니다.
    - **쿼리 추적** 옵션을 **예** 로 설정합니다.

    ![실행 추적 섹션, 사용자 매개변수 대화 상자.](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>ER 형식 실행

이 항목 앞부분의 [ER 형식 실행](#run-format) 섹션에 있는 단계를 반복하여 새 성능 추적을 생성합니다.

웹 브라우저는 다운로드용 zip 파일을 제공합니다. 이 파일에는 PerfView 형식의 성능 추적이 포함되어 있습니다. 그런 다음 PerfView 성능 분석 도구를 사용하여 ER 형식 실행의 세부 정보를 분석할 수 있습니다. 이제 이 추적에는 ER 형식을 실행하는 동안 SQL 데이터베이스 액세스에 대한 세부 정보가 포함됩니다.

![PerfView에서 실행된 ER 형식에 대한 정보를 추적합니다.](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [매개 변수화된 CALCULATED FIELD 데이터 소스를 추가하여 ER 솔루션의 성능 향상](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
