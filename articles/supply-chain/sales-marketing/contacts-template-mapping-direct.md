---
title: Sales에서 Supply Chain Management의 연락처 또는 고객으로 직접 연락처 동기화
description: 이 토픽에서는 Dynamics 365 Sales에서 Dynamics 365 Supply Chain Management로 연락처(연락처) 및 연락처(고객) 엔터티를 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
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
ms.openlocfilehash: 57a9c2a860e99855e841f0f4276ba2f92767c2b1
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449845"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Sales에서 Supply Chain Management의 연락처 또는 고객으로 직접 연락처 동기화

[!include [banner](../includes/banner.md)]



> [!NOTE]
> 잠재 고객 지출 유도 솔루션을 사용하기 전에 [앱용 Microsoft Dataverse에 데이터 통합](/powerapps/administrator/data-integrator)을 숙지해야 합니다.

이 토픽에서는 Dynamics 365 Sales에서 Dynamics 365 Supply Chain Management로 직접 연락처(연락처) 및 연락처(고객) 테이블을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

## <a name="data-flow-in-prospect-to-cash"></a>잠재 고객의 결제 유도에서의 데이터 흐름

잠재 고객의 결제 유도 솔루션은 데이터 통합 기능을 사용하여 Supply Chain Management 및 Sales의 인스턴스 간에 데이터를 동기화합니다. 데이터 통합 기능과 함께 사용할 수 있는 잠재 고객의 결제 유도 템플릿을 사용하면 Supply Chain Management와 Sales 간에 계정, 연락처, 제품, 판매 견적, 판매 주문 및 판매 송장에 대한 데이터 흐름이 가능합니다. 다음 그림은 Supply Chain Management와 Sales 간에 데이터가 동기화되는 방법을 보여줍니다.

[![잠재 고객의 결제 유도에서의 데이터 흐름.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>템플릿 및 작업

사용 가능한 템플릿에 액세스하려면 [PowerApps 관리 센터](https://preview.admin.powerapps.com/dataintegration)를 엽니다. **프로젝트** 를 선택한 다음 오른쪽 위 모서리에서 **새 프로젝트** 를 선택하여 공개 템플릿을 선택합니다.

다음은 Field Service의 작업 주문을 Supply Chain Management의 영업에서 연락처(고객) 테이블의 연락처(연락처) 테이블을 동기화하는 데 사용되는 템플릿 및 기본 작업입니다.

- **데이터 통합의 템플릿 이름**

    - 연락처(Sales에서 Supply Chain Management로) - 직접
    - 고객에게 연락(Sales에서 Supply Chain Management로) - 직접

- **데이터 통합 프로젝트의 작업 이름**

    - 연락처
    - ContactToCustomer

연락처 동기화가 발생하기 전에 다음 동기화 작업이 필요합니다. 계정(Supply Chain Management에 대한 판매)

## <a name="entity-sets"></a>엔터티 세트

| 영업    | Supply Chain Management |
|----------|------------------------|
| 연락처 | Dataverse 연락처           |
| 연락처 | 고객 V2           |

## <a name="entity-flow"></a>엔터티 흐름

연락처가 Sales에서 관리되며 Supply Chain Management에 동기화됩니다.

Sales의 담당자는 Supply Chain Management의 담당자 또는 고객이 될 수 있습니다. Sales의 연락처를 Supply Chain Management에 연락처 또는 고객으로 동기화해야 하는지 여부를 결정하기 위해 시스템은 Sales의 연락처에서 다음 속성을 확인합니다.

- **Supply Chain Management에서 고객과 동기화:** **활성 고객임** 이 **네** 로 설정된 연락처
- **Supply Chain Management의 담당자와 동기화:** **활성 고객임** 이 **아니요** 로 설정되고 **회사**(상위 계정/연락처)가 계정(연락처 아님)을 가리키는 연락처

## <a name="prospect-to-cash-solution-for-sales"></a>Sales를 위한 잠재 고객의 결제 유도 솔루션

새로운 **활성 고객임** 열이 연락처에 추가되었습니다. 이 열은 판매 활동이 있는 연락처와 판매 활동이 없는 연락처를 구별하는 데 사용됩니다. 관련 견적, 주문 또는 송장이 있는 연락처에만 **활성 고객임** 이 **네** 로 설정됩니다. 해당 연락처만 고객으로서 Supply Chain Management에 동기화됩니다.

새로운 **IsCompanyAnAccount** 열이 연락처에 추가되었습니다. 이 열은 연락처가 **계정** 유형의 회사(상위 계정/연락처)에 연결되어 있는지 여부를 나타냅니다. 이 정보는 Supply Chain Management에 연락처로 동기화해야 하는 연락처를 식별하는 데 사용됩니다.

새로운 **연락처 번호** 열이 통합을 위한 자연스럽고 고유한 키를 보장하기 위해 연락처에 추가되었습니다. 새 연락처가 생성되면 **연락처 번호** 값이 숫자 시퀀스를 사용하여 자동으로 생성됩니다. 값은 **CON** 로 구성되며, 그 뒤에 증가하는 번호 시퀀스와 6자의 접미사가 옵니다. 다음은 예입니다. **CON-01000-BVRCPS**

Sales용 통합 솔루션이 적용될 때 업그레이드 스크립트는 앞에서 언급한 번호 시퀀스를 사용하여 기존 연락처에 대해 **연락처 번호** 열을 설정합니다. 업그레이드 스크립트는 또한 영업 활동이 있는 모든 연락처에 대해 **활성 고객임** 열을 **네** 로 설정합니다.

## <a name="in-supply-chain-management"></a>Supply Chain Management에서

연락처는 **IsContactPersonExternallyMaintained** 속성을 사용하여 태그가 지정됩니다. 이 속성은 지정된 연락처가 외부에서 유지 관리됨을 나타냅니다. 이 경우 외부에서 유지 관리되는 연락처는 Sales에서 유지 관리됩니다.

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

### <a name="contact-to-customer"></a>연락처에서 고객으로

- **CustomerGroup** 이 Supply Chain Management에 필요합니다. 동기화 오류를 방지하기 위해 매핑에서 기본값을 지정할 수 있습니다. Sales에서 열이 비어 있는 경우 해당 기본값이 사용됩니다.

    기본 템플릿 값은 **10** 입니다.

- 다음 매핑을 추가하면 Supply Chain Management에 필요한 수동 업데이트 수를 줄이는 데 도움이 될 수 있습니다. 예를 들어 다음에서 기본값 또는 값 맵을 사용할 수 있습니다. **국가/지역** 또는 **도시**.

    - **SiteId** – 기본 사이트는 Supply Chain Management의 제품에도 정의할 수 있습니다. Supply Chain Management에서 견적 및 판매 주문을 생성하려면 사이트가 필요합니다.

        **SiteId** 의 템플릿 값이 정의되어 있지 않습니다.

    - **WarehouseId** – 기본 창고는 Supply Chain Management의 제품에도 정의할 수 있습니다. Supply Chain Management에서 견적 및 판매 주문을 생성하려면 창고가 필요합니다.

        **WarehouseId** 의 템플릿 값이 정의되어 있지 않습니다.

    - **LanguageId** – Supply Chain Management에서 견적 및 판매 주문을 생성하려면 언어가 필요합니다.
    
        기본 템플릿 값은 **en-us** 입니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑의 예를 보여줍니다. 

> [!NOTE]
> 매핑은 Sales에서 Supply Chain Management로 동기화될 열 정보를 보여줍니다.

### <a name="contact-to-contact-example"></a>연락처에서 연락처 예

![데이터 통합기의 연락처 템플릿 매핑에 대한 연락처.](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer-example"></a>연락처에서 고객 예

![데이터 통합기의 고객 템플릿 매핑에 대한 연락처.](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>관련 토픽

[잠재 고객의 결제 유도](prospect-to-cash.md)

[Sales에서 Supply Chain Management의 고객으로 직접 계정 동기화](accounts-template-mapping-direct.md)

[Supply Chain Management에서 Sales의 제품으로 직접 제품 동기화](products-template-mapping-direct.md)

[Sales 및 Supply Chain Management 간에 직접 판매 주문 동기화](sales-order-template-mapping-direct-two-ways.md)

[Supply Chain Management에서 Sales로 직접 판매 송장 헤더 및 라인 동기화](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]