---
title: Supply Chain Management에서 Field Service로 프로젝트 목록 동기화
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 프로젝트를 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
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
ms.openlocfilehash: b825e2fce61e96b963ba0d41f8db49ca9ba646f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448435"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Supply Chain Management에서 Field Service로 프로젝트 목록 동기화

[!include[banner](../includes/banner.md)]

이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 프로젝트를 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업
다음 템플릿 및 기본 작업은 Supply Chain Management에서 Field Service로 프로젝트 동기화를 실행하는 데 사용됩니다.

**데이터 통합의 템플릿**
- 프로젝트(Supply Chain Management에서 Field Service로)

**데이터 통합 프로젝트의 작업**
- 프로젝트

프로젝트 목록의 동기화를 수행하려면 다음 동기화 작업이 필요합니다.
- 계정(Sales에서 Supply Chain Management로) 

## <a name="entity-set"></a>엔터티 세트
| Field Service           | Supply Chain Management  |
|-------------------------|-------------------------|
|msdynce_externalprojects | 프로젝트                |

## <a name="entity-flow"></a>엔터티 흐름
프로젝트는 Supply Chain Management에서 생성됩니다. **프로젝트 유형** 이 **시간 및 재료** 로 설정되고 **프로젝트 단계** 가 **진행 중** 으로 설정된 프로젝트는 프로젝트 번호, 프로젝트 이름, 프로젝트 단계 및 고객 계정 정보를 포함하여 Field Service의 **외부 프로젝트** 엔터티와 동기화됩니다. **외부 프로젝트** 목록은 Field service 작업 주문을 Supply Chain Management 프로젝트와 연결하는 데 사용됩니다.

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션
**외부 프로젝트** 엔터티는 Supply Chain Management에서 모든 프로젝트를 가져옵니다. **외부 프로젝트** 필드가 **작업 주문** 엔터티에 추가되었습니다. 이것은 조회 필드이므로 작업 주문에 프로젝트에 태그를 지정하면 판매 주문이 Supply Chain Management 내의 프로젝트에 연결됩니다. **시스템 상태** 가 **열림 - 진행 중(690,970,000)** 을 더 높은 상태로 변경하면 **외부 프로젝트** 필드가 잠기고 더 이상 값을 추가, 제거 또는 변경할 수 없습니다.

## <a name="prerequisites-and-mapping-setup"></a>전제 조건 및 매핑 설정
### <a name="supply-chain-management"></a>Supply Chain Management
데이터 엔터티 프로젝트에 대한 변경 내용 추적을 사용 설정합니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑


### <a name="projects-supply-chain-management-to-field-service-projects"></a>프로젝트(Supply Chain Management에서 Field Service로): 프로젝트

[![데이터 통합의 템플릿 매핑.](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]