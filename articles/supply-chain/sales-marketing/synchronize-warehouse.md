---
title: Supply Chain Management에서 Field Service로 창고 동기화
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 창고를 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 03/13/2019
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
ms.openlocfilehash: f38d2dfdba1f2afa1005bd740cba27afe9dcb0ec
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449833"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Supply Chain Management에서 Field Service로 창고 동기화

[!include[banner](../includes/banner.md)]



이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 창고를 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업
다음 템플릿 및 기본 작업은 Supply Chain Management에서 Field Service로 창고 동기화를 실행하는 데 사용됩니다.

**데이터 통합의 템플릿**
- 창고(Supply Chain Management에서 Field Service로)

**데이터 통합 프로젝트의 작업**
- 창고

## <a name="table-set"></a>테이블 세트
| Field Service    | Supply Chain Management                 |
|------------------|----------------------------------------|
| msdyn_warehouses | 창고                             |

## <a name="table-flow"></a>테이블 흐름
Supply Chain Management에서 생성 및 유지 관리하는 창고는 Microsoft Dataverse 데이터 통합 프로젝트를 통해 Field Service와 동기화할 수 있습니다. Field Service와 동기화하려는 창고는 프로젝트에 대한 고급 쿼리 및 필터링을 사용하여 제어할 수 있습니다. Supply Chain Management에서 동기화하는 창고는 **외부에서 유지됨** 열이 **예** 로 설정된 Field Service에서 생성되고 레코드는 읽기 전용입니다.

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션
Field Service와 Supply Chain Management 간의 통합을 지원하려면 Field Service CRM 솔루션의 추가 기능이 필요합니다. 솔루션에서 **외부에서 유지 관리됨** 열이 **창고(msdyn_warehouses)** 테이블에 추가되었습니다. 이 열은 창고가 Supply Chain Management에서 처리되는지 또는 Field Service에만 존재하는지 식별하는 데 도움이 됩니다. 이 열에 대한 설정은 다음과 같습니다.
- **예** – 창고는 Supply Chain Management에서 시작되었으며 Sales에서 편집할 수 없습니다.
- **아니요** – 창고는 Field Service에 직접 입력되었으며 여기에서 유지 관리됩니다.

**외부에서 유지 관리됨** 열은 작업 주문에 대한 재고 수준, 조정, 이전 및 사용량의 동기화를 제어하는 데 도움이 됩니다. **외부에서 유지 관리됨** 이 **예** 로 설정된 창고만 다른 시스템의 동일한 창고로 직접 동기화하는 데 사용할 수 있습니다. 

> [!NOTE]
> Field Service에서 여러 창고를 만든 다음(**외부적으로 유지 관리됨** = 아니요) 고급 쿼리 및 필터링 기능을 사용하여 단일 창고에 매핑할 수 있습니다. 이것은 Field Service가 상세한 재고 수준을 마스터하고 Supply Chain Management에 업데이트만 보내도록 하려는 상황에서 사용됩니다. 이 경우 Field Service는 Supply Chain Management에서 재고 수준 업데이트를 수신하지 않습니다. 자세한 내용은 [Field Service의 재고 조정을 Finance and Operations로 동기화](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) 및 [Field Service의 작업 주문을 Finance and Operations의 프로젝트에 연결된 판매 주문과 동기화](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)를 참조하세요.

## <a name="prerequisites-and-mapping-setup"></a>전제 조건 및 매핑 설정
### <a name="data-integration-project"></a>데이터 통합 프로젝트
창고를 동기화하기 전에 Supply Chain Management에서 Field Service로 가져올 창고만 포함하도록 프로젝트에 대한 고급 쿼리 및 필터링을 업데이트해야 합니다. 작업 주문, 조정 및 이전에 적용하려면 Field Service의 창고가 필요합니다.  

**msdyn_warehouses** 에 대한 **통합 키** 가 있는지 확인하려면:
1. 데이터 통합으로 이동합니다.
2. **연결 세트** 탭을 선택합니다.
3. 작업 주문 동기화에 사용되는 연결 집합을 선택합니다.
4. **통합 키** 탭을 선택합니다.
5. msdyn_warehouses를 찾아 **msdyn_name (name)** 키가 추가되었는지 확인합니다. 표시되지 않으면 **키 추가** 를 클릭하여 추가한 다음 페이지 상단의 **저장** 을 클릭합니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>창고(Supply Chain Management에서 Field Service로): 창고

[![데이터 통합의 템플릿 매핑.](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]