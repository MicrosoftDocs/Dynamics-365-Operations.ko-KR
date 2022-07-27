---
title: 음수 현재고 수량으로 계획
description: 이 항목에서는 계획 최적화를 사용할 때 음수 현재고를 처리하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 07/22/2021
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 97688e09aae9706dd85e7965aa08c7ea873a44d81391c39406e2e6367660e0d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447100"
---
# <a name="planning-with-negative-on-hand-quantities"></a>음수 현재고 수량으로 계획

[!include [banner](../../includes/banner.md)]

시스템이 음수 집계 현재고 수량을 표시하는 경우 계획 엔진은 과잉 공급을 방지하기 위해 수량을 0(영)으로 처리합니다. 이 기능이 작동하는 방식은 다음과 같습니다.

1. 계획 최적화 기능은 적용 범위 차원의 최하위 레벨에서 현재고 수량을 집계합니다. (예를 들어 *위치* 가 적용 범위 차원이 아닌 경우 계획 최적화는 현재고 수량을 *창고* 수준에서 집계합니다.)
1. 적용 범위 차원의 최하위 레벨에서 총 현재고 수량이 음수인 경우 시스템은 현재고 수량이 실제로 0(영)이라고 가정합니다.

> [!IMPORTANT]
> 계획 시스템은 입력 데이터만큼만 정확할 수 있습니다. 입력 데이터가 정확하지 않은 경우 음수 현재고 레코드는 Microsoft Dynamics 365 Supply Chain Management의 재고 정보가 현실 세계와 동기화되지 않습니다. 따라서 계획 결과에 결함이 있습니다. 정확한 계획 결과를 얻으려면 음수 현재고 수량을 표시하는 레코드 수를 최소화해야 합니다.

## <a name="example-1"></a>예시 1

창고 13은 다음과 같은 방식으로 구성됩니다.

- **적용 범위 코드:** 최소/최대
- **최소:** 15개(개)
- **최대:** 25개

적용 범위 차원의 가장 낮은 수준은 *창고* 이고 다음 현재고 수량이 *위치* 수준에 기록됩니다.

- **사이트 1, 창고 13, 위치 1:** 20개
- **사이트 1, 창고 13, 위치 2:** &minus;8개

따라서 창고 13의 총 현재고 수량은 12개 (= 20개 &minus; 8개)입니다.

이 경우 계획 엔진은 창고 13에 대해 총 12개의 현재고 수량을 사용합니다.

결과는 창고 13을 12개에서 25개로 채우는 13개 (= 25개 &minus; 12개)의 계획 주문입니다.

## <a name="example-2"></a>예시 2

창고 13은 다음과 같은 방식으로 구성됩니다.

- **적용 범위 코드:** 최소/최대
- **최소:** 15개
- **최대:** 25개

적용 범위 차원의 가장 낮은 수준은 *창고* 이고 다음 현재고 수량이 *위치* 수준에 기록됩니다.

- **사이트 1, 창고 13, 위치 1:** 4개
- **사이트 1, 창고 13, 위치 2:** &minus;8개

따라서 창고 13의 총 현재고 수량은 &minus;4개 (= 4개 &minus; 8개)입니다. 즉, 0(영)보다 작습니다.

이 경우 계획 엔진은 창고 13의 현재고 수량이 &minus;4개 대신 0개라고 가정합니다.

결과는 창고 13을 0개에서 25개로 채우는 13개 (= 25개 &minus; 0개)의 계획 주문입니다.

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>음수 보유 재고에 대한 예약이 있는 경우 계획

실제 예약이 있는 동안 재고를 조정하면 주문이 음수 재고에 대해 물리적으로 예약되는 상황이 발생할 수 있습니다. 이 경우 실제 예약이 존재하기 때문에 계획 최적화는 보유 재고 입고가 시스템에 아직 등록되지 않은 경우에도 보유 재고에서 지원한다고 가정합니다. 따라서 보충이 필요하지 않다고 가정하고 주문 수량을 보충하기 위한 계획 주문을 생성하지 않습니다.

다음 예제는 이 시나리오를 보여줍니다.

### <a name="example"></a>예:

시스템은 다음과 같이 구성됩니다.

- 제품 *FG* 가 존재하고 보유 재고는 *10* 개 가 있습니다.
- 제품 구성은 실제 음수 재고를 허용합니다.
- 수량 *10* 개 (제품 *FG*)의 판매 주문이 존재합니다.
- 판매 주문 수량은 기존 보유 재고에 대해 물리적으로 예약됩니다.

그런 다음 보유 재고가 0(영)이 되도록 제품 *FG* 의 수량을 조정합니다. 보유 제품 재고가 0이므로 판매 주문 수량은 이제 음수 재고에 대해 예약됩니다. 그러나 지금 기준 계획을 실행하는 경우 계획 최적화에서는 실제 예약을 제공하는 데 필요한 보유 재고가 있다고 가정하기 때문에 판매 주문을 공급하기 위해 계획 주문이 생성되지 않습니다.

## <a name="related-resources"></a>관련 리소스

- [계획 최적화 개요](planning-optimization-overview.md)
- [계획 최적화 시작하기](get-started.md)
- [계획 최적화 적합 분석](planning-optimization-fit-analysis.md)
- [계획 기록 및 계획 로그 보기](plan-history-logs.md)
- [계획 작업 취소](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
