---
title: 선적 통합 페이지를 사용하여 수동으로 선적 통합
description: 이 항목은 동일한 자동화된 창고로의 출고 주기 절차로 여러 주문이 창고로 출고되고 배송 통합 페이지를 사용하여 나중에 통합됩니다.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0da98b24b9e0ab1ae19fd353ec226b2e0ab008fe
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448702"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>선적 통합 페이지를 사용하여 수동으로 선적 통합

[!include [banner](../includes/banner.md)]

이 항목은 동일한 자동화된 창고로의 출고 주기 절차로 여러 주문이 창고로 출고되고 **배송 통합** 페이지를 사용하여 나중에 통합됩니다.

## <a name="make-demo-data-available"></a>데모 데이터 사용 가능

이 토픽의 시나리오는 Microsoft Dynamics 365 Supply Chain Management에 제공되는 표준 데모 데이터에 포함된 값과 레코드를 참조합니다. 연습을 하면서 여기에 제공된 값을 사용하려면 데모 데이터가 설치된 환경에서 작업하고 시작하기 전에 법인을 **USMF** 로 설정해야 합니다.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>배송 통합 정책 및 제품 필터 설정

여기에 설명된 시나리오는 이미 기능을 켜고 [배송 통합 정책 구성](configure-shipment-consolidation-policies.md)에서 연습을 완료했으며 거기에 설명된 정책 및 기타 기록을 만들었다고 가정합니다. 이 시나리오를 계속하기 전에 이러한 연습을 수행해야 합니다.

## <a name="create-the-sales-orders-for-this-scenario"></a>이 시나리오에 대한 판매 주문 생성

작업할 수 있는 판매 주문 모음을 만드는 것으로 시작합니다. 고급 웨어하우스(WMS) 프로세스에 대해 사용 가능한 웨어하우스에 대해 작업해야 합니다. 다른 창고가 명시적으로 언급되지 않는 한 다음 주문 세트 각각에 대해 동일한 창고를 사용해야 합니다.

**수취 계정 \> 주문 \> 모든 판매 주문** 으로 이동하고 다음 하위 섹션에 설명된 설정이 있는 판매 주문 컬렉션을 만듭니다.

### <a name="create-sales-orders-1-and-2"></a>판매 주문 1 및 2 만들기

1. 다음 설정이 있는 두 개의 동일한 판매 주문을 만듭니다.

    - **고객 계정** *US-007*
    - **풀:** *ShipCons*

1. 다음 설정이 있는 주문 라인을 추가합니다.

    - **품목 번호:** *A0001*(**코드 4** 필터가 할당되지 않은 항목)
    - **수량:** *1.00*

1. **재고 \> 예약** 을 선택한 다음 작업 창에서 **부지 확보** 를 선택하여 주문 라인을 예약합니다.

### <a name="create-sales-orders-3-and-4"></a>판매 주문 3 및 4 만들기

1. 다음 설정이 있는 두 개의 동일한 판매 주문을 만듭니다.

    - **고객 계정** *US-007*
    - **풀:** 이 필드를 비워 둡니다.

1. 다음 설정이 있는 주문 라인을 추가합니다.

    - **품목 번호:** *A0001*(**코드 4** 필터가 할당되지 않은 항목)
    - **수량:** *1.00*

1. **재고 \> 예약** 을 선택한 다음 작업 창에서 **부지 확보** 를 선택하여 주문 라인을 예약합니다.

## <a name="release-the-orders-to-the-warehouse"></a>주문을 웨어하우스로 릴리스

다음 단계에 따라 이 시나리오에 대해 생성한 각 판매 주문을 창고로 릴리스합니다.

1. **수령 가능한 계정 \> 주문 \> 모든 판매 주문** 으로 이동합니다.
1. 릴리즈할 판매 오더를 찾아 선택합니다.
1. 작업 창의 **창고** 탭에서 **작업 \> 창고로 출고** 를 선택하여 선택한 판매 주문을 릴리스합니다.
1. 이 시나리오에 대해 생성한 모든 다른 판매 주문에 대해 이 절차를 반복합니다.

## <a name="consolidate-shipments"></a>배송 통합

1. **창고 관리 \> 배송 \> 모든 배송** 으로 이동합니다.
1. 판매 주문 1이 창고로 출고될 때 생성된 배송을 찾아 선택합니다. (**배송 통합 정책** 필드는 *주문 풀* 로 설정되어야 합니다.)
1. 작업 창의 **배송** 탭에서 **배송 \> 배송 통합** 을 선택합니다.
1. 통합을 위해 제안된 배송을 확인합니다. 동일한 정책을 가진 하나의 배송만 통합을 위해 제안되어야 합니다.
1. **배송 통합** 페이지를 닫습니다.
1. 판매 주문 3이 창고로 출고될 때 생성된 배송을 찾아 선택합니다. (**배송 통합 정책** 필드는 *기본값* 으로 설정되어야 합니다.)
1. 작업 창의 **배송** 탭에서 **배송 \> 배송 통합** 을 선택합니다.
1. 통합을 위해 제안된 배송이 없는지 확인합니다.
1. **필터 표시** 를 선택합니다.
1. **필터** 창에서 **주문 번호** 를 제거한 다음 **적용** 을 선택합니다.
1. 통합을 위해 제안된 배송을 확인합니다. 동일한 정책을 가진 하나의 배송만 통합을 위해 제안되어야 합니다.

## <a name="additional-resources"></a>추가 리소스

- [배송 통합 정책](about-shipment-consolidation-policies.md)
- [배송 통합 정책 구성](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]