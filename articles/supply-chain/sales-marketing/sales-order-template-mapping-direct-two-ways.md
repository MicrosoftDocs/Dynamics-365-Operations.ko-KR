---
title: Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화
description: 이 토픽에서는 Dynamics 365 Sales와 Dynamics 365 Supply Chain Management 간에 직접 판매 주문 동기화를 실행하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 05/09/2019
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
ms.openlocfilehash: eb41a21395a5d115b779e6b1ef71e9eb1176e28e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449818"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화

[!include [banner](../includes/banner.md)]



이 토픽에서는 Dynamics 365 Sales와 Dynamics 365 Supply Chain Management 간에 직접 판매 주문 동기화를 실행하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

## <a name="data-flow-in-prospect-to-cash"></a>잠재 고객의 결제 유도에서의 데이터 흐름

잠재 고객의 결제 유도 솔루션은 데이터 통합 기능을 사용하여 Supply Chain Management 및 Sales의 인스턴스 간에 데이터를 동기화합니다. 데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿을 사용하면 Supply Chain Management와 Sales 간에 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 가능합니다. 다음 그림은 Supply Chain Management와 Sales 간에 데이터가 동기화되는 방법을 보여줍니다.

[![잠재 고객의 결제 유도에서의 데이터 흐름.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업

사용 가능한 템플릿에 액세스하려면 [Power Apps 관리 센터](https://preview.admin.powerapps.com/dataintegration)를 엽니다. **프로젝트** 를 선택한 다음 오른쪽 위 모서리에서 **새 프로젝트** 를 선택하여 공개 템플릿을 선택합니다.

다음 템플릿 및 기본 작업은 Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화를 실행하는 데 사용됩니다.

- **데이터 통합의 템플릿 이름:** 

    - 판매 주문(Sales에서 Supply Chain Management로) - 직접
    - 판매 주문(Supply Chain Management에서 Sales로) - 직접

- **데이터 통합 프로젝트의 작업 이름:**

    - OrderHeader
    - OrderLine

판매 송장 헤더 및 라인을 동기화하려면 다음 동기화 태스크가 필요합니다.

- 제품(Supply Chain Management에서 Sales로) - 직접
- 계정(Sales에서 Supply Chain Management로) - 직접(사용한 경우)
- 고객에게 연락(Sales에서 Supply Chain Management로) - 직접(사용한 경우)

## <a name="entity-set"></a>엔터티 세트

| Supply Chain Management  | 영업             |
|-------------------------|-------------------|
| Dataverse 판매 주문 헤더 | SalesOrders       |
| Dataverse 판매 주문 라인   | SalesOrderDetails |

## <a name="entity-flow"></a>엔터티 흐름

**판매 주문(Sales에서 Supply Chain Management로) - 직접** 템플릿을 기반으로 하는 프로젝트에 대해 **프로젝트 실행** 이 트리거되면 판매 주문이 판매에서 생성되고 Supply Chain Management와 동기화됩니다. 모든 **주문 제품** 이 외부에서 유지 관리되는 제품으로 구성된 경우에만 Sales의 주문을 활성화하고 동기화할 수 있습니다. 따라서 기입된 제품이 없을 수 있습니다. 주문이 활성화되면 판매 주문은 UI(사용자 인터페이스)에서 읽기 전용이 됩니다. 이 시점에서 업데이트는 Supply Chain Management에서 이루어집니다. 판매 주문의 상태가 **확인됨** 이 되면 **판매 주문(Supply Chain Management에서 Sales로) - Direct** 템플릿을 기반으로 하는 프로젝트를 사용하여 Supply Chain Management에서 Sales로 업데이트 또는 주문 이행 상태를 동기화할 수 있습니다.

Sales에서 주문을 생성할 필요가 없습니다. 대신 Supply Chain Management에서 새 판매 주문을 생성할 수 있습니다. 판매 주문의 상태가 **확인됨** 이 되면 이전 단락에서 설명한 대로 판매 주문과 동기화됩니다.

Supply Chain Management에서 템플릿의 필터는 관련 판매 주문만 동기화에 포함되도록 보장합니다.

- 판매 주문에서 주문 고객과 송장 발행 고객은 모두 Sales에서 시작해야 동기화에 포함됩니다. Supply Chain Management에서 **OrderingCustomerIsExternallyMaintained** 및 **InvoiceCustomerIsExternallyMaintained** 열은 데이터 테이블에서 판매 주문을 필터링하는 데 사용됩니다.
- Supply Chain Management의 판매 주문을 확인해야 합니다. **배송됨** 또는 **송장 발행됨** 과 같이 처리 상태가 더 높은 확인된 판매 주문 또는 판매 주문만 판매와 동기화됩니다.
- 판매 주문을 생성하거나 수정한 후에는 Supply Chain Management에서 **판매 총액 계산** 배치 작업을 실행해야 합니다. 판매 합계가 계산되는 판매 주문만 판매와 동기화됩니다.

## <a name="freight-tax"></a>운임세

세금은 라인 레벨에서 저장되기 때문에 판매는 헤더 레벨에서 세금을 지원하지 않습니다. 운임에 대한 세금과 같이 Supply Chain Management의 헤더 레벨에서 세금을 지원하기 위해 시스템은 세금을 Sales에 동기화하고 이름이 **운임세** 이고 Supply Chain Management의 세액이 있는 기입 제품입니다. 이러한 방식으로 Supply Chain Management의 헤더 수준에 세금이 있는 경우에도 Sales의 표준 가격 계산을 총계에 사용할 수 있습니다.

## <a name="discount-calculation-and-rounding"></a>할인 계산 및 반올림

Sales의 할인 계산 모델은 Supply Chain Management의 할인 계산 모델과 다릅니다. Supply Chain Management에서 판매 라인의 최종 할인 금액은 할인 금액과 할인 비율을 조합한 결과일 수 있습니다. 이 최종 할인 금액을 라인의 수량으로 나누면 반올림이 발생할 수 있습니다. 그러나 반올림된 단위당 할인 금액이 판매와 동기화된 경우 이 반올림은 고려되지 않습니다. Supply Chain Management에서 판매 라인의 전체 할인 금액이 Sales와 올바르게 동기화되도록 하려면 라인 수량으로 나누지 않고 전체 금액을 동기화해야 합니다. 따라서 Sales에서 **라인 항목** 으로 **할인 계산 방법** 을 정의해야 합니다.

판매 주문 라인이 Sales에서 Supply Chain Management로 동기화되면 전체 라인 할인 금액이 사용됩니다. Supply Chain Management에는 라인에 대한 전체 할인 금액을 저장할 수 있는 필드가 없기 때문에 금액을 수량으로 나누어 **라인 할인** 필드에 저장합니다. 이 부서에서 발생하는 모든 반올림은 판매 라인의 **판매 비용** 필드에 저장됩니다.

### <a name="example"></a>예

**Sales에서 Supply Chain Management로 동기화**

- **판매:** 수량 = 3, 라인당 할인 = $10.00
- **Supply Chain Management:** 수량 = 3, 라인 할인 금액 = $3.33, 판매 수수료 = -$0.01 

**Supply Chain Management에서 Sales로 동기화**

- **Supply Chain Management:** 수량 = 3, 라인 할인 금액 = $3.33, 판매 수수료 = -$0.01
- **판매:** 수량 = 3, 라인당 할인 = (3 × $3.33) + $0.01 = $10.00

## <a name="prospect-to-cash-solution-for-sales"></a>Sales를 위한 잠재 고객의 결제 유도 솔루션

새 열이 **주문** 테이블에 추가되어 페이지에 나타납니다.

- **외부에서 관리됨** – 주문이 Supply Chain Management에서 오는 경우 이 옵션을 **예** 로 설정합니다.
- **처리 상태** – 이 열은 Supply Chain Management에서 주문의 처리 상태를 보여줍니다. 다음 값을 사용할 수 있습니다.

    - **초안** – Sales에서 주문이 생성된 초기 상태입니다. Sales에서는 이 처리 상태의 주문만 편집할 수 있습니다.
    - **활성** – **활성화** 단추를 사용하여 판매에서 주문이 활성화된 후의 상태입니다.
    - **확인됨**
    - **포장 전표**
    - **송장 발부됨**
    - **선택됨**
    - **부분적으로 선택됨**
    - **부분적으로 포장됨**
    - **발송됨**
    - **부분 배송됨**
    - **부분 청구됨**
    - **취소됨**

**외부에서 유지 관리되는 제품만 있음** 설정은 판매 주문이 완전히 외부에서 유지 관리되는 제품으로 구성되어 있는지 여부를 일관되게 추적하기 위해 주문 활성화 중에 사용됩니다. 판매 주문이 전적으로 외부에서 관리되는 제품으로 구성된 경우 제품은 Supply Chain Management에서 관리됩니다. 이 설정을 사용하면 Supply Chain Management에 알려지지 않은 제품이 있는 판매 주문 라인을 활성화하고 동기화하지 않도록 할 수 있습니다.

송장이 Supply Chain Management에서 생성되고 Sales와 동기화되기 때문에 **판매 주문** 페이지의 **송장 생성**, **주문 취소**, **재계산**, **제품 가져오기** 및 **주소 조회** 단추는 외부에서 유지 관리되는 주문에 대해 숨겨집니다. 활성화 후 Supply Chain Management에서 판매 주문 정보가 동기화되므로 이 주문을 편집할 수 없습니다.

판매 주문 상태는 Supply Chain Management의 변경 사항이 Sales의 판매 주문으로 흐를 수 있도록 보장하기 위해 **활성** 상태로 유지됩니다. 이 동작을 제어하려면 데이터 통합 프로젝트에서 기본 **Statecode\[상태\]** 값을 **활성** 으로 설정하세요.

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

판매 주문을 동기화하기 전에 시스템에서 다음 설정을 업데이트하는 것이 중요합니다.

### <a name="setup-in-sales"></a>Sales 설정

- Sales 연결 집합의 사용자가 할당된 팀에 대한 권한이 설정되어 있는지 확인하세요. 데모 데이터를 사용하는 경우 일반적으로 사용자에게 관리자 액세스 권한이 있지만 팀에는 관리자 액세스 권한이 없습니다. 팀에 관리자 액세스 권한이 없는 경우 데이터 통합에서 프로젝트를 실행할 때 주도자 팀이 없다는 오류 메시지를 받게 됩니다.

    **설정** &gt; **보안** &gt; **팀** 으로 이동하여 해당 팀을 선택하고 **역할 관리** 를 선택하고 **시스템 관리자** 와 같이 원하는 권한이 있는 역할을 선택합니다.

- Sales 및 Supply Chain Management 모두에서 할인을 올바르게 계산하려면 **할인 계산 방법** 을 **항목** 으로 설정해야 합니다.
- **설정** &gt; **관리** &gt; **시스템 설정** &gt; **영업** 으로 이동하여 다음 설정이 사용되었는지 확인합니다.

    - **시스템 상금 계산 시스템** 옵션이 **예** 로 설정되어 있습니다.
    - **할인 계산 방법** 열이 **라인 항목** 으로 설정됩니다.

### <a name="setup-in-supply-chain-management"></a>Supply Chain Management 설정

- **영업 및 마케팅** &gt; **정기 작업** &gt; **판매 합계 계산** 으로 이동하고 배치 작업으로 실행되도록 작업을 설정합니다. **판매 주문 합계 계산** 옵션을 **예** 로 설정합니다. 판매 합계가 계산되는 판매 주문만 판매와 동기화되기 때문에 이 단계는 중요합니다. 배치 작업의 빈도는 판매 주문 동기화 빈도와 일치해야 합니다.

작업 주문 통합도 사용하는 경우 판매 출처를 설정해야 합니다. 판매 출처는 Field Service의 작업 주문에서 생성된 Supply Chain Management의 판매 주문을 구별하는 데 사용됩니다. 판매 주문에 **작업 주문 통합** 유형의 판매 출처가 있는 경우 **외부 작업 주문 상태** 필드가 판매 주문 헤더에 나타납니다. 또한 판매 출처는 Field Service의 작업 주문에서 생성된 판매 주문이 Supply Chain Management에서 Field Service로 판매 주문 동기화 중에 필터링되도록 합니다.

1. **영업 및 마케팅** \> **설정** \> **판매 주문** \> **판매 출처** 로 이동합니다.
2. **새로 만들기** 를 선택하여 판매 출처를 만듭니다.
3. **판매 출처** 열에 판매 출처의 이름(예: **SalesOrder**)을 입력합니다.
4. **설명** 열에 **Sales의 판매 주문** 과 같은 설명을 입력합니다.
5. **출처 유형 할당** 확인란을 선택합니다.
6. **판매 출처 유형** 열을 **판매 주문 통합** 으로 설정합니다.
7. **저장** 을 선택합니다.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>판매 주문 설정(Sales에서 Supply Chain Management로) - 직접 데이터 통합 프로젝트

- **Shipto\_country** 에서 **DeliveryAddressCountryRegionISOCode** 로의 필수 매핑이 있는지 확인하세요. 국가 주문에 대해 국가를 입력하지 않아도 되도록 값 맵에서 기본값을 비워 둘 수 있습니다. 왼쪽은 '공백'으로, 오른쪽은 원하는 국가나 지역으로 설정합니다.

    템플릿 값은 여러 국가 또는 지역이 매핑된 값 맵이며 '공백' = 미국입니다.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>판매 주문 설정(Supply Chain Management에서 Sales로) - 직접 데이터 통합 프로젝트

#### <a name="salesheader-task"></a>SalesHeader 태스크

- Sales에서 주문을 생성하려면 가격 목록이 필요합니다. **pricelevelid.name\[가격 목록 이름\]** 에 대한 값 맵을 통화당 판매에 사용되는 가격 목록으로 업데이트하세요. 단일 통화에 대해 기본 가격 목록을 사용할 수 있습니다. 또는 여러 통화로 된 가격 목록이 있는 경우 값 맵을 사용할 수 있습니다.

    **pricelevelid.name\[가격 목록 이름\]** 의 기본 템플릿 값은 **CRM Service USA(샘플)** 입니다.

#### <a name="salesline-task"></a>SalesLine 태스크

- Supply Chain Management의 **SalesUnitSymbol** 에 필요한 값 맵이 있는지 확인합니다.
- 필요한 단위가 Sales에 정의되어 있는지 확인하세요.

    값 맵이 있는 템플릿 값은 **SalesUnitSymbol** 에서 **oumid.name** 으로 정의됩니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

> [!NOTE]
> **결제 조건**, **운임 조건**, **배송 조건**, **배송 방법**, **배송 모드** 열은 기본 매핑에 포함되지 않습니다. 이러한 열을 매핑하려면 테이블이 동기화되는 조직의 데이터와 관련된 값 매핑을 설정해야 합니다.

다음 그림은 데이터 통합에서 템플릿 매핑의 예를 보여줍니다.

> [!NOTE]
> 매핑은 Sales에서 Supply Chain Management로 또는 Supply Chain Management에서 Sales로 동기화될 열 정보를 보여줍니다.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>판매 주문(Supply Chain Management에서 Sales로) - 직접: OrderHeader

[![데이터 통합의 템플릿 매핑, 판매 주문(Supply Chain Management에서 Sales로) - 직접: OrderHeader.](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>판매 주문(Supply Chain Management에서 Sales로) - 직접: OrderLine

[![데이터 통합의 템플릿 매핑, 판매 주문(Supply Chain Management에서 Sales로) - 직접: OrderLine.](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>판매 주문(Sales에서 Supply Chain Management로) - 직접: OrderHeader

[![데이터 통합의 템플릿 매핑, 판매 주문(Sales에서 Supply Chain Management로) - 직접: OrderHeader.](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>판매 주문(Sales에서 Supply Chain Management로) - 직접: OrderLine

[![데이터 통합의 템플릿 매핑, 판매 주문(Sales에서 Supply Chain Management로) - 직접: OrderLine.](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>관련 토픽

[잠재 고객의 결제 유도](prospect-to-cash.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]