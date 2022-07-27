---
title: Supply Chain Management에서 Sales로 직접 판매 송장 헤더 및 라인 동기화
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Sales로 직접 판매 송장 헤더 및 라인을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: c2f988b4f170c027444ba7cf54a55e0bd846cedf
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448441"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Supply Chain Management에서 Finance and Operations로 직접 판매 송장 헤더 및 라인 동기화

[!include [banner](../includes/banner.md)]

이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Sales로 직접 판매 송장 헤더 및 라인을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

## <a name="data-flow-in-prospect-to-cash"></a>잠재 고객의 결제 유도에서의 데이터 흐름

잠재 고객의 결제 유도 솔루션은 데이터 통합 기능을 사용하여 Supply Chain Management 및 Sales의 인스턴스 간에 데이터를 동기화합니다. 데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿을 사용하면 Supply Chain Management와 Sales 간에 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 가능합니다. 다음 그림은 Supply Chain Management와 Sales 간에 데이터가 동기화되는 방법을 보여줍니다.

[![잠재 고객의 결제 유도에서의 데이터 흐름.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업

사용 가능한 템플릿에 액세스하려면 [Power Apps 관리 센터](https://preview.admin.powerapps.com/dataintegration)를 엽니다. **프로젝트** 를 선택한 다음 오른쪽 위 모서리에서 **새 프로젝트** 를 선택하여 공개 템플릿을 선택합니다.

다음 템플릿 및 기본 태스크는 Supply Chain Management의 판매 송장 헤더 및 라인을 Sales로 동기화하는 데 사용됩니다.

- **데이터 통합의 템플릿 이름:** 판매 송장(Fin 및 Ops에서 Sales로) - 직접
- **데이터 통합 프로젝트의 작업 이름:**

    - SalesInvoiceHeader
    - SalesInvoiceLine

판매 송장 헤더 및 라인을 동기화하려면 다음 동기화 태스크가 필요합니다.

- 제품(Supply Chain Management에서 Sales로) - 직접
- 계정(Sales에서 Supply Chain Management로) - 직접(사용한 경우)
- 연락처(Sales에서 Supply Chain Management로) - 직접(사용한 경우)
- 판매 주문 헤더 및 라인(Supply Chain Management에서 Sales로) - 직접

## <a name="entity-set"></a>엔터티 세트

| Supply Chain Management                              | 영업          |
|------------------------------------------------------|----------------|
| 외부에서 유지 관리하는 고객 판매 송장 헤더 | 송장       |
| 외부에서 유지 관리하는 고객 판매 송장 라인   | InvoiceDetails |

## <a name="entity-flow"></a>엔터티 흐름

판매 송장은 Supply Chain Management에서 생성되고 Sales와 동기화됩니다.

> [!NOTE]
> 현재 판매 송장 헤더의 비용과 관련된 세금은 Supply Chain Managements에서 Sales로의 동기화에 포함되지 않습니다. Sales는 헤더 수준에서 세금 정보를 지원하지 않습니다. 그러나 라인 레벨의 비용과 관련된 세금은 동기화에 포함됩니다.

## <a name="prospect-to-cash-solution-for-sales"></a>Sales를 위한 잠재 고객의 결제 유도 솔루션

- **송장 번호** 필드가 **송장** 엔터티에 추가되었으며 페이지에 나타납니다.
- 송장이 Supply Chain Management에서 생성되고 Sales와 동기화되기 때문에 **판매 주문** 페이지의 **송장 생성** 단추는 숨겨져 있습니다. 송장이 Supply Chain Management에서 동기화되므로 **송장** 페이지를 편집할 수 없습니다.
- Supply Chain Management의 관련 송장이 Sales와 동기화되면 **판매 주문 상태** 값이 자동으로 **송장 발행** 으로 변경됩니다. 또한 송장이 생성된 판매 주문의 담당자가 송장의 담당자로 지정됩니다. 따라서 판매 주문의 담당자는 송장을 볼 수 있습니다.

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

판매 송장을 동기화하기 전에 시스템에서 다음 설정을 업데이트하는 것이 중요합니다.

### <a name="setup-in-sales"></a>Sales 설정

**설정** > **관리** > **시스템 설정** > **영업** 으로 이동하여 다음 설정이 사용되는지 확인합니다.

- **시스템 상금 계산 시스템** 옵션이 **예** 로 설정되어 있습니다.
- **할인 계산 방법** 필드가 **라인 항목** 으로 설정됩니다.

### <a name="setup-in-the-data-integration-project"></a>데이터 통합 프로젝트에서 설정

#### <a name="salesinvoiceheader-task"></a>SalesInvoiceHeader 태스크

- **InvoiceCountryRegionId** 에서 **BillingAddress\_Country** 에 대한 필수 매핑이 있는지 확인하세요.

    템플릿 값은 여러 국가 또는 지역이 매핑된 값 맵입니다.

- Sales에서 송장을 생성하려면 가격 목록이 필요합니다. **pricelevelid.name\[가격 목록 이름\]** 에 대한 값 맵을 통화당 판매에 사용되는 가격 목록으로 업데이트하세요. 단일 통화에 대해 기본 가격 목록을 사용할 수 있습니다. 또는 여러 통화로 된 가격 목록이 있는 경우 값 맵을 사용할 수 있습니다.

    **pricelevelid.name\[가격 목록 이름\]** 의 템플릿 값은 USD = CRM Service USA(샘플)인 통화를 기반으로 하는 값 맵입니다.  
    
#### <a name="salesinvoiceline-task"></a>SalesInvoiceLine 태스크

- **측정 단위** 에 필요한 매핑이 있는지 확인합니다.
- Supply Chain Management의 **SalesUnitSymbol** 에 필요한 값 맵이 있는지 확인합니다.

    값 맵이 있는 템플릿 값은 **SalesUnitSymbol** 에서 **Quantity\_UOM** 으로 정의됩니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

> [!NOTE]
> **지불 조건**, **운임 조건**, **배송 조건**, **배송 방법** 및 **배송 모드** 필드는 기본 매핑에 포함되지 않습니다. 이러한 필드를 매핑하려면 엔터티가 동기화되는 조직의 데이터와 관련된 값 매핑을 설정해야 합니다.

다음 그림은 데이터 통합에서 템플릿 매핑의 예를 보여줍니다. 

> [!NOTE]
> 매핑은 Sales에서 Supply Chain Management로 동기화될 필드 정보를 보여줍니다.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![SalesInvoiceHeader에 대한 데이터 통합의 템플릿 매핑.](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![SalesInvoiceLine에 대한 데이터 통합의 템플릿 매핑.](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>관련 토픽

[잠재 고객의 결제 유도](prospect-to-cash.md)

[Sales에서 Supply Chain Management의 고객으로 직접 계정 동기화](accounts-template-mapping-direct.md)

[Supply Chain Management에서 Sales의 제품으로 직접 제품 동기화](products-template-mapping-direct.md)

[Sales에서 Supply Chain Management의 연락처 또는 고객으로 직접 연락처 동기화](contacts-template-mapping-direct.md)

[Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화](sales-order-template-mapping-direct-two-ways.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]