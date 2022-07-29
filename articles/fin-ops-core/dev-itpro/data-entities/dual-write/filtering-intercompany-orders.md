---
title: Orders 및 OrderLines 동기화를 방지하기 위해 회사 간 주문 필터링
description: 이 항목에서는 Orders 및 OrderLines 엔터티가 동기화되지 않도록 회사 간 주문을 필터링하는 방법에 대해 설명합니다.
author: negudava
ms.date: 11/09/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: negudava
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8575f38ca23ef245947a41c35846983604662ef2
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8461000"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Orders 및 OrderLines 동기화를 방지하기 위해 회사 간 주문 필터링

[!include [banner](../../includes/banner.md)]

**Orders** 및 **OrderLines** 테이블이 동기화되지 않도록 내부 거래 주문을 필터링할 수 있습니다. 일부 시나리오에서는 Customer Engagement 앱에 회사 간 주문 세부 정보가 필요하지 않습니다.

각 표준 Dataverse 테이블은 **IntercompanyOrder** 열에 대한 참조를 통해 확장되며 이중 쓰기 맵이 필터의 추가 열을 참조하도록 수정됩니다. 따라서 회사 간 주문이 더 이상 동기화되지 않습니다. 이 프로세스는 Customer Engagement 앱에서 불필요한 데이터를 방지하는 데 도움이 됩니다.

1. **IntercompanyOrder** 열에 대한 참조를 추가하여 **CDS 판매 주문 헤더** 를 연장합니다. 이 열은 내부 거래 주문에 대해서만 채워집니다. **IntercompanyOrder** 열은 **SalesTable** 테이블에서 사용할 수 있습니다.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="CDS 판매 주문 헤더의 대상 페이지에 스테이징을 매핑합니다.":::

2. **CDS 판매 주문 헤더** 가 연장된 후 **IntercompanyOrder** 열을 매핑에서 사용할 수 있습니다. 쿼리 문자열로 `INTERCOMPANYORDER == ""`가 있는 필터를 적용합니다.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="CDS 판매 주문 헤더에 대한 쿼리 편집 대화 상자.":::

3. **IntercompanyInventTransId** 열에 대한 참조를 추가하여 **CDS 판매 주문 라인** 을 연장합니다. 이 열은 내부 거래 주문에 대해서만 채워집니다. **InterCompanyInventTransId** 열은 **SalesLine** 테이블에서 사용할 수 있습니다.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="CDS 판매 주문 라인의 대상 페이지에 스테이징을 매핑합니다.":::

4. **CDS 판매 주문 라인** 이 연장된 후 **IntercompanyInventTransId** 열을 매핑에서 사용할 수 있습니다. 쿼리 문자열로 `INTERCOMPANYINVENTTRANSID == ""`가 있는 필터를 적용합니다.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="CDS 판매 주문 라인에 대한 쿼리 편집 대화 상자.":::

5. 1단계와 2단계를 반복하여 **판매 송장 헤더 V2** 테이블을 확장하고 필터 쿼리를 추가합니다. 이 경우 `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`를 필터에 대한 쿼리 문자열로 사용합니다.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="판매 청구서 헤더 V2의 대상 페이지에 스테이징을 매핑합니다.":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="판매 청구서 헤더 V2에 대한 쿼리 편집 대화 상자.":::

6. 3단계와 4단계를 반복하여 **판매 송장 라인 V2** 테이블을 확장하고 필터 쿼리를 추가합니다. 이 경우 `INTERCOMPANYINVENTTRANSID == ""`를 필터에 대한 쿼리 문자열로 사용합니다.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="판매 청구서 라인 V2에 대한 쿼리 편집 대화 상자.":::

7. **견적** 테이블에 회사 간 관계가 없습니다. 누군가가 내부 거래 고객 중 한 명에 대한 견적을 생성하는 경우 **CustGroup** 열을 사용하여 해당 모든 고객을 하나의 고객 그룹에 넣습니다. **CustGroup** 열을 추가하여 헤더와 라인을 확장한 다음 그룹이 포함되지 않도록 필터링합니다.

    :::image type="content" source="media/filter-cust-group.png" alt-text="CDS 판매 견적 헤더의 대상 페이지에 스테이징을 매핑합니다.":::

8. **견적** 을 확장한 후에 `CUSTGROUP != "<company>"`이 쿼리 문자열인 필터를 적용합니다.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="CDS 판매 견적 헤더에 대한 쿼리 편집 대화 상자.":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]