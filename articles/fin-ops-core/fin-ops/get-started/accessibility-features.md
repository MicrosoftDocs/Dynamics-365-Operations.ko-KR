---
title: 접근성 기능
description: 이번에는 다양한 장애가 있는 사용자를 돕기 위해 설계된 함수에 대해 설명합니다.
author: TLeforMicrosoft
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 022c51f7050d11caf5ce67c5df8f9f9040a54b98
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460609"
---
# <a name="accessibility-features"></a>접근성 기능

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이번에는 다양한 장애가 있는 사용자가 이 앱을 사용할 수 있도록 설계된 함수에 대해 설명합니다. 예를 들어 Microsoft Windows 내레이터와 같은 시각 보조 기술을 사용하는 사람들을 위한 기능이 있습니다.

## <a name="windows-narrator-and-keyboard-only-access"></a>Windows 내레이터 및 키보드 전용 액세스

모든 필드와 컨트롤에는 레이블과 적용 가능한 바로 가기에 대한 설명이 있습니다. 스크린 리더는 레이블과 설명을 읽을 수 있습니다.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>가장 자주 수행되는 작업에 대한 바로 가기

대부분의 사용자에게 일상적인 시스템 사용에는 많은 데이터 입력과 키보드 상호 작용이 포함됩니다. 사용자 경험을 향상시키기 위해 화면에서 '점프'하는 데 도움이 되는 바로 가기와 특수 작업에 대한 바로 가기를 만들었습니다. 자세한 내용은 [키보드 단축키](shortcut-keys.md)를 참조하십시오.

## <a name="navigation-search"></a>탐색 검색

가장 왼쪽 창인 탐색 창 메뉴를 사용하여 액세스하는 모든 페이지는 **검색** 상자에서도 사용할 수 있습니다. Alt+G를 눌러 포커스를 **검색** 상자로 이동한 다음 페이지의 이름이나 설명을 입력합니다.

![검색창에 입력한 은행 계좌](media/6d08b0be32808221023e2aa92d69fd70.png "검색창에 입력한 '은행 계좌'")

자세한 내용은 [탐색 검색](navigation-search.md)을 참조하십시오.

> [!NOTE]
> 최상위 페이지로만 직접 이동할 수 있습니다. 보조 페이지는 상위 페이지의 정보 또는 컨텍스트에 의존합니다.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>키보드 전용 사용자 또는 헤드다운 데이터 입력에 대한 작업 검색

페이지에서 제공되는 모든 작업은 탭 시퀀스를 통해 키보드에서 액세스할 수 있습니다. 탭 순서에 대한 정보는 이 항목의 뒷부분에서 제공됩니다. 작업을 보다 직접 실행하려면 작업 검색 함수를 사용할 수 있습니다.

### <a name="example"></a>예시

작업 창의 **판매 주문** 탭에 있는 **이메일 알림** 그룹에 나타나는 **이메일 알림 로그** 작업을 실행하려고 합니다.

![작업 창에서 이메일 알림 로그 작업.](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "작업 창의 '이메일 알림 로그' 작업")

한 가지 옵션은 키보드를 사용하는 것입니다. Ctrl+F6을 눌러 포커스를 작업 창으로 이동한 다음 Tab 키를 반복해서 눌러 **전자 메일 알림 로그** 작업에 포커스가 있을 때까지 모든 탭과 작업을 이동합니다.

그러나 작업을 더 직접 실행할 수도 있습니다. 페이지의 아무 곳에서나 Ctrl+아포스트로피(')를 눌러 작업에 대한 검색 상자를 표시합니다.

![작업 검색 상자.](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "작업 검색창")

검색 상자에 작업을 설명하는 단어를 입력합니다. 작업을 사용할 수 있으며 직접 실행할 수 있습니다. 예를 들어 **이메일**, **알림**(단어 일부) 또는 **로그** 를 입력하여 이메일 알림 로그 함수로 '이동'할 수 있습니다.

![검색창에 입력한 이메일](media/image4.png "검색창에 입력한 '이메일'")

![검색창에 입력된 알림](media/image5.png "검색창에 '통지' 입력")

![검색창에 입력한 로그](media/image6.png "검색창에 입력한 '로그'")

작업을 마치면 Ctrl+아포스트로피를 다시 눌러 작업 검색을 실행하기 전에 작업하고 있던 필드로 포커스를 되돌릴 수 있습니다.

자세한 내용은 [작업 검색](action-search.md)을 참조하십시오.

## <a name="tab-sequence"></a>탭 순서

일상적인 시스템 사용에서 일반적인 작업을 수행하기 위해 모든 필드가 필요한 것은 아닙니다. 따라서 기본적으로 탭 순서는 '최적화'됩니다. 탭 정지는 일반적인 시나리오에 필수적인 필드에만 설정됩니다.

그러나 작업을 수행하는 데 자주 사용하는 일부 필드가 기본 탭 순서에 포함되어 있지 않을 수 있습니다. 이 경우 Windows 내레이터를 사용하는 경우 Windows 내레이터의 키보드 동작을 사용하여 해당 필드에 액세스하고 해당 콘텐츠를 검사할 수 있습니다. 또는 **옵션** 페이지에서 **고급 탭 순서** 옵션을 켤 수 있습니다. 이 옵션은 편집 가능한 모든 필드와 읽기 전용 필드를 탭 시퀀스의 일부로 만듭니다. 이후 페이지 개인화를 사용하여 사용자 지정 탭 순서를 만들고 탭 순서의 일부가 아니어도 되는 필드를 생략할 수 있습니다. 개인화에 대한 자세한 내용은 [사용자 경험 개인화](personalize-user-experience.md)를 참조하십시오.

![향상된 탭 시퀀스 옵션](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "'고급 탭 순서' 옵션")

## <a name="form-patterns"></a>양식 패턴

앱 페이지의 거의 90%는 작은 패턴 집합을 기반으로 합니다. 이러한 패턴을 *양식 패턴* 이라고 합니다. 각 양식 패턴은 페이지에서 가장 자주 수행되는 작업을 제공하는 데 사용됩니다. 양식 패턴은 자주 사용하는 작업과 데이터가 항상 다른 페이지의 동일한 위치에 표시되기 때문에 친숙함과 이해 용이성을 보장하는 데 도움이 됩니다. 양식 패턴의 수가 적기 때문에 사용자는 페이지 수에 관계없이 시스템을 쉽게 배울 수 있으며 양식 패턴을 인식한 후에는 자신 있게 사용할 수 있습니다.

양식 패턴에 대한 자세한 내용은 [양식 스타일 및 패턴](../../dev-itpro/user-interface/form-styles-patterns.md)을 참조하십시오.

## <a name="responsive-layout"></a>반응형 레이아웃

이 제품은 가장 작은 화면에서 가장 높은 해상도의 큰 화면까지 다양한 디바이스와 폼팩터에서 작동하도록 설계되었습니다. 반응형 레이아웃 엔진을 통해 사용자는 확대 수준을 200%(또는 일부 시나리오에서는 200% 이상)로 확대할 수 있습니다.

스마트폰 및 기타 작은 화면에서 컨트롤과 양식 레이아웃은 핵심 데이터가 선호되도록 반응적으로 조정됩니다. 이러한 응답 동작에는 그룹 및 탭의 열 수를 단일 열로 줄이기, 셸 요소 숨기기 및 작업 창 축소가 포함될 수도 있습니다.

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>개발자와 고객이 사용자 지정에 접근 가능한 사고를 통합할 수 있도록 지원하는 지침

접근성을 활성화하기 위한 Microsoft 모범 사례에 대해 자세히 알아보려면 [양식, 제품 및 컨트롤의 접근성](../../dev-itpro/user-interface/enable-accessibility.md)을 참조하십시오.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]