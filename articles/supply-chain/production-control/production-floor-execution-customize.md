---
title: 생산 현장 실행 인터페이스 사용자 지정
description: 이 항목에서는 현재 양식을 확장하거나 생산 현장 실행 인터페이스에 대한 새 양식 및 버튼을 만드는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 67fb381cbef6f1673afcaa834666b4a859bdf4e6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449869"
---
# <a name="customize-the-production-floor-execution-interface"></a>생산 현장 실행 인터페이스 사용자 지정

[!include [banner](../includes/banner.md)]

개발자는 현재 양식을 확장하거나 생산 현장 실행 인터페이스에 대한 고유한 양식 및 버튼을 만들 수 있습니다. 이러한 새 요소에 대한 코드를 추가한 후 관리자 또는 작업 현장 관리자는 표준 구성 제어를 사용하여 인터페이스에 쉽게 추가할 수 있습니다.

예를 들어 기본 양식에 새 열이 필요한 경우 가능한 솔루션은 다음과 같습니다.

- `JmgProductionFloorExecutionMainGrid` 형식을 확장하고 원하는 필드를 추가합니다.
- 새 양식을 만들고 새 기본 보기(탭)로 추가합니다.

## <a name="add-a-new-button-action"></a>새 버튼 추가(액션)

새 버튼(액션)을 추가하려면 다음 단계에 따라 사용자 지정 작업을 구현하는 클래스를 만듭니다.

1. 다음에서 `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`이라는 새 클래스를 만듭니다.

    - `<ExtensionPrefix>`는 일반적으로 회사 이름을 사용하여 솔루션을 고유하게 식별합니다.
    - `<ActionName>`은 클래스의 고유한 이름입니다. 일반적으로 작업의 종류를 식별합니다.

1. 새 클래스는 `JmgProductionFloorExecutionAction` 클래스를 확장해야 합니다.
1. 필요한 모든 방법을 재정의합니다.

예를 들어 다음 클래스에 대한 코드를 살펴보세요.

- `JmgProductionFloorExecutionBreakAction` – 기록이 필요 없는 간단한 작업을 위한 클래스.
- `JmgProductionFloorExecutionReportFeedbackAction` – 보다 복잡한 기능을 제공하는 클래스입니다.

완료하면 새 버튼(액션)이 Microsoft Dynamics 365 Supply Chain Management의 **디자인 탭** 페이지에 자동으로 나열됩니다. 여기에서 표준 버튼을 추가할 수 있는 것처럼 사용자(또는 관리자 또는 현장 관리자)가 기본 또는 보조 도구 모음에 쉽게 추가할 수 있습니다. 지침은 [생산 현장 실행 인터페이스 설계](production-floor-execution-tabs.md)를 참조하세요.

## <a name="add-a-new-main-view"></a>새 기본 보기 추가

1. 원하는 요소 및 기능이 있는 새 양식을 만듭니다. 이 양식은 확장이 아닌 새 양식입니다. 다음에서 양식의 이름을 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`로 지정합니다.

    - `<ExtensionPrefix>`는 일반적으로 회사 이름을 사용하여 솔루션을 고유하게 식별합니다.
    - `<FormName>`은 양식의 고유한 이름입니다.

1. `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`이라는 메뉴 항목을 만듭니다.
1. 목록에 새 메뉴 항목을 추가하여 `getMainMenuItemsList` 메서드를 확장하는 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`이라는 확장을 만듭니다. 다음 코드는 예를 보여줍니다.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

완료하면 새 기본 보기가 Supply Chain Management의 **디자인 탭** 페이지에 있는 **기본 보기** 콤보 상자에 자동으로 나열됩니다. 여기에서 표준 보기를 추가할 수 있는 것처럼 사용자(또는 관리자 또는 현장 관리자)가 새 탭 또는 기존 탭에 쉽게 추가할 수 있습니다. 지침은 [생산 현장 실행 인터페이스 설계](production-floor-execution-tabs.md)를 참조하세요.

## <a name="add-a-details-view"></a>세부정보 보기 추가

1. 원하는 요소 및 기능이 있는 새 양식을 만듭니다. 이 양식은 확장이 아닌 새 양식입니다. 다음에서 양식의 이름을 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`로 지정합니다. 

    - `<ExtensionPrefix>`는 일반적으로 회사 이름을 사용하여 솔루션을 고유하게 식별합니다.
    - `<FormName>`은 양식의 고유한 이름입니다.

1. `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`이라는 메뉴 항목을 만듭니다.
1. 목록에 새 메뉴 항목을 추가하여 `getDetailsMenuItemList` 메서드를 확장하는 `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`이라는 확장을 만듭니다.

완료하면 새 세부 정보 보기가 Supply Chain Management의 **디자인 탭** 페이지에 있는 **세부 정보 보기** 콤보 상자에 자동으로 나열됩니다. 여기에서 세부 정보 보기를 추가할 수 있는 것처럼 사용자(또는 관리자 또는 현장 관리자)가 새 탭 또는 기존 탭에 쉽게 추가할 수 있습니다. 지침은 [생산 현장 실행 인터페이스 설계](production-floor-execution-tabs.md)를 참조하세요.

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>양식 또는 대화 상자에 숫자 키패드 추가

다음 예에서는 양식에 숫자 키패드를 추가하는 방법을 보여줍니다.

1. 각 양식에 포함된 숫자 키패드 컨트롤러의 수는 해당 양식의 숫자 키패드 수와 같아야 합니다.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. 각 숫자 키패드 컨트롤러의 동작을 설정하고 각 숫자 키패드 컨트롤러를 숫자 키패드 양식 파트에 연결합니다.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>숫자 키패드를 팝업 대화 상자로 사용

다음 예는 팝업 대화 상자에 대한 숫자 키패드 컨트롤러를 설정하는 한 가지 방법을 보여줍니다.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

다음 예는 숫자 키패드 팝업 대화 상자를 호출하는 한 가지 방법을 보여줍니다.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="additional-resources"></a>추가 리소스

- [생산 현장 실행 인터페이스 스타일 지정](production-floor-execution-styles.md)
- [생산 현장 실행 인터페이스 설계](production-floor-execution-tabs.md)
