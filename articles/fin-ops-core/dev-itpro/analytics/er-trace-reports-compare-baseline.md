---
title: 생성된 보고서 결과 추적 및 기준 값과 비교
description: 이 항목에서는 생성된 전자 보고(ER) 보고서의 결과를 기준 보고서 값과 비교하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 9fabdef96b02747c84a76bf42997633842f185e9
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460669"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>생성된 보고서 결과 추적 및 기준 값과 비교

[!include[banner](../includes/banner.md)]

발신 전자 문서를 생성하는 전자 보고(ER) 형식의 결과를 추적할 수 있습니다. 추적 생성이 켜져 있는 경우(**디버그 모드에서 실행** ER 사용자 매개 변수 사용), ER 보고서가 실행될 때마다 ER 형식 실행 로그에 새 추적 레코드가 생성됩니다. 다음 세부 정보는 생성된 각 추적에 저장됩니다.

- 유효성 검사 규칙에 의해 생성된 모든 경고
- 유효성 검사 규칙에 의해 생성된 모든 오류
- 추적 레코드의 첨부 파일로 저장되는 생성된 모든 파일

모든 ER 형식에 대해 개별 기준 응용 프로그램 파일을 저장할 수 있습니다. 파일은 실행되는 보고서의 예상 결과를 설명할 때 기준 파일로 간주됩니다. 추적 생성이 켜진 상태에서 실행되는 ER 형식에 기준 파일을 사용할 수 있는 경우 추적에는 앞에서 언급한 세부 정보 외에 생성된 전자 문서를 기준 파일과 비교한 결과가 저장됩니다. 한 번의 클릭으로 생성된 전자 문서와 기본 파일을 하나의 zip 파일로 가져올 수도 있습니다. 그런 다음 WinDiff와 같은 외부 도구를 사용하여 자세한 비교를 수행할 수 있습니다.

추적을 평가하여 생성된 전자 문서에 예상 콘텐츠가 포함되어 있는지 분석할 수 있습니다. 코드 기반이 변경된 경우(예: 애플리케이션의 새 인스턴스로 마이그레이션하거나 핫픽스 패키지를 설치하거나 코드 수정을 배포한 경우) UAT(사용자 승인 테스트) 환경에서 이 평가를 수행할 수 있습니다. 이러한 방식으로 평가가 사용되는 ER 보고서의 실행에 영향을 미치지 않는지 확인할 수 있습니다. 많은 ER 보고서의 경우 무인 모드에서 평가를 수행할 수 있습니다.

이 기능에 대해 자세히 알아보려면 **ER 보고서 생성 및 결과 비교(1부)** 및 **ER 보고서 생성 및 결과 비교(2부)** 의 일부인 작업 가이드 **7.5.4.3 IT 서비스/솔루션 테스트(10679)** 비즈니스 프로세스를 확인하고 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?linkid=874684)에서 다운로드하세요. 이 작업 가이드는 생성된 전자 문서를 평가하기 위해 기준 파일을 사용하도록 ER 프레임워크를 구성하는 프로세스를 설명합니다.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>예: 생성된 보고서 결과 추적 및 기준 값과 비교

이 절차에서는 ER 형식 실행에 대한 정보를 수집한 다음 해당 실행 결과를 평가하도록 ER 프레임워크를 구성하는 방법을 설명합니다. 해당 평가의 일부로 생성된 문서는 기준 파일과 비교됩니다. 이 예에서는 샘플 회사 Litware, Inc.에 대한 필수 ER 구성을 만듭니다. 이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위한 것입니다. 모든 데이터 세트를 사용하여 이러한 단계를 완료할 수 있습니다.

이 예의 단계를 완료하려면 RCS에서 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md) 절차를 완료해야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 Litware, Inc. 샘플 회사의 구성 공급자가 나열되어 있고 **활성** 으로 표시되어 있는지 확인합니다. 이 구성 공급자가 표시되지 않으면 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)의 단계를 따르세요.

### <a name="configure-document-management-parameters"></a>문서 관리 매개 변수 구성

1. **조직 관리** \> **문서 관리** \> **문서 유형** 으로 이동하고 기준 파일을 저장할 새 문서 유형을 만듭니다.
2. **클래스** 필드에 **파일 첨부** 를 입력합니다.
3. **그룹** 필드에 **파일** 을 입력합니다.

![문서 유형 페이지.](media/GER-BaselineSample-SetupDocumentType.PNG "문서 유형 페이지의 스크린샷")

> [!NOTE]
> ER 기준 기능을 사용할 계획인 각 데이터 세트에 대해 동일한 이름을 가진 새 문서 유형을 구성해야 합니다.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>기준 기능 사용을 시작하도록 ER 매개변수 구성

1. **전자 보고** 작업 영역의 **관련 링크** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.

    ![전자 보고 작업 영역.](media/GER-BaselineSample-ERWorkspace.PNG "전자 보고 작업 공간의 스크린샷")

2. **첨부 파일** 탭의 **기준** 필드에 방금 생성한 문서 유형을 입력하거나 선택합니다.

    ![전자 보고 매개변수 페이지의 첨부 탭.](media/GER-BaselineSample-ERParameters.PNG "전자 보고 매개 변수의 스크린샷")

3. **저장** 을 선택한 다음 **전자 보고 매개 변수** 페이지를 닫습니다.

### <a name="add-a-new-er-model-configuration"></a>새 ER 모델 구성 추가

1. **전자 보고** 작업 공간의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
2. 작업 창에서 **구성 만들기** 를 선택합니다.
3. 드롭다운 대화 상자의 **이름** 필드에 **ER 기준을 학습할 모델** 을 입력합니다.
4. **구성 만들기** 를 선택하여 새 ER 데이터 모델 항목의 생성을 확인합니다.

![구성 생성 대화 상자에서 새 ER 모델 구성을 추가합니다.](media/GER-BaselineSample-ModelAdd.PNG "구성 만들기 드롭다운 대화 상자의 스크린샷")

### <a name="design-a-data-model"></a>데이터 모델 설계

1. **구성** 페이지의 작업 창에서 **디자이너** 를 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. 드롭다운 대화 상자의 **이름** 필드에 **루트** 를 입력합니다.
4. **추가** 를 선택합니다.
5. **루트 참조** 를 선택합니다.
6. **확인** 을 선택하고 **저장** 을 선택합니다.
7. **모델 디자이너** 페이지를 닫습니다.
8. **상태 변경** 을 선택합니다.
9. **완료** 를 선택하고 **확인** 을 선택합니다.

![구성 페이지.](media/GER-BaselineSample-ModelComplete.PNG "구성 페이지의 스크린샷")

### <a name="add-a-new-er-format-configuration"></a>새 ER 형식 구성 추가

1. **구성** 페이지의 작업 창에서 **구성 만들기** 를 선택합니다.
2. 드롭다운 대화 상자의 **새로 만들기** 필드 그룹에서 **ER 베이스라인 학습을 위한 데이터 모델 모델 기반 형식** 을 선택합니다.
3. **이름** 필드에 **ER 베이스라인 학습을 위한 형식** 을 입력합니다.
4. **구성 만들기** 를 선택하여 새 ER 형식 항목의 생성을 확인합니다.

![구성 생성 대화 상자에서 새 ER 형식 구성을 추가합니다.](media/GER-BaselineSample-FormatAdd.PNG "구성 만들기 드롭다운 대화 상자의 스크린샷")

### <a name="design-a-format"></a>형식 디자인

이 예에서는 간단한 ER 형식을 만들어 XML 문서를 생성합니다.

1. **구성** 페이지의 작업 창에서 **디자이너** 를 선택합니다.
2. **루트 추가** 를 선택합니다.
3. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. 트리에서 **공통\\파일** 을 선택합니다.
    2. **이름** 필드에 **출력** 을 입력합니다.
    3. **확인** 을 선택합니다.

4. **추가** 를 선택합니다.
5. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. 트리에서 **XML\\요소** 를 선택합니다.
    2. **이름** 필드에 **문서** 를 입력합니다.
    3. **확인** 을 선택합니다.

6. 트리에서 **출력\\문서** 를 선택합니다.
7. **추가** 를 선택합니다.
8. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. 트리에서 **XML\\특성** 을 선택합니다.
    2. **이름** 필드에 **ID** 를 입력합니다.
    3. **확인** 을 선택합니다.

    ![형식 디자이너 페이지, 트리에서 XML 속성이 선택되었습니다.](media/GER-BaselineSample-FormatLayoutDesign.PNG "형식 디자이너 페이지의 스크린샷")

9. **매핑** 탭에서 **삭제** 를 선택합니다.
10. **루트 추가** 를 선택합니다.
11. 드롭다운 대화 상자의 트리에서 **일반\\사용자 입력 매개 변수** 를 선택한 후 다음 단계를 따르세요.

    1. **이름** 필드에 **ID** 를 입력합니다.
    2. **레이블** 필드에 **ID 입력** 을 입력합니다.
    3. **확인** 을 선택합니다.

12. 트리에서 **출력\\문서\\Id** 를 선택합니다.
13. **바인딩** 을 선택하고 **저장** 을 선택합니다.

![형식 디자이너 페이지, 매핑 탭.](media/GER-BaselineSample-FormatMappingDesign.PNG "형식 디자이너 페이지의 스크린샷")

설계된 구조를 기반으로 구성된 형식은 XML 파일을 생성합니다. 이 XML에는 사용자가 ER 런타임 대화 상자에 입력하는 값으로 설정되는 **ID** 특성이 있는 **루트** 요소가 포함되어 있습니다.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>설계된 ER 형식에 대한 새 기준 파일 생성

1. **구성** 페이지의 **버전** 빠른 탭에서 **실행** 을 선택합니다.
2. **ID 입력** 필드에 **1** 을 입력합니다.
3. **확인** 을 선택합니다.

    ![전자 보고서 매개변수 대화 상자.](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "전자 보고 매개 변수 대화 상자의 스크린샷")

4. 생성된 **out.Admin.xml** 파일의 로컬 사본을 저장하여 나중에 이 ER 형식의 기준으로 사용할 수 있도록 합니다.

    ![구성 페이지에서 생성된 파일에 대한 알림입니다.](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "구성 페이지에서 생성된 파일에 대한 알림의 스크린샷")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>기준 기능 사용하도록 ER 매개변수 구성

1. **구성** 페이지의 작업 창에서 **구성** 탭의 **사용자 매개 변수** 를 선택합니다.
2. **디버그 모드에서 실행** 옵션을 **예** 로 설정합니다.
3. **확인** 을 선택합니다.

![사용자 매개 변수 대화 상자.](media/GER-BaselineSample-ERUserParameters.PNG "사용자 매개 변수 대화 상자의 스크린샷")

### <a name="add-a-new-baseline-for-designed-er-format"></a>설계된 ER 형식에 대한 새 기준 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. 작업 창에서 **기준** 을 선택합니다.

    ![구성 페이지의 기준선 버튼.](media/GER-BaselineSample-OpenBaselinePage.PNG "구성 페이지의 기준 버튼 스크린샷")

3. 작업 창에서 **새로 만들기** 를 선택합니다.
4. 이전에 디자인한 **ER 베이스라인 학습을 위한 형식** ER 형식을 선택합니다.
5. **저장** 을 선택합니다.

![전자 보고 형식 기준 페이지.](media/GER-BaselineSample-AddBaseline.PNG "전자 보고 형식 기준 페이지의 스크린샷")

**ER 베이스라인 학습을 위한 형식** 형식에 대한 기준선이 추가됩니다.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>추가된 기준선에 대한 기준선 규칙 구성

1. **전자 보고 형식 기준선** 페이지의 작업 창에서 **첨부 파일** 버튼(종이 클립 기호)을 선택합니다.
2. 작업 창에서 **새로 만들기** \> **파일** 을 선택합니다. ER 매개 변수에서 **파일** 문서 유형이 기준 파일을 저장하는 데 사용되는 문서 유형으로 이전에 선택되어 있어야 합니다.
3. **검색** 을선택하고 이전에 구성된 ER 형식을 실행할 때 생성된 **out.Admin.xml** 파일을 선택합니다.

    ![첨부 파일 페이지.](media/GER-BaselineSample-UploadBaselineFile.PNG "첨부 파일 페이지의 스크린샷")

4. **첨부 파일** 페이지를 닫습니다.
5. **기준** 빠른 탭에서 **새로 만들기** 를 선택합니다.
6. **이름** 필드에 **기준 1** 을 입력합니다.
7. **파일 구성 요소 이름** 필드에서 **출력** 을 입력하거나 선택합니다. 이 값은 구성된 기준이 **출력** 형식 요소를 사용하여 생성된 파일과 비교됨을 나타냅니다.
8. **파일 이름 마스크** 필드에 **\*.xml** 을 입력합니다.

    > [!NOTE]
    > 파일 이름 마스크를 정의할 수 있습니다. 파일 이름 마스크가 정의되면 기준 레코드는 생성된 출력 파일의 이름이 해당 마스크를 충족하는 경우에만 생성된 출력을 평가하는 데 사용됩니다.

9. 구성된 기준선을 **ER 베이스라인 학습을 위한 형식** ER 형식이 특정 회사에 로그인한 사용자에 의해 실행될 때만 사용해야 하는 경우 **회사** 필드에서 해당 회사를 선택합니다.
10. **기준선** 필드에서 **out.Admin** 첨부 파일을 입력하거나 선택합니다.
11. **저장** 을 선택합니다.

![전자 보고 형식 기준 페이지, 기준이 선택된 기준 빠른 탭.](media/GER-BaselineSample-SetupBaselineLine.PNG "전자 보고 형식 기준 페이지의 스크린샷")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>설계된 ER 형식을 실행하고 로그를 검토하여 결과 분석

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. 트리에서 **ER 베이스라인 학습 모델** 을 확장한 다음 **ER 베이스라인 학습 모델\\ER 베이스라인 학습을 위한 형식** 을 선택합니다.
3. **버전** FastTab에서 **실행** 을 선택합니다.
4. **ID 입력** 필드에 **1** 을 입력합니다.
5. **확인** 을 선택합니다.
6. **조직 관리** \> **전자 보고** \> **구성 디버그 로그** 로 이동합니다.

    ![기준이 동일한 전자 보고 실행 로그 페이지.](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "전자 보고 실행 로그 페이지의 스크린샷")

    > [!NOTE]
    > 실행 로그에는 생성된 파일을 구성된 기준선과 비교한 결과에 대한 정보가 포함됩니다. 이 예에서 로그는 생성된 파일과 기준선이 동일함을 나타냅니다.

7. **모두 삭제** 를 선택합니다.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>설계된 ER 형식을 실행하고 로그를 검토하여 결과 분석

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. 트리에서 **ER 베이스라인 학습 모델** 을 확장한 다음 **ER 베이스라인 학습 모델\\ER 베이스라인 학습을 위한 형식** 을 선택합니다.
3. **버전** FastTab에서 **실행** 을 선택합니다.
4. **ID 입력** 필드에 **2** 를 입력합니다.
5. **확인** 을 선택합니다.
6. **조직 관리** \> **전자 보고** \> **구성 디버그 로그** 로 이동합니다.

    ![기준이 다른 전자 보고 실행 로그 페이지.](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "전자 보고 실행 로그 페이지의 스크린샷")

    > [!NOTE]
    > 실행 로그에는 생성된 파일을 구성된 기준선과 비교한 결과에 대한 정보가 포함됩니다. 이 예에서 로그는 생성된 파일과 기준이 다름을 나타냅니다.

7. **비교** 를 선택합니다.

> [!NOTE]
> 생성된 파일과 기준 파일은 zip 파일로 제공됩니다. WinDiff와 같은 외부 비교 도구를 사용하여 파일을 비교하고 차이점을 검토할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고(ER) 프레임워크 구성](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
