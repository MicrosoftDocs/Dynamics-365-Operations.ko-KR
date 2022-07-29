---
title: 기준 값과 비교하기 위해 생성된 ER 보고서의 결과 추적 개선
description: 이 항목에서는 Microsoft Dynamics 365 for Finance and Operations 버전 10.0.3(2019년 6월)의 ER 기준선 기능 개선 사항에 대해 설명합니다.
author: NickSelin
ms.date: 06/19/2019
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
ms.openlocfilehash: b6e8299dd57730486c731cd38578bd5ff6b8a1754f145432e300c1217c6dd640
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460671"
---
# <a name="improve-tracing-the-results-of-generated-er-reports-to-compare-with-baseline-values"></a>기준 값과 비교하기 위해 생성된 ER 보고서의 결과 추적 개선

[!include[banner](../includes/banner.md)]

이 항목에서는 전자 보고(ER) 프레임워크의 기본 기능에 적용된 첫 번째 개선 사항에 대해 설명합니다. 이러한 개선 사항은 Microsoft Dynamics 365 for Finance and Operations 버전 10.0.3(2019년 6월) 이상에서 사용할 수 있습니다.

## <a name="automate-the-setting-of-baseline-rules"></a>기준 규칙 설정 자동화

[생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md) 항목에서는 ER 형식 실행에 대한 정보를 수집하고 이러한 실행 결과를 평가하도록 ER 프레임워크를 구성하는 방법을 설명합니다. 이 항목의 예는 완료해야 하는 단계를 보여줍니다.

다음은 단계 중 일부입니다.

- ER 형식을 실행하여 아웃바운드 파일을 생성하고 파일을 로컬에 저장합니다.
- ER 형식에 추가된 기준선의 첨부 파일로 로컬에 저장된 파일을 추가합니다.
- 추가된 기준선에 대한 기준선 규칙을 구성합니다. 이 구성에는 다음 단계가 포함됩니다.

    - 아웃바운드 파일을 생성하는 데 사용되는 ER 형식 요소를 지정합니다.
    - 생성된 아웃바운드 파일을 참조하는 첨부 파일을 선택합니다.

> [!NOTE]
> 이러한 단계는 새로운 ER 기능으로 자동화가 가능하더라도 수동으로 수행해야 합니다. 이 기능에 대해 자세히 알아보려면 다음 예를 완료하세요.

## <a name="example-automate-the-setting-of-baseline-rules"></a>예: 기준 규칙 설정 자동화

이 예제의 단계를 완료하려면 먼저 [생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md) 토픽의 "설계된 ER 형식에 대한 새 기준선 추가" 섹션까지 예에 있는 단계를 완료해야 합니다.

### <a name="review-added-baseline"></a>추가된 기준선 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **기준선** 을 선택합니다.

    > [!NOTE]
    > 작업 창의 **기준선** 버튼은 **디버그 모드에서 실행** ER 사용자 매개변수가 현재 회사에 대해 켜져 있는 경우에만 사용할 수 있습니다.

기준선은 선택한 **ER 베이스라인 학습을 위한 형식** 형식에 대해 추가되었지만 이 기준선에 대한 기준선 규칙이 아직 추가되지 않았습니다.

![전자 보고 형식 기준 페이지, 아직 규칙이 없습니다.](media/GER-BaselineSample-AddBaseline2.PNG "전자 보고 형식 기준 페이지의 스크린샷")

### <a name="make-a-new-baseline-rule"></a>새 기준선 규칙 만들기

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. 트리에서 **ER 베이스라인 학습 모델** 을 확장합니다.
3. 트리에서 **ER 베이스라인 학습 모델\\ER 베이스라인 학습을 위한 형식** 을 선택합니다.
4. **버전** FastTab에서 **실행** 을 선택합니다.
5. **ID 입력** 필드에 **1** 을 입력합니다.
6. **기준 파일 만들기** 옵션을 **네** 로 설정합니다.
7. **확인** 을 선택합니다.
8. **기준선** 을 선택합니다.

    ![전자 보고 형식 기준 페이지, 기준선 선택됨.](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "전자 보고 형식 기준 페이지의 스크린샷")

    생성된 아웃바운드 파일은 실행된 ER 형식의 기준선에 자동으로 첨부되었습니다. 기준선 규칙은 이 기준선에 자동으로 추가되었으며 첨부 파일에 대한 참조도 포함합니다.

9. **이름** 필드에 **기준 1** 을 입력합니다.
10. **파일 이름 마스크** 필드에 **.xml** 을 입력합니다.
11. **저장** 을 선택합니다.

### <a name="run-the-format"></a>형식 실행

이제 [생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md) 토픽의 "설계된 ER 형식을 실행하고 로그를 검토하여 결과 분석" 섹션부터의 남은 예제 단계를 완료할 준비가 되었습니다.

> [!NOTE]
> **기준** 빠른 탭에서 자동으로 추가된 베이스라인 규칙을 삭제할 때 참조된 첨부 파일은 자동으로 삭제되지 않습니다.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>지속적으로 변화하는 ER 출력 부분을 무시하도록 기준선을 구성합니다.

ER 형식이 실행될 때 변경되는 정보를 포함하도록 설계된 경우 ER 기준선 기능을 사용하여 생성된 결과를 기준선 값과 비교하려면 형식이 필요해야 합니다. 예를 들어, 정보는 처리 날짜 및 시간 또는 다른 형식으로 생성된 문서의 고유 식별자(전역 고유 식별자 \[GUID\] 등). 새로운 ER 기능을 사용하면 기준 값을 형식 실행 결과와 비교할 목적으로 형식이 실행될 때 ER 형식의 변경 가능한 요소를 무시하도록 기준 규칙을 구성할 수 있습니다. 이 기능에 대해 자세히 알아보려면 다음 예를 완료하세요.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>예: 지속적으로 변화하는 ER 출력 부분을 무시하도록 기준선을 구성합니다

이 예제의 단계를 완료하려면 먼저 [생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md) 토픽의 예에 있는 단계를 완료해야 합니다.

### <a name="modify-a-configured-er-format"></a>구성된 ER 형식 수정

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. 트리에서 **ER 베이스라인 학습 모델** 을 확장합니다.
3. 트리에서 **ER 베이스라인 학습 모델\\ER 베이스라인 학습을 위한 형식** 을 선택합니다.
4. **디자이너** 를 선택합니다.
5. 트리에서 **출력\\문서** 를 선택합니다.
6. **추가** 를 선택합니다.
7. 드롭다운 대화 상자의 트리에서 **XML\\특성** 을 선택합니다.
8. **이름** 필드에 **ProcessingDateTime** 을 입력합니다.
9. **확인** 을 선택합니다.
10. **매핑** 탭의 트리에서 **출력\\문서\\ProcessingDateTime** 을 선택합니다.
11. **수식 편집** 을 선택합니다.
12. **공식** 필드에 다음 표현식을 입력합니다. **DATETIMEFORMAT(NOW(), "O")**
13. **저장** 을 선택하고 **테스트** 를 선택합니다.
14. **테스트** 를 다시 선택하여 구성된 표현식을 다시 테스트합니다.

    ![수식 디자이너 페이지.](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "수식 디자이너 페이지의 스크린샷")

    > [!NOTE]
    > **검사 결과** 탭은 구성된 표현식이 호출될 때마다 다른 날짜 및 시간 값을 반환함을 보여줍니다.

15. **수식 디자이너** 페이지를 닫고 **저장** 을 선택합니다.

    ![형식 디자이너 페이지.](media/GER-BaselineSample-FormatMappingDesign2.PNG "형식 디자이너 페이지의 스크린샷")

16. **형식 디자이너** 페이지를 닫습니다.

### <a name="remove-an-existing-baseline-rule"></a>기존 기준 규칙 제거

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **기준선** 을 선택합니다.
3. 기준선 목록에서 **ER 베이스라인 학습을 위한 형식** 형식에 대해 구성된 기준선을 선택합니다.
4. **기준선** 빠른 탭에서 **삭제** 를 선택하여 이전에 구성한 기준선 규칙을 제거합니다.

![전자 보고 형식 기준 페이지, 삭제됨.](media/GER-BaselineSample-AddBaseline3.PNG "전자 보고 형식 기준 페이지의 스크린샷")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>설계된 ER 형식의 바인딩에 대한 대체 정의

1. **구성** 페이지의 **교체** 빠른 탭에서 **구성 요소 선택** 을 선택합니다.
2. 형식 구성 요소 트리에서 **출려** 을 확장하고 **출력\\문서** 를 확장한 다음 **출력\\문서\\ProcessingDateTime** 확인란을 선택합니다.
3. **확인** 을 선택합니다.

![전자 보고 형식 기준 페이지, 구성 요소.](media/GER-BaselineSample-AddBaseline4.PNG "전자 보고 형식 기준 페이지의 스크린샷")

선택한 ER 형식 구성 요소가 **바꾸기** 빠른 탭의 구성 요소 목록에 추가되었습니다. 기본 ER 형식이 디버그 모드에서 실행될 때 각 구성 요소에 대한 형식의 바인딩은 **바인딩** 열에 표시되는 바인딩으로 대체됩니다. **바꾸기** 빠른 탭의 목록에 있는 구성 요소의 기본 바인딩을 변경하려면 **편집** 을 선택합니다.

### <a name="make-a-new-baseline-rule"></a>새 기준선 규칙 만들기

이 항목 앞부분의 "예: 기준 규칙 설정 자동화" 섹션의 단계를 따릅니다. 알림은 아웃바운드 파일이 기준 설정을 사용하여 생성되었으며 형식 바인딩의 강제 교체가 발생했음을 경고합니다.

![구성 페이지의 알림.](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "구성 페이지의 알림 스크린샷")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>형식 바인딩 교체에 대한 경고 표시 안 함

특정 ER 매개변수를 설정하여 형식 바인딩 교체에 대해 경고하는 알림을 표시하지 않을 수 있습니다. 이 억제는 형식 바인딩이 무인 모드에서 Regression Suite Automation Tool을 사용하여 대체될 때 유용할 수 있습니다. 이 경우 경고는 실행 중인 테스트 케이스의 실패로 간주될 수 있습니다.

1. **구성** 페이지의 작업 창에서 **구성** 탭의 **사용자 매개 변수** 를 선택합니다.
2. **기준선 경고 억제** 옵션을 **네** 로 설정한 다음 **확인** 을 선택합니다.

### <a name="review-the-generated-baseline-file"></a>생성된 기준 파일 검토

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **기준선** 을 선택합니다.
3. **첨부 파일** 을 선택합니다.
    > [!NOTE]
    > 생성된 파일에는 처리 날짜 및 시간 텍스트(**"#"**) 형식의 바인딩이 아니라 추가된 기준 규칙에 구성된 바인딩에서 가져옵니다.
    
4. **첨부 파일** 페이지를 닫습니다.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>설계된 ER 형식을 실행하고 로그를 검토하여 결과 분석

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. 트리에서 **ER 베이스라인 학습 모델** 을 확장합니다.
3. 트리에서 **ER 베이스라인 학습 모델\\ER 베이스라인 학습을 위한 형식** 을 선택합니다.
4. **버전** 빠른 탭에서 **실행** 을 선택합니다.
5. **ID 입력** 필드에 **1** 을 입력합니다.
6. **확인** 을 선택합니다.
7. **조직 관리** \> **전자 보고** \> **구성 디버그 로그** 로 이동합니다.

실행 로그에는 생성된 파일을 구성된 기준선과 비교한 결과에 대한 정보가 포함됩니다. 실행된 형식에는 아웃바운드 파일에서 지속적으로 변경되는 날짜 및 시간 값을 입력하는 바인딩이 포함되어 있지만 로그는 생성된 파일과 기준선이 동일함을 나타냅니다.

> [!NOTE]
> 아웃바운드 파일은 형식 바인딩을 강제로 교체하는 기준 설정을 사용하여 생성되었지만 교체에 대한 경고는 수신되지 않습니다.

## <a name="exchange-baseline-settings-between-environments"></a>환경 간 기본 설정 교환

### <a name="export-baseline-settings"></a>기준 설정 내보내기

새로운 ER 기능을 사용하면 현재 환경에서 선택한 ER 형식에 대한 기준 설정을 내보내고 XML 파일로 저장할 수 있습니다. 

기준 설정을 내보내려면 **전자 보고 형식 기준선** 페이지에서 **내보내기** 를 선택합니다.

### <a name="import-baseline-settings"></a>기준 설정 가져오기

내보낸 기준 설정을 다른 환경으로 가져올 수 있습니다. 먼저 환경을 ER 형식으로 가져와야 합니다. 그런 다음 기준 설정을 가져올 수 있습니다.

로컬에 저장된 XML 파일에서 기준 설정을 가져오려면 **전자 보고 형식 기준선** 페이지에서 **가져오기** 를 선택한 다음 **검색** 을 선택하여 XML 파일을 선택합니다.

![기준 설정 가져오기 대화 상자.](media/GER-BaselineSample-ImportBaseline1.PNG "기준선 설정 가져오기 대화 상자의 스크린샷")

Microsoft SharePoint 서버에 저장된 XML 파일에서 기준 설정을 가져오려면 현재 문서 관리 설정과 선택한 문서 유형을 기반으로 **전자 보고 형식 기준선** 페이지에서 **소스에서 가져오기** 를 선택합니다. 그런 다음 문서 유형과 XML 파일을 선택합니다. SharePoint 폴더에 액세스하는 데 필요한 문서 유형을 미리 구성해야 합니다.

![소스 대화 상자에서 가져오기.](media/GER-BaselineSample-ImportBaseline2.PNG "소스에서 가져오기 대화 상자의 스크린샷")

> [!NOTE]
> 작업 레코더를 사용하여 **소스에서 가져오기** 대화 상자에서 필요한 문서 유형과 파일 이름을 선택하는 단계를 기록할 수 있습니다. 이러한 방식으로 SharePoint 서버의 필요한 기준선 설정을 유지하고 Regression Suite Automation Tool을 사용하여 자동화 테스트를 실행할 때 녹음된 작업을 재생하여 자동으로 가져올 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [생성된 보고서 결과 추적 및 기준 값과 비교](er-trace-reports-compare-baseline.md)
- [작업 레코더 리소스](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
