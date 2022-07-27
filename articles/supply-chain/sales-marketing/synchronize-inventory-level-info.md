---
title: Supply Chain Management에서 Field Service로 인벤토리 수준 정보 동기화
description: 이 토픽에서는 인벤토리 수준 정보를 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 05/07/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 8dfba2d2dc2fdd4af136e3cb20061d794369011f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449806"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Supply Chain Management에서 Field Service로 인벤토리 수준 정보 동기화 

[!include[banner](../includes/banner.md)]



이 토픽에서는 인벤토리 수준 정보를 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업
다음 템플릿 및 기본 작업은 인벤토리 현인벤토리 수준을 Supply Chain Management에서 Field Service로 동기화하는 데 사용됩니다.

**데이터 통합의 템플릿**
- 상품 인벤토리(Supply Chain Management에서 Field Service로)
  
**데이터 통합 프로젝트의 작업**
- 상품 인벤토리

인벤토리 수준의 동기화를 수행하려면 다음 동기화 작업이 필요합니다.
- 창고(Supply Chain Management에서 Field Service로) 
- Field Service 상품 인벤토리 단위(Supply Chain Management에서 Sales로) 

## <a name="entity-set"></a>엔터티 세트

| Field Service                      | Supply Chain Management                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Dataverse창고별 인벤토리 현인벤토리     |

## <a name="entity-flow"></a>엔터티 흐름
재무 및 운영의 인벤토리 수준 정보는 선택한 제품에 대해 Field Service로 전송됩니다. 인벤토리 수준 정보에는 다음이 포함됩니다. 
- 현인벤토리 수량(창고에 있는 현재 기록된 물리적 수량)
- 주문 수량(판매 주문 등 주문에 대해 기록된 총 수량)
- 주문 수량(구매 주문과 같이 기록된 총 주문 수량)

이 정보는 각 창고에 대해 출시된 제품별로 캡처되고 인벤토리 수준이 변경될 때 변경 내용 추적을 기반으로 동기화됩니다.

Field Service에서 통합 솔루션은 델타에 대한 인벤토리 분개장을 만들어 Field Service의 수준이 Supply Chain Management의 수준과 일치하도록 합니다.

Supply Chain Management는 인벤토리 수준의 마스터 역할을 합니다. 따라서 이 기능이 Field Service에서 사용되는 경우 Supply Chain Management의 인벤토리 수준 동기화와 함께 Field Service에서 Supply Chain Management로의 작업 주문, 이전 및 조정에 대한 통합을 설정하는 것이 중요합니다.

Supply Chain Management에서 인벤토리 수준이 마스터링되는 제품 및 창고는 고급 쿼리 및 필터링(Power Query)으로 제어할 수 있습니다.

> [!NOTE]
> Field Service에서 여러 창고를 만든 다음(**외부적으로 유지 관리됨 = 아니요**) 고급 쿼리 및 필터링 기능을 사용하여 Supply Chain Management의 단일 창고에 매핑할 수 있습니다. 이것은 Field Service가 상세한 인벤토리 수준을 마스터하고 Supply Chain Management에 업데이트만 보내도록 하려는 상황에서 사용됩니다. 이 경우 Field Service는 Supply Chain Management에서 재고 수준 업데이트를 수신하지 않습니다. 자세한 내용은 [Field Service의 인벤토리 조정을 Supply Chain Management로 동기화](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) 및 [Field Service의 작업 주문을 Supply Chain Management의 프로젝트에 연결된 판매 주문과 동기화](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)를 참조하세요.

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션
**외부 제품 인벤토리** 엔터티는 통합에 대한 백엔드에만 사용됩니다. 이 엔터티는 통합의 Supply Chain Management에서 인벤토리 수준 값을 받은 다음 해당 값을 수동 인벤토리 분개장으로 변환한 다음 창고의 인벤토리 제품을 변경합니다.

## <a name="prerequisites-and-mapping-setup"></a>전제 조건 및 매핑 설정

### <a name="data-integration"></a>데이터 통합
프로젝트가 작동하려면 msdynce_externalproductinventories에 대한 통합 키가 업데이트되었는지 확인해야 합니다.
1.  **데이터 통합 > 연결 세트** 로 이동합니다.
2.  사용된 연결 세트를 선택합니다.
3.  **통합 키** 탭에서 다음 키가 msdynce_externalproductinventories에 추가되었는지 확인합니다.
      - msdynce_productnumber(제품 번호)
      - msdynce_warehouseid(창고 ID)
      
### <a name="data-integration-project"></a>데이터 통합 프로젝트
특정 제품 및 창고만 Supply Chain Management에서 Field Service로 인벤토리 수준 정보를 보내도록 고급 쿼리 및 필터링을 사용하여 필터를 적용할 수 있습니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>상품 인벤토리(Supply Chain Management에서 Field Service로): 상품 인벤토리

[![데이터 통합의 템플릿 매핑.](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]