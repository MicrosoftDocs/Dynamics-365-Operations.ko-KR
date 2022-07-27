---
title: 아웃바운드 프로세스 개요
description: 이 항목에서는 재고 관리의 아웃바운드 프로세스에 대한 개요를 제공합니다.
author: yufeihuang
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 85012ada693a98652325a142ba4649a9a826b22b
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449641"
---
# <a name="outbound-process-overview"></a>아웃바운드 프로세스 개요

[!include [banner](../includes/banner.md)]

이 항목에서는 재고 관리의 아웃바운드 프로세스에 대한 개요를 제공합니다.

## <a name="output-orders"></a>출력 주문

출력 주문은 판매 주문 라인 및 이전 주문 라인을 피킹 목록을 사용하는 아웃바운드 피킹 프로세스와 연결하는 데 사용됩니다.

판매 주문 또는 이전 주문에서 피킹 목록이 생성되면 출력 주문 및 배송이 자동으로 생성됩니다. 피킹 목록은 배송과 일대일 관계가 있습니다. 이전 주문 배송 또는 판매 주문 포장 전표는 배송에서 처리할 수 있습니다. 

다음 다이어그램은 아웃바운드 주문 프로세스의 개요를 보여줍니다. 

[![아웃바운드 주문 프로세스 개요.](./media/outbound-order.png)](./media/outbound-order.png)

아웃바운드 규칙을 설정하여 프로그램이 아웃바운드 프로세스를 처리하는 방법을 정의할 수 있습니다. 이 규칙을 사용하여 배송 프로세스를 제어할 수 있습니다. 특히 규칙을 사용하여 배송을 보낼 수 있는 프로세스의 단계를 제어할 수 있습니다. 다음 설정은 아웃바운드 프로세스가 처리되는 방식을 정의합니다.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>판매 및 이전 주문에 대한 피킹 경로 상태 

**수취 계정** \> **설정** \> **수취 계정 매개 변수** 로 이동한 다음 **업데이트** 탭에서 **피킹 경로 상태** 필드에서 값을 선택합니다.

[![판매 주문에 대한 피킹 경로 상태 필드.](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

**피킹 경로 상태** 필드가 **완료됨** 으로 설정된 경우, 피킹 프로세스는 불출 목록 생성 프로세스의 일부로 자동으로 발생합니다. 필드가 **활성화됨** 으로 설정된 경우 불출 목록 라인을 수동으로 업데이트해야 합니다.

동일한 설정이 이전 주문에도 적용됩니다. **재고 관리** \> **설정** \> **재고 및 창고 관리 매개 변수** 로 이동하고 **이전** 탭의 **피킹 경로 상태** 필드에서 값을 선택합니다.

[![이전 주문에 대한 피킹 경로 상태 필드.](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>출력 재고 주문 종료

**재고 관리** \> **설정** \> **재고 및 창고 관리 매개 변수** 로 이동하고 **일반** 탭에서 **출력 재고 주문 종료** 옵션을 설정합니다.

[![출력 재고 주문 종료 옵션.](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

창고 작업자가 불출 목록 수량을 줄이면 해당 재고 주문 수량은 배송에서 제거됩니다. 불출 목록이 특정 시점에 업데이트되면 나머지 수량은 **출력 재고 주문 종료** 옵션이 **예** 로 설정된 경우 주문에 다시 보고됩니다. **출력 재고 주문 종료** 옵션이 **아니요** 로 설정된 경우 나머지 수량은 미결 출력 주문 수량으로 유지되며 **출력 주문 열기** 기능의 일부로 새 불출 목록에 추가되어야 합니다. 

[![기능 메뉴에서 출력 주문 명령을 엽니다.](./media/open-output-order.png)](./media/open-output-order.png)

[![출력 주문 열기 페이지의 기능 메뉴.](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>수량 감소

불출 목록 생성 프로세스의 일부로 사용할 수 있는 세 번째 매개 변수는 **수량 감소** 매개 변수입니다. 이 매개변수의 설정은 창고에 대한 릴리스의 일부로 예약 프로세스를 트리거하는 **예약** 설정과 함께 작동합니다.

[![수량 감소 매개 변수](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>판매 주문에 대한 아웃바운드 프로세스의 예

이 예에는 두 개의 품목에 대한 판매 주문이 있습니다. 불출 목록 생성 중에 **수량 감소** 매개 변수를 선택합니다. 따라서 사용 가능한 현재고에 대해서만 피킹 라인을 릴리즈하고 생성합니다. 피킹은 불출 목록 등록 프로세스를 통해 보고되어야 합니다(**피킹 경로 상태** = **활성화됨**).

아직 예약되지 않은 재고는 불출 목록 생성 중에 예약됩니다. 사용할 수 없는 재고는 판매 주문에서 제거하거나 나중에 재고를 피킹할 수 있을 때 아웃바운드 처리를 위해 창고로 릴리즈할 수 있습니다.

[![불출 목록 업데이트.](./media/update-picking-list.png)](./media/update-picking-list.png)

**불출 목록 등록** 페이지에서 모든 피킹 라인이 선택되는 즉시 관련 배송이 완료됩니다. 그런 다음 선택한 재고를 기반으로 판매 주문 포장 전표 프로세스를 초기화할 수 있습니다.

[![아웃바운드 배송 업데이트.](./media/outbound-shipments.png)](./media/outbound-shipments.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]