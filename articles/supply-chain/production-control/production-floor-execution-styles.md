---
title: 생산 현장 실행 인터페이스 스타일 지정
description: 이 항목에서는 기본 생산 현장 실행 스타일이 적용되도록 양식 컨트롤을 구성하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ef39dc6414f0afdadd4a4b5a41e1fb1fe60e4974
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449476"
---
# <a name="style-the-production-floor-execution-interface"></a>생산 현장 실행 인터페이스 스타일 지정

[!include [banner](../includes/banner.md)]

이 항목에서는 기본 생산 현장 실행 스타일이 적용되도록 양식 컨트롤을 구성하는 방법에 대해 설명합니다.

## <a name="forms-and-dialogs"></a>양식 및 대화 상자

다음 요구 사항이 충족되는 경우에만 양식 또는 대화 상자에 스타일을 적용할 수 있습니다.

- 양식이 기존 보고서 진행 양식과 유사해야 하는 경우 양식 또는 대화 상자의 이름은 `JmgProductionFloorExecutionCustomInputDialog`로 시작해야 합니다.
- 양식 또는 대화 상자에는 세부 양식 파트가 포함될 수 있습니다. 스타일을 적용하려면 세부 양식 파트의 이름이 `JmgProductionFloorExecutionCustomDetailsDialog`로 시작해야 합니다.
- 양식 또는 대화 상자에 단순 보기가 있어야 하는 경우 단순 보기의 이름은 `JmgProductionFloorExecutionCustomDialog`로 시작해야 합니다. 단순 보기가 있는 양식의 예로는 시작 양식 및 간접 활동 양식이 있습니다.
- 대화 상자의 모든 컨트롤은 이 항목에 설명된 대로 구성해야 합니다.

> [!IMPORTANT]
> 이 목록의 처음 두 글머리 기호에 언급된 기능을 사용하려면 Supply Chain Management 버전 10.0.19 이상이 필요합니다.

다음 요구 사항이 충족되는 경우에만 양식 또는 대화 상자의 **확인** 버튼에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `OkButtonGroup`로 시작합니다.

다음 요구 사항이 충족되는 경우에만 양식 또는 대화 상자의 **취소** 버튼에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `CancelButtonGroup`로 시작합니다.

### <a name="header"></a>머리글

다음 그림은 일반적인 양식 또는 대화 상자 헤더를 보여줍니다.

![일반적인 양식 또는 대화 상자 헤더입니다.](media/pfe-styles-header.png "일반적인 양식 또는 대화 상자 헤더입니다.")

Visual Studio에서 헤더는 다음 그림과 같은 구조를 사용하여 생성됩니다.

![헤더를 생성하기 위한 일반적인 코드 구조입니다.](media/pfe-styles-header-code-structure.png "헤더를 생성하기 위한 일반적인 코드 구조입니다.")

헤더에 텍스트를 추가하려면 다음 예제와 같은 코드를 사용하세요.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

헤더 코드를 작성할 때 다음 규칙을 적용하세요.

- 기본 그룹의 이름은 `TableRowHeaderGroup`이어야 합니다.
- 각 텍스트 블록(글머리 기호로 구분)은 `HeaderFieldWithSeparatorText`로 시작해야 합니다.
- 성은 `HeaderFieldText`로 시작해야 합니다.
- `CaptionImage`은 건너뛸 수 있습니다.

### <a name="progress-indicator"></a>진행 상태 표시기

헤더 오른쪽에 표시되는 진행 상태 표시기를 포함할 수 있습니다. 다음 그림은 진행 상태 표시기를 보여줍니다.

![일반적인 진행 상태 표시기.](media/pfe-styles-header-progress.png "일반적인 진행 상태 표시기.")

진행 상태 표시기를 표시하려면 텍스트 필드의 이름을 `ShowProgress`로 지정해야 합니다.

## <a name="grid"></a>그리드

스타일이 자동으로 적용됩니다. 특정 구성이 필요하지 않습니다.

그리드에는 `TabularView` 스타일이 있어야 하며 새 그리드가 아직 지원되지 않기 때문에 사용자 지정 양식의 `run()` 메서드를 덮어써야 합니다. 다음 코드를 추가합니다.

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

기본 보기에서 데이터를 새로 고치려면 작업의 `click` 방법에서 `this.parmParentForm().updateLayout();`와 같은 것을 사용하고 싶을 수 있습니다. (예를 들어 `JmgProductionFloorExecutionReportFeedbackAction` 클래스를 보십시오.) 새 양식(`formCaller.parmDataSource(this.dataSource(1));`)의 `init` 메소드에 `parmDataSource`가 설정되어 있는지 확인하세요. 예를 들어 `JmgProductionFloorExecutionMainGrid` 형식을 보십시오.

## <a name="card-view"></a>카드 보기

다음 요구 사항이 충족되는 경우에만 카드 보기 컨트롤에 스타일을 적용할 수 있습니다.

- 각 카드 보기는 양식 그룹에 포함됩니다.
- 그룹 이름은 `CardGroup`로 시작합니다(예: `CardGroupJobsView`).

다음 그림은 내부에 컨트롤이 없는 카드 보기를 보여줍니다.

![요소가 없는 카드 보기.](media/pfe-styles-empty-card.png)

다음 그림은 내부에 컨트롤이 있는 카드 보기를 보여줍니다.

![Hz를 표시하는 요소가 있는 카드.](media/pfe-styles-elements.png)

![유지 관리 요청을 위한 요소가 있는 카드입니다.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>명함

다음 요구 사항이 충족되는 경우에만 명함 컨트롤에 스타일을 적용할 수 있습니다.

- 각 명함은 양식 그룹에 포함됩니다.
- 그룹 이름은 `BusinessCardGroup`로 시작합니다(예: `BusinessCardGroupJobsList`).

명함에서 다음 속성을 설정합니다.

- **스타일:** *목록*
- **확장 스타일:** *카드 목록*
- **다중 선택:** *아니요*
- **열 레이블 표시:** *아니요*

![명함.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>라디오 단추

다음 요구 사항이 충족되는 경우에만 라디오 단추에 스타일을 적용할 수 있습니다.

- 각 라디오 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 텍스트를 표시할 위치에 따라 `RadioTextBelow` 또는 `RadioTextRight`로 시작합니다.

라디오 단추에서 다음 속성을 설정합니다.

- **토글 단추:** *검사*
- **토글 값:** *켜짐* 라디오 단추를 선택해야 하는지 여부. 그렇지 않으면, *끄기*

다음 그림은 라디오 단추 아래에 텍스트가 나타나는 예를 보여줍니다.

![아래에 텍스트가 있는 라디오 단추.](media/pfe-styles-radio-text-below.png)

다음 그림은 라디오 단추 오른쪽에 텍스트가 나타나는 예를 보여줍니다.

![오른쪽에 텍스트가 있는 라디오 단추.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Internet Explorer의 라디오 단추

라디오 단추 스타일은 Internet Explorer에서 지원되지 않습니다. 다음 그림은 Internet Explorer에서 라디오 단추의 모양을 보여줍니다.

![Internet Explorer의 라디오 단추](media/pfe-styles-browser.png)

## <a name="buttons"></a>단추

다음 요구 사항이 충족되는 경우에만 단추에 스타일을 적용할 수 있습니다.

- 각 단추 그룹은 양식 그룹에 포함되어 있습니다. 그룹의 모든 단추는 동일한 스타일을 갖습니다.
- 그룹 이름에 대한 요구 사항은 없습니다.

단추에서 다음 속성을 설정합니다.

- **단추 디스플레이:** *TextWithImageLeft*
- **기본 이미지:** 이 속성은 비워둘 수 없습니다. 예를 들어 *CoffeeScript* 를 사용합니다.
- **텍스트:** 이 속성은 비워둘 수 없습니다. 예를 들어 *Start Break* 를 사용합니다.
- **너비:** *자동* 또는 *SizeToContent*
- **높이:** *자동* 또는 *SizeToContent*

### <a name="primary-button"></a>기본 버튼

다음 요구 사항이 충족되는 경우에만 기본 단추에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `DefaultButtonGroup` 또는 `PrimaryButtonGroup`로 시작합니다(예: `DefaultButtonGroup10`).

![기본 버튼](media/pfe-styles-first.png)

### <a name="secondary-button"></a>보조 버튼

다음 요구 사항이 충족되는 경우에만 보조 단추에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 **오른쪽 패널** 이거나 그룹 이름이 `SecondaryButtonGroup`로 시작합니다.

![보조 버튼](media/pfe-styles-second.png)

### <a name="third-group-button"></a>세 번째 그룹 단추

다음 요구 사항이 충족되는 경우에만 세 번째 그룹 단추에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 **왼쪽 패널** 이거나 그룹 이름이 `ThirdButtonGroup`로 시작합니다.

![세 번째 그룹 단추](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>네 번째 그룹 단추

다음 요구 사항이 충족되는 경우에만 네 번째 그룹 단추에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `FourthButtonGroup`로 시작합니다.

단추에서 다음 속성을 설정합니다.

- **단추 디스플레이:** *텍스트만*
- **기본 이미지:** 이 속성은 비어 있어야 합니다.
- **텍스트:** 이 속성은 비워둘 수 없습니다. 예를 들어 *보기* 또는 *편집* 을 사용합니다.
- **너비:** *자동*
- **높이:** *자동*

![네 번째 그룹 단추](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>고정 단추

다음 요구 사항이 충족되는 경우에만 고정 단추에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `FlatButtonGroup`로 시작합니다.

단추에서 다음 속성을 설정합니다.

- **단추 디스플레이:** *이미지만*
- **기본 이미지:** 이 속성은 비워둘 수 없습니다. 예를 들어 *CoffeeScript* 를 사용합니다.
- **텍스트:** 이 속성은 비어 있어야 합니다.
- **너비:** *자동* 또는 *SizeToContent*
- **높이:** *자동* 또는 *SizeToContent*

![고정 단추](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>계속 단추

다음 요구 사항이 충족되는 경우에만 계속 단추에 스타일을 적용할 수 있습니다.

- 버튼은 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `ContinueButtonGroup`로 시작합니다.

단추에서 다음 속성을 설정합니다.

- **단추 디스플레이:** *이미지만*
- **기본 이미지:** *앞으로*
- **텍스트:** 이 속성은 비어 있어야 합니다.
- **너비:** *자동* 또는 *SizeToContent*
- **높이:** *자동* 또는 *SizeToContent*

![계속 단추](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>콤보 상자

콤보 상자는 입력 컨트롤, 입력 컨트롤을 지우는 단추 및 검색을 실행하는 단추의 세 가지 컨트롤의 조합입니다.

다음 요구 사항이 충족되는 경우에만 콤보 상자에 스타일을 적용할 수 있습니다.

- 콤보 상자는 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `Combobox`로 시작합니다.
- 그룹 내에서 첫 번째 컨트롤은 `AxFormStringControl` 컨트롤입니다. 이 컨트롤은 현재 값을 표시하며 사용자가 필요한 값을 입력하는 곳입니다.
- 두 번째 컨트롤은 `CommonButton` 컨트롤이며 이름은 `ClearButton`로 시작합니다. 이 단추는 `enable` 속성을 사용하여 단추를 표시하거나 숨기는 코드를 포함해야 합니다. 예를 들어, 사용자가 입력 컨트롤에 정보를 입력하는 동안 **지우기** 단추를 표시하거나 숨기려면 다음 코드를 사용할 수 있습니다.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    데이터가 입력 컨트롤에 설정되는 한 가지 방법이 있어야 합니다. 해당 방법에서 **지우기** 단추를 사용합니다. 다음은 예입니다.

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    **지우기** 단추의 `clicked` 메소드에 다음 코드를 사용하세요.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    `init` 방법을 사용하여 양식을 초기화할 때 입력 컨트롤의 값 `AxFormStringControl`을 설정합니다. 값이 비어 있지 않으면 **지우기** 단추를 활성화합니다. 값이 비어 있으면 **지우기** 단추를 비활성화합니다.

- 세 번째 컨트롤은 `CommonButton` 컨트롤이며 이름은 `SearchButton`로 시작합니다.

다음 그림에서는 두 개의 콤보 상자 컨트롤을 보여줍니다. 왼쪽의 콤보 상자에는 빈 텍스트 상자가 있으며 **지우기** 단추가 비활성화되어 있습니다. 오른쪽의 콤보 상자에는 텍스트 상자에 텍스트가 있으며 **지우기** 단추가 활성화되어 있습니다.

![지우기 단추가 있거나 없는 콤보 상자.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>빠른 필터

빠른 필터 컨트롤은 페이지에 검색 필드를 추가합니다. 다음 요구 사항이 충족되는 경우 빠른 필터에 스타일을 적용할 수 있습니다.

- 빠른 필터는 양식 그룹에 포함되어 있습니다.
- 그룹 이름은 `SearchInputGroup`로 시작합니다.
- 그룹 내에서 첫 번째 컨트롤은 `QuickFilter` 컨트롤입니다. (이 컨트롤은 사용자가 검색 문자열을 입력하는 곳입니다.)
- 두 번째 컨트롤은 `NumberOfResults`라는 이름의 `FormStaticTextControl`입니다. (이 컨트롤은 선택 사항입니다. 포함되어 있으면 찾은 아이템의 개수를 보여줍니다.)
- 세 번째 컨트롤은 `CommonButton` 컨트롤이며 이름은 `ClearButton`로 시작합니다.

다음 그림에서는 두 개의 빠른 필터 컨트롤을 보여줍니다. 왼쪽의 빠른 필터에는 비어 있는 빠른 필터가 있으며 결과 수가 표시되지 않습니다. 오른쪽의 빠른 필터는 검색 문자열을 포함하고 결과 수를 보여줍니다.

![검색 문자열이 있거나 없는 빠른 필터 컨트롤의 예.](media/pfe-styles-quick-filter.png "검색 문자열이 있거나 없는 빠른 필터 컨트롤의 예.")

## <a name="center-align-elements-on-a-tab"></a>탭의 중앙 맞춤 요소

탭 중앙에 요소를 정렬하려면 그룹 이름이 `TabContentGroup`로 시작해야 하고 그룹에 다음 속성이 있어야 합니다.

- **너비 모드:** `SizeToAvailable`
- **높이 모드:** `SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>그리드, 세부 사항 부분, 빠른 필터 정렬

사용자 지정 그리드, 세부 사항 부분, 빠른 필터를 표준 디자인과 유사하게 정렬하려면 모두 함께 사용할 때 다음 사항을 염두에 두십시오.

- 그리드에 빠른 필터가 있는 경우 그리드와 빠른 필터는 모두 `GridGroup`로 시작하는 이름을 가진 그룹 안에 있어야 합니다.
- 세부 사항 부분에 스타일을 적용하려면 그룹 이름이 `DetailInformationGroup`로 시작해야 합니다.

다음 그림은 오른쪽에 빠른 필터와 세부 사항 부분을 포함하는 일반적인 그리드를 보여줍니다.

![빠른 필터 정렬 및 세부 사항 부분이 포함된 일반적인 그리드](media/pfe-styles-align-grid.png "빠른 필터 정렬 및 세부 사항 부분이 포함된 일반적인 그리드")

Visual Studio에서는 다음 그림과 같은 구조를 사용하여 그리드, 세부 사항 부분 및 빠른 필터를 생성할 수 있습니다.

![그리드, 세부 사항 부분 및 빠른 필터를 정렬하는 일반적인 코드 구조입니다.](media/pfe-styles-header-code-structure2.png "그리드, 세부 사항 부분 및 빠른 필터를 정렬하는 일반적인 코드 구조입니다.")

## <a name="additional-resources"></a>추가 리소스

- [생산 현장 실행 인터페이스 사용자 지정](production-floor-execution-customize.md)
- [생산 현장 실행 인터페이스 설계](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
