---
title: 배치 특성
description: 이 항목에서는 배치 특성에 대한 정보를 제공합니다. 배치 특성은 재고 배치를 구성하는 원자재 및 완제품의 특성입니다. 이 항목에서는 배치 특성을 할당하는 방법과 배치를 예약할 때 속성을 검색하는 방법도 설명합니다.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup, WHSBatchAttribReserve
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceb971e7468245297f2359317533b123a3a4f83a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447805"
---
# <a name="batch-attributes"></a>배치 특성

[!include [banner](../includes/banner.md)]

이 항목에서는 배치 특성에 대한 정보를 제공합니다. 배치 특성은 재고 배치를 구성하는 원자재 및 완제품의 특성입니다. 이 항목에서는 배치 특성을 할당하는 방법과 배치를 예약할 때 속성을 검색하는 방법도 설명합니다.

배치 특성은 재고 배치를 구성하는 원자재 및 완제품의 특성입니다. 배치 특성은 환경 조건, 배치를 생산하는 데 사용되는 원자재의 품질 또는 완제품의 결과와 같은 요인에 따라 달라질 수 있습니다. 사용되는 배치 속성의 수와 유형은 산업마다 크게 다를 수 있습니다. 다음은 배치 속성을 사용하는 방법을 보여주는 두 가지 예입니다.

-   치즈 산업에서 치즈를 생산하는 데 사용되는 원료 중 하나인 우유는 지방 함량 및 중량 백분율과 같은 속성을 가질 수 있습니다. 우유에서 생산되는 치즈는 수분 및 숙성과 같은 다른 속성을 가질 수 있습니다.
-   철강 산업에서 생산되는 철은 마그네슘 함량, 은 함량 및 아연 함량의 백분율과 같은 속성을 가질 수 있습니다.

특성의 수와 유형을 더 잘 관리하기 위해 일괄 특성 그룹을 사용할 수 있습니다. 이런 식으로 각 특성을 개별적으로 추가할 필요가 없습니다.

## <a name="assign-batch-attributes"></a>배치 특성 할당
재고 배치에 보관된 개별 제품에 배치 특성을 지정하거나 특정 고객과 연결된 제품에 지정할 수 있습니다. 고객 수준에서 배치 특성을 지정하려면 먼저 제품 수준에서 지정해야 합니다. 제품은 배치 차원이 추적 규모 그룹에서 **활성** 으로 설정되어야 합니다. 개별 제품에 배치 속성을 할당하려면 제품별 페이지를 사용하세요. 속성이 고객의 제품에만 해당하는 경우 고객별 페이지를 사용하세요. 제품에 속성을 추가할 때 다른 매개변수도 정의합니다. 여기 예시들이 있습니다 :

-   **정수** 또는 **분수** 유형의 속성에 대한 최소 및 최대 범위.
-   **정수** 또는 **분수** 유형의 특성에 대한 허용 오차 조치. 특성 값이 최소 및 최대 범위를 벗어나는 경우 조치는 경고 메시지 또는 오류 메시지가 될 수 있습니다.
-   특성의 대상 값입니다. 이 값은 특성의 최적 값이며 모든 속성 유형에 적용됩니다.

제품 정보 관리의 **출고된 제품** 페이지에서 선택한 제품의 페이지에 액세스할 수 있습니다. 제품에 배치 속성을 할당한 후 **인벤토리 배치 특성** 페이지에서 특정 값을 제품의 속성에 추가할 수 있습니다.

## <a name="reserve-batches"></a>예약 배치
고객의 주문을 이행하기 위해 판매 주문에 대해 일괄 예약을 수행하거나 생산 주문에 대해 일괄을 선택 및 예약할 때 일괄 속성을 검색할 수 있습니다. 검색은 원하는 배치 속성이 있는 제품이 포함된 재고 배치를 찾는 데 도움이 됩니다. 배치를 찾은 후 원래 재고 트랜잭션 라인에 제품을 예약할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]