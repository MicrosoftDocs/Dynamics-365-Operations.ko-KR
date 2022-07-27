---
title: 부분적으로 예약된 이전 주문의 일괄 릴리스
description: 이 항목에서는 모바일 디바이스에서 부분적으로 예약된 이전 주문의 일괄 릴리스를 설정하고 적용하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fbe12b66da68bcd130fdb188eb0106b686200c3b59edc2af96b79f65022567a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447106"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>부분적으로 예약된 이전 주문의 일괄 릴리스

[!include [banner](../includes/banner.md)]

부분적으로 예약된 이전 주문의 일괄 릴리스 기능을 사용하면 일괄 작업을 사용하여 이전 주문을 창고로 부분적으로 릴리스할 수 있습니다.
일부 수량을 릴리스할 수 있는 옵션이 있기 때문에 주문을 릴리스하기 전에 전체 주문 수량을 창고에서 사용할 수 있을 때까지 기다릴 필요가 없습니다.

창고에 대한 주문 릴리스는 고급 창고 관리 프로세스입니다. 이 프로세스에는 창고 작업자가 모바일 디바이스를 사용하여 수행할 수 있는 피킹, 포장 및 배송과 같은 활동이 포함됩니다.

## <a name="where-it-applies"></a>적용되는 곳

이 기능을 위해 일괄 작업을 사용하여 이전 주문을 창고로 릴리즈합니다. 이 기능은 창고에 재고가 충분하지 않지만 한 창고에서 다른 창고로 품목을 이전하려는 경우에 유용합니다.

## <a name="how-it-is-set-up"></a>설정 방법

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>이전 주문 및 판매 주문에 대한 이행 기준 지정

주문을 일괄적으로 창고로 출고하려면 먼저 이행 기준을 충족해야 합니다. 이러한 이행 기준은 이행 정책에 의해 결정됩니다.

이전 주문 및 판매 주문에 대한 이행 정책은 회사 수준에서 지정됩니다. 이행 정책 설정에 따라 일괄 주문 릴리스가 수락되거나 거부됩니다. 그러면 주문이 그에 따라 처리됩니다.

-   이전 주문 및 판매 주문에 대한 이행 정책을 생성하려면 **창고 관리** \> **설정** \> **창고로 출고** \> **이행 정책** 을 클릭한 다음 이름과 설명을 입력하여 이행 정책을 생성합니다.

-   이행률, 값 유형 및 이행 정책 위반 시 표시되는 메시지를 지정하려면 **창고 관리** \> **설정** \> **창고로 출고** \> **이행 정책** 을 클릭한 다음 **이행률**, **값 유형** 및 **이행 위반 메시지** 필드를 설정합니다.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>이전 주문 및 판매 주문에 대한 이행 정책 설정

-   이전 주문에 대한 이행 정책을 설정하려면 **재고 관리** \> **설정** \> **재고 및 창고 관리 매개 변수** \> **주문 이전** \> **창고 관리** 를 클릭한 다음 이전 주문 이행 정책을 선택합니다.

-   판매 주문에 대한 이행 정책을 설정하려면 **미수금** \> **설정** \> **미수금 매개 변수** \> **창고 관리** 를 클릭한 다음 판매 주문 이행 정책을 선택합니다.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>일괄 릴리스를 허용하고 일괄 릴리스해야 하는 수량을 지정합니다.

배치 작업은 배치의 창고로 주문을 릴리스하는 데 사용됩니다. 일괄 작업에서 실행해야 하는 주문을 구별하는 매개변수는 일괄 작업 자체에서 설정됩니다.

**수량** 매개 변수는 전체 수량 또는 물리적으로 예약된 수량을 배치에서 릴리스해야 하는지 여부를 지정합니다. **부분적으로 릴리스된 주문 릴리스 허용** 매개 변수는 배치의 주문이 이전에 부분적으로 릴리스된 경우 승인 또는 거부되어야 하는지 여부를 결정합니다.

-   이전 주문에 **수량** 및 **부분적으로 릴리스된 주문 릴리스 허용** 매개 변수를 설정하려면 **창고 관리** \> **창고로 출고** \> **이전 주문의 자동 릴리스** 를 클릭합니다.

-   판매 주문에 **수량** 및 **부분적으로 릴리스된 주문 릴리스 허용** 매개 변수를 설정하려면 **창고 관리** \> **창고로 출고** \> **판매 주문의 자동 릴리스** 를 클릭합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]