---
title: Supply Chain Management의 Sales에서 고객으로 직접 계정 동기화
description: 이 항목에서는 Dynamics 365 Sales에서 Supply Chain Management로 계정을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 10/25/2018
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
ms.openlocfilehash: b3257f4582ede6cd1be8e593a5ed99f5ffd0ca6f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449857"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Supply Chain Management의 Sales에서 고객으로 직접 계정 동기화

[!include [banner](../includes/banner.md)]



> [!NOTE]
> 잠재 고객 지출 유도 솔루션을 사용하기 전에 [앱용 Microsoft Dataverse에 데이터 통합](/powerapps/administrator/data-integrator)을 숙지해야 합니다.

이 항목에서는 Dynamics 365 Sales에서 Dynamics 365 Supply Chain Management로 계정을 직접 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

## <a name="data-flow-in-prospect-to-cash"></a>잠재 고객의 결제 유도에서의 데이터 흐름

잠재 고객의 결제 유도 솔루션은 데이터 통합 기능을 사용하여 Supply Chain Management 및 Sales의 인스턴스 간에 데이터를 동기화합니다.  데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿을 사용하면 Supply Chain Management와 Sales 간에 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 가능합니다. 다음 그림은 Supply Chain Management와 Sales 간에 데이터가 동기화되는 방법을 보여줍니다.

[![잠재 고객의 결제 유도에서의 데이터 흐름.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업

사용 가능한 템플릿에 액세스하려면 [Power Apps 관리 센터](https://preview.admin.powerapps.com/dataintegration)를 엽니다. **프로젝트** 를 선택한 다음 오른쪽 위 모서리에서 **새 프로젝트** 를 선택하여 공개 템플릿을 선택합니다.

다음 템플릿 및 기본 작업은 Sales에서 Supply Chain Management로 계정을 동기화하는 데 사용됩니다.

- **데이터 통합의 템플릿 이름:**  계정(Sales에서 Fin 및 Ops로) - 직접
- **프로젝트의 작업 이름:** 계정 - 고객

계정/고객 동기화가 발생하기 전에 동기화 작업이 필요하지 않습니다.

## <a name="entity-set"></a>엔터티 세트

| 영업    | Supply Chain Management |
|----------|------------------------|
| 어카운트 | 고객 V2           |

## <a name="entity-flow"></a>엔터티 흐름

계정이 Sales에서 관리되며 Supply Chain Management에 고객으로 동기화됩니다. 이러한 고객의 **외부에서 유지 관리됨** 속성은 **예** 로 설정되어 Sales에서 시작하는 고객을 추적합니다. 송장 발행 중에 이 정보는 Sales에 동기화된 송장을 필터링하는 데 사용됩니다.

## <a name="prospect-to-cash-solution-for-sales"></a>Sales를 위한 잠재 고객의 결제 유도 솔루션

**계정 번호** 열은 **계정** 페이지에서 사용할 수 있습니다. 통합을 지원하기 위해 자연스럽고 고유한 키로 만들었습니다. CRM(고객 관계 관리) 솔루션의 자연 키 기능은 이미 **계정 번호** 열을 사용하지만 계정별로 고유한 **계정 번호**  값을 사용하지 않는 고객에게 영향을 미칠 수 있습니다. 현재 통합 솔루션은 이 경우를 지원하지 않습니다.

새 계정이 생성되면 **계정 번호** 값이 이미 존재하지 않는 경우 번호 시퀀스를 사용하여 자동으로 생성됩니다. 값은 **ACC** 로 구성되며, 그 뒤에 증가하는 번호 시퀀스와 6자의 접미사가 옵니다. 다음은 예입니다. **ACC-01000-BVRCPS**

Sales용 통합 솔루션이 적용되면 업그레이드 스크립트는 Sales의 기존 계정에 대해 **계정 번호** 열을 설정합니다. **계정 번호** 값이 없으면 앞에서 언급한 번호 시퀀스가 사용됩니다.

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

- **CustomerGroupId** 매핑은 Supply Chain Management에서 유효한 값으로 업데이트되어야 합니다. 기본값을 지정하거나 값 맵을 사용하여 값을 설정할 수 있습니다.

    기본 템플릿 값은 **10** 입니다.

- 다음 매핑을 추가하면 Supply Chain Management에 필요한 수동 업데이트 수를 줄이는 데 도움이 될 수 있습니다. 예를 들어 다음에서 기본값 또는 값 맵을 사용할 수 있습니다. **국가/지역** 또는 **도시**.

    - **SiteId** – Supply Chain Management에서 견적 및 판매 주문 라인을 생성하려면 사이트가 필요합니다. 기본 사이트는 제품에서 가져오거나 주문 헤더에서 고객으로부터 가져올 수 있습니다.

        기본 템플릿 값은 **1** 입니다.

    - **WarehouseId** – Supply Chain Management에서 견적 및 판매 주문 라인을 처리하려면 창고가 필요합니다. 기본 창고는 제품에서 가져오거나 Supply Chain Management의 주문 헤더에서 고객으로부터 가져올 수 있습니다.

        기본 템플릿 값은 **13** 입니다.

    - **LanguageId** – Supply Chain Management에서 견적 및 판매 주문을 생성하려면 언어가 필요합니다. 기본적으로 고객의 주문 헤더에 있는 언어가 사용됩니다.

        기본 템플릿 값은 **en-us** 입니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

> [!NOTE]
> **결제 조건**, **운임 조건**, **배송 조건**, **배송 방법**, **배송 모드** 열은 기본 매핑에 포함되지 않습니다. 이러한 열을 매핑하려면 테이블이 동기화되는 조직의 데이터와 관련된 값 매핑을 설정해야 합니다.

다음 그림은 데이터 통합에서 템플릿 매핑의 예를 보여줍니다. 

> [!NOTE]
> 매핑은 Sales에서 Supply Chain Management로 동기화될 열 정보를 보여줍니다.

![데이터 통합의 템플릿 매핑.](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>관련 주제


[잠재 고객의 결제 유도](prospect-to-cash.md)

[Sales에서 Supply Chain Management의 고객으로 직접 계정 동기화](accounts-template-mapping-direct.md)

[Sales에서 Supply Chain Management의 연락처 또는 고객으로 직접 연락처 동기화](contacts-template-mapping-direct.md)

[Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화](sales-order-template-mapping-direct-two-ways.md)

[Supply Chain Management에서 Sales로 직접 판매 송장 헤더 및 라인 동기화](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]