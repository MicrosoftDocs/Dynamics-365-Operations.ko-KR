---
title: 조회를 사용하여 정보 찾기
description: 이 항목에서는 조회 기능에 대해 배우고 시스템에서 조회를 최적으로 사용하는 데 유용한 몇 가지 팁을 받게 됩니다.
author: jasongre
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7135487e5d87564163c643d1315c51231fa66de
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460750"
---
# <a name="find-information-by-using-lookups"></a>조회를 사용하여 정보 찾기

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

많은 필드에는 정확하거나 원하는 값을 쉽게 찾는 데 도움이 되는 조회가 있습니다. 이러한 컨트롤을 더욱 유용하게 만들고 사용자의 생산성을 높이는 몇 가지 개선 사항이 조회에 추가되었습니다. 이 항목에서는 이러한 새 조회 기능에 대해 배우고 시스템에서 조회를 최적으로 사용하는 데 유용한 몇 가지 팁을 받게 됩니다.

## <a name="responsive-lookups"></a>반응형 조회

이전 버전에서는 조회 컨트롤과 상호 작용할 때 사용자가 드롭다운 메뉴를 열려면 명시적인 작업을 수행해야 했습니다. 컨트롤에서 별표(\*)를 입력하여 컨트롤의 현재 값을 기준으로 조회를 필터링하거나 드롭다운 버튼을 클릭하거나 **Alt**+**아래쪽 화살표** 키보드 단축키를 사용했을 수 있습니다. 조회 컨트롤은 현재 웹 관행에 더 잘 부합하도록 다음과 같이 수정되었습니다.

- 조회 드롭다운 메뉴는 이제 입력을 잠시 멈춘 후 자동으로 열리고 조회 컨트롤의 값에 따라 필터링된 드롭다운 메뉴 내용이 표시됩니다.

    별표(\*)를 입력한 후 드롭다운이 자동으로 열린는 이전 동작은 더 이상 사용되지 않습니다.

- 조회 드롭다운 메뉴가 열리면 다음이 발생합니다.

    - 커서는 (드롭다운 메뉴로 이동하는 포커스 대신) 조회 컨트롤에 남아 있으므로 컨트롤 값을 계속 수정할 수 있습니다. 그러나 사용자는 계속해서 **위쪽 화살표** 및 **아래쪽 화살표** 를 사용하여 드롭다운 메뉴에서 행을 변경하려면 입력하고 Enter 키를 눌러 드롭다운 메뉴에서 현재 행을 선택할 수 있습니다.
    - 드롭다운 메뉴의 내용은 조회 컨트롤의 값을 수정한 후 조정됩니다.

예를 들어 **도시** 라는 조회 필드를 고려해 보세요.

초점이 **도시** 필드에 있으면 "col"과 같은 몇 글자를 입력하여 원하는 도시를 찾을 수 있습니다. 입력을 중단하면 조회가 자동으로 열리고 "col"로 시작하는 도시로 필터링됩니다.

[![typeaheadLookupExample.](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)

이 시점에서 커서는 여전히 조회 필드에 있습니다. 값이 "열"이 되도록 계속 입력하면 조회 내용이 컨트롤의 최신 값을 반영하도록 자동으로 조정됩니다.

![updateFilterLookupExample.](./media/updatefilterlookupexample.png)

포커스가 여전히 조회 컨트롤에 있더라도 **위쪽 화살표** 또는 **아래쪽 화살표** 키를 눌러 선택하려는 행을 강조 표시할 수 있습니다. **Enter** 를 누르면 강조 표시된 행이 조회에서 선택되고 컨트롤의 값이 업데이트됩니다.

![changingSelectionLookup.](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>ID 이상 입력

데이터를 입력할 때 사용자가 엔터티를 나타내는 식별자가 아니라 이름으로 고객이나 공급업체와 같은 엔터티를 식별하려고 시도하는 것은 당연합니다. 많은(전부는 아니지만) 조회에서 이제 상황별 데이터 입력이 허용됩니다. 이 강력한 기능을 통해 사용자는 조회 컨트롤에 ID 또는 해당 이름을 입력할 수 있습니다.

예를 들어 판매 주문을 생성할 때 **고객 계정** 필드를 고려해 보세요. 이 필드는 고객의 **계정 ID** 를 보여주지만 사용자는 "US-003" 대신 "Forest Wholesale"와 같이 판매 주문을 생성할 때 이 필드에 일반적으로 **계정 ID** 대신 **계정 이름** 을 입력합니다.

사용자가 조회 컨트롤에 **계정 ID** 를 입력하기 시작하면 이전 섹션에서 설명한 대로 드롭다운 메뉴가 자동으로 열리고 사용자는 아래와 같이 조회를 볼 수 있습니다.

[![고객 계정 ID가 입력될 때 컨텍스트 조회.](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

그러나 사용자는 이제 **계정 이름** 의 시작 부분을 입력할 수도 있습니다. 이것이 감지되면 사용자는 다음 조회를 보게 됩니다. **이름** 열이 조회의 첫 번째 열로 이동되고 조회가 **이름** 열에 따라 정렬 및 필터링되는 방식을 알려줍니다.

[![고객 이름이 입력될 때 컨텍스트 조회.](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>고급 필터링 및 정렬을 위해 그리드 열 헤더 사용

이전 두 섹션에서 논의한 조회 개선 사항은 조회의 **ID** 또는 **이름** 필드의 "시작" 검색을 기반으로 조회에서 행을 탐색하는 사용자의 능력을 크게 향상시킵니다. 그러나 올바른 행을 찾기 위해 고급 필터링(또는 정렬)이 필요한 상황이 있습니다. 이러한 상황에서 사용자는 조회 내부의 그리드 열 헤더에서 필터링 및 정렬 옵션을 사용해야 합니다. 예를 들어, 제품으로 올바른 "케이블"을 찾아야 하는 판매 주문 라인을 입력하는 직원을 생각해 보세요. "케이블"을 **품목 번호** 컨트롤에 입력하는 것은 "cable"로 시작하는 제품 이름이 없기 때문에 도움이 되지 않습니다.

![emptyitemlookup.](./media/emptyitemlookup.png)

대신, 사용자는 아래와 같이 조회 컨트롤의 값을 지우고 조회 드롭다운 메뉴를 열고 그리드 열 머리글을 사용하여 드롭다운 메뉴를 필터링해야 합니다. 마우스(또는 터치) 사용자는 열 헤더를 클릭(또는 터치)하여 해당 열에 대한 필터링 및 정렬 옵션에 액세스할 수 있습니다. 키보드 사용자의 경우 사용자는 **Alt**+**아래** **화살표** 를 두 번 눌러 드롭다운 메뉴로 포커스를 이동한 후 사용자가 올바른 열로 탭한 다음 **Ctrl**+**G** 를 눌러 그리드 열 머리글 드롭다운 메뉴를 엽니다.

[![gridfilteritemlookup.](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)

필터가 적용된 후(아래 이미지 참조) 사용자는 평소와 같이 행을 찾아 선택할 수 있습니다.

![filtereditemlookup.](./media/filtereditemlookup.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]