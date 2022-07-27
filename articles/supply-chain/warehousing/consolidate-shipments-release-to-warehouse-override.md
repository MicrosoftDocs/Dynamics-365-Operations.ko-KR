---
title: 배송 통합 정책이 무효화된 경우 배송 통합
description: 이 항목은 하나 이상의 판매 라인을 창고로 릴리즈 페이지에서 창고로 수동으로 릴리즈해야 하고 릴리즈 전에 시스템 정의 선적 통합 정책을 재정의해야 하는 시나리오를 나타냅니다.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 606f370277b67a65612d81916f4fcc93ca47224e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448699"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden"></a>배송 통합 정책이 무효화된 경우 배송 통합

[!include [banner](../includes/banner.md)]

이 항목은 하나 이상의 판매 라인을 **창고로 릴리즈** 페이지에서 창고로 수동으로 릴리즈해야 하고 릴리즈 전에 시스템 정의 선적 통합 정책을 재정의해야 하는 시나리오를 나타냅니다. 예를 들어, 일반적으로 미결 배송으로 통합되지 않는 주문을 미결제 배송으로 통합해야 하는 경우 배송 통합 정책을 재정의해야 할 수 있습니다.

시나리오 중에 판매 주문 세트를 생성한 다음 창고로 주문을 릴리즈하기 전에 기본 배송 통합 정책을 재정의합니다.

## <a name="make-demo-data-available"></a>데모 데이터 사용 가능

이 토픽의 시나리오는 Microsoft Dynamics 365 Supply Chain Management에 제공되는 표준 데모 데이터에 포함된 값과 레코드를 참조합니다. 연습을 하면서 여기에 제공된 값을 사용하려면 데모 데이터가 설치된 환경에서 작업하고 시작하기 전에 법인을 **USMF** 로 설정해야 합니다.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>배송 통합 정책 및 제품 필터 설정

여기에 설명된 시나리오는 이미 기능을 켜고 [배송 통합 정책 구성](configure-shipment-consolidation-policies.md)에서 연습을 완료했으며 거기에 설명된 정책 및 기타 기록을 만들었다고 가정합니다. 이 시나리오를 계속하기 전에 이러한 연습을 수행해야 합니다.

## <a name="create-the-sales-orders-for-this-scenario"></a>이 시나리오에 대한 판매 주문 생성

1. **수취 계정 \> 주문 \> 모든 판매 주문** 으로 이동하고 다음 설정을 가진 세 개의 동일한 판매 주문을 생성합니다.

    - **고객 계정** *US-002*

1. 다음 설정이 있는 주문 라인을 추가합니다.

    - **품목 번호:** *A0001*(**코드 4** 필터가 할당되지 않은 항목)
    - **수량:** *1.00*

1. **재고 \> 예약** 을 선택한 다음 작업 창에서 **부지 확보** 를 선택하여 주문 라인을 예약합니다.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>창고로 릴리즈 페이지에서 판매 주문 릴리즈

창고로 출고되는 동안 배송 통합 정책을 무시하려면 다음 단계를 따르세요.

1. **창고 관리 \> 창고로 출고 \> 창고로 릴리스** 로 이동합니다.
1. 위쪽 창에서 이 시나리오에 대해 생성한 첫 번째 판매 주문을 선택합니다.
1. **추가** 를 선택하여 창고에 대한 릴리즈에 라인을 추가합니다. *기본* 배송 통합 정책은 하단 창에 적용됩니다.
1. 하단 창에서 **새 배송 통합 정책 선택** 을 선택합니다.
1. 동일한 정책의 다른 미결 발송물과의 통합을 허용하는 정책을 선택합니다. 예를 들어, *CustomerOrderNo* 정책을 선택합니다.
1. **창고로 릴리스** 를 선택합니다.
1. 이 시나리오에 대해 생성한 두 번째 및 세 번째 판매 주문을 선택합니다.
1. **추가** 를 선택하여 창고에 대한 릴리즈에 라인을 추가합니다. *기본* 정책은 하단 창에 적용됩니다.
1. 두 번째 라인을 선택한 다음 **새 배송 통합 정책 선택** 필드에서 *CustomerOrderNo* 정책을 선택합니다.
1. 두 라인에 대해 **창고로 출고** 를 선택합니다.

## <a name="verify-the-shipments"></a>배송 확인

두 개의 배송이 생성되어야 합니다.

- 첫 번째 배송에는 두 개의 라인이 포함되어 있으며 *CustomerOrderNo* 배송 통합 정책을 사용하여 생성되었습니다.
- 두 번째 배송에는 하나의 라인이 포함되어 있으며 *기본값* 배송 통합 정책을 사용하여 생성되었습니다.

생성된 발송물을 검토하려면 다음 단계를 따르세요.

1. **창고 관리 \> 배송 \> 모든 배송** 으로 이동합니다.
1. 필요한 배송을 찾아 선택합니다.
1. **배송 통합 정책** 필드에서 배송이 생성될 때 사용된 통합 정책을 검토합니다.

## <a name="additional-resources"></a>추가 리소스

- [배송 통합 정책](about-shipment-consolidation-policies.md)
- [배송 통합 정책 구성](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]