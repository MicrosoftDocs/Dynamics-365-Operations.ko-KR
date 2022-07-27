---
title: Sales에서 Supply Chain Management로 직접 판매 견적 헤더 및 라인 동기화
description: 이 토픽에서는 Dynamics 365 Sales에서 Dynamics 365 Supply Chain Management로 직접 판매 견적 헤더 및 라인을 동기화하는 데 사용되는 템플릿 및 기본 태스크에 대해 설명합니다.
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
ms.openlocfilehash: 362b6c290b1784d05e42ecb650911cc51aa8478a
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449827"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a>Sales에서 Supply Chain Management로 직접 판매 견적 헤더 및 라인 동기화

[!include [banner](../includes/banner.md)]



이 토픽에서는 Dynamics 365 Sales에서 Dynamics 365 Supply Chain Management로 직접 판매 견적 헤더 및 라인을 동기화하는 데 사용되는 템플릿 및 기본 태스크에 대해 설명합니다.

> [!NOTE]
> 잠재 고객 지출 유도 솔루션을 사용하기 전에 [앱용 Microsoft Dataverse에 데이터 통합](/powerapps/administrator/data-integrator)을 숙지해야 합니다.

## <a name="data-flow-in-prospect-to-cash"></a>잠재 고객의 결제 유도에서의 데이터 흐름

잠재 고객의 결제 유도 솔루션은 데이터 통합 기능을 사용하여 Supply Chain Management 및 Sales의 인스턴스 간에 데이터를 동기화합니다. 데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿을 사용하면 Supply Chain Management와 Sales 간에 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 가능합니다. 다음 그림은 Supply Chain Management와 Sales 간에 데이터가 동기화되는 방법을 보여줍니다.

[![잠재 고객의 결제 유도에서의 데이터 흐름.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>템플릿 및 태스크

다음 템플릿 및 기본 태스크는 Sales의 견적 헤더 및 라인을 Supply Chain Management로 로 동기화하는 데 사용됩니다.

- **데이터 통합의 템플릿 이름:** 판매 견적(Sales에서 Supply Chain Management) - 직접
- **데이터 통합 프로젝트의 작업 이름:**

    - QuoteHeader
    - QuoteLine

견적 송장 헤더 및 라인을 동기화하려면 다음 동기화 태스크가 필요합니다.

- 제품(Supply Chain Management에서 Sales로) - 직접
- 계정(Sales에서 Supply Chain Management로) - 직접(사용한 경우)
- 고객에게 연락(Sales에서 Supply Chain Management로) - 직접(사용한 경우)

## <a name="entity-set"></a>엔터티 세트

| 영업        | Supply Chain Management     |
|--------------|----------------------------|
| 견적       | Dataverse 판매 견적 헤더 |
| QuoteDetails | Dataverse 판매 견적 라인  |

## <a name="entity-flow"></a>엔터티 흐름

판매 견적은 Sales에서 생성되고 Supply Chain Management와 동기화됩니다.

Sales의 판매 견적은 다음 조건이 충족되는 경우에만 동기화됩니다.

- 판매 견적의 모든 견적 제품은 외부에서 유지 관리됩니다.
- **견적 활성화** 를 클릭하면 판매 견적이 활성화됩니다.

## <a name="prospect-to-cash-solution-for-sales"></a>Sales를 위한 잠재 고객의 결제 유도 솔루션

**외부에서 유지 관리되는 제품만 있음** 필드가 **견적** 엔터티에 추가되어 판매 견적이 외부에서 유지 관리되는 제품으로만 구성되었는지 여부를 일관되게 추적할 수 있습니다. 판매 견적에 전적으로 외부에서 관리되는 제품만 있는 경우 제품은 Supply Chain Management에서 관리됩니다. 이 동작을 사용하면 Supply Chain Management에 알려지지 않은 제품이 있는 판매 견적 라인을 동기화하지 않도록 할 수 있습니다.

판매 견적의 모든 견적 제품은 판매 견적 헤더의 **외부에서 유지 관리되는 제품만 있음** 정보로 업데이트됩니다. 이 정보는 **QuoteDetails** 엔터티의 견적에 **외부에서 유지 관리되는 제품만 있음** 필드에 있습니다.

할인은 견적 제품에 추가할 수 있으며 Supply Chain Management와 동기화됩니다. 헤더의 **할인**, **비용** 및 **세금** 필드는 Supply Chain Management의 설정에 의해 제어됩니다. 현재 이 설정은 통합 매핑을 지원하지 않습니다. 현재 디자인에서 **가격**, **할인**, **비용** 및 **세금** 필드는 Supply Chain Management에서 유지 관리되고 처리됩니다.

Sales에서 솔루션은 값이 Supply Chain Management와 동기화되지 않기 때문에 다음 필드를 읽기 전용으로 만듭니다.

- 판매 견적 헤더의 읽기 전용 필드: **할인 %**, **할인** 및 **운임 금액**
- 견적 제품의 읽기 전용 필드: **세금**

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

판매 견적을 동기화하기 전에 다음 설정을 업데이트하는 것이 중요합니다.

### <a name="setup-in-sales"></a>Sales 설정

- Sales에서 연결 집합의 사용자가 할당된 팀에 대한 권한이 설정되어 있는지 확인합니다. 데모 데이터를 사용하는 경우 일반적으로 사용자에게 관리자 액세스 권한이 있지만 팀에는 관리자 액세스 권한이 없습니다. 팀에 관리자 액세스 권한이 없는 경우 데이터 통합에서 프로젝트를 실행할 때 주도자 팀이 없다는 오류 메시지를 받게 됩니다.

    팀에 대한 권한을 설정하려면 **설정** &gt; **보안** &gt; **팀** 으로 이동하여 해당 팀을 선택합니다. **역할 관리** 를 선택한 다음 **시스템 관리자** 와 같이 원하는 권한이 있는 역할을 선택합니다.

- **설정** &gt; **관리** &gt; **시스템 설정** &gt; **영업** 으로 이동하여 다음 설정이 사용되었는지 확인합니다.

    - **시스템 상금 계산 시스템** 옵션이 **예** 로 설정되어 있습니다.
    - **할인 계산 방법** 필드가 **라인 항목** 으로 설정됩니다.

### <a name="setup-in-the-data-integration-project"></a>데이터 통합 프로젝트에서 설정

#### <a name="quoteheader"></a>QuoteHeader

- **Shipto\_country** 에서 **DeliveryAddressCountryRegionISOCode** 로의 필수 매핑이 있는지 확인하세요. 값 맵에서 값이 비어 있는 경우 사용되는 기본값을 정의할 수 있습니다. 왼쪽은 공백으로, 오른쪽은 원하는 국가나 지역으로 설정합니다. 이런 식으로 국가 주문에 대해 국가 또는 지역을 입력할 필요가 없습니다.

    템플릿 값은 여러 국가 또는 지역이 매핑되고 공백 값이 **US** 값과 동일한 값 맵입니다.

#### <a name="quoteline"></a>QuoteLine

- Supply Chain Management의 **SalesUnitSymbol** 에 필요한 값 맵이 있는지 확인하세요.
- 필요한 단위가 Sales에 정의되어 있는지 확인하세요.

    값 맵이 있는 템플릿 값은 **oumid.name** 에서 **SalesUnitSymbol** 로 정의됩니다.

- 선택 사항: 다음 매핑을 추가하여 고객이나 제품의 기본 정보가 없는 경우 판매 견적 라인이 Supply Chain Management로 임포트되도록 할 수 있습니다.

    - **SiteId** – Supply Chain Management에서 견적 및 판매 주문 라인을 생성하려면 사이트가 필요합니다. **SiteId** 에 대한 기본 템플릿 값이 없습니다.
    - **WarehouseId** – Supply Chain Management에서 견적 및 판매 주문 라인을 처리하려면 창고가 필요합니다. **WarehouseId** 에 대한 기본 템플릿 값이 없습니다.

## <a name="template-mapping-in-data-integrator"></a>데이터 통합자의 템플릿 매핑.

> [!NOTE]
> - **할인**, **비용** 및 **세금** 필드는 Supply Chain Management의 복잡한 설정에 의해 제어됩니다. 현재 이 설정은 통합 매핑을 지원하지 않습니다. 현재 디자인에서 **가격**, **할인**, **비용** 및 **세금** 필드는 Supply Chain Management에서 처리됩니다.
> - **결제 조건**, **운임 조건**, **배송 조건**, **배송 방법**, **배송 모드** 필드는 기본 매핑에 포함되지 않습니다. 이러한 필드를 매핑하려면 엔터티가 동기화되는 조직의 데이터와 관련된 값 매핑을 설정해야 합니다.

다음 그림은 데이터 통합자에서 템플릿 매핑의 예를 보여줍니다.

### <a name="quoteheader"></a>QuoteHeader

![데이터 통합자 QuoteHeader의 템플릿 매핑.](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![데이터 통합자 QuoteLine의 템플릿 매핑.](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>관련 토픽

[잠재 고객의 결제 유도](prospect-to-cash.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]