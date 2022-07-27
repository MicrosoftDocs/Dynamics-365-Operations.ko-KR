---
title: Supply Chain Management의 제품을 Field Service의 제품과 동기화
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 제품을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 04/09/2018
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
ms.openlocfilehash: 09460139ba2ae7c9be78b1441e1d095952b405f8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447916"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Supply Chain Management의 제품을 Field Service의 제품과 동기화

[!include[banner](../includes/banner.md)]

이 토픽에서는 Dynamics 365 Supply Chain Management에서 Dynamics 365 Field Service로 제품을 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

사용된 **Field Service 제품(Supply Chain Management에서 Field Service로)** 템플릿은 **제품(Supply Chain Management에서 Sales로) – 직접** Prospect에서 Cash로의 템플릿을 기반으로 합니다. 자세한 내용은 [제품(Supply Chain Management에서 Sales로) – 직접](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct)을 참조하세요.

이 토픽에서는 **Field Service 제품(Supply Chain Management에서 Field Service로)** 과 **제품(Supply Chain Management에서 Sales로) – 직접** 템플릿 간의 차이점에 대해서만 설명합니다.

## <a name="templates-and-tasks"></a>템플릿 및 작업

**데이터 통합의 템플릿 이름**

- Field Service 제품(Supply Chain Management에서 Field Service로)

**데이터 통합 프로젝트의 작업 이름**

- 제품 - 제품

**Field Service 제품(Supply Chain Management에서 Field Service로)** 템플릿에는 **제품(Supply Chain Management에서 Sales로) – 직접** 템플릿에 포함되지 않은 하나의 매핑이 포함되어 있습니다. 이 매핑은 필수 Field Service 특정 필드 **서비스 제품 유형** 이 올바르게 설정되도록 합니다.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

다음 값 매핑이 사용됩니다.

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

Supply Chain Management에서 **판매 가능한 출시 제품** 데이터 엔터티의 **Field Service 제품 유형** 값은 다음과 같이 계산됩니다.

- **Inventory:** 제품 유형 = 제품 및 품목 모델 그룹, 재고 제품 = True
- **NonInventory:** 제품 유형 = 제품 및 품목 모델 그룹, 재고 제품 = False
- **Service:** 제품 유형 = 서비스

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Field Service 제품(Supply Chain Management에서 Field Service로): 제품 - 제품

[![데이터 통합의 템플릿 매핑.](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]