---
title: Supply Chain Management에서 Sales의 제품으로 직접 제품 동기화
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Sales로 제품을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 06/10/2019
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
ms.openlocfilehash: dd84f96a5597c480648ae30b6d0274e15d750ff6
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449839"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Supply Chain Management에서 Sales의 제품으로 직접 제품 동기화

[!include [banner](../includes/banner.md)]



> [!NOTE]
> 잠재 고객 지출 유도 솔루션을 사용하기 전에 [앱용 Microsoft Dataverse에 데이터 통합](/powerapps/administrator/data-integrator)을 숙지해야 합니다.

이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Sales로 제품을 직접 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

## <a name="data-flow-in-prospect-to-cash"></a>잠재 고객의 결제 유도에서의 데이터 흐름

잠재 고객의 결제 유도 솔루션은 데이터 통합 기능을 사용하여 Supply Chain Management 및 Sales의 인스턴스 간에 데이터를 동기화합니다. 데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿을 사용하면 Supply Chain Management와 Sales 간에 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 가능합니다. 다음 그림은 Supply Chain Management와 Sales 간에 데이터가 동기화되는 방법을 보여줍니다.

[![잠재 고객의 결제 유도에서의 데이터 흐름.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업

사용 가능한 템플릿에 액세스하려면 [Power Apps 관리 센터](https://admin.powerapps.com/dataintegration)를 엽니다. **프로젝트** 를 선택한 다음 오른쪽 위 모서리에서 **새 프로젝트** 를 선택하여 공개 템플릿을 선택합니다.

다음 템플릿 및 기본 작업은 Supply Chain Management에서 Sales로 제품을 동기화하는 데 사용됩니다.

- **데이터 통합의 템플릿 이름:** 제품(Supply Chain Management에서 Sales로) - 직접
- **데이터 통합 프로젝트의 작업 이름:** 제품

제품 동기화가 발생하기 전에 동기화 작업이 필요하지 않습니다.

## <a name="entity-set"></a>엔터티 세트

| Supply Chain Management    | 영업    |
|----------------------------|----------|
| 판매 가능한 출시 제품 | 제품 |

## <a name="entity-flow"></a>엔터티 흐름

제품은 Supply Chain Management에서 관리되고 Sales와 동기화됩니다. Supply Chain Management의 **판매 가능한 출시 제품** 데이터 엔터티는 *판매할 수 있는* 제품만 내보냅니다. 판매 가능 제품은 판매 주문에 사용하기 위해 필요한 정보가 있는 제품입니다. **출시된 제품** 페이지의 **유효성 검사** 기능을 사용하여 제품의 유효성을 검사할 때도 동일한 규칙이 적용됩니다.

제품 번호는 키로 사용됩니다. 따라서 제품 변형이 Sales와 동기화되면 각 제품 변형에는 개별 제품 ID가 있습니다.

## <a name="prospect-to-cash-solution-for-sales"></a>Sales를 위한 잠재 고객의 결제 유도 솔루션

Sales에서 지정된 제품이 외부적으로 유지 관리됨을 나타내기 위해 제품에 새로운 **외부에서 유지 관리됨** 필드가 추가되었습니다. 기본적으로 값은 Sales로 가져오는 동안 **예** 로 설정됩니다. 다음 값을 사용할 수 있습니다.

- **예** – 제품은 Supply Chain Management에서 시작되었으며 Sales에서 편집할 수 없습니다.
- **아니요** – 제품이 Sales에 직접 입력되었습니다.
- **(공백)** – 잠재 고객의 결제 유도 솔루션이 활성화되기 전에 제품이 Sales에 존재했습니다.

**외부에서 유지 관리됨** 필드는 외부에서 유지 관리되는 제품이 있는 견적 및 판매 주문만 Supply Chain Management와 동기화되도록 합니다.

외부에서 유지 관리되는 제품은 통화가 동일한 첫 번째 유효한 가격 목록에 자동으로 추가됩니다. 가격 목록은 이름의 알파벳순으로 구성되어 있습니다. Supply Chain Management의 제품 판매 가격은 가격 목록의 가격으로 사용됩니다. 따라서 Supply Chain Management의 모든 제품 판매 통화에 대한 판매 가격 목록이 있어야 합니다. 출시된 판매 가능 제품의 통화는 제품을 수출하는 법인의 회계 통화로 설정됩니다.

> [!NOTE]
> - 일치하는 통화가 있는 가격 목록이 없으면 제품 동기화가 성공하지 않습니다.
> - 데이터 통합 프로젝트에서 pricelevelid.name [기본 가격 목록(이름)]을 매핑하여 통합으로 사용된 가격 목록을 제어할 수 있습니다. 입력은 모두 소문자여야 합니다. 예를 들어 이름이 'Standard'인 Sales의 가격 목록에 대한 기본값은 다음과 같습니다. 대상 필드: pricelevelid.name [기본 가격 목록(이름)] 및 지도 유형: [ { "transformType": "Default", "defaultValue ": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

- 처음으로 동기화를 실행하기 전에 Supply Chain Management에서 기존 제품에 대한 고유 제품 테이블을 채워야 합니다. 이 작업이 완료될 때까지 기존 제품이 동기화되지 않습니다.

    1. Supply Chain Management에서 검색을 사용하여 **고유한 제품 테이블 채우기** 를 검색합니다.
    2. **고유한 제품 테이블 채우기** 작업을 실행합니다. 이 작업은 한 번만 실행해야 합니다.

- **SalesUnitSymbol** 에서 **DefaultUnit(이름)** 으로의 매핑에 Supply Chain Management와 Sales 간의 판매 측정 단위(UOM)에 대한 필수 값 맵이 있는지 확인합니다.
- **단위 그룹**(**defaultuomscheduleid.name**)에 대한 값 맵을 업데이트하여 Sales의 **단위 그룹** 과 일치하도록 합니다.

    기본 템플릿 값은 **기본 단위** 입니다.

- Supply Chain Management의 모든 제품에 대한 판매 UOM이 Sales에 있는지 확인하세요.
- Supply Chain Management의 모든 제품 판매 통화에 대한 가격 목록이 Sales에 있는지 확인하세요.
- 제품이 Sales에서 생성되면 **초안** 또는 **활성** 상태가 될 수 있습니다. 동작은 Sales의 **설정** > **관리** > **시스템 설정** > **판매** 에서 제어됩니다.

    제품이 생성될 때 **초안** 상태인 제품을 활성화해야 견적이나 판매 주문에 추가할 수 있습니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합자에서 템플릿 매핑의 예를 보여줍니다. 

> [!NOTE]
> 매핑은 Sales에서 Supply Chain Management로 동기화될 필드 정보를 보여줍니다.

![데이터 통합자의 템플릿 매핑.](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>관련 토픽

[잠재 고객의 결제 유도](prospect-to-cash.md)

[Sales에서 Supply Chain Management의 고객으로 직접 계정 동기화](accounts-template-mapping-direct.md)

[Sales에서 Supply Chain Management의 연락처 또는 고객으로 직접 연락처 동기화](contacts-template-mapping-direct.md)

[Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화](sales-order-template-mapping-direct-two-ways.md)

[Supply Chain Management에서 Sales로 직접 판매 송장 헤더 및 라인 동기화](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]