---
title: 계획에 필터 적용
description: 이 품목에서는 계획 최적화 기능을 사용할 때 계획에서 필터를 사용하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 01/08/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3612dd45a3f4b8c3597c81962a66c21ed14fb206
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2021
ms.locfileid: "8449410"
---
# <a name="apply-filters-to-a-plan"></a>계획에 필터 적용

[!include [banner](../../includes/banner.md)]

계획 최적화 기능을 사용하는 경우 계획에 필터를 적용할 수 있습니다. **계획 필터** 는 기준 계획 실행 중에 항상 적용됩니다. **계획 필터** 는 계획을 특정 품목 그룹으로 제한하고 결과 기준 계획의 일부로 다른 품목이 포함되지 않도록 하려는 경우에 유용합니다.

**계획 필터** 는 기준 계획 실행 중에 런타임 필터도 적용되고 두 필터의 교차만 계획 실행에 포함됩니다.

**계획 필터** 는 계획 최적화가 사용되는 경우 **기준 계획** 에서 액세스할 수 있습니다.

## <a name="example-scenario"></a>예시 시나리오

품목 A, B 및 C를 포함하는 계획 필터가 설정됩니다. 그런 다음 동일한 계획에 대해 기준 계획 실행이 실행되지만 다른 런타임 필터가 적용됩니다.

- **품목 D를 포함하는 런타임 필터:** 계획 필터와 런타임 필터 사이에 교차점이 없기 때문에 계획된 품목이 없습니다.
- **품목 A 및 D를 포함하는 런타임 필터:** 품목 D는 계획 필터의 일부가 아니므로 품목 A만 계획 실행에 포함됩니다.
- **품목 B를 포함하는 런타임 필터:** 품목 B만 계획 실행에 포함되고 품목 A에 대한 이전 계획 결과는 유지됩니다.
- **모든 품목을 포함하는 런타임 필터(빈 필터):** 품목 A, B 및 C가 계획 실행에 포함되고 품목 A 및 B에 대한 이전 계획 결과를 덮어씁니다.

> [!NOTE]
> **기준 계획 매개변수** 페이지에서 **현재 동적 기준 계획** 으로 선택된 계획에 계획 필터를 설정하면 동적 기준 계획 기능은 필터링된 품목으로 제한됩니다. 예를 들어 계획 필터의 일부가 아닌 품목에 대해 순 소요량을 업데이트하면 결과가 생성되지 않습니다.

## <a name="related-resources"></a>관련 리소스

[계획 최적화 개요](planning-optimization-overview.md)

[계획 최적화 시작하기](get-started.md)

[계획 최적화 적합 분석](planning-optimization-fit-analysis.md)

[계획 기록 및 계획 로그 보기](plan-history-logs.md)

[계획 작업 취소](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
