---
title: 기준 계획 개요
description: 다양한 기준 계획을 사용하여 회사의 일상적인 작업을 지원하고, 모니터링하려는 다양한 계획 전략을 시뮬레이션하고, 내부 성과 또는 고객 만족에 대한 정책과 같은 회사 정책을 구현합니다.
author: ChristianRytt
ms.date: 05/28/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "7911"
- intro-internal
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03467778025287f3692e171bea37b1bfb2ca1646
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449635"
---
# <a name="master-plans-overview"></a>기준 계획 개요

[!include [banner](../includes/banner.md)]

다양한 기준 계획을 사용하여 회사의 일상적인 작업을 지원하고, 모니터링하려는 다양한 계획 전략을 시뮬레이션하고, 내부 성과 또는 고객 만족에 대한 정책과 같은 회사 정책을 구현합니다.

**기준 계획** 페이지에서 기준 계획을 구성할 수 있습니다.

두 가지 유형의 계획이 있습니다.

- **정적 계획** – 기준 계획 계산은 현재 데이터를 사용하여 순 소요량 계획을 생성합니다. 이 계획은 다음에 기준 계획을 실행하거나 계획을 수동으로 변경할 때까지 변경되지 않은 상태로 유지됩니다. 이는 다양한 회사 직원(예: 구매자 또는 생산 계획자)이 자신의 결정을 기반으로 일상 활동을 수행하는 데 사용할 수 있는 운영 계획입니다.
- **동적 계획** – 이 계획은 기준 계획에서 생성된 동일한 순 소요량 계획으로 시작합니다. 그러나 마스터 데이터가 변경될 때마다 동적 계획을 업데이트할 수 있습니다. 예를 들어 새 판매 주문을 생성할 때 발생할 수 있습니다. 이를 통해 사용자는 다른 사람들이 작업 프로세스에 사용하는 고정 계획을 방해하지 않고 주문 변경 네트워크와 항목 가용성을 모니터링할 수 있습니다.

회사는 동적 계획만 사용하거나 정적 및 동적 계획을 모두 사용할 수 있습니다. 또한 특정 전략을 반영하거나 문제를 해결하도록 기준 계획을 구성할 수 있습니다. 예는 다음과 같습니다.

- 재고 부족을 방지하려면 더 높은 재고 수준을 설정하세요.
- 신뢰할 수 없는 공급업체로부터 보호하기 위해 더 긴 안전 여유를 설정합니다.

기준 계획을 실행할 때마다 새 요구 사항 계획으로 업데이트되도록 시작 동적 계획을 설정할 수도 있습니다. **기준 계획 매개 변수** 페이지에서 이러한 설정을 지정할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [적용 범위 설정](coverage-settings.md)
- [기준 일정 계획을 위한 전술 및 작업 계획 분리](https://community.dynamics.com/ax/b/dynamicsaxmanufacturingrdteamblog/posts/separating-tactical-and-operative-planning-for-master-scheduling)
- [기준 계획: 정적 및 동적 기준 계획을 사용합니까, 아니면 하나의 계획을 사용합니까?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
