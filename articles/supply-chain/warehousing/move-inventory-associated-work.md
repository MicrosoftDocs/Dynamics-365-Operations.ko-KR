---
title: Warehouse Management에서 관련 업무에 따른 재고 이동
description: 재고 이동을 사용하여 예약된 재고를 이동할 수 있는 창고 작업자를 결정할 수 있습니다.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d996886a90037f288e839c54c8c9d932cabb21f19f2aef1552ca82b192c96a51
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446848"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Warehouse Management에서 관련 업무에 따른 재고 이동

[!include [banner](../includes/banner.md)]

재고 이동을 사용하여 예약된 재고를 이동할 수 있는 창고 작업자를 결정할 수 있습니다. 이는 작업자가 이미 생성된 피킹 작업에 대해 새로운 피킹 위치를 선택하지 못하도록 결정할 수 있는 규제된 창고에 유연성을 제공합니다. 또한 창고 관리자는 경험이 부족한 작업자가 갖추어야 할 기능을 제어할 수 있습니다.

창고 작업자의 일상적인 작업을 관리할 수 있는 유연성은 다음과 같은 시나리오에서 유용할 수 있습니다.

## <a name="scenario-1"></a>시나리오 1

회사는 비교적 작은 입고 영역을 가지고 있으며, 치워지기를 기다리는 팔레트와 상자로 혼잡합니다. 당일 대량 배송이 예상되므로 입고 담당자는 일부 팔레트를 2차 인바운드 대기 장소로 이동하여 입고 지역을 정리하기로 결정합니다.

## <a name="scenario-2"></a>시나리오 2

숙련된 창고 작업자는 창고에서 품목을 소량으로 가까운 세 위치에 나누어 보관하는 대신 한 위치에 통합할 수 있는 기회를 발견했습니다. 작업자는 이러한 각 위치에서 동일한 위치 및 동일한 번호판으로 항목을 이동하여 수량을 통합하려고 합니다.

## <a name="scenario-3"></a>시나리오 3

팔레트가 BAYDOOR01 근처에 있는 STAGE01과 같은 준비 위치에서 선적을 기다리고 있습니다. 그러나 계획 변경으로 인해 트럭이 BAYDOOR04에 도착할 예정입니다. 선적 직원은 이를 인지하고 트럭이 STAGE01에서 적재될 때까지 기다릴 필요가 없도록 해야 합니다. 배송 직원은 해당 배송의 항목을 새 목적지에 더 가까운 STAGE01에서 STAGE04로 이동하기로 결정합니다.

### <a name="current-limitations"></a>현재 제한 사항

이동할 수 있는 작업 예약은 매도 주문, 이전 주문 발행, 이전 주문 접수, 구매 주문, 보충 작업으로 제한됩니다.

작업 라인의 분할을 방지하기 위해 항목 이동을 제한합니다. 즉, 위치 Loc1에서 항목 A 100개에 대한 작업 라인이 있는 경우 해당 위치에서 다른 위치로 항목 A 30개만 이동할 수 없습니다. 이렇게 하면 위치가 이제 다르기 때문에 기존 작업 라인이 30과 70으로 분할됩니다.

상품을 이동하는 번호판이나 상품을 이동하는 번호판이 작업 주문의 대상 LP로 설정되어 있는 스테이징 시나리오에서는 대상 LP가 분리되지 않도록 전체 LP의 이동만 허용됩니다.

현재 임시 이동만 지원됩니다. 즉, 템플릿 모바일 디바이스 메뉴 항목에 의한 이동을 통해 예약된 재고를 이동할 수 없습니다.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>개별 작업자의 예약 재고 이동 권한 설정

예약된 재고 이동이 허용된 작업자의 경우 **창고 관리 \> 설정 \> 작업자** 에서 **관련 작업과 함께 재고 이동 허용** 확인란을 선택합니다.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
