---
title: 특정 제품 수명 주기 상태가 있는 제품 제외
description: 이 항목에서는 계획 최적화 기능을 사용할 때 수명 주기 상태를 기반으로 제품을 제외하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 030bdea7c03dd5eb3347c1d43acd1aeabdf566602872dd8ef5aab6d16b06f503
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446863"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>특정 제품 수명 주기 상태가 있는 제품 제외

[!include [banner](../../includes/banner.md)]

출시된 제품 및 출시된 제품 버전에는 **제품 수명 주기 상태** 필드가 포함됩니다. 이 필드를 사용하면 무엇보다도 기준 계획 중에 포함되는 제품을 제어할 수 있습니다. **제품 정보 관리 \> 설정 \> 제품 수명 주기 상태** 로 이동하여 필요에 따라 수명 주기 상태를 추가, 제거 및 편집할 수 있습니다. 각 제품 수명 주기 상태에 대해 해당 상태의 제품이 기준 계획 중에 포함되어야 하는 경우 **계획에 대해 활성** 옵션을 *예* 로 설정합니다. 옵션을 *아니요* 로 설정하면 관련 제품 및 변형이 모든 기준 계획 및 BOM(자재 명세서) 수준의 모든 계산에서 제외됩니다.

**제품 수명 주기 상태** 필드가 비어 있는 출시된 제품 및 변형은 **계획에 대해 활성** 옵션이 *예* 로 설정된 제품 수명 주기 상태가 있는 것처럼 처리됩니다. 즉, 기준 계획에 포함될 예정입니다.

> [!NOTE]
> 불필요한 공급 제안을 방지하려면 사용되지 않는 출시된 모든 제품 및 변형을 **계획에 대해 활성** 옵션이 *아니요* 로 설정된 제품 수명 주기 상태와 연결하는 것이 좋습니다. 이 접근 방식은 낭비를 방지하는 데 도움이 되므로 재사용할 수 없는 제품 구성 변형으로 작업할 때 특히 중요합니다.

## <a name="related-resources"></a>관련 리소스

제품 수명 주기 상태에 대한 자세한 내용은 [제품 수명 주기 상태 개요](../../pim/product-lifecycle.md)를 참조하세요.

제품 수명 주기 상태를 사용하여 기준 계획 및 BOM 수준 계산에서 제품을 제외하는 단계가 포함된 자세한 내용은 [기준 계획에서 제품을 제외하도록 제품 수명 주기 상태 만들기](../../pim/tasks/exclude-products-master-planning.md)를 참조하세요.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]