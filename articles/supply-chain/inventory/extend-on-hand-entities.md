---
title: 재고 보유 데이터 엔터티 확장
description: 이 토픽에서는 재고 보유 데이터 엔티티의 기능이 확장과 함께 작동할 수 있도록 INVENTORSITEONHANDENTITY 및 INVENTWAREHOUSEONHANDENTITY 보기에 확장 필드를 추가하는 방법을 보여주는 예를 제공합니다.
author: yufeihuang
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8161d951c3296b63476c4e7b527efca163a4f4b3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449035"
---
# <a name="extend-inventory-on-hand-data-entities"></a>재고 보유 데이터 엔터티 확장

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management는 [확장을 통해 테이블에 필드를 추가](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md)할 수 있는 [확장 기능](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md)을 제공합니다. 이 토픽에서는 재고 보유 데이터 엔티티의 기능이 확장과 함께 작동할 수 있도록 `INVENTORSITEONHANDENTITY` 및 `INVENTWAREHOUSEONHANDENTITY` 보기에 확장 필드를 추가하는 방법을 보여주는 예를 제공합니다. 데이터 엔터티에 대한 자세한 내용은 [데이터 관리](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md) 개요를 참조하세요.

> [!NOTE]
> 다음은 재고 보유 데이터 항목의 일부 목록입니다.
>
> - 사이트별 현재고
> - 사이트별 현재고 V2
> - 창고별 현재고
> - 창고별 현재고 V2

`inventSiteOnHandView` 보기에서 사용하는 테이블에 필드를 추가한 후 확장이 올바르게 인식되도록 엔진을 동기화해야 합니다.

1. 확장 필드를 추가하여 `InventSiteOnHandView` 보기를 확장합니다.
1. 확장 필드를 사용하여 `InventSiteOnHandAggregatedView` 보기를 확장합니다.
1. `getExtensionFields()` 메서드를 수정하여 `InventSiteOnHandAggregatedViewBuilder` viewBuilder 클래스를 확장합니다. 이러한 방식으로 viewBuilder 동기화가 실행될 때 이전 보기 필드를 새 보기 필드에 매핑합니다.

예를 들어 확장을 통해 `InventTable` 테이블에 다음 네 개의 필드를 추가했습니다.

- 사용자 지정 필드 1
- 사용자 지정 필드 2
- 사용자 지정 필드 3
- 사용자 지정 필드 4

이 경우 `getExtensionFields()` 메서드를 다음과 같이 수정해야 합니다.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

이 단계를 완료한 후 새 필드를 추가하여 창고 데이터 엔티티별 현재고와 사이트별 현재고를 확장할 수 있습니다. 이러한 방식으로 해당 데이터 엔터티를 사용하는 데이터 마이그레이션 중에 확장 필드가 인식되고 포함되도록 할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]