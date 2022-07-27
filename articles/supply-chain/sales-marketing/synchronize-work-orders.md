---
title: Field Service에서 Supply Chain Management로 프로젝트와 작업 주문 동기화
description: 이 토픽에서는 Dynamics 365 Field Service에서 Dynamics 365 Supply Chain Management로 프로젝트 번호가 있는 작업 주문을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 03/12/2019
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
ms.openlocfilehash: f0b3214aba5882a585664030d6c1aebe34de455c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448534"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Field Service에서 Supply Chain Management로 프로젝트와 작업 주문 동기화

[!include[banner](../includes/banner.md)]

이 토픽에서는 Dynamics 365 Field Service에서 Dynamics 365 Supply Chain Management로 프로젝트 번호가 있는 작업 주문을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

사용된 **프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로)** 템플릿은 **작업 주문(Field Service에서 Supply Chain Management로)** 템플릿을 기반으로 합니다. 자세한 내용은 [Field Service의 작업 주문을 Supply Chain Management의 판매 주문에 동기화](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)를 참조하세요.

이 토픽에서는 두 템플릿 간의 차이점만 설명합니다.
- **프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로)**
- **작업 주문(Field Service에서 Supply Chain Management로)**

주요 차이점은 이 템플릿에는 Field Service의 작업 주문에 할당된 프로젝트 번호 매핑이 포함되어 있어 Supply Chain Management에서 생성된 판매 주문에 프로젝트 번호가 포함되고 관련 프로젝트에서 송장이 발생할 수 있다는 점입니다. 이 외에도 템플릿은 고급 쿼리 및 필터링을 사용합니다.

## <a name="templates-and-tasks"></a>템플릿 및 작업

**데이터 통합의 템플릿 이름:**

- 프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로)

**데이터 통합 프로젝트의 작업 이름:**

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션
**외부 프로젝트** 필드가 작업 주문 엔터티에 추가되었습니다. 이 필드는 판매 주문이 Supply Chain Management 내의 프로젝트에 연결될 프로젝트가 있는 작업 주문에 태그를 지정하는 조회 및 구매입니다. **시스템 상태** 가 열림 - 진행 중(690,970,000)을 더 높은 상태로 변경하면 **외부 프로젝트** 필드가 잠기고 값을 추가, 제거 또는 변경할 수 없습니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderHeader

[![데이터 통합의 템플릿 매핑, 프로젝트가 포함된 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderHeader.](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderHeaderProject

[![데이터 통합의 템플릿 매핑, 프로젝트가 포함된 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderHeaderProject.](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderProduct

[![데이터 통합의 템플릿 매핑, 프로젝트가 포함된 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderProduct.](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>프로젝트가 있는 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderService

[![데이터 통합의 템플릿 매핑, 프로젝트가 포함된 작업 주문(Field Service에서 Supply Chain Management로): WorkOrderService.](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]