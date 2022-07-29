---
title: 액션 검색
description: 이 문서에서는 작업 검색 함수에 대해 설명합니다. 작업 검색은 페이지에서 작업을 찾고 실행하는 데 도움이 됩니다.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6277c37ac43b8cc05c8b53da5ca0a1909f58c4f9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460608"
---
# <a name="action-search"></a>액션 검색

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 문서에서는 작업 검색 함수에 대해 설명합니다. 작업 검색은 페이지에서 작업을 찾고 실행하는 데 도움이 됩니다.

## <a name="introduction"></a>소개

페이지는 주로 페이지 상단에 나타나는 표준 작업 창과 페이지의 다양한 섹션에 나타나는 도구 모음인 작업 창에 명령을 표시합니다. 이전 버전에서 키 팁 기능을 사용하면 Alt 키를 누른 다음 일련의 문자를 눌러 작업 창의 모든 버튼에 빠르게 액세스할 수 있습니다.

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)

작업 검색 기능은 더 이상 사용할 수 없는 주요 팁을 대체합니다. 이 새로운 기능을 사용하면 보이는 모든 작업 창에서 버튼을 빠르게 검색하고 실행할 수 있습니다.

## <a name="using-action-search"></a>작업 검색 사용

액션 검색 기능을 사용하려면 다음 단계를 따르십시오.

1. 작업 창에서 **작업 검색** 필드를 클릭합니다. (**작업 검색** 필드에는 돋보기 아이콘이 있습니다.)
2. 실행하려는 버튼 이름의 전체 또는 일부를 입력합니다. 버튼의 '경로'에 있는 단어를 사용하여 검색할 수도 있습니다. (자세한 내용은 이 문서의 다음 섹션을 참조하십시오.) 일반적으로 2-4자를 입력하면 결과 목록 상단 근처에 버튼이 나타납니다.
3. 결과 목록에서 버튼을 찾아 실행합니다(마우스 또는 키보드 사용).

버튼이 실행되면 포커스가 페이지의 마지막 위치로 돌아가서 계속 작업할 수 있습니다.

[![액션 검색 필드.](./media/action-search-field.png)](./media/action-search-field.png)

Ctrl+/ 또는 Alt+Q를 눌러 작업 검색을 시작할 수도 있습니다. 포커스를 페이지의 마지막 위치로 되돌리려면 키보드 단축키를 다시 누르십시오.

## <a name="understanding-the-results-list"></a>결과 목록 이해

버튼의 목적을 완전히 이해하려면 버튼의 위치와 컨텍스트를 모두 알아야 하는 경우가 많습니다. 따라서 결과 목록에는 목록에 나타나는 버튼을 정확히 이해하는 데 도움이 되는 추가 정보가 표시됩니다. 특히 버튼의 '경로'가 표시됩니다. 이 경로에는 관련되는 다음 UI 요소의 레이블이 포함될 수 있습니다.

- 작업 창 탭
- 버튼 그룹
- 메뉴 버튼(버튼이 메뉴 버튼 안에 있는 경우)
- 메뉴 구분 기호(버튼이 메뉴 버튼 내의 명명된 그룹 안에 있는 경우)
- 페이지의 그룹 또는 탭(예: FastTab의 이름)

예를 들어, **작업 검색** 필드에 **tot** 를 입력했고 이제 결과 목록을 검사하고 있습니다. **Totals** 라는 버튼의 첫 번째 항목이 강조 표시됩니다. **판매 주문** &gt; **보기** 의 버튼 경로도 표시됩니다. 경로의 **판매 주문** 부분은 작업 창의 **판매 주문** 탭에 해당하고 경로의 **보기** 부분은 해당 탭의 **보기** 그룹에 해당합니다. 마찬가지로 **총 할인** 버튼(**계산** &gt; **판매**)의 경로는 이 버튼이 작업 창의 **판매** 탭에 있는 **계산** 그룹에 있음을 알려줍니다. 따라서 이 정보는 작업 검색에 의해 트리거될 버튼을 정확히 이해하는 데 도움이 됩니다(결과 목록에서 해당 버튼을 선택한 경우).

[![action-search-field-with-data.](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

이전 예시에서 작업 검색은 페이지 상단에 표준 작업 창의 결과를 표시했습니다. 그러나 작업 검색은 페이지의 다른 위치에 있는 표시되는 도구 모음의 결과도 표시합니다. 예를 들어, **판매 주문 라인** FastTab에 있는 **현재고** 버튼을 검색하고 있습니다. 이 경우 결과 목록의 버튼 경로(**판매 주문 라인** &gt; **재고** &gt; **보기**)는 이 버튼이 **판매 주문 라인** FastTab의 **재고** 메뉴 버튼에 있는 **보기** 표제 아래에 있음을 알려줍니다.

[![보유 재고.](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

> [!NOTE]
> 액션 검색에 표시되지 않는 버튼이 있습니다. 여기에는 드롭 대화 상자 버튼과 하위 양식의 버튼이 포함됩니다. 

## <a name="action-search-vs-navigation-search"></a>액션 검색 대 탐색 검색

작업 검색은 페이지에서 작업을 찾고 실행하기 위한 것이지만 페이지를 찾고 탐색하기 위한 별도의 검색 메커니즘이 있습니다. 해당 기능에 대한 자세한 내용은 [탐색 검색](navigation-search.md) 문서를 참조하십시오.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]