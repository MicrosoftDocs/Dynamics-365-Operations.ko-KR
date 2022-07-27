---
title: 판매 주문에 대해 동일한 배치 예약
description: 이 문서에서는 단일 인벤토리 배치에 대해 인벤토리 예약을 허용하도록 제품을 설정하는 방법을 설명합니다.
author: Henrikan
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d4f3ee5d99648155e663c9ad0849b0b9ae3f80e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448924"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>판매 주문에 대해 동일한 배치 예약

[!include [banner](../includes/banner.md)]

이 문서에서는 단일 인벤토리 배치에 대해 인벤토리 예약을 허용하도록 제품을 설정하는 방법을 설명합니다.

동일한 배치 예약을 사용하면 단일 재고 배치에 대해 판매 주문 라인에 대한 재고를 예약할 수 있습니다. 예를 들어, 벽지를 주문하는 고객은 롤 간의 불일치를 피하기 위해 전체 주문이 동일한 배치 또는 로트에서 채워지도록 요청할 수 있습니다. 동일한 일괄 예약을 사용하도록 제품을 설정하려면 제품에 할당하는 항목 모델 그룹, 추적 규모 그룹 및 재고 규모 그룹에서 다음 설정이 사용되어야 합니다.

- **항목 모델 그룹** – 항목 모델 그룹에는 재고 정책에 대한 **예약** 필드 그룹에서 **동일한 일괄 선택** 및 **통합 요구 사항** 필드가 선택되어 있어야 합니다.
- **추적 규모 그룹** – 추적 규모 그룹에는 배치 번호에 대해 **규모별 적용 계획** 필드가 선택되어 있어야 합니다.
- **재고 규모 그룹** – 재고 규모 그룹에는 **사이트** 및 **창고** 에 대해 **규모별 적용 범위** 계획 필드가 선택되어 있어야 합니다.

동일한 배치 선택을 위해 설정된 판매 주문 라인의 제품에 대한 재고를 예약하면 시스템은 단일 재고 배치에서 주문 수량을 예약하려고 시도합니다. 특정 배치 속성 요구 사항도 고려됩니다. 단일 배치에서 수량을 채울 수 없는 경우 **동일한 배치 예약 충돌** 페이지가 나타납니다. 이 페이지에서는 문제와 예약을 계속하기 위해 취할 수 있는 조치에 대해 설명합니다. 다음 조건으로 인해 배치가 예약되지 않을 수 있습니다.

- 배치 코드에는 **차단됨** 플래그가 지정된 판매에 대한 **차단 예약** 이 있습니다.
- 만료 날짜 및 해당 고객 판매 가능 날짜를 기준으로 배치가 만료되었습니다. 항목에 대한 항목 모델 그룹이 FEFO(선입선출) 날짜로 통제되고 품질 유지 기한이 선택 기준으로 선택된 경우 항목을 예약 대상으로 고려할 수 있습니다.
- 만료 날짜와 품질 유지 기한 및 고객 판매 가능 날짜를 기준으로 배치에 남은 유효 기간이 충분하지 않습니다.

**창고 관리 프로세스 사용** 이 사용 설정된 재고 규모 그룹과 연결된 항목의 경우 배치 번호 재고 규모가 이 위치 차원 위에 정의된 예약 계층을 사용하여 특정 배치 번호를 예약할 수 있습니다. 이러한 유형의 예약 계층을 *Batch-above \[위치\]* 예약 계층이라고도 합니다. 판매 및 이전 주문 라인에 대한 **배치 예약** 페이지에서는 사용 가능한 배치 번호를 기반으로 여러 라인을 선택하고 예약할 수도 있습니다. *위치(Batch-low \[위치\])* 아래에 배치 번호 차원이 있는 예약 계층을 사용하는 경우 수행할 작업에 대한 자세한 내용은 [유연한 창고 수준 차원 예약 정책](../warehousing/flexible-warehouse-level-dimension-reservation.md)을 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
