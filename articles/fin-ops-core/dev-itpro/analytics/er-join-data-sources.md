---
title: ER 모델 매핑에서 JOIN 데이터 소스를 사용하여 여러 애플리케이션 테이블에서 데이터 가져오기
description: 이번에는 전자 보고(ER)에서 JOIN 유형 데이터 소스를 사용하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: c9a06c048e98676e30a6652cad6634c2e13531d4ebc6d35f325f4c7153cd82ae
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460973"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>JOIN 데이터 소스를 사용하여 전자 보고(ER) 모델 매핑의 여러 애플리케이션 테이블에서 데이터 가져오기

[!include[banner](../includes/banner.md)]

전자 보고(ER) 모델 매핑 또는 형식을 구성하는 동안 **조인** 유형의 필수 데이터 소스를 [추가](#review)할 수 있습니다. 디자인 타임에 **조인** 데이터 원본은 각각 기록 목록을 반환하는 여러 데이터 원본 집합으로 구성됩니다. 첫 번째 데이터 소스를 제외한 모든 데이터 소스에 대해 현재 및 이전 데이터 소스의 기록을 결합하는 데 필요한 조건을 정의해야 합니다. 런타임에 **조인** 유형의 구성된 데이터 원본은 중첩 데이터 원본의 기록에서 필드가 포함된 단일 조인된 기록 목록을 [반환](#executeERformat)합니다.

현재 지원되는 조인 유형은 다음과 같습니다.

- 외부(왼쪽) 조인:
    - 첫 번째(맨 왼쪽) 데이터 소스의 모든 기록을 결합한 다음 두 번째(맨 오른쪽) 데이터 소스의 구성된 조건 기록에 따라 일치하는 모든 기록을 결합합니다.
- 내부(오른쪽) 조인:
    - 구성된 조건에 따라 일치하는 첫 번째(맨 왼쪽) 데이터 소스의 기록만 결합하고 두 번째(맨 오른쪽) 데이터 소스의 기록만 결합합니다.

구성된 **Join** 데이터 소스에서 모든 데이터 소스가 **테이블 기록** 타입인 경우 단일 SQL 문을 사용하여 [데이터베이스 수준에서](#analyze) Join 데이터 소스의 실행이 가능하다. 이 문은 데이터베이스 호출 수를 줄여 모델 매핑 성능을 향상시킵니다. 그렇지 않으면 **Join 데이터** 소스의 실행은 메모리에서 수행됩니다.

> [!NOTE]
> Join 유형의 데이터 소스에서 기록을 결합하기 위한 조건을 지정하는 ER 표현식에서 **VALUEIN** 함수를 사용하는 것은 아직 지원되지 않습니다. 이 함수에 대한 자세한 내용은 [전자 보고 페이지의 공식 디자이너](general-electronic-reporting-formula-designer.md)를 방문하십시오.

이 기능에 대해 자세히 알아보려면 이 항목의 예시를 완료하십시오.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>예:, ER 모델 매핑에서 JOIN 데이터 소스 사용

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자가 데이터 액세스 성능을 개선하기 위해 **조인** 유형의 데이터 소스를 사용하여 한 번에 여러 애플리케이션 테이블에서 데이터를 가져오도록 전자 보고(ER) 모델 매핑을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 Dynamics 365 Finance 또는 RCS(Regulatory Configuration Services)의 모든 회사에 대해 수행할 수 있습니다.

### <a name="prerequisites"></a>전제 조건

이 항목의 예를 완료하려면 이러한 단계를 수행하는 데 사용되는 서비스에 따라 다음 중 하나에 액세스할 수 있어야 합니다.

**다음 역할 중 하나에 대한 재무 액세스:**

- 전자 보고 개발자
- 전자 보고 기능 컨설턴트
- 시스템 관리자

**다음 역할 중 하나에 대한 RCS 액세스:**

- 전자 보고 개발자
- 전자 보고 기능 컨설턴트
- 시스템 관리자

또한 먼저 [구성 공급자 생성의 단계를 완료하고 활성 절차로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)해야 합니다.

미리 다음 샘플 ER 구성 파일도 다운로드하여 저장해야 합니다.

| **콘텐츠 설명**  | **파일 이름**   |
|--------------------------|-----------------|
| 예시의 데이터 소스로 사용되는 샘플 **ER 데이터 모델** 구성 파일입니다.| [JOIN 데이터 sources.version.1.1.xml을 학습하는 모델](https://download.microsoft.com/download/5/c/1/5c1d8a57-6ebd-425b-bc5d-c71dde92c6af/ModeltolearnJOINdatasources.version.1.xml) |
| 예시에 대한 ER 데이터 모델을 구현하는 샘플 **ER 모델 매핑** 구성 파일입니다. | [JOIN 데이터 sources.version.1.1.xml 학습을 위한 매핑](https://download.microsoft.com/download/9/2/f/92f339ca-41fc-4f5e-b458-6983c957d3dd/MappingtolearnJOINdatasources.version.1.1.xml)|
| 샘플 **ER 형식** 구성 파일. 이 파일은 예시의 ER 형식 구성 요소를 채우기 위한 데이터를 설명합니다. | [JOIN 데이터 sources.version.1.1.xml을 학습하는 형식](https://download.microsoft.com/download/f/f/8/ff8f1b48-14d0-4c73-9145-bcdf8b5265bc/FormattolearnJOINdatasources.version.1.1.xml) |

### <a name="activate-a-configurations-provider"></a>구성 공급자 활성화

1. 웹 브라우저의 첫 번째 세션에서 재무 또는 RCS에 액세스합니다.
2. **조직 관리 \> 작업 영역 \> 전자 보고** 로 이동합니다.
3. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 [Litware, Inc.](http://www.litware.com) 샘플 회사의 구성 공급자가 나열되어 있고 **활성** 으로 표시되어 있는지 확인합니다. 이 구성 공급자가 표시되지 않으면 [구성 공급자 만들기의 단계에 따라 활성 절차로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)합니다.

    ![전자 보고 작업 공간.](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>샘플 ER 구성 파일 가져오기

1. **보고 구성** 을 선택합니다.
2. ER 데이터 모델 구성 파일을 가져옵니다.
    1. **교환** 을 선택합니다.
    2. **XML 파일에서 로드** 를 선택합니다.
    3. **찾아보기** 를 선택하여 **JOIN 데이터 소스.version.1.1.xml 파일을 학습할 모델** 을 찾습니다.
    4. **확인** 을 선택합니다.
3. ER 모델 매핑 구성 파일을 가져옵니다.
    1. **교환** 을 선택합니다.
    2. **XML 파일에서 로드** 를 선택합니다.
    3. **찾아보기** 를 선택하여 **JOIN 데이터 소스.version.1.1.xml 파일을 학습하기 위한 매핑** 을 찾습니다.
    4. **확인** 을 선택합니다.
4. ER 형식 구성 파일을 가져옵니다.
    1. **교환** 을 선택합니다.
    2. **XML 파일에서 로드** 를 선택합니다.
    3. **찾아보기** 를 선택하여 **JOIN 데이터 sources.version.1.1.xml 파일을 학습하는 형식** 을 찾습니다.
    4. **확인** 을 선택합니다.
5. 구성 트리에서 모델을 확장하여 **JOIN 데이터 소스 항목과 다른 모델** 항목(사용 가능한 경우)을 학습합니다.
6. **버전** 빠른 탭에서 트리의 ER 구성 목록과 버전 FastTab의 버전 세부 정보를 관찰하십시오. 이는 샘플 보고서의 데이터 소스로 사용됩니다.

    ![전자 보고 구성 페이지.](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>실행 추적 옵션 켜기

1. **구성** 을 선택합니다.
2. **사용자 매개 변수** 를 선택합니다.
3. 아래 스크린샷과 같이 실행 추적 매개 변수를 설정합니다.

    ![전자 보고 사용자 매개 변수 페이지.](./media/GER-JoinDS-Parameters.PNG)

    이 매개 변수를 켜면 가져온 ER 형식 파일을 실행할 때마다 실행 추적이 생성됩니다. 생성된 실행 추적의 세부 정보를 사용하여 ER 형식 및 ER 모델 매핑 구성 요소의 실행을 분석할 수 있습니다. ER 실행 추적 기능에 대한 자세한 내용은 [성능 문제를 해결하기 위해 ER 형식의 실행 추적](trace-execution-er-troubleshoot-perf.md) 페이지를 방문하십시오.

### <a name="review-er-model-mapping-part-1"></a>ER 모델 매핑 검토(1부)

ER 모델 매핑 구성 요소의 설정을 검토합니다. 구성 요소는 **Join** 유형의 데이터 소스를 사용하지 않고 ER 구성 버전, 구성 세부 정보 및 구성 공급자에 대한 정보에 액세스하도록 구성됩니다.

1. **매핑을 선택하여 JOIN 데이터 소스 구성을 학습** 합니다.
2. **디자이너** 를 선택하여 매핑 목록을 엽니다.
3. **디자이너** 를 선택하여 매핑 세부 정보를 검토합니다.
4. **세부 정보 표시** 를 선택합니다.
5. 구성 트리에서 **Set1** 및 **Set1.Details** 데이터 모델 항목을 확장합니다.

    1. 바인딩 **세부 정보: 기록 목록 = 버전** 은 **Set1.Details** 항목이 **ERSolutionVersionTable** 테이블의 기록을 반환하는 **버전** 데이터 원본에 바인딩되어 있음을 나타냅니다. 이 테이블의 각 기록은 ER 구성의 단일 버전을 나타냅니다. 이 표의 내용은 **구성** 페이지의 **버전** FastTab에 표시됩니다.
    2. 바인딩 **구성 버전: 스트링 = @.PublicVersionNumber** 는 각 ER 구성 버전의 공개 버전 값을 **ERSolutionVersionTable** 테이블의 **PublicVersionNumber** 필드에서 가져와 **ConfigurationVersion** 항목에 배치함을 의미합니다.
    3. 바인딩 **구성 제목: 스트링 = @.'>Relations'.Solution.Name** 은 **ERSolutionVersionTable과** **ERSolutionTable** 테이블 사이의 다대일 관계(**'>Relations'**)를 사용하여 **ERSolutionTable** 테이블의 **이름** 필드에서 ER 구성 이름을 가져옴을 나타냅니다. 현재 애플리케이션 인스턴스의 ER 구성 이름은 **구성** 페이지의 구성 트리에 표시됩니다.
    4. **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** 바인딩은 현재 구성을 소유한 구성 공급자의 이름이 다대일을 사용하여 평가하는 **ERVendorTable** 테이블의 **이름** 필드에서 가져옴을 의미합니다. **ERSolutionTable과** **ERVendorTable** 테이블 간의 관계. ER 구성 공급자의 이름은 각 구성에 대한 페이지 헤더의 **구성** 페이지에 있는 구성 트리에 표시됩니다. ER 구성 공급자의 전체 목록은 **조직 관리 \> 전자 보고 \> 구성 공급자** 테이블 페이지에서 찾을 수 있습니다.

    ![ER 모델 매핑 디자이너 페이지, 바인딩된 데이터 모델 항목 목록.](./media/GER-JoinDS-Set1Review.PNG)

6. 구성 트리에서 **Set1.Summary** 데이터 모델 항목을 확장합니다.

    1. 바인딩 **버전 번호: 정수 = VersionsSummary.aggregated.VersionsNumber** 는 **Set1.Summary.VersionsNumber** 항목이 **Versions** 데이터 소스를 통해 **ERSolutionVersionTable 테이블** 의 기록 수를 반환하도록 구성된 **GroupBy** 유형의 **VersionsSummary** 데이터 소스의 **VersionsNumber** 집계 필드에 바인딩되었음을 나타냅니다. .

    !['그룹화 기준' 매개 변수 페이지 편집.](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. 페이지를 닫습니다.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> ER 모델 매핑 검토(2부)

ER 모델 매핑 구성 요소의 설정을 검토합니다. 구성 요소는 **Join** 유형의 데이터 소스를 사용하여 ER 구성 버전, 구성 세부 정보 및 구성 공급자에 대한 정보에 액세스하도록 구성됩니다.

1. 구성 트리에서 **Set2** 및 **Set2.Details** 데이터 모델 항목을 확장합니다. 바인딩 **세부 정보: 기록 목록 = 세부 정보** 는 **Set2.Details** 항목이 **조인** 유형의 데이터 원본으로 구성된 **세부 정보** 데이터 원본에 바인딩되어 있음을 나타냅니다.

    ![확장된 Set2:Record 데이터 모델 항목을 보여주는 ER 모델 매핑 디자이너 페이지.](./media/GER-JoinDS-Set2Review.PNG)

    **Functions\Join** 데이터 소스를 선택하여 **Join** 데이터 소스를 추가할 수 있습니다.

    ![ER 모델 매핑 디자이너 페이지, 데이터 소스 유형 조인.](./media/GER-JoinDS-AddJoinDS.PNG)

2. **세부 정보** 데이터 원본을 선택합니다.
3. **데이터 원본** 창에서 **편집** 을 선택합니다.
4. **조인 편집** 을 선택합니다.
5. **세부 정보 표시** 를 선택합니다.

    ![JOIN 데이터 소스 매개 변수 페이지.](./media/GER-JoinDS-JoinDSEditor.PNG)

    이 페이지는 **조인 유형** 의 필수 데이터 소스를 디자인하는 데 사용됩니다. 런타임 시 이 데이터 소스는 **결합된 목록** 그리드의 데이터 소스에서 단일 결합된 기록 목록을 생성합니다. 기록 조인은 그리드에 있는 **ConfigurationProviders** 데이터 원본에서 첫 번째 것으로 시작됩니다(**유형** 열은 비어 있음). 다른 모든 데이터 소스의 기록은 결과적으로 이 그리드의 순서에 따라 상위 데이터 소스의 기록에 결합됩니다. 모든 조인 데이터 원본은 대상 데이터 원본 아래에 중첩된 데이터 원본으로 구성되어야 합니다(`1Versions` 데이터 원본은 `1Configurations` 하나 아래에 중첩되고 `1Configurations` 데이터 원본은 **ConfigurationProviders** 아래에 중첩됨). 구성된 각 데이터 소스에는 조인 조건이 포함되어야 합니다. 이 특정 **조인** 에 대한 데이터 소스에서 다음 조인이 정의됩니다.

    - **ConfigurationProviders** 데이터 소스의 각 기록(**ERVendorTable** 테이블 참조)는 **SolutionVendor** 및 **RecId** 필드에서 동일한 값을 갖는 **1Configurations** 기록(**ERSolutionTable** 테이블 참조)의 기록과만 결합됩니다. **내부 조인** 유형은 이 조인과 일치하는 기록에 대한 다음 조건에 사용됩니다.

    FILTER(구성, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - **1Configurations** 데이터 소스(**ERSolutionTable** 테이블 참조)의 각 기록은 **Solution** 및 **RecId** 필드에서 동일한 값을 갖는 **1Versions** 1(**ERSolutionVersionTable** 테이블 참조)의 유일한 기록와 결합됩니다. **내부 조인** 유형은 이 조인과 일치하는 기록에 대한 다음 조건에 사용됩니다.

    필터(ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - **실행** 옵션은 **쿼리** 로 구성되어 이 조인 데이터 소스가 런타임 시 데이터베이스 수준에서 직접 SQL 호출로 실행됩니다.

    애플리케이션 테이블을 나타내는 데이터 소스의 기록을 조인하는 경우 이러한 테이블 간의 AOT 관계에 존재하는 것을 설명하는 필드가 아닌 다른 필드 쌍을 사용하여 조인 조건을 지정할 수 있습니다. 이 유형의 조인은 데이터베이스 수준에서도 실행되도록 구성할 수 있습니다.

6. 페이지를 닫습니다.
7. **취소** 를 선택합니다.
8. 구성 트리에서 **Set2.Summary** 데이터 모델 항목을 확장합니다.

    - 바인딩 **버전 번호: Integer = DetailsSummary.aggregated.VersionsNumber** 는 **Set2.Summary.VersionsNumber** 항목이 **Join** 의 **Details** 데이터 소스의 조인된 기록 수를 반환하도록 구성된 **GroupBy** 유형의 **DetailsSummary** 데이터 소스의 **VersionsNumber** 집계 필드에 바인딩되었음을 나타냅니다. 유형.
    - **실행** 위치 옵션은 **쿼리** 로 구성되어 이 **GroupBy** 데이터 소스가 런타임 시 데이터베이스 수준에서 직접 SQL 호출로 실행됩니다. 이 동작은 **Join** 유형의 기본 데이터 원본 **세부 정보** 가 데이터베이스 수준에서 실행되도록 구성되어 있기 때문에 가능합니다.

    ![GROUPBY 데이터 소스 매개 변수 페이지.](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. 페이지를 닫습니다.
10. **취소** 를 선택합니다.

### <a name="execute-er-format"></a><a name="executeERformat"></a> ER 형식 실행

1. 웹 브라우저의 두 번째 세션에서 첫 번째 세션과 동일한 자격 증명 및 회사를 사용하여 재무 또는 RCS에 액세스합니다.
2. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
3. **모델을 확장하여 JOIN 데이터 소스** 구성을 배우십시오.
4. **JOIN 데이터 소스 구성을 배우려면 형식** 을 선택하십시오.
5. **디자이너** 를 선택합니다.
6. **세부 정보 표시** 를 선택합니다.
7. **매핑** 을 선택합니다.
8. **확장/축소** 를 선택합니다.

    이 형식은 생성된 텍스트 파일을 모든 버전의 ER 구성(**버전** 순서)에 대해 새 줄로 채우도록 설계되었습니다. 생성된 각 줄에는 현재 구성을 소유한 구성 공급자의 이름, 구성 이름 및 세미콜론 표시로 구분된 구성 버전이 포함됩니다. 생성된 파일의 마지막 줄에는 검색된 ER 구성 버전의 수가 포함됩니다(**요약** 순서).

    ![ER 형식 디자이너 페이지, 형식 탭.](./media/GER-JoinDS-FormatReview.PNG)

    **데이터** 및 **요약** 데이터 소스는 생성된 파일에 구성 버전 세부 정보를 채우는 데 사용됩니다.

    - **Set1** 데이터 모델의 정보는 ER 형식을 실행할 때 사용자 대화 페이지에서 런타임 시 **선택기** 데이터 소스에 대해 **아니요** 를 선택할 때 사용됩니다.
    - **Set2** 데이터 모델의 정보는 사용자 대화 상자 페이지에서 런타임 시 **선택기** 데이터 소스에 대해 **예** 를 선택할 때 사용됩니다.

    ![ER 형식 디자이너 페이지, 매핑 탭.](./media/GER-JoinDS-FormatMappingReview.PNG)

9. **실행** 을 선택합니다.
10. 대화 상자 페이지의 **JOIN 데이터 소스 사용** 필드에서 **아니오** 를 선택하십시오.
11. **확인** 을 선택합니다.
12. 생성된 파일을 검토합니다.

    ![JOIN 데이터 소스를 사용하지 않는 전자 보고서 매개 변수 생성 파일.](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>ER 형식 실행 추적 분석

1. 재무 또는 RCS의 첫 번째 세션에서 **디자이너** 를 선택합니다.
2. **성능 추적** 을 선택합니다.
3. **성능 추적** 그리드에서 현재 모델 매핑 구성 요소를 사용한 ER 형식의 최신 실행 추적의 최상위 기록을 선택합니다.
4. **확인** 을 선택합니다.

    실행 통계는 애플리케이션 테이블에 대한 중복 호출에 대해 알려줍니다.

    - **ERSolutionTable** 은 **ERSolutionVersionTable** 테이블에 있는 구성 버전 기록만큼 여러 번 호출되었지만 성능 향상을 위해 이러한 호출 횟수를 줄일 수 있습니다.
    - **ERVendorTable** 은 **ERSolutionVersionTable** 테이블에서 발견된 모든 구성 버전 기록에 대해 두 번 호출되었지만 이러한 호출 수도 감소할 수 있습니다.

    ![ER 모델 매핑 디자이너 페이지의 실행 통계입니다.](./media/GER-JoinDS-Set1Run2.PNG)

5. 페이지를 닫습니다.

### <a name="execute-er-format"></a>ER 형식 실행

1. 재무 또는 RCS의 두 번째 세션에서 웹 브라우저 탭으로 전환합니다.
2. **실행** 을 선택합니다.
3. 대화 상자 페이지의 **JOIN 데이터 소스 사용** 필드에서 **예** 를 선택하십시오.
4. **확인** 을 선택합니다.
5. 생성된 파일을 검토합니다.

    ![JOIN 데이터 소스를 사용하여 생성된 전자 보고서 매개 변수 파일.](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> ER 형식 실행 추적 분석

1. 재무 또는 RCS의 첫 번째 세션에서 **디자이너** 를 선택합니다.
2. **성능 추적** 을 선택합니다.
3. **성능 추적** 그리드에서 현재 모델 매핑 구성 요소를 사용한 ER 형식의 최신 실행 추적을 나타내는 최상위 기록을 선택합니다.
4. **확인** 을 선택합니다.

    통계는 다음에 대해 알려줍니다.

    - 애플리케이션 데이터베이스는 필수 필드에 액세스하기 위해 **ERVendorTable**, **ERSolutionTable** 및 **ERSolutionVersionTable** 테이블에서 기록을 가져오기 위해 한 번 호출되었습니다.

    ![ER 모델 매핑 디자이너 페이지 성능 통계 세부 정보.](./media/GER-JoinDS-Set2Run2.PNG)

    - **세부 정보** 데이터 원본에 구성된 조인을 사용하여 구성 버전 수를 계산하기 위해 애플리케이션 데이터베이스가 한 번 호출되었습니다.

    ![애플리케이션 데이터베이스 호출을 보여주는 ER 모델 매핑 디자이너 페이지.](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>한계

이 항목의 예시에서 볼 수 있듯이 **JOIN** 데이터 원본은 결국 조인해야 하는 기록의 개별 데이터 집합을 설명하는 여러 데이터 원본에서 빌드할 수 있습니다. 내장된 ER [FILTER](er-functions-list-filter.md) 함수를 사용하여 이러한 데이터 소스를 구성할 수 있습니다. **JOIN** 데이터 원본을 넘어 호출되도록 데이터 원본을 구성할 때 회사 범위를 데이터 선택 조건의 일부로 사용할 수 있습니다. **JOIN** 데이터 소스의 초기 구현은 이 유형의 데이터 소스를 지원하지 않습니다. 예를 들어, **JOIN** 데이터 소스의 실행 범위 내에서 [FILTER](er-functions-list-filter.md) 기반 데이터 소스를 호출할 때 호출된 데이터 소스에 데이터 선택 조건의 일부로 회사 범위가 포함되어 있으면 예외가 발생합니다.

Microsoft Dynamics 365 Finance 버전 10.0.12(2020년 8월)에서는 **JOIN** 데이터 원본의 실행 범위 내에서 호출되는 [FILTER](er-functions-list-filter.md) 기반 데이터 원본에서 데이터 선택 조건의 일부로 회사 범위를 사용할 수 있습니다. 애플리케이션 [쿼리](../dev-ref/xpp-library-objects.md#query-object-model) 빌더의 한계로 인해 회사 범위는 **JOIN** 데이터 소스의 첫 번째 데이터 소스에 대해서만 지원됩니다.

### <a name="example"></a>예시

예를 들어, 여러 회사의 대외 무역 거래 목록과 해당 거래에서 참조되는 재고 항목의 세부 정보를 가져오려면 애플리케이션 데이터베이스를 한 번만 호출해야 합니다.

이 경우 ER 모델 매핑에서 다음 아티팩트를 구성합니다.

- **Intrastat** 테이블을 나타내는 **Intrastat** 루트 데이터 소스입니다.
- **InventTable** 테이블을 나타내는 **항목** 루트 데이터 원본입니다.
- 트랜잭션에 액세스해야 하는 회사 목록(이 예시에서는 **DEMF** 및 **GBSI**)을 반환하는 **회사** 루트 데이터 소스입니다. 회사 코드는 **Companies.Code** 필드에서 사용할 수 있습니다.
- `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))` 표현식이 있는 **X1** 루트 데이터 소스입니다. 데이터 선택 조건의 일부로 이 표현식에는 회사 범위 `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`의 정의가 포함됩니다.
- **X1** 데이터 소스의 중첩 항목으로 **X2** 데이터 소스. `FILTER (Items, Items.ItemId = X1.ItemId)`라는 표현이 포함되어 있습니다.

마지막으로 **X1** 이 첫 번째 데이터 소스이고 **X2** 가 두 번째 데이터 소스인 **JOIN** 데이터 소스를 구성할 수 있습니다. **쿼리** 를 **실행** 옵션으로 지정하여 ER이 데이터베이스 수준에서 이 데이터 소스를 직접 SQL 호출로 실행하도록 할 수 있습니다.

ER 실행이 [추적](trace-execution-er-troubleshoot-perf.md)되는 동안 구성된 데이터 소스가 실행되면 다음 명령문이 ER 성능 추적의 일부로 ER 모델 매핑 디자이너에 표시됩니다.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> 실행된 **JOIN** 데이터 소스의 추가 데이터 소스에 대한 회사 범위가 있는 데이터 선택 조건을 포함하도록 구성된 **JOIN** 데이터 소스를 실행하면 오류가 발생합니다.

## <a name="additional-resources"></a>추가 리소스

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
