---
title: 제품 데이터 엔터티
description: 이 토픽에서는 제품 데이터를 가져오고 내보내는 데 사용할 수 있는 다양한 엔터티에 대한 정보를 제공합니다.
author: t-benebo
ms.date: 01/07/2020
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
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 2784e552d7984bbea9c74ad800c6305ab2a216e9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447988"
---
# <a name="product-data-entities"></a>제품 데이터 엔터티

[!include [banner](../includes/banner.md)]

제품 데이터를 가져오고 내보내려면 데이터 엔터티를 사용해야 합니다. 다음 테이블은 제품 관련 데이터 엔터티에 대한 세부 정보를 제공하고 각각의 목적을 설명합니다.

| 엔터티 | AOT(애플리케이션 개체 트리) 이름(유형) | 메모 |
|--------|-------------------------------------------|-------|
| 제품 V2 | `EcoResProductV2Entity` | 이 엔터티는 공유 제품(고유 제품 및 제품 마스터)을 가져오고 내보내는 데 사용됩니다. 업데이트를 허용합니다. 세트 기반 SQL 작업을 지원하지 않습니다. OData(Open Data Protocol)에 대해 활성화되어 있습니다. |
| 출시된 제품 V2 | `EcoResReleasedProductV2Entity` | 이 엔터티는 출시 제품(고유 제품 및 제품 마스터)을 가져오고 내보내는 데 사용됩니다. 업데이트를 허용합니다. 공유 제품이 이미 생성되어 있어야 합니다. 새로 출시된 제품을 가져오면 공유 제품의 출시가 발생합니다. 출시된 제품 마스터 및 출시된 고유한 변형을 가져오고 내보내는 데 사용할 수 있는 별도의 엔터티도 있습니다. 이 엔터티는 집합 기반 SQL 작업 또는 삭제 작업을 지원하지 않습니다. OData에 대해 활성화되었습니다. |
| 출시된 제품 생성 V2 | `EcoResReleasedProductCreationV2Entity` | 이 엔터티는 공유 제품과 출시 제품을 한 번에 가져오는 데 사용됩니다. 내보내기를 지원하지만 엔터티의 목적이 제품 생성이므로 사용하지 않는 것이 좋습니다. 업데이트를 지원하지 않습니다. 제한된 필드 집합(제품 생성 대화 상자에서 사용 가능한 필드)를 지원합니다. 세트 기반 SQL 작업을 지원하지 않습니다. OData를 통해 노출되지 않습니다. |
| 제품 변형 | `EcoResProductVariantEntity` | 이 엔터티는 공유 제품 변형을 가져오고 내보내는 데 사용됩니다. 업데이트를 허용합니다. 차원 값이 이미 생성되어 있어야 합니다. 통합 키는 제품 마스터에 제품 크기를 더한 것입니다. 엔터티는 세트 기반 SQL 작업을 지원하지 않습니다. OData에 대해 활성화되었습니다. 삭제 작업을 지원합니다. 새 제품 크기를 추가하여 확장할 수 없습니다. |
| 제품 번호 식별 기준 제품 변형 | `EcoResProductNumberIdentifiedProductVariantEntity` | 이 엔터티는 공유 제품 변형을 가져오고 내보내는 데 사용됩니다. 업데이트를 허용합니다. 차원 값이 이미 생성되어 있어야 합니다. 통합 키는 제품 번호입니다(**제품 변형** 엔터티의 통합 키는 제품 마스터에 제품 크기를 더한 것입니다). |
| 출시된 제품 변형 | `EcoResReleasedProductVariantEntity` | 이 엔티티는 출시된 제품 변형을 가져오고 내보내는 데 사용됩니다. 업데이트를 허용합니다. 공유 제품 변형이 이미 생성되어 있어야 합니다. 새로 출시된 제품 변형을 가져오면 공유 제품 변형의 출시가 발생합니다. 엔터티는 세트 기반 SQL 작업을 지원하지 않습니다. OData에 대해 활성화되었습니다. 삭제 작업을 지원하지만 해당 사용은 현재 플랫폼의 버그로 인해 현재 데이터 손상을 일으킵니다. 이 엔터티는 새 제품 크기를 추가하여 확장할 수 없습니다. |
| 출시된 제품 번호 식별 기준 제품 변형 | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | 이 엔터티는 **출시된 제품 변형** 엔터티와 유사하지만 통합 키는 제품 마스터에 제품 치수를 더한 대신 제품 번호입니다. 새 제품 크기를 추가하여 확장할 수 없습니다. |
| 판매 가능한 출시 제품 | `EcoResSellableReleasedProductEntity` | 이 엔터티는 판매 가능한 제품만 내보내는 데 사용됩니다. 판매 가능 제품은 판매 주문에 사용하기 위해 필요한 정보가 있는 제품입니다. **출시된 제품** 페이지의 **유효성 검사** 기능을 사용하여 제품의 유효성을 검사할 때도 동일한 규칙이 적용됩니다. |
| 고유 제품 V2 출시 | `EcoResDistinctProductV2Entity` | 이 엔터티는 고유 제품을 내보내는 데 사용됩니다. 이러한 고유 제품은 제품, 하위 유형 제품 및 제품 변형일 수 있습니다. |
| 출시된 제품 마스터 V2 | `EcoResProductMasterV2Entity` | 이 엔터티는 제품 마스터를 가져오고 내보내는 데 사용됩니다. 데이터 관리에 사용할 수 없습니다. |
| 항목 - 바코드 | `EcoResProductBarcodeEntityV3` | 이 엔터티는 제품 및 바코드를 내보내는 데 사용됩니다. 이 엔터티는 변경 내용 추적, 업데이트 또는 삭제를 허용하지 않습니다. 바코드에 대한 변경 추적, 업데이트 또는 삭제를 사용하려면 **항목 - 바코드 연결** 엔터티를 사용합니다. |
| 항목 - 바코드 연결 | `EcoResProductBarcodeAssociationEntity` | 이 엔터티는 제품 및 바코드를 내보내는 데 사용됩니다. 변경 추적, 업데이트 및 삭제가 가능합니다. 엔터티를 사용하려면 기능 *항목 - 바코드 개선 기능* 이 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 활성화되어야 합니다. 엔터티 키는 `AssociationID`이며 바코드와 제품 간의 연결을 생성합니다. 이 키에 대한 지원을 추가하려면 테이블 `InventitemBarcodeAssociation` 기능을 켤 때 기존 항목 바코드 데이터에 대해 채워집니다. 테이블은 일괄 작업을 사용하여 채워지며 바코드 테이블에 많은 수의 레코드가 있는 경우 일괄 작업을 실행하는 데 상당한 시간이 걸릴 수 있습니다. 따라서 비즈니스 일정에 맞는 시간에 기능을 사용 설정(따라서 일괄 작업 실행)하도록 계획하는 것이 좋습니다. |
| 제품 수명 주기 상태 | `EcoResProductLifecycleSateEntity` | 이 엔터티는 제품에 할당할 수 있는 다양한 제품 수명 주기 상태를 가져오고 내보내는 데 사용됩니다. |

> [!NOTE]
> **출시된 제품 V2** 데이터 엔터티를 사용하여 공유 제품이 이미 생성된 경우에만 시스템으로 제품을 가져올 수 있습니다. 그렇지 않으면 제품을 시스템으로 가져오려면 **제품 생성** 데이터 엔터티를 사용해야 합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]