---
title: 다음에서 캔버스 앱 포함 Power Apps
description: 이번에는 제품의 함수를 보강하기 위해 에서 캔버스 앱을 Microsoft Power Apps 클라이언트에 포함하는 방법에 대해 설명합니다.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: c2f7b660d364be6e62d484e67908201027190a8a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460632"
---
# <a name="embed-canvas-apps-from-power-apps"></a>다음에서 캔버스 앱 포함 Power Apps

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Microsoft Power Apps 개발자와 비기술적 사용자가 코드를 작성하지 않고도 모바일 장치, 태블릿 및 웹용 맞춤형 비즈니스 앱을 구축할 수 있는 서비스입니다. 재무 및 운영 앱은 Power Apps. 귀하, 귀하의 조직 또는 광범위한 에코시스템이 개발하는 캔버스 앱을 재무 및 운영 앱에 포함하여 제품 함수를 보강할 수 있습니다. 예를 들어 다른 시스템에서 검색한 정보로 재무 및 운영 앱을 보완하기 위해 Power Apps 캔버스 앱을 빌드할 수 있습니다.

캔버스 앱 포함에 대해 자세히 알아보려면 [캔버스 앱을 포함하는 방법](https://www.youtube.com/watch?v=x3qyA1bH-NY) 비디오를 시청하십시오.

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Power Apps에서 페이지에 포함된 캔버스 앱 추가

캔버스 앱을 클라이언트에 포함하기 전에 Power Apps 원하는 비주얼 또는 함수가 있는 앱을 찾거나 빌드해야 합니다. 이 항목에는 앱 빌드 프로세스에 대한 자세한 설명이 포함되어 있지 않습니다. Power Apps를 처음 사용하는 경우 [Power Apps 설명서](/powerapps/)를 참조하십시오.

재무 및 운영 앱에 캔버스 앱을 포함하는 세 가지 방법이 있습니다. 시나리오에 가장 적합한 접근 방식을 사용할 수 있습니다. 

- 페이지의 표준 작업 창에 있는 **Power Apps** 버튼에 캔버스 앱을 포함합니다. 이러한 방식으로 추가한 앱은 메뉴 **Power Apps** 버튼에 항목으로 표시되고 앱은 측면 창에서 열립니다. 
- 새 탭 페이지(피벗 탭, FastTab, 블레이드 또는 작업 영역 섹션)로 기존 페이지에 캔버스 앱을 직접 포함합니다.
- 대시보드에서 캔버스 앱에 대한 새로운 전체 페이지 환경을 만듭니다.

포함된 캔버스 앱을 구성할 때 앱에 컨텍스트로 보낼 단일 필드를 선택할 수 있습니다. 이 단계를 수행하면 현재 보고 있는 데이터를 기반으로 앱이 응답할 수 있습니다.

> [!NOTE]
> 이 메커니즘을 사용하여 모델 기반 앱을 포함할 수 없습니다.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>기존 페이지에 캔버스 앱 포함

다음 절차에서는 Power Apps의 기존 페이지에 캔버스 앱을 포함하는 방법을 보여줍니다.

1. 캔버스 앱을 포함할 페이지로 이동합니다. 이 페이지에는 앱에 입력으로 전달해야 하는 모든 데이터가 포함됩니다.
2. **Power Apps에서 앱 추가 창** 을 엽니다.

    - 앱이 페이지에 직접 포함되는 경우 **옵션** \> **이 페이지 개인화** \> **더 보기** 를 선택한 후 다음 단계 중 하나를 따릅니다.

        - **전체 페이지 앱** 기능이 켜져 있는 경우 **페이지 추가** 를 선택한 다음 앱을 추가할 지역을 선택합니다. **Power Apps** 메뉴 버튼에 앱을 포함하려면 작업 창을 선택합니다. 앱을 페이지에 직접 포함하려면 적절한 탭, FastTab, 블레이드 또는 섹션(작업 영역에 있는 경우)을 선택합니다. 이후 **앱 추가** 창에서 **Power Apps** 을 선택합니다.
        - **전체 페이지 앱** 기능이 꺼져 있는 경우 **Power Apps에서 앱 추가** 를 선택한 다음 앱을 추가할 지역을 선택합니다. **Power Apps** 메뉴 버튼에 앱을 포함하려면 작업 창을 선택합니다. 앱을 페이지에 직접 포함하려면 적절한 탭, FastTab, 블레이드 또는 섹션(작업 영역에 있는 경우)을 선택합니다.

    - **Power Apps** 메뉴 버튼을 사용하여 앱에 액세스하는 경우 표준 작업 창에서 **Power Apps** 메뉴 버튼을 선택한 다음 **앱 추가** 를 선택할 수 있습니다.

3. 포함된 앱을 구성합니다. 자세한 내용은 이 항목 뒷부분의 [캔버스 앱 구성](#configuring-a-canvas-app) 섹션을 참조하십시오.
4. 구성이 올바른지 확인한 후 **삽입** 을 선택합니다.

    - **저장된 보기** 기능이 꺼져 있는 경우 포함된 앱을 보려면 브라우저를 새로 고치라는 메시지가 표시됩니다.
    - **저장된 보기** 기능이 켜져 있는 경우 변경 사항을 유지하려면 보기를 저장해야 합니다.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>대시보드에서 전체 페이지 환경으로 캔버스 앱 포함

앱이 기존 페이지와 관련이 없거나 앱을 재무 및 운영 앱 내에서 전체 페이지 환경으로 표시하려는 경우 대시보드에서 캔버스 앱을 포함할 수 있습니다.

> [!NOTE]
> 이 기능을 사용 가능하게 하려면 기능 관리에서 **전체 페이지 앱** 기능을 켜야 합니다. 

1. 대시보드를 엽니다.
2. 페이지를 길게 선택(또는 마우스 오른쪽 버튼으로 클릭)하고 **개인 설정** 을 선택한 다음 **페이지 추가** 를 선택합니다.
3. **페이지 추가** 창에서 **Power Apps** 을 선택합니다.
4. 포함된 앱을 구성합니다. 자세한 내용은 이 항목 뒷부분의 [캔버스 앱 구성](#configuring-a-canvas-app) 섹션을 참조하십시오.
5. **저장** 을 선택하여 앱을 대시보드에 새 타일로 추가합니다.
6. 대시보드에서 새 타일을 선택하고 캔버스 앱이 예상대로 나타나는지 확인합니다.

### <a name="configuring-a-canvas-app"></a>캔버스 앱 구성

캔버스 앱을 포함할 때 다음 매개 변수를 설정해야 합니다.

- **이름** – 포함된 앱을 포함할 버튼이나 탭에 표시할 텍스트를 입력합니다. 종종 이 필드에서 앱 이름을 반복할 수 있습니다.
- **앱 ID** – 포함하려는 캔버스 앱의 GUID(Globally Unique Identifier)를 지정합니다. 이 값을 검색하려면 [make.powerapps.com](https://make.powerapps.com)에서 앱을 찾은 다음 **세부 정보** 에서 **앱 ID** 필드를 찾습니다.
- **앱에 대한 입력 컨텍스트** – 앱에 입력으로 전달할 데이터가 포함된 필드를 선택적으로 선택할 수 있습니다. 앱이 재무 및 운영 앱에서 보낸 데이터에 액세스하는 방법에 대한 자세한 내용은 이 항목 뒷부분의 [재무 및 운영 앱에서 보낸 데이터를 활용하는 앱 빌드](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) 섹션을 참조하십시오.

    버전 10.0.19부터 현재 법인도 **cmp** URL 매개 변수를 통해 컨텍스트로 캔버스 앱에 전달됩니다. 이 동작은 해당 앱이 해당 정보를 사용할 때까지 대상 캔버스 앱에 영향을 주지 않습니다.

- **애플리케이션 크기** – 포함할 앱 유형을 선택합니다. 모바일 장치용으로 제작된 앱의 경우 **Thin** 을 선택하거나 태블릿용으로 제작된 앱의 경우 **Wid** e를 선택합니다. 이 매개 변수는 포함된 앱에 충분한 공간이 할당되도록 합니다.
- **법인** – 앱을 사용할 수 있는 법인을 선택할 수 있습니다. 기본적으로 앱은 모든 법인에서 사용할 수 있습니다. 이 옵션은 기존 페이지에 직접 포함하고 **[저장된 보기](saved-views.md)** 기능이 꺼져 있는 경우에만 사용할 수 있습니다.

## <a name="sharing-an-embedded-app"></a>포함된 앱 공유

페이지에 캔버스 앱을 포함하고 올바르게 작동하는지 확인한 후 시스템의 다른 사용자와 앱을 공유할 수 있습니다. 포함된 캔버스 앱을 공유하려면 다음 단계를 따르십시오.

1. [Power Apps 캔버스 앱을 적절한 사용자와 공유](/powerapps/maker/canvas-apps/share-app)하여 Power Apps에서 직접 앱에 액세스할 수 있도록 합니다.
2. 임베디드 앱과 관련된 개인화를 원하는 사용자와 공유하십시오. 다음 방법 중 하나를 사용할 수 있습니다.

    - **보기 게시(권장):** **[저장된 보기](saved-views.md)** 기능이 켜져 있는 경우 권장되고 선호되는 접근 방식은 포함된 캔버스 앱이 포함된 보기를 만든 다음 해당 보기를 원하는 사용자에게 게시하는 것입니다. 이 접근 방식을 사용하면 게시된 보기의 대상이 되는 보안 역할이 있는 모든 사용자가 페이지에서 캔버스 앱을 볼 수 있습니다.

        대시보드에서 전체 페이지 환경으로 포함된 캔버스 앱을 게시할 수도 있습니다. 대시보드에서 앱과 연결된 타일을 길게 선택(또는 마우스 오른쪽 버튼으로 클릭)하고 **개인 설정** 을 선택한 다음 페이지 **게시** 를 선택합니다. *게시 보기* 환경과 유사한 환경이 표시되며 게시할 보안 역할을 선택할 수 있습니다. 업데이트 10.0.21 이상에서 **저장된 보기 기능에 대한 향상된 법인 지원이 켜져 있는 경우** 원하는 법인에 앱을 게시할 수도 있습니다.

    - **저장된 보기** 기능이 꺼져 있는 경우 시스템 관리자는 개인화 페이지를 통해 캔버스 앱을 포함하는 **개인화** 를 적절한 사용자 집합에 제공할 수 있습니다. 또는 페이지의 개인 설정을 내보낸 다음 한 명 이상의 사용자에게 보낼 수 있습니다. 이후 각 사용자는 개인화를 가져올 수 있습니다. 개인화 도구 모음에는 개인화를 내보내고 가져올 수 있는 버튼이 있습니다.

> [!NOTE]
> 캔버스 앱이 외부 사용자와 공유된 경우 해당 사용자는 재무 및 운영 앱 내부에 포함된 앱을 사용할 수 없습니다. 그러나 Power Apps에서 직접 앱에 액세스할 수 있습니다. 외부 사용자에는 Finance and Operations 앱이 배포된 Microsoft 365 Azure Directory에 속하지 않는 게스트 및 사용자가 포함됩니다.

제품의 개인화 기능 및 사용 방법에 대한 자세한 내용은 [사용자 경험 개인화](personalize-user-experience.md)를 참조하십시오.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>재무 및 운영 앱에서 보낸 데이터를 사용하는 캔버스 앱 빌드

재무 및 운영 앱에 포함될 캔버스 앱을 빌드할 때 프로세스의 중요한 부분 중 하나는 해당 재무 및 운영 앱의 입력 데이터를 사용하는 것입니다. Power Apps 개발 경험에서 재무 및 운영 앱에서 전달된 입력 데이터는 **Param('EntityId')** 변수를 사용하여 액세스할 수 있습니다. 또한 버전 10.0.19부터 현재 법인도 **Param('cmp')** 변수를 통해 캔버스 앱에 전달됩니다. 

예를 들어 앱의 OnStart 함수에서 재무 및 운영 앱의 입력 데이터를 다음과 같은 변수로 설정할 수 있습니다.

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>캔버스 앱 보기

재무 및 운영 앱의 페이지에 포함된 캔버스 앱을 보려면 포함된 앱이 있는 페이지로 이동하면 됩니다. 표준 작업 창의 **Power Apps** 버튼을 사용하여 앱에 액세스할 수 있음을 기억하십시오. 또는 새 탭, FastTab 또는 블레이드로 페이지에 직접 표시되거나 작업 영역의 새 섹션으로 표시될 수 있습니다. 사용자가 페이지에서 앱을 처음 로드하려고 하면 로그인하라는 메시지가 표시됩니다. 이 단계에서는 사용자에게 앱을 사용할 수 있는 적절한 권한이 있는지 확인합니다.

## <a name="editing-an-embedded-app"></a>포함된 앱 편집

앱이 페이지에 포함된 후 앱 구성을 일부 변경해야 할 수 있습니다. 예를 들어 포함된 앱과 연결된 레이블을 수정하려고 하거나 앱의 새 버전이 생성되었으며 최신 버전을 가리키도록 앱 ID를 업데이트해야 할 수 있습니다.

포함된 앱의 구성을 편집하려면 다음 단계를 따르십시오.

1. **앱 편집** 창으로 이동합니다.

    - 내장된 앱이 Power Apps 메뉴 버튼을 통해 액세스되는 경우 Power Apps 메뉴 버튼을 길게 선택(또는 마우스 오른쪽 버튼 클릭)하고 **개인화** 를 선택합니다. **앱 선택** 드롭다운 메뉴에서 구성할 앱을 선택합니다.
    - 포함된 앱이 페이지에 직접 표시되는 경우 **옵션** 을 선택한 다음 이 페이지 **개인화** 를 선택합니다. **선택** 도구를 사용하여 포함된 앱을 클릭합니다.
    - 포함된 앱이 대시보드에서 추가된 경우 대시보드를 열고 캔버스 앱과 연결된 타일을 길게 선택(또는 마우스 오른쪽 버튼으로 클릭)하고 **개인화** 를 선택한 다음 **페이지 편집** 을 선택합니다.

2. 앱 구성을 필요한 대로 수정한 다음 **저장** 을 클릭합니다.

## <a name="removing-an-app"></a>앱 제거

앱이 페이지에 삽입된 후 필요한 경우 제거하는 몇 가지 방법이 있습니다.

- 이 항목 앞부분에 있는 포함된 **앱 편집** 섹션의 지침을 사용하여 [앱 편집 창으로 이동](#editing-an-embedded-app)합니다. 제거하려는 포함된 앱에 대한 정보가 창에 표시되는지 확인한 다음 **삭제** 버튼을 클릭합니다.
- 포함된 앱이 대시보드에서 추가된 경우 대시보드를 열고 캔버스 앱과 연결된 타일을 길게 선택(또는 마우스 오른쪽 버튼으로 클릭)하고 **개인 설정** 을 선택한 다음 **페이지 제거** 를 선택합니다. 
- 포함된 앱은 개인화 데이터로 저장되기 때문에 페이지의 개인화를 지우면 해당 페이지에 포함된 모든 앱도 제거됩니다. 페이지의 개인 설정을 지우는 것은 영구적이며 취소할 수 없습니다. 페이지에서 개인 설정을 제거하려면 **옵션**, **이 페이지 개인 설정**, 마지막으로 **지우기** 버튼을 차례로 선택합니다. 브라우저를 새로고침하면 이 페이지에 대한 이전 개인 설정이 모두 제거됩니다. 개인화를 사용하여 페이지를 최적화하는 방법에 대한 자세한 내용은 [사용자 경험 개인화](personalize-user-experience.md)를 참조하십시오.

## <a name="appendix"></a>부록

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[개발자] 폼에 캔버스 앱 모델링

이번에는 개인화를 통해 캔버스 앱을 포함하는 데 중점을 두고 있지만 개발자는 Visual Studio 개발 환경을 사용하여 양식에 캔버스 앱을 추가할 수도 있습니다. 이렇게 하려면 PowerAppsHostControl을 양식에 추가하기만 하면 됩니다. 컨트롤에서 사용할 수 있는 메타데이터 속성은 개인화 경험과 동일한 기능을 제공합니다.

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[개발자] 앱을 삽입할 수 있는 위치 지정

기본적으로 사용자는 Power Apps 메뉴 버튼 아래 또는 페이지에 탭, FastTab, 블레이드 또는 작업 영역의 새 섹션으로 직접 앱을 포함할 수 있습니다. 그러나 필요한 경우 개발자는 다음 방법을 구현하여 특정 페이지에만 앱을 포함할 수 있도록 이 기능을 구성할 수도 있습니다.

- **isPowerAppPersonalizationEnabled** – 이 메서드가 특정 페이지에 대해 false를 반환하면 Power Apps 메뉴 버튼이 표시되지 않으며 사용자는 탭을 포함하여 이 페이지의 어디에도 앱을 포함할 수 없습니다.
- **isPowerAppTabPersonalizationEnabled** – 이 메서드가 특정 페이지에 대해 false를 반환하면 사용자는 페이지에 탭, FastTab 또는 파노라마 섹션으로 앱을 직접 포함할 수 없습니다. 페이지에서 포함이 허용된 경우 사용자는 Power Apps 메뉴 버튼을 통해 앱을 계속 포함할 수 있습니다.

다음 예시에서는 앱을 포함할 수 있는 위치를 구성하는 데 필요한 두 가지 메서드가 있는 새 클래스를 보여줍니다.

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
