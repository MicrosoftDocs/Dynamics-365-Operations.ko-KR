---
title: 계획 최적화를 통한 재고 표시
description: 이 토픽에서는 계획 최적화를 사용할 때 확정 주문의 재고를 표시하는 데 사용할 수 있는 옵션에 대한 정보를 제공합니다.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: dc94ca8b15d626d8ff64f50718d7d2e3e0326144465f3d27787805220842849f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446614"
---
# <a name="inventory-marking-with-planning-optimization"></a>계획 최적화를 통한 재고 표시

[!include [banner](../../includes/banner.md)]

이 토픽에서는 계획 최적화를 사용할 때 확정 주문의 재고를 표시하는 데 사용할 수 있는 옵션에 대한 정보를 제공합니다.

*마킹* 수요와 공급을 연결하는 데 사용됩니다. 이는 기준 계획이 수요를 커버할 것으로 예상하는 방식을 나타내는 *페깅* 과 유사합니다. 계획의 관점에서 주요 차이점은 마킹이 페깅보다 더 영구적이라는 것입니다.

마킹은 선입선출(FIFO) 및 후입선출(LIFO)에 대한 특별 원가계산 시나리오를 지원하기 위해 도입되었습니다. 그러나 이제는 비용이 들지 않는 일부 시나리오에도 사용됩니다. 수요와 공급 사이의 표시는 선택 사항이며 거의 영구적입니다. 마킹은 사용자가 수동으로 제거하거나 **마킹 제거** 옵션을 선택한 판매 주문 라인 전개를 실행하여 제거할 수 있습니다.

페깅은 수요를 필요한 공급과 연결하기 위해 적용 범위 동안 기준 계획에 의해 제어됩니다. 수요를 충당하는 데 필요한 공급을 최적화하기 위해 각 계획 실행에 대해 페깅을 업데이트할 수 있습니다. 기준 계획이 페깅 정보를 업데이트할 때 기존 표시를 따릅니다.

페깅은 관련 표시, 현재고 예약 및 주문 시 예약을 다음 순서로 포함하는 것으로 시작됩니다.

1. 수요와 공급 사이의 마킹
1. 직접 예약
1. 주문 시 예약

계획 주문을 확정할 때 **확정** 대화 상자는 확정 중에 생성된 주문에 대한 마킹 옵션을 설정하는 데 사용하는 **업데이트 마킹** 필드를 제공합니다. 다음 값 중 하나를 선택합니다.

- **아니요** – 재고 마킹이 적용되지 않습니다.
- **표준** - 페깅에 따라 재고 마킹이 업데이트됩니다. 요구 사항 주문(수요)은 이행 주문(공급)에 대해 표시됩니다. 주문 처리에 일부 수량이 남아 있으면 표시되지 않고 참조 정보가 공백으로 남습니다. 예를 들어, 100개 판매 주문이 150개 구매 주문에 페깅된 경우 참조 정보는 판매 주문에만 할당됩니다.
- **확장** – 이행 주문에 남아 있는 수량에 관계없이 요구 사항 오더(수요)와 이행 주문(공급)이 모두 표시됩니다. 예를 들어, 100개에 대한 판매 주문이 150개에 대한 구매 주문에 페깅된 경우 참조 정보는 판매 주문과 구매 주문 모두에 할당됩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]