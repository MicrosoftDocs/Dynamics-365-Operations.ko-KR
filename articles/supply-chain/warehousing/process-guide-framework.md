---
title: 프로세스 가이드 프레임워크
description: 이 항목은 X++에서 웨어하우스 모바일 프로세스를 확장하는 개발자를 위한 프로세스 가이드 프레임워크에 대한 정보를 제공합니다.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449527"
---
# <a name="process-guide-framework"></a>프로세스 가이드 프레임워크

[!include [banner](../includes/banner.md)]

이 항목은 X++에서 웨어하우스 모바일 프로세스를 확장하는 개발자를 위한 프로세스 가이드 프레임워크에 대한 정보를 제공합니다. 창고 모바일 프로세스는 프로세스가 작은 단계로 분할된 결과로 확장 가능합니다. 각 단계의 비즈니스 로직과 사용자 인터페이스 구축을 개별 클래스로 추출하여 확장성을 제공합니다.

## <a name="overview-of-the-existing-design"></a>기존 설계 개요

창고 모바일 실행 흐름은 단일 사용자 지정 서비스 엔드포인트를 통해 노출됩니다. 요청은 모바일 앱에서 제공되는 사용자 인터페이스의 메타데이터와 사용자가 입력한 값이 포함된 XML 문자열 형식으로 모바일 앱에서 도착합니다.

요청이 수신되면 첫 번째 단계는 이 XML을 역직렬화하는 것입니다. **WHSMobileAppServiceXMLTranslator** 클래스는 XML을 제어 정보와 세션 정보를 모두 포함하는 컨테이너로 변환합니다.

그런 다음 컨테이너의 정보를 사용하여 사용자가 작업 중이거나 시작하려고 하는 창고 프로세스(**WHSWorkExecuteMode** 열거로 표시됨)를 추론하고 **WHSWorkExecuteDisplay** 의 파생 클래스를 인스턴스화합니다. **displayform()** 메서드가 호출되면 다음을 수행합니다.

-   사용자의 데이터를 처리합니다(**WHSRFControlData** 클래스에 위임되지만 일부 프로세스는 **processControl()** 메서드를 재정의하여 특정 논리를 구현합니다).

-   비즈니스 로직을 실행합니다.

-   단계를 증가시킵니다.

-   새 사용자 인터페이스를 나타내는 컨테이너를 빌드합니다(일반적으로 **build…()** 메서드).

컨테이너는 그런 다음 XML을 직렬화하고 모바일 디바이스에 대한 응답으로 다시 전송하는 변환기로 반환됩니다.

다음 시퀀스 다이어그램은 실행 흐름의 개요를 보여줍니다. 다이어그램은 도식적인 개요에 가깝고 실제 코드를 1:1로 표현한 것이 아닙니다.

![프로세스의 개략도.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>재설계 사유

위의 디자인은 모바일 흐름에서 사용되는 프로세스를 구축하기 위한 매우 간단한 프레임워크를 제공합니다. 그러나 위에서 분명히 알 수 있듯이, **displayform()** 메서드는 여러 책임을 떠맡습니다. 다른 메서드와 클래스에 위임하지만, 구체적인 클래스 책임이 없으면 클래스 간에 일관되지 않은 방식으로 수행됩니다. 또한 지원되는 시나리오의 수가 유기적으로 증가함에 따라 이러한 클래스 중 일부는 상당히 복잡해질 수 있습니다. 문제를 더 흥미롭게 만들기 위해 이러한 클래스/메서드 중 일부는 재정의되어 여러 모드에서 재사용됩니다. 그 결과 순환 복잡성이 매우 높은 매우 긴 메서드가 생성됩니다. 이러한 문제는 과거에 유지 관리 문제를 제기했습니다. 이러한 메서드에서 버그를 해결하는 것은 위험하고 회귀하기 쉽습니다.
예를 들어, **WhsWorkExecuteDisplay** 클래스의 **processWorkLine()** 메서드는 여러 프로세스(기본적으로 작업 실행이 수행되는 모든 위치)에서 참조됩니다.

이를 확장 가능하게 만들기 위한 옵션 중 하나는 **displayForm** 메서드를 더 작은 메서드로 나누고 확장성 지점을 도입하는 것입니다. 그러나 시나리오 매트릭스로 인해 파트너가 확장을 작성하고 회귀에 대해 검증하는 것이 어려울 수 있습니다. 뿐만 아니라 위에서 언급한 구조화된 책임 분배가 없기 때문에 코드는 시간이 지남에 따라 예측할 수 없는 방식으로 계속 성장하여 품질 확장을 구축하는 데 어려움을 겪을 수 있습니다.

결과적으로 재설계는 독립적인 책임을 갖는 명확하게 정의된 클래스를 갖는 것을 목표로 지속 가능한 옵션입니다. 클래스에는 하나의 책임, 하나의 변경 이유, 하나의 확장 이유가 있어야 합니다.

## <a name="design-overview"></a>설계 개요

재설계된 프레임워크에서 핵심 전략은 두 가지 원칙을 중심으로 진행됩니다. 실행 흐름을 잘 정의된 책임이 있는 개별 구성 요소로 나누고 각 구성 요소에 확장 지점이 잘 정의되어 있습니다.

새 프레임워크의 이름은 "ProcessGuide"입니다. 이러한 클래스의 목적은 사용자가 데이터와 상호작용하는 방법이나 작업을 수행하는 순서에 있어 보다 유연한 형태 기반 경험인 리치 클라이언트와는 달리 비즈니스 프로세스를 통해 사용자를 안내하는 데 있기 때문입니다.

> [!NOTE]
> 한 가지 주목할 만한 세부 사항은 "WHS" 접두사를 의도적으로 생략한 것입니다. 모바일 프로세스는 초기에 창고용으로 도입되었지만 이후에는 다양한 생산 및 재고 관리 프로세스를 지원하기 위해 경계를 초월했습니다. 그 결과 창고 참조는 프레임워크 이름에서 제외되었습니다.

구성 요소를 식별하기 위한 첫 번째 단계는 생산 시작 프로세스(**WhsWorkExecuteDisplayProdStart** 클래스)를 찾는 것입니다. 다음은 프로세스의 개략도입니다.

![도식 프로세스의 이미지입니다.](media/production-start-process-schematic.png)

제어 흐름을 살펴보면 다음과 같은 구성 요소가 필요합니다.

-   전체 비즈니스 프로세스를 붙이는 컨트롤러.
-   프로세스의 단계 실행을 담당하는 단계입니다.
-   데이터를 단계적으로 처리하기 위한 데이터 프로세서입니다.
-   단계에 대한 사용자 인터페이스 빌드를 담당하는 페이지 빌더입니다.
-   단계 전환을 담당하는 탐색 에이전트입니다.
-   비즈니스 프로세스 실행을 담당하는 클래스입니다.

위의 프로세스 흐름도에서 1단계에서 시작하여 이전 단계의 데이터 처리를 시작한 다음 UI 빌드로 끝내면 데이터는 다음 단계에서 계속 처리됩니다. 이것은 연속적인 단계 사이에 긴밀한 결합을 도입하여 결과적으로 새로운 상위 수준 회로도는 다음과 같이 보일 것입니다.

![높은 수준의 도식 프로세스 이미지.](media/high-level-schematic.png)

다음은 재설계된 프로세스의 주요 구성 요소입니다.

-   **ProcessGuideController** - 이 클래스는 비즈니스 프로세스의 전체 실행을 조정합니다. 단계를 인스턴스화하는 팩토리와 이후에 프로세스 실행을 구성하는 탐색 에이전트 및 프로세스를 취소하거나 종료하기 위한 정리 논리를 정의합니다.

-   **ProcessGuideStep** - 이 클래스는 비즈니스 프로세스의 한 단계를 나타냅니다. 이 클래스에는 페이지 빌더, 작업 및 데이터 프로세서를 인스턴스화하고 올바른 순서로 호출하는 팩토리에 대한 정의가 포함되어 있습니다.

-   **ProcessGuideNavigationAgent** - 이 클래스는 단계 간의 탐색을 담당합니다. 단계가 완료되면 탐색 에이전트는 다음 단계를 정의하고 이전 단계에서 다음 단계로 통신하는 데 필요할 수 있는 매개 변수를 전달합니다.

-   **ProcessGuidePageBuilder** - 이 클래스는 사용자 인터페이스를 인스턴스화하는 역할을 합니다.

-   **ProcessGuideAction** - 이 클래스는 사용자에게 버튼으로 표시되는 작업을 나타냅니다.

-   **ProcessGuideDataProcessor** - 이 클래스는 사용자가 필드에 입력한 데이터를 처리하는 역할을 합니다.

## <a name="execution-flow"></a>실행 흐름

실행 흐름의 시작점은 변경되지 않은 상태로 유지됩니다. 따라서 요청은 여전히 동일한 끝점을 통해 도착한 다음 XML을 컨테이너로 역직렬화합니다. 이 컨테이너는 **getNextFormState()** 로 전달됩니다.

주의해야 할 세 가지 중요한 클래스가 있습니다.

-  **ProcessGuideSessionState** – 여기에는 세션 상태 정보(모드, 패스, 컨트롤러 및 실행 중인 단계 등)가 포함됩니다.

-  **ProcessGuidePage** – 여기에는 사용자 인터페이스 메타데이터의 강력한 형식 표현이 포함됩니다.

-  **ProcessGuideRequest** – 이것은 위의 두 가지를 구성원으로 포함하며 모바일 디바이스에서 수신된 요청의 강력한 형식 표현입니다.

이러한 클래스는 컨테이너 정보(상태 및 사용자 입력 제어 데이터 모두)를 사용하여 생성됩니다. 이는 값에 액세스하고 조작하는 형식이 안전한 방법을 제공합니다. 프로세스 동안 컨테이너에 반복적으로 액세스하는 것과 비교하여 가독성과 성능 면에서 모두 이점을 제공합니다.

세션 상태 정보는 올바른 **ProcessGuideController** 클래스의 인스턴스를 생성하는 데 사용됩니다. 일단 인스턴스화되면 **ProcessGuideController** 클래스의 **createResponse()** 메서드가 호출됩니다. 이 메서드는 프로세스 가이드 로직에 대한 진입점이며 실행 후에 응답과 함께 돌아옵니다(**ProcessGuideResponse** 클래스로 표시됨). 그런 다음 응답은 컨테이너로 다시 변환되고 레거시 논리로 다시 전달되며, 레거시 논리는 이를 XML로 직렬화하고 응답을 다시 모바일 디바이스로 보냅니다.

다음으로 컨트롤러는 실행할 다음 단계를 찾아야 합니다. 이것이 새 프로세스의 시작인 경우 컨트롤러는 **initialStep()** 을 호출하여 프로세스의 첫 번째 단계를 수행합니다. 그 후, **ProcessGuideStep** 에서 **execute()** 메서드를 호출합니다. 이 메서드는 **ProcessGuidePageBuilder** 클래스를 인스턴스화하고 **buildPage()** 를 호출하여, 사용자에게 표시될 사용자 인터페이스의 가상 표현인 **ProcessGuidePage** 개체를 반환합니다. 그런 다음 단계는 결과를 컨트롤러로 다시 보내고, 컨트롤러는 현재 세션 상태를 저장한 다음 결과를 다시 **ProcessGuideResponse** 클래스의 형태로 **getNextFormState()** 에 반환합니다. 그 후, 응답은 컨테이너로 다시 변환되고, 이후에 XML로 직렬화되고 응답을 모바일 디바이스로 다시 보냅니다.

다음 시퀀스 다이어그램은 이 제어 흐름을 설명합니다. 이것은 설계를 설명하기 위해 단순화된 가장 일반적인 제어 흐름입니다.

![제어 흐름이 간소화되었습니다.](media/control-flow.png)

사용자가 버튼을 클릭하여(또는 일반적으로 기본 작업을 트리거하는 값을 스캔하여) 모바일 디바이스에서 작업을 수행하면 요청이 같은 경로를 통해 **ProcessGuideController** 클래스의 **createResponse()** 메서드에 도착합니다. 그러나 이번에는 컨트롤러가 세션 상태 정보를 통해 사용자가 어느 단계에 있는지 알고 있습니다. 따라서 적절한 **ProcessGuideStep** 클래스를 인스턴스화하고 실행 메서드를 호출합니다. **ProcessGuideStep** 은 차례로 사용자가 호출한 작업 이름을 읽은 다음 적절한 **ProcessGuideAction** 클래스를 인스턴스화하고 **execute()** 를 호출합니다.

**ProcessGuideAction** 클래스는 특정 작업을 실행하는 책임이 있지만 두 가지 주목할만한 예외가 있습니다.

첫 번째는 **ProcessGuideOKAction** 클래스입니다. 이 작업은 사용자가 프로세스를 확인하고 진행하기를 원함을 의미합니다. 그에 따라 이 메서드는 실제로 ProcessGuideStep 클래스에 대한 콜백을 수행합니다. 즉, 이 단계는 **ProcessGuideDataProcessor** 에서 **processData()** 를 호출합니다. 이것은 사용자가 입력한 데이터를 처리한 후 단계의 상태를 업데이트하고 결과를 다시 컨트롤러로 보냅니다. 프로세서의 결과에 따라 단계는 페이지 빌더를 호출하여 적절한 사용자 인터페이스를 빌드하거나 단계의 상태를 완료된 것으로 설정합니다. 이는 아래 시퀀스 다이어그램의 위쪽 절반에 반영됩니다.

다른 예외는 취소 조치로, **ProcessGuideCancelResetProcessAction** 및 **ProcessGuideCancelExitProcessAction** 클래스에서 구현됩니다. 이러한 작업은 프로세스를 취소하고 프로세스 시작으로 돌아가거나 프로세스를 완전히 종료하려는 의도를 나타냅니다. **OK** 작업과 유사하게 이러한 작업은 **ProcessGuideController** 에 의도를 알리는 단계에 대한 콜백도 수행합니다. 그런 다음 컨트롤러는 상태 변수의 필요한 정리를 수행하고 제어를 프로세스의 초기 단계로 이동하거나 프로세스를 완전히 종료합니다.

단계가 완료된 후 단계의 상태가 **완료됨** 으로 설정되면 컨트롤러는 다음 단계의 이름을 반환하는 **ProcessGuideNavigationAgent** 를 인스턴스화합니다. 그런 다음 컨트롤러는 이 단계를 인스턴스화하고 **execute()** 메서드를 호출하고 사이클은 계속됩니다. 가장 일반적으로 새 단계는 해당 **ProcessGuidePageBuilder** 를 호출하여 사용자에게 표시될 다음 화면에 대한 사용자 인터페이스를 빌드한 다음 다시 전송됩니다. 이 흐름은 아래 시퀀스 다이어그램의 아래쪽 절반에 설명되어 있습니다.

![시퀀스 다이어그램.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>ProcessGuide 프레임워크를 사용하여 새 프로세스 빌드

제어 흐름을 설명하는 가장 좋은 방법은 응용 프로그램에 있는 예제인 생산 시작 프로세스를 사용하는 것입니다.

## <a name="overview-of-the-production-start-process"></a>생산 시작 프로세스 개요

프로세스 흐름을 이해하는 것부터 시작하겠습니다. 첫 번째 단계에서 사용자에게 생산 주문 ID를 입력하라는 메시지가 표시됩니다.

![프로덕션 ID를 묻는 메시지가 표시됩니다.](media/production-id-prompt.png)

사용자가 생산 주문 ID를 입력하면 주문 번호가 검증됩니다. 실행되는 일부 검증은 주문이 사용자가 로그인한 것과 동일한 창고에 있는지 여부와 주문 상태를 기반으로 합니다. 유효성 검사가 실패하면 사용자에게 오류 메시지가 표시됩니다. 유효성 검사가 성공하면 사용자에게 생산 주문 및 항목의 세부 정보가 표시됩니다.

사용자는 취소하여 프로세스 시작 부분으로 돌아가거나 **확인** 을 클릭하여 확인합니다. 후자의 경우 생산 주문이 **시작됨** 상태로 설정되고 해당 분개가 전기되고 제어가 첫 번째 단계로 다시 이동하고 "작업 완료" 메시지가 사용자에게 표시됩니다.


## <a name="creating-the-controller"></a>컨트롤러 만들기

비즈니스 프로세스를 구축하는 첫 번째 단계는 컨트롤러의 기본 동작을 구현하는 **ProcessGuideController** 추상 클래스에서 확장된 컨트롤러 클래스를 만드는 것입니다. 새 클래스 이름은 **ProdProcessGuideProductionStartController** 이며 **StartProdOrder** 의 **WHSWorkExecuteMode** 값으로 장식됩니다. **WHSWorkExecuteDisplay** 클래스에서 사용된 것과 동일한 **SysExtension** 기반 인스턴스화가 사용되어 사용자가 이 모드의 메뉴 항목을 실행할 때 컨트롤러를 인스턴스화하는 데 도움이 됩니다.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> 클래스의 명명 패턴은 **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller** 입니다. 이는 컨트롤러 클래스에 사용하고 다른 클래스로 확장하는 패턴입니다.


## <a name="building-the-first-step"></a>첫 번째 단계 구축

다음으로, **ProdProcessGuidePromptProductionIdStep** 클래스를 생성하는 첫 번째 단계를 정의하기 위해, **ProcessGuideStep** 에서 확장됩니다.

클래스를 인스턴스화하는 작업은 **ProcessGuideController** 기본 클래스에 의해 호출되는 단계 팩토리에 위임됩니다. 팩토리의 기본 구현은 이름을 기반으로 단계를 인스턴스화합니다. 따라서 **ProdProcessGuidePromptProductionIdStep** 을 컨트롤러의 첫 번째 단계로 인스턴스화하려면 두 가지 작업을 수행해야 합니다.

-   **ProcessGuideStepName** 특성으로 **ProdProcessGuidePromptProductionIdStep** 클래스를 장식합니다.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   컨트롤러 클래스에서 추상 메서드 **initialStepName()** 을 구현하여 단계 이름을 반환합니다.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> **ProcessGuideStepName** 특성의 값은 위에 표시된 것처럼 클래스 이름과 정확히 일치할 필요가 없습니다. 그러나 이를 구현하면 클래스를 사용할 때 상호 참조에 대한 균일성과 형식 안전성이 허용됩니다. 이 명명 규칙을 사용하는 것이 좋습니다.
>
> 단계의 **ProcessGuideStepName** 기반 인스턴스화는 **ProcessGuideStepDefaultFactory** 클래스에서 구현됩니다. 드문 경우지만 단계를 인스턴스화하기 위해 다른 전략을 원하는 경우 다음을 수행해야 합니다.
> -   **ProcessGuidStepAbstractFactory** 에서 상속하는 새 팩토리 클래스를 만듭니다.
> -   선택적으로 팩토리에서 필요로 하는 매개 변수를 포함하는 **ProcessGuideIStepCreationParameters** 인터페이스를 구현하는 새 매개변수 클래스를 만듭니다.
> -   컨트롤러 클래스에서 **stepFactory()** 및 **stepCreationParameters()** 메서드를 재정의하여 위의 팩토리 및 매개 변수를 반환합니다.

다음 단계는 **ProdProcessGuidePromptProductionIdStep** 클래스의 기능을 구현하는 것입니다. 사용자 인터페이스를 구축하고, 사용자가 입력한 데이터를 처리하고, 단계가 완료되는 시점을 결정하기 위한 논리를 구현해야 합니다.

### <a name="building-the-user-interface-for-the-first-step"></a>첫 번째 단계를 위한 사용자 인터페이스 구축

사용자 인터페이스는 **ProcessGuidePageBuilder** 추상 클래스에서 상속된 클래스를 사용하여 구축됩니다. 이 단계에서 클래스의 이름을 지정하여 역할을 나타내는 **ProdProcessGuidePromptProductionIdPageBuilder** 를 지정합니다.

클래스의 인스턴스화 메커니즘은 컨트롤러에서 단계가 인스턴스화되는 방식과 유사합니다. 

-   **ProcessGuidePageBuilderName** 특성으로 **ProdProcessGuidePromptProductionIdPageBuilder** 클래스를 장식합니다.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   **ProdProcessGuidePromptProductionIdStep** 클래스에서 추상 메서드 **pageBuilderName()** 을 구현하여 이 이름을 반환합니다.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> 단계 팩토리와 유사하게 페이지 빌더 팩토리에 대해 구현된 추상 팩토리 패턴도 있습니다. 따라서, 드문 경우지만 페이지 빌더를 인스턴스화하기 위해 다른 전략을 원하는 경우 다음을 수행할 수 있습니다.
> - **ProcessGuidePageBuilderAbstractFactory** 에서 상속하는 새 팩토리 클래스를 만듭니다.
> - 선택적으로 팩토리에서 필요로 하는 매개 변수를 포함하는 **ProcessGuideIPageBuilderCreationParameters** 인터페이스를 구현하는 새 매개변수 클래스를 만듭니다.
> - 단계 클래스에서 **pageBuilderFactory()** 및 **pageBuilderCreationParameters()** 메서드를 재정의하여 위의 팩토리 및 매개 변수를 반환합니다.

사용자 인터페이스를 구현하려면 생산 주문 ID를 입력하기 위한 하나의 텍스트 상자와 함께 **확인** 버튼 및 **취소** 버튼이 있는 페이지가 필요합니다. **취소** 버튼은 프로세스를 종료해야 합니다.

이를 구현하려면 **ProdProcessGuidePromptProductionIdPageBuilder** 클래스에서 두 가지 메서드를 재정의해야 합니다.

-   **addDataControls()** 메서드를 사용하여 텍스트 상자를 추가합니다.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   **addActionControls()** 메서드를 사용하여 **확인** 및 **취소** 버튼을 추가합니다.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

그러면 데이터 컨트롤이 추가되고 그 뒤에 버튼이 추가됩니다. 그러나 산재된 데이터 컨트롤과 버튼이 있는 화면을 구축하려는 경우 유연성을 위해 대신 **addControls()** 메서드를 재정의할 수 있습니다.

고려해야 할 추가 시나리오는 사용자가 잘못된 생산 주문 ID를 입력하는 경우와 같이 유효성 검사에 실패한 경우 페이지를 다시 작성하는 방법입니다. **ProcessGuidePageBuilder** 기본 클래스는 사용자 인터페이스를 다시 빌드하고 스캔한 값을 지우고 오류 메시지와 함께 오류 제어를 추가하는 기본 동작을 구현합니다. 이것은 사용하려는 기본 동작이므로 오류 처리를 위해 코드를 추가할 필요가 없습니다.

> [!TIP]
> 오류 상황에 대한 사용자 정의 UI 동작을 구현하려면 **rebuildFromRequestPage()**, **isErrorState()** 및 **reuseRequestPageOnError()** 메서드 중 하나 이상을 재정의할 수 있습니다.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>첫 번째 단계에서 사용자가 입력한 데이터 처리

데이터 처리는 **ProcessGuideDataProcessorDefault** 클래스에서 수행되며, 이 클래스는 레거시 **WhsRfControlData** 클래스를 차례로 호출합니다. 이 기본 동작을 변경할 필요가 없으며 **WhsRfControlData** 에는 이미 **ProdId** 필드를 검증하기 위한 논리가 있으므로 이를 처리하기 위한 논리를 작성할 필요가 없습니다. 유효성 검사 논리에 필요한 확장의 경우 **WhsControl** 기반 확장 메커니즘을 사용하는 것이 좋습니다.

### <a name="determine-if-the-first-step-is-complete"></a>첫 번째 단계가 완료되었는지 확인

유효성 검사가 성공하면 단계를 완료된 것으로 표시해야 합니다. 이것은 기본 클래스에서 수행되지만 단계 완료를 결정하기 위해 조건을 구현해야 합니다. 다음 재정의된 메서드가 이를 수행합니다.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>2단계: 주문 세부정보 보기 및 확인

프로세스의 두 번째 단계에서는 주문에 대한 세부 정보가 포함된 화면이 사용자에게 표시됩니다. 사용자는 **확인** 버튼을 클릭하여 생산 주문의 시작을 확인하거나 **취소** 를 클릭하여 프로세스 시작으로 돌아갈 수 있습니다. 이 예의 경우 단계 이름을 **ProdProcessGuideConfirmProductionOrderStep** 으로 지정하고 페이지 빌더 클래스의 이름을 **ProdProcessGuideConfirmProductionOrderPageBuilder** 로 지정합니다.

ProdProcessGuideConfirmProductionOrderStep 클래스는 다음과 같습니다.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

사용자가 여기에 값을 입력하지 않기 때문에 **isComplete()** 메서드를 재정의할 필요가 없습니다. 사용자가 **확인** 을 클릭하면 단계가 완료됩니다.

페이지 빌더 클래스는 **addDataControls()** 메서드를 재정의하여 세 개의 레이블을 추가합니다. 첫 번째 레이블에는 생산 주문 ID가 표시되고 두 번째 레이블에는 항목 정보(예: 항목 ID, 치수 또는 설명)가 포함되며 세 번째 레이블에는 수량 및 측정 단위가 포함됩니다.

그런 다음 **addActionControls()** 를 재정의하여 **확인** 버튼과 **취소** 버튼 2개를 추가하여 프로세스를 취소하고 프로세스의 시작으로 돌아갑니다.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> 응용 프로그램 탐색기를 사용하여 이 항목에서 X++ 메서드에 대한 동일한 소스 코드를 찾을 수 있습니다. 클래스 이름을 필터링한 다음 클래스 이름을 마우스 오른쪽 버튼으로 클릭하고 **코드 보기** 를 선택합니다.

### <a name="step-3-start-the-production-order"></a>3단계: 생산 주문 시작

세 번째 단계는 생산 주문을 시작하는 비즈니스 로직이 실행되는 곳입니다. 이 단계는 사용자 인터페이스가 없다는 점에서 이전 단계와 다소 다릅니다. 이 단계는 사용자가 이전 단계에서 **확인** 을 클릭하면 자동으로 실행됩니다.

**ProcessGuideStepWithoutPrompt** 추상 클래스는 이러한 단계에 대한 기본 동작을 구현합니다. 따라서 현재 단계는 **ProcessGuideStepWithoutPrompt** 클래스를 확장하고 **doExecute()** 메서드를 재정의해야 합니다.

다음 코드 예제는 클래스와 **doExecute()** 메서드 구현을 보여줍니다. 이 메서드는 세션 상태에서 주문 ID와 사용자 ID를 검색하고 이 생산 주문을 시작하기 위해 메서드를 호출합니다.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

예외의 경우 프레임워크 예외 처리 논리는 프로세스가 이전 단계로 롤백되도록 합니다.

> [!NOTE]
> **addProcessCompletionMessage()** 를 호출하면 탐색 매개 변수에 "작업 완료" 메시지가 추가됩니다. 다음 단계(사용자 인터페이스가 있다고 가정)에서 이 메시지를 표시합니다. 기본 클래스는 이 논리를 처리하며 이 동작을 달성하기 위해 프로세스 클래스에 특정 코드를 추가할 필요가 없습니다.


### <a name="building-the-navigation-through-the-steps"></a>단계를 통해 탐색 빌드

**ProcessGuideController** 기본 클래스는 소스 및 대상 단계의 간단한 맵인 미리 정의된 탐색 경로에 의존하는 **ProcessGuideNavigationAgentDefault** 클래스를 인스턴스화합니다. 프로덕션 시작 시나리오의 경우 조건부 분기가 없으므로 이 구현으로 충분합니다. 따라서 **initializeNavigationRoute()** 메서드를 재정의하기만 하면 탐색 경로를 정의할 수 있습니다.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

조건부 분기가 있는 프로세스가 있습니다(사용자 작업 또는 기타 조건을 기반으로 함). 이러한 프로세스는 다음을 수행해야 합니다.

-   **ProcessGuideNavigationAgent** 클래스에서 상속된 특정 탐색 에이전트를 구현합니다.

-   현재 단계, 세션 상태, 사용자 작업 또는 기타 논리를 기반으로 올바른 탐색 에이전트를 인스턴스화하는 논리가 포함된 **ProcessGuideNavigationAgentAbstractFactory** 클래스에서 상속된 특정 탐색 에이전트 팩토리를 구현합니다.

-   선택적으로 컨트롤러 클래스에서 **navigationAgentCreationParameters()** 를 재정의하여 적절한 매개 변수를 전달합니다.

-   컨트롤러에서 **navigationAgentFactory()** 를 재정의하여 위에서 만든 탐색 에이전트 팩토리를 인스턴스화합니다.

### <a name="action-classes"></a>작업 클래스

작업 클래스는 사용자 작업을 나타내므로 이 예에서는 **확인** 작업을 사용하여 작업이 생성되는 방식을 보여줍니다.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

클래스는 2개의 추상 메서드를 구현해야 합니다.

-   **label()**, 이 작업에 연결된 버튼 컨트롤에 표시할 레이블을 반환합니다.

-   **doExecute()**, 작업을 수행합니다. 앞서 언급했듯이, **확인** 버튼은 단순히 단계에 대한 콜백을 수행합니다. 그러나 다른 작업은 여기에서 더 복잡한 논리를 가질 수 있습니다.

작업은 **ProcessGuideActionName** 특성을 기반으로 하는 **SysExtension** 프레임워크를 사용하여 인스턴스화됩니다. 페이지 빌더의 인스턴스화와 유사하게 단계 클래스는 기본 작업 팩토리를 구현하며 이를 재정의할 수 있습니다. 페이지 빌더는 이와 같은 버튼 컨트롤을 추가합니다.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

그렇게 하면 전달된 이름에 대한 작업 클래스를 생성하도록 단계를 요청하고 해당 작업을 버튼에 연결합니다.

### <a name="summary"></a>요약

이 항목에서 설명한 모든 내용을 요약하기 위해 다음은 프로세스에 필요한 코드에 대한 포괄적인 요약입니다.

1.  **ProdProcessGuideProductionStartController**

    1.  **initialStepName()** 을 재정의하여 첫 번째 단계의 이름을 제공합니다.
    2.  **initializeNavigationRoute()** 를 재정의하여 탐색 지도를 구성합니다.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  **isComplete()** 를 재정의하여 단계가 완료된 것으로 간주되는 시점을 지정합니다.
    2.  **pageBuilderName()** 을 재정의하여 사용할 페이지 빌더를 지정합니다.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  **addDataControls()** 를 재정의하여 **제품 ID** 텍스트 상자를 추가합니다.
    2.  **addActionControls()** 를 재정의하여 **확인** 및 **취소** 버튼을 추가합니다.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  **pageBuilderName()** 을 재정의하여 사용할 페이지 빌더를 지정합니다.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  **addDataControls()** 를 재정의하여 주문, 항목 및 수량 정보 레이블을 추가합니다.

    2.  **addActionControls()** 를 재정의하여 **확인** 및 **취소** 버튼을 추가합니다.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > 항목 정보 레이블을 생성하는 데 사용되는 **generateItemInfoForProdId()** 메서드는 이 항목에서 제외됩니다. 이 메서드는 항목 ID, 설명 및 차원을 가져오기 위해 몇 가지 테이블을 쿼리합니다. **generateItemInfoForProdId()** 를 더 잘 이해하려면 소스 코드를 살펴보십시오.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  **doExecute()** 를 재정의하여 생산 시작 프로세스를 수행하고 프로세스 완료 메시지를 추가합니다.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> 많은 공통 패턴(오류 시 UI 재생성, 프로세스 완료 메시지 설정, **확인** 및 **취소** 동작)이 프레임워크로 이동되었습니다. 따라서 응용 프로그램 개발자가 오류가 발생하기 쉽고 프로세스 전반에 걸쳐 일관되지 않은 동작의 위험이 있는 상용구 코드를 작성하지 않아도 됩니다. 그러나 시나리오가 공통 경로에서 벗어나야 하는 경우 응용 프로그램 개발자에게 적절한 방법을 재정의할 수 있는 옵션이 제공되지만 이는 명시적이고 추적 가능한 의도적인 편차입니다.


### <a name="extending-a-business-process"></a>비즈니스 프로세스 확장

지금까지 이 항목에서는 **ProcessGuide** 프레임워크를 사용하여 새 프로세스를 빌드하는 방법을 강조했습니다. 이 마지막 섹션에서는 이 비즈니스 프로세스를 확장하는 방법에 대한 몇 가지 예를 찾을 수 있습니다.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>흐름에 단계 추가(ProcessGuideNavigationAgentDefault 사용)

확장할 곳:

-   프로세스에 대한 **ProcessGuideController** 클래스의 자식입니다.

확장 방법:

-   컨트롤러 클래스에서 **initializeNavigationRoute()** 메서드를 확장하고 **ProcessGuideNavigationRoute** 클래스에서 **addFollowingStep()** 을 호출합니다.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>흐름에 단계 추가(사용자 지정 탐색 에이전트 사용)

확장할 곳:

-   **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent** 의 자식.

확장 방법:

-   원하는 단계 이름을 반환하는 **ProcessGuideNavigationAgent** 의 새 하위 클래스를 만듭니다.

-   위에서 만든 탐색 에이전트를 조건부로 반환하는 **ProcessGuideNavigationAgentFactory** 에서 파생된 새 클래스를 만듭니다.

-   컨트롤러 클래스에서 **navigationAgentFactory()** 메서드를 확장하여 위에서 만든 팩토리를 반환합니다.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>기존 단계의 UI에 새 컨트롤 추가 

확장할 곳:

-   단계에 대한 **ProdProcessGuidePageBuilder** 의 자식.

확장 방법:

-   **addDataControls()** 메서드를 확장하고 추가 컨트롤을 추가합니다.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>기존 단계에서 사용자 인터페이스의 완전한 점검

확장할 곳:

-   **ProdProcessGuideStep** 의 자식.

확장 방법:

-   **ProdProcessGuidePageBuilder** 클래스의 새 하위 클래스를 만들고 원하는 사용자 인터페이스를 구현합니다.

-   단계 클래스에서 **pageBuildeName()** 메서드를 확장하여 위에서 만든 클래스의 **ProcessGuidePageBuilderNameAttribute** 를 반환합니다.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>단계가 완료된 것으로 간주되면 로직 변경

확장할 곳:

-   **ProdProcessGuideStep** 의 자식.

확장 방법:

-   **isComplete()** 메서드를 확장하여 추가 논리를 구축합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]