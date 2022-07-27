---
title: Field Service에서 Supply Chain Management로 인벤토리 이전 및 조정 동기화
description: 이 토픽에서는 인벤토리 조정 및 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로의 이전을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 04/30/2019
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
ms.openlocfilehash: cfa7f617cbc4cd75d669972b35f8d33ba3cbcc56
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449824"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Field Service에서 Supply Chain Management로 인벤토리 이전 및 조정 동기화

[!include[banner](../includes/banner.md)]



이 토픽에서는 인벤토리 조정 및 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로의 이전을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업
다음 템플릿 및 기본 작업은 Field Service의 인벤토리 조정 및 이전을 Supply Chain Management에 동기화하는 데 사용됩니다.

**데이터 통합의 템플릿**
- 인벤토리 조정(Field Service에서 Supply Chain Management로)
- 인벤토리 이전(Field Service에서 Supply Chain Management로)

**데이터 통합 프로젝트의 작업**
- 인벤토리 조정
- 인벤토리 이전

## <a name="table-set"></a>테이블 세트
| Field Service                     | Supply Chain Management                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | Dataverse 인벤토리 조정 분개장 헤더 및 라인 |
| msdyn_inventoryadjustmentproducts | Dataverse 인벤토리 이전 분개장 헤더 및 라인   |

## <a name="table-flow"></a>테이블 흐름
Field Service에서 수행된 인벤토리 조정 및 이전은 **게시 상태** 가 **생성됨** 에서 **게시됨** 으로 변경된 후 Supply Chain Management와 동기화됩니다. 이 경우 조정 또는 이전 주문이 잠기고 읽기 전용이 됩니다. 이는 조정 및 이전을 Supply Chain Management에 전기할 수 있지만 수정할 수는 없음을 의미합니다. Supply Chain Management에서 일괄 작업을 설정하여 조정을 자동으로 전기하고 통합 중에 생성된 인벤토리 분개장을 전송할 수 있습니다. 배치 작업을 사용 설정하는 방법에 대한 자세한 내용은 다음 사전 요구 사항을 참조하세요.

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션 
**인벤토리 단위** 열이 **제품** 테이블에 추가되었습니다. 이 열은 판매 및 인벤토리 단위가 Supply Chain Management에서 항상 동일한 것은 아니며 인벤토리 단위는 Supply Chain Management의 창고 인벤토리에 필요하기 때문에 필요합니다.
인벤토리 조정 및 인벤토리 이전 모두에 대해 인벤토리 조정 제품에 제품을 설정하면 인벤토리 제품 값에서 단위를 가져옵니다. 값을 찾으면 인벤토리 조정 제품에서 **단위** 열이 잠깁니다.

**인벤토리 조정** 테이블과 **인벤토리 이전** 테이블에 **게시 상태** 열이 추가되었습니다. 이 열은 조정 또는 이전이 Supply Chain Management로 전송될 때 필터로 사용됩니다. 이 열의 기본값은 생성됨(1)이지만 Supply Chain Management로 전송되지 않습니다. 값을 전기됨(2)으로 갱신하면 Supply Chain Management로 보내지지만 그 후에는 조정을 변경하거나 신규 라인을 이전 또는 추가할 수 없습니다.

**번호 시퀀스** 열이 **인벤토리 조정 제품** 테이블에 추가되었습니다. 이 열은 통합이 고유 번호를 갖도록 보장하므로 통합에서 조정을 생성하고 업데이트할 수 있습니다. 첫 번째 인벤토리 조정 제품을 생성하면 **P2C AutoNumber** 테이블에 새 레코드가 생성되어 사용되는 번호 시리즈와 접두사가 유지됩니다.

## <a name="prerequisites-and-mapping-setup"></a>전제 조건 및 매핑 설정

### <a name="supply-chain-management"></a>Supply Chain Management
통합으로 생성된 통합 인벤토리 분개는 배치 작업을 사용하여 자동으로 전기될 수 있습니다. 이는 **인벤토리 관리 > 정기 작업 > Dataverse 통합 > 통합 후 인벤토리 분개장** 에서 활성화됩니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>인벤토리 조정(Field Service에서 Supply Chain Management로): 인벤토리 조정

[![데이터 통합의 템플릿 매핑, 인벤토리 조정(Field Service에서 Supply Chain Management로): 인벤토리 조정.](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>인벤토리 이전(Field Service에서 Supply Chain Management로): 인벤토리 이전

[![데이터 통합의 템플릿 매핑, 인벤토리 이전(Field Service에서 Supply Chain Management로): 인벤토리 이전.](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]