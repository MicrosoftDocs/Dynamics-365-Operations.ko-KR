---
title: 인벤토리 차단 생성 및 유지
description: 이 항목에서는 재고 차단을 사용하여 실제 현재고가 다른 아웃바운드 출처 문서에 의해 예약되는 것을 방지하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bad7d4e5794dc543bd750912ef0d3e4460e611b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448561"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>인벤토리 차단 생성 및 유지

[!include [banner](../../includes/banner.md)]

이 항목에서는 재고 차단을 사용하여 실제 현재고가 다른 아웃바운드 출처 문서에 의해 예약되는 것을 방지하는 방법에 대해 설명합니다. 이 항목의 절차를 시작하기 전에 실제 현재고를 사용할 수 있는 품목이 있어야 합니다.

## <a name="block-inventory"></a>인벤토리 차단

인벤토리가 차단되도록 인벤토리 차단 레코드를 만들려면 다음 단계를 따르세요.

1. **인벤토리 관리 \> 정기 작업 \> 인벤토리 차단** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 차단 레코드의 헤더에서 **품목 번호** 필드를 차단하려는 항목에 설정하고 설명을 입력합니다.
1. **일반** 빠른 탭의 **수량** 필드에 차단할 항목의 수를 입력합니다.
1. **인벤토리 차원** 빠른 탭에서 차단하려는 항목이 현재 위치한 사이트 및 창고를 지정합니다.
1. 작업 창에서 **저장** 을 선택합니다.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>인벤토리 차단 조건 업데이트

인벤토리 차단 레코드를 업데이트하려면 다음 단계를 따르세요.

1. **인벤토리 관리 \> 정기 작업 \> 인벤토리 차단** 으로 이동합니다.
1. 목록 창에서 관련 차단 레코드를 선택합니다.
1. 필요에 따라 레코드를 편집합니다. 예를 들어 **예정일** 필드를 변경하여 차단된 인벤토리를 예약할 수 있을 것으로 예상되는 시점을 나타낼 수 있습니다. **예상 수령** 옵션을 선택하면 예상 거래에 날짜가 표시됩니다. (**예상 수령** 옵션은 차단 레코드를 수동으로 생성할 때 기본적으로 선택됩니다.)
1. 작업 창에서 **저장** 을 선택합니다.

## <a name="unblock-inventory"></a>인벤토리 차단 해제

인벤토리가 차단 해제되도록 인벤토리 차단 레코드를 제거하려면 다음 단계를 따르세요.

1. **인벤토리 관리 \> 정기 작업 \> 인벤토리 차단** 으로 이동합니다.
1. 목록 창에서 관련 차단 레코드를 선택합니다.
1. 작업 창에서 **삭제** 를 선택합니다.
1. 작업을 확인하라는 메시지가 표시됩니다. **예** 를 선택하여 계속합니다.
1. 페이지를 닫습니다.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
