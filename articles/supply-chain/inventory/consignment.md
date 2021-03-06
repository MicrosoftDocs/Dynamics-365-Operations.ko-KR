---
title: 위탁 설정
description: 이 항목에서는 인바운드 위탁 재고 프로세스를 사용하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchTablePart, PurchVendorPortalConfirmedOrders, DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4a1b96d18048a1ae6e380374f32d2bfa2270ae24
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449038"
---
# <a name="set-up-consignment"></a>위탁 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 인바운드 위탁 재고 프로세스를 사용하는 방법에 대해 설명합니다.

위탁 재고는 공급업체가 소유하지만 귀하의 사이트에 저장되어 있는 재고입니다. 인벤토리를 소비하거나 사용할 준비가 되면 인벤토리의 소유권을 인수합니다. 이 항목에는 총계정원장 트랜잭션을 생성하지 않고 현재고에서 공급업체 소유 재고를 물리적으로 받는 방법, 공급업체 소유 재고를 물리적으로 예약할 수 있는 생산 프로세스를 시작하는 방법에 대한 정보가 포함되어 있습니다. 생산 주문 처리의 일부로 소비를 처리할 수 있도록 원자재 소유권을 변경하는 방법. 공급업체가 공급업체 협업 인터페이스를 사용하여 인벤토리 소비를 모니터링하는 방법에 대한 정보도 있습니다.

## <a name="overview-of-the-consignment-process"></a>위탁 절차의 개요

이 예제 시나리오에서 USMF는 원자재 M9211CI에 대해 공급업체 US-104와 위탁 계약을 체결했습니다.

1. USMF의 누군가가 예상 수요에 따라 위탁 보충 주문을 수동으로 생성합니다. 공급업체 US-104에 대한 주문이 생성되고 품목 MS9211CI에 대한 라인이 추가됩니다.
1. 공급업체는 예상 배송에 대한 정보를 받습니다. 이는 다음 세 가지 방법 중 하나로 발생할 수 있습니다.
    - USMF에서 일하는 누군가가 주문 정보를 공급업체에 보냅니다.
    - 공급업체는 공급업체 협업 인터페이스를 사용하여 예상 재고를 직접 모니터링할 수 있습니다.
    - USMF에서 일하는 누군가가 **보유 재고** 페이지에서 데이터를 필터링하여 영수증 상태가 **주문됨** 인 공급업체 US-104에 대한 레코드만 표시한 다음 이 정보를 공급업체에 보냅니다.
1. 인벤토리는 US-104에서 USMF로 배달됩니다.
1. 자재가 USMF에 도착하면 위탁 보충 주문이 제품 영수증으로 업데이트됩니다. 공급업체 소유 재고의 실제 수량만 기록됩니다. 재고는 여전히 공급업체가 소유하고 있기 때문에 생성된 총계정원장 트랜잭션이 없습니다.
1. 공급업체는 **현재고 위탁 재고** 페이지를 사용하여 실제 보유 재고에 대한 업데이트를 모니터링합니다.
1. 이제 총 재고가 준비되었으므로 생산 프로세스는 공급업체 소유 재고를 예약하고 원자재 M9211CI를 소비할 완제품에 대한 생산 오더를 시작합니다.
1. 오늘의 생산에 소비될 예약된 원료의 소유자는 US-104에서 USMF로 변경됩니다. 이것은 재고 소유권 변경 저널을 사용하여 수행됩니다. 이 프로세스는 **기원** 필드가 **위탁** 으로 설정된 구매 주문을 생성합니다.
1. 공급업체는 **위탁 재고에서 입고된 제품** 페이지애소 소비(소유권 변경)를 모니터링하고 두 회사 간의 계약에 따라 송장을 발행합니다.
1. 생산 공정은 생산 피킹 목록을 통해 원자재를 소비합니다. 실제 예약은 현재고가 USMF의 소유임을 반영하도록 자동으로 업데이트됩니다.
1. 재고 소유권 변경 분개가 처리될 때 자동 생성된 구매 주문에 대해 US-104의 송장이 처리됩니다. 소비된 인벤토리에 대한 지불은 US-104 공급업체에 이루어집니다.

USMF는 추가 정기 프로세스를 수행합니다.

- 다른 창고 간의 공급업체 소유 재고의 물리적 이동은 이전 저널을 사용하여 처리됩니다.
- 현재고는 **아이템 카운팅** 저널을 사용하여 갱신됩니다. 판매업체가 이를 수행할 권한이 있는 경우 현재고를 업데이트하기 위해 계산을 사용할 수도 있습니다.

공급업체인 US-104는 **현재고 위탁 재고** 페이지를 사용하여 업데이트를 모니터링할 수 있습니다.

## <a name="consignment-replenishment-orders"></a>위탁 보충 주문

위탁 보충 주문은 주문된 재고 트랜잭션을 생성하여 공급업체가 특정 날짜 간격 내에 배송하려는 제품의 재고 수량을 요청하고 추적하는 데 사용되는 문서입니다. 일반적으로 이는 특정 제품의 예측 및 실제 수요를 기반으로 합니다. 위탁 보충 주문에 대해 입고될 재고는 공급업체의 소유권으로 유지됩니다. 실제 입고 업데이트와 관련된 상품의 보유만 기록되므로 총계정원장 거래 업데이트는 발생하지 않습니다.

**소유자** 차원은 공급업체가 소유한 재고와 수령 법인이 소유한 재고에 대한 정보를 구분하는 데 사용됩니다. 위탁 보충 주문 라인에는 **오픈 오더** 상태가 있으며 이는 라인의 전체 수량이 접수되거나 취소되지 않은 한 상태입니다. 전체 수량이 입고되거나 취소되면 상태가 **완료됨** 으로 변경됩니다. 위탁 보충 주문과 관련된 실제 현재고는 등록 프로세스와 제품 입고 업데이트 프로세스를 사용하여 기록할 수 있습니다. 등록은 품목 도착 프로세스의 일부로 또는 주문 라인을 수동으로 업데이트하여 수행할 수 있습니다. 제품 입고 업데이트 프로세스를 사용하는 경우 제품 입고 일지에 기록이 작성되어 공급업체에 제품 수령을 확인하는 데 사용할 수 있습니다.

[![위탁 보충 주문.](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>재고 소유권 변경 분개

**재고 소유권 변경** 분개는 위탁 재고 소유권 이전을 공급업체에서 이를 소비하는 현재 법인으로 기록하는 데 사용됩니다. 저널에 대해 생성된 예상 재고 트랜잭션이 없습니다. 모든 인벤토리 저널과 마찬가지로 인벤토리 저널 이름으로 식별해야 합니다. 이러한 이름은 **인벤토리 저널 이름** 페이지에 생성되며 **저널 유형** 은 **소유권 변경** 으로 설정해야 합니다.

게시된 분개와 관련된 인벤토리 트랜잭션만 생성됩니다. 저널이 게시될 때:

- 공급업체 소유 재고는 **소유권 변경** 참조가 **판매됨** 상태를 참조하여 발행됩니다.
- 보유 재고는 구매 주문에 대한 제품 영수증으로 업데이트되는 재고 트랜잭션을 사용하여 소비하는 법인에 의해 수신됩니다. 주문 상태를 **수령함** 으로 설정합니다. 위탁에 사용되는 구매 주문에는 **기원** 필드가 **위탁** 으로 설정됩니다.

주문이 생성된 후에는 위탁 구매 발주 라인의 수량을 업데이트할 수 없습니다.

[![재고 소유권 변경 분개.](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>위탁 프로세스의 공급업체 협업

공급업체가 공급업체 협업 인터페이스를 사용하는 경우 이를 사용하여 사이트의 재고 소비를 모니터링할 수 있습니다. 공급업체 협업 인터페이스에는 인바운드 위탁 프로세스와 관련된 세 페이지가 있습니다.

- **구매 주문** **위탁 재고 소비** - 위탁 과정에서 소유권 변경과 관련된 상세 구매 주문 정보를 보여줍니다.
- **위탁 재고에서 입고된 제품** - 소유권 변경 과정에서 제품 영수증이 업데이트된 품목 및 수량에 대한 정보를 표시합니다.
- **현재고 위탁 재고** - 배송이 예상되는 위탁 품목 및 고객 사이트에서 이미 물리적으로 사용 가능한 품목에 대한 정보를 표시합니다.

공급업체 협업을 사용하도록 공급업체를 설정하는 방법에 대한 자세한 내용은 [공급업체 포털 사용자 보안](../procurement/configure-security-vendor-portal-users.md)을 참조하세요.

## <a name="inventory-owners"></a>인벤토리 소유자

실제 인바운드 위탁 재고를 기록하려면 공급업체 소유자를 정의해야 합니다. **인벤토리 소유자** 페이지에서 수행됩니다. **공급업체 계정** 을 선택하면 **이름** 및 **소유자** 필드의 기본값을 생성합니다. **소유자** 필드의 값은 공급업체에 표시되므로 외부 사람들이 공급업체 계정 이름을 쉽게 인식할 수 없는 경우 변경할 수 있습니다. **소유자** 필드를 편집할 수 있지만 **재고 소유자** 레코드를 저장하는 시점까지만 가능합니다. **이름** 필드는 공급업체 계정이 연결된 당사자의 이름으로 채워지며 변경할 수 없습니다.

[![인벤토리 소유자.](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>추적 규모 그룹

위탁 프로세스에 사용될 품목은 **추적 측정기준 그룹** 과 연결되어야 하며 **소유자** 차원이 **활성** 으로 설정되어야 합니다. 소유자 차원에는 항상 **총실사** 및 **재무 인벤토리** 옵션이 선택되어 있습니다. **차원별 보장 계획** 은 절대 선택되지 않습니다.

[![추적 규모 그룹.](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
