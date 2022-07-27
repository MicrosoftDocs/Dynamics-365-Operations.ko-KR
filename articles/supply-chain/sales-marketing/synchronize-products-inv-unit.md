---
title: Supply Chain Management에서 Field Service로 인벤토리 단위 및 제품 동기화
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 인벤토리 단위의 제품을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
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
ms.openlocfilehash: 6ac346d735bc44e9f9660c60b23a73057e4b7306
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447913"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Supply Chain Management에서 Field Service로 인벤토리 단위 및 제품 동기화

[!include[banner](../includes/banner.md)]

이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 인벤토리 단위의 제품을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

사용된 **Field Service 상품 및 인벤토리 단위(Supply Chain Management에서 Field Service로)** 템플릿은 **Field Service 제품(Supply Chain Management에서 Field Service로)** 템플릿을 기반으로 합니다. 자세한 내용은 [Supply Chain Management의 제품을 Field Service의 제품과 동기화](field-service-product.md)를 참조하세요.

이 토픽에서는 두 템플릿 간의 차이점만 설명합니다. 
- **Field Service 상품 인벤토리 단위(Supply Chain Management에서 Sales로)**
- **Field Service 제품(Supply Chain Management에서 Field Service로)** 

## <a name="templates-and-tasks"></a>템플릿 및 작업

**데이터 통합의 템플릿 이름:**

- Field Service 상품 인벤토리 단위(Supply Chain Management에서 Sales로)

**데이터 통합 프로젝트의 작업 이름:**

- 제품

**Field Service 상품 및 인벤토리 단위(Supply Chain Management에서 Field Service로)** 템플릿에는 **Field Service 제품(Supply Chain Management에서 Field Service로)** 템플릿에 포함되지 않은 하나의 매핑이 포함되어 있습니다. 이 매핑은 인벤토리 수준 동기화에 필요한 인벤토리 단위가 포함되도록 합니다.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Field Service 제품 및 인벤토리 단위(Supply Chain Management에서 Field Service로): 제품

[![데이터 통합의 템플릿 매핑.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]