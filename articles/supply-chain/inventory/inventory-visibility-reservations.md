---
title: 인벤토리 가시성 예약
description: 이 토픽에서는 인벤토리 가시성를 사용하여 예약 생성, 예약 소비 및/또는 지정된 재고 수량 예약 취소를 위한 예약 기능을 설정하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5e6752539a6381e1f7271883102391374e04f3aa
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449821"
---
# <a name="inventory-visibility-reservations"></a>인벤토리 가시성 예약

[!include [banner](../includes/banner.md)]


이 토픽에서는 인벤토리 가시성를 사용하여 예약 생성, 예약 소비 및/또는 지정된 재고 수량 예약 취소를 위한 예약 기능을 설정하는 방법에 대해 설명합니다.

예약은 미래에 사용될 인벤토리의 수량을 표시합니다. 예약을 생성하면 시스템은 예약이 소비되거나 예약되지 않을 때까지 다른 주문이 예약 상품을 예약하거나 소비하는 것을 방지합니다. 인벤토리 가시성 서비스에 대한 API 호출을 사용하여 예약이 생성, 사용 및 취소됩니다.

인벤토리 가시성을 사용하여 예약된 수량을 자동으로 상쇄하도록 Microsoft Dynamics 365 Supply Chain Management(및 기타 타사 시스템)를 선택적으로 설정할 수 있습니다. 상쇄 수량은 인벤토리 가시성의 예약 기록에서 삭제됩니다.

예약 기능을 켜면 Supply Chain Management가 자동으로 인벤토리 가시성을 사용하여 이루어진 예약을 상쇄할 준비가 됩니다.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>예약 기능 켜기 및 설정

예약 기능을 켜려면 다음 단계를 따르세요.

1. Power Apps에 로그인하고 **인벤토리 가시성** 을 엽니다.
1. **구성** 페이지를 엽니다.
1. **기능 관리** 탭에서 *OnHandReservation* 기능을 켭니다.
1. Supply Chain Management에 로그인합니다.
1. **[기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** 작업 영역으로 이동하여 *예약 상쇄와 인벤토리 가시성 통합* 기능을 활성화합니다(버전 10.0.22 이상 필요).
1. **재고 관리 \> 설정 \> 인벤토리 가시성 통합 매개 변수** 로 이동하여 **예약 상쇄** 탭을 열고 다음 설정을 지정합니다.
    - **예약 상쇄 사용** – 이 기능을 활성화하려면 *예* 로 설정합니다.
    - **예약 상쇄 수정자** – 인벤토리 가시성에서 이루어진 예약을 상쇄할 재고 트랜잭션 상태를 선택합니다. 이 설정은 상쇄를 트리거하는 주문 처리 단계를 결정합니다. 단계는 주문의 재고 트랜잭션 상태로 추적됩니다. 다음 중 하나를 선택합니다.
        - *주문 시* – *주문 시* 상태의 경우 주문이 생성될 때 상쇄 요청을 보냅니다. 상쇄 수량은 생성된 주문의 수량입니다.
        - *예약* – *예약 주문 거래* 상태의 경우 예약, 피킹, 포장 명세서 게시 또는 송장 발행 시 주문에서 상쇄 요청을 보냅니다. 요청은 언급된 프로세스가 발생하는 첫 번째 단계에 대해 한 번만 트리거됩니다. 상쇄 수량은 해당 주문 라인에서 재고 트랜잭션 상태가 *주문 시* 에서 *주문 예약*(또는 이후 상태)으로 변경된 수량입니다.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>인벤토리 가시성에서 예약 기능 사용

예약 API를 호출하면 시스템은 지정된 항목 및 수량의 예약을 표시합니다. 예약 계층을 정의하고 해당 예약 계층과 일치하는 요청을 게시해야 합니다. 그런 다음 예약 API를 직접 호출하여 예약할 수 있습니다.

### <a name="configure-the-reservation-hierarchy"></a>예약 계층 구성

예약 계층은 예약 시 지정해야 하는 차원의 순서를 설명합니다. 인덱스 계층 구조가 현재 쿼리에 대해 작동하는 것과 동일한 방식으로 작동합니다.

예약 계층 구조는 인덱스 계층 구조와 다를 수 있습니다. 이러한 독립성을 통해 사용자가 차원을 세부적으로 분류하여 보다 정확한 예약을 위한 요구 사항을 지정할 수 있는 범주 관리를 구현할 수 있습니다.

Power Apps에서 소프트 예약 계층을 구성하려면 **구성** 페이지를 연 다음, **소프트 예약 계층** 탭에서 차원 및 해당 계층 수준을 추가 및/또는 수정하여 예약 계층을 설정합니다.

소프트 예약 계층 구조는 파티션 구성을 구성하기 때문에 `SiteId` 및 `LocationId`를 구성 요소로 포함해야 합니다.

예약을 구성하는 방법에 대한 자세한 내용은 [예약 구성](inventory-visibility-configuration.md#reservation-configuration)을 참조하세요.

### <a name="call-the-reservation-api"></a>예약 API 호출

인벤토리 가시성 서비스에서 예약은 POST 요청을 서비스 URL(예: `/api/environment/{environment-ID}/onhand/reserve`)로 제출하여 이루어집니다.

예약의 경우 요청 본문에 조직 ID, 제품 ID, 예약 수량 및 차원이 포함되어야 합니다. 요청은 각 예약 레코드에 대해 고유한 예약 ID를 생성합니다. 예약 레코드에는 제품 ID와 치수의 고유한 조합이 포함됩니다.

예약 API를 호출할 때 요청 본문에 부울 `ifCheckAvailForReserv` 매개 변수를 지정하여 예약 유효성 검사를 제어할 수 있습니다. 값 `True`는 유효성 검사가 필요함을 의미하고 `False` 값은 유효성 검사가 필요하지 않음을 의미합니다. 기본값은 `True`입니다.

예약을 취소하거나 지정된 재고 수량을 예약 해제하려면 수량을 음수로 설정하고 `ifCheckAvailForReserv` 매개 변수를 `False`로 설정하여 유효성 검사를 건너뜁니다.

다음은 참조용으로 요청 본문의 예입니다.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Supply Chain Management의 상계 예약

지정된 예약 상쇄 수정자를 포함하는 재고 트랜잭션 상태의 경우 트랜잭션 업데이트는 다음 조건이 모두 충족될 때 해당 예약 레코드를 상쇄합니다.

- 인벤토리 트랜잭션의 예약 ID는 인벤토리 가시성 서비스의 예약 레코드 예약 ID와 일치합니다.
- 인벤토리 트랜잭션의 차원은 인벤토리 가시성 서비스의 예약 레코드 차원과 동일합니다.
- 재고 트랜잭션 상태가 주문 프로세스가 완료되거나 건너뛴 사실을 반영할 때 재고 트랜잭션 상태의 변경은 예약에 대한 상쇄를 트리거합니다.

상쇄 수량은 재고 트랜잭션에 지정된 재고 수량을 따릅니다. 인벤토리 가시성 서비스에 예약 수량이 남아 있지 않으면 오프셋이 적용되지 않습니다.

### <a name="set-up-the-reservation-offset-modifier"></a>예약 상쇄 수정자 설정

아직 설정하지 않은 경우 [예약 기능 켜기 및 설정에](#turn-on) 설명된 대로 예약 수정자를 설정합니다.

### <a name="set-up-reservation-ids"></a>예약 ID 설정

예약 ID는 인벤토리 가시성에서 예약 레코드를 고유하게 표시합니다. Supply Chain Management에서 사용자는 해당 예약 레코드의 상쇄를 표시하기 위해 주문 라인에 예약을 둡니다.

Supply Chain Management에서 예약 ID를 설정하려면 다음 단계를 따르세요.

1. 판매 주문을 엽니다(예: **모든 판매 주문** 페이지에서).
1. **판매 주문 라인** 빠른 탭에 주문 라인을 선택합니다.
1. **판매 주문 라인** 빠른 탭의 도구 모음에서 **업데이트 \> 재고 \> 인벤토리 가시성 통합** 을 선택합니다.
1. 관련 예약 ID를 입력합니다.

재고 상태 변경이 상쇄 수정자 설정과 일치합니다.
