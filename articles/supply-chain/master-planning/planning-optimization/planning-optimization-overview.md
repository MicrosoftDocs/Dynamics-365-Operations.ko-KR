---
title: 계획 최적화 개요
description: 이 항목에서는 계획 최적화 기능에 대한 개요를 제공합니다.
author: ChristianRytt
ms.date: 10/31/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 49da88be9faff8f327f8079245b3c07db79308e6
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449707"
---
# <a name="planning-optimization-overview"></a>계획 최적화 개요

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management용 계획 최적화 추가 기능을 사용하면 Dynamics 365 Supply Chain Management 및 관련 SQL 데이터베이스 외부에서 기준 계획 계산을 수행할 수 있습니다. 계획 최적화 기능과 관련된 이점에는 기준 계획 실행 중 성능 향상 및 SQL 데이터베이스에 대한 영향 최소화가 포함됩니다. 빠른 계획 실행은 근무 시간 중에도 수행할 수 있으므로 계획자는 수요 또는 매개 변수 변경에 즉시 대응할 수 있습니다.

계획 최적화를 사용하려면 Microsoft Dynamics Lifecycle Services(LCS)의 프로젝트에서 계획 최적화 추가 기능을 설치하고 Supply Chain Management에서 계획 최적화 기능을 켜야 합니다. 자세한 내용은 [계획 최적화 시작하기](get-started.md)를 참조하세요.

다음 그림은 근무 시간 동안 계획 최적화를 실행할 때의 이점을 보여줍니다.

![근무 시간 동안 계획 최적화를 실행하는 이점.](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>향상된 성능

계획 최적화는 장기 실행 기준 계획과 관련된 시나리오에서 사용할 수 있습니다. 매우 많은 양의 데이터를 포함하는 매우 빠른 계산을 위해 특별히 설계되었습니다. 확장성이 뛰어난 다중 테넌트 서비스로 구축되었기 때문에 여러 인스턴스가 동시에 작동하여 계획을 계산할 수 있습니다. 또한 계획 서비스는 시스템에서 기준 계획의 로드를 제거하고 서버 로드를 최소화하는 데이터 스트림과 함께 작동합니다.

계획 최적화는 다음 목표를 달성하는 데 도움이 될 수 있습니다.

- 더 짧은 런타임을 통해 계획 성능을 개선합니다.
- 기준 계획 실행 중에 다른 프로세스에 대한 영향을 줄입니다.
- 더 자주 계획 실행을 수행합니다. (일일 실행으로 제한되지 않습니다.)
- 향후 비즈니스 성장이 계획 시스템에 과부하를 주지 않을 것이라는 확신을 가지십시오.

## <a name="architecture-and-data-flow"></a>아키텍처 및 데이터 흐름

LCS에서 계획 최적화 추가 기능을 설치하면 계획 최적화 서비스에 대한 보안 연결이 설정됩니다. 서비스는 관련 Supply Chain Management 인스턴스와 동일한 데이터 센터 국가 또는 지역에 있습니다. 계획 최저화가 설정된 후 기준 계획이 실행되면 마스터 데이터 및 트랜잭션 데이터가 Supply Chain Management에서 계획 최적화 서비스로 전송됩니다.

계획 최적화 추가 기능을 제거하면 계획 최적화 서비스의 모든 관련 데이터가 제거됩니다.

### <a name="high-level-data-flow-for-regeneration-runs"></a>재생성 실행을 위한 높은 수준의 데이터 흐름

1. Supply Chain Management 클라이언트는 계획 최적화에서 계획 실행을 요청하는 신호를 보냅니다.
2. 계획 최적화는 통합 커넥터를 통해 필요한 데이터를 요청합니다.
3. SQL 데이터베이스는 설정, 마스터 및 트랜잭션 데이터에 대한 요청된 정보를 커넥터를 통해 계획 최적화로 보냅니다. 커넥터는 Supply Chain Management와 계획 최적화 서비스 간에 정보를 변환합니다.
4. 계획 최적화 서비스는 계획 관련 데이터를 메모리에 보유하고 필요한 계산을 수행합니다.
5. 계획 결과는 커넥터를 통해 Supply Chain Management 데이터베이스로 전송됩니다. 결과에는 계획 주문 및 페깅 정보와 같은 정보가 포함됩니다. 계획 최적화는 계획 실행이 완료되었음을 나타내기 위해 Supply Chain Management에 신호를 보냅니다. 또한 관련 메시지와 경고를 보냅니다.

다음 그림은 데이터 흐름을 보여줍니다.

![재생성 실행을 위한 데이터 흐름.](media/PlanningOptimization2.png)

## <a name="related-resources"></a>관련 리소스

[계획 최적화 시작하기](get-started.md)

[계획 최적화 적합 분석](planning-optimization-fit-analysis.md)

[계획 기록 및 계획 로그 보기](plan-history-logs.md)

[계획에 필터 적용](plan-filters.md)

[계획 작업 취소](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]