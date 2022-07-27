---
title: 린 조직 모델링
description: 이 문서에서는 린 조직 모델링의 핵심 개념에 대한 정보를 제공합니다.
author: johanhoffmann
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, KanbanFlowSelection, KanbanFlow
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3958d21188163fe95e36ba4b8117ae8314b0fd1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448282"
---
# <a name="modeling-a-lean-organization"></a>린 조직 모델링

[!include [banner](../includes/banner.md)]

이 문서에서는 린 조직 모델링의 핵심 개념에 대한 정보를 제공합니다. 

일반적으로 린 제조 시나리오는 관련 없는 칸반 규칙 또는 자재 공급 정책의 집합 이상입니다. 특정 생산 또는 공급 시나리오에 대한 작업 셀 및 위치 전반에 걸친 자재 및 제품의 흐름은 프로세스 또는 이전 활동의 시퀀스 또는 소규모 네트워크로 설명될 수 있습니다. 이 시퀀스 또는 네트워크를 생산 흐름이라고 합니다.

## <a name="production-flows-in-lean-manufacturing"></a>린 제조의 생산 흐름
생산 주문을 기반으로 하는 생산 시나리오에서 자재는 특정 생산 주문로 출고됩니다. BOM(자재 명세서) 및 경로를 기반으로 하는 일련의 작업 중에 제품이 생성되고 최종적으로 제공된 위치에 입고됩니다. 생산 주문의 처리 시간은 몇 분에서 몇 주까지 다양합니다. 모든 관련 원가, 자재 및 노무는 생산 주문에 누적됩니다. 

일괄 생산으로 인한 작업 센터 간의 배송 리드 타임과 초과 재고를 줄이기 위해 린 제조는 제조 및 창고 보충에 칸반 보충 및 슈퍼마켓을 도입합니다. 일반적으로 이러한 기능은 부분적으로 독립적인 칸반 주기의 생성을 방해합니다. 반제품에 대한 칸반 보충은 더 이상 완제품 주문으로 트리거되지 않습니다. 

제안된 다양한 칸반 시나리오에 대한 생산 및 비용 컨텍스트를 재설정하기 위해 활동 기반 생산 흐름이 린 제조의 중추로 도입되었습니다. 모든 칸반 규칙은 이 사전 정의된 구조를 참조합니다. 활동 기반 모델은 다양한 시나리오의 설정을 지원합니다. 그러나 이 모델은 모든 시나리오가 동일한 활동 기반 사용자 인터페이스를 사용하기 때문에 작업 현장 작업자에게 복잡성을 추가하지 않습니다.

## <a name="semi-finished-products-non-bom-levels"></a>반제품(비BOM 레벨)
린 제조는 재고 제품 및 반제품에 대한 칸반을 단일 프레임워크에 통합하므로 모든 경우에 대해 통합된 사용자 경험을 제공합니다. 이 아키텍처로 인해 반제품에 간판을 사용할 수 있도록 추가 BOM 수준을 더 이상 도입할 필요가 없습니다. 이 아키텍처는 또한 재고 거래를 최소한으로 줄이는 데 도움이 됩니다.

## <a name="products-and-material-in-work-in-progress"></a>진행 중인 제품 및 재료
린 제조에서 단일 부품 흐름의 이상적인 상태로 배치 크기를 줄이면 각 피킹 프로세스 또는 간판 등록이 소비 품목에 대한 트랜잭션을 유발하는 경우 재고 트랜잭션이 극적으로 증가할 수 있습니다. 생산 흐름 아키텍처를 사용하면 보관 또는 운송 처리 단위 크기의 철수 칸반과 함께 자재를 생산 흐름으로 이전할 수 있습니다. 출고된 자재의 값은 생산 흐름과 관련된 WIP(작업 진행) 계정에 추가됩니다. 이 동작은 생산 주문에 발행되는 자재의 동작과 유사합니다. 제품 및 반제품에도 동일한 원리를 적용할 수 있습니다. 이러한 제품이 생산 흐름 내에서 생성, 이전 또는 소비되지 않는 한 재고 트랜잭션은 선택 사항입니다. 제품이 재고에 전기된 후 생산 흐름에 대한 WIP 계정은 관련 표준 원가만큼 차감하여 감소합니다.

## <a name="value-streams-and-value-stream-mapping"></a>가치 흐름과 가치 흐름 매핑
린 제조 아키텍처는 Womack과 Jones가 공식화한 5가지 린 원칙인 고객 가치, 가치 흐름, 흐름, 끌어당김 및 완벽에서 영감을 받았습니다. 물리적 제조 세계에서 린 제조 솔루션을 구현하기 위해 승인된 한 가지 방법은 VSM(가치 흐름 매핑)입니다. 이 방법은 Rother와 Shook이 Lean Manufacturing Institute에서 발행한 "Learning to See"에서 소개했습니다. 

미래 상태 가치 흐름은 생산 흐름 버전으로 모델링할 수 있습니다. 가치 흐름의 모든 프로세스는 프로세스 활동으로 모델링됩니다. 이전 상태를 등록해야 하거나 재고 피킹 또는 통합 배송과의 통합이 필요한 경우 이동 또는 이전을 이전 활동으로 모델링할 수 있습니다. 

가치 흐름 자체는 운영 단위로 모델링됩니다. 따라서 가치 흐름을 재정적 차원으로 사용할 수 있습니다.

운영 단위에 대한 자세한 내용은 [운영 단위 생성](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)을 참조하세요.

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>생산 흐름을 기반으로 하는 린 제조 원가 계산
생산 흐름에 대한 원가를 주기적으로 통합하면 관련 WIP 계정이 수정되고 생산 플로우에서 제공하는 제품에 대한 차이를 결정할 수 있습니다.

## <a name="continuous-improvement"></a>지속적인 개선
지속적인 개선을 더 잘 지원하기 위해 생산 흐름은 시간 효율적인 버전으로 구현됩니다. 따라서 모든 관련 간판 규칙과 함께 기존 생산 흐름 버전을 생산 흐름의 향후 버전으로 복사할 수 있습니다. 또한 생산을 위해 검증 및 활성화되기 전에 미래 상태의 생산 흐름을 모델링할 수 있습니다. 전환 날짜 이후에 원활한 자재 흐름을 보장하기 위해 이전 생산 흐름 버전의 기존 칸반이 자동으로 새 버전과 연결됩니다.

## <a name="simplicity"></a>간단
린 제조 구현을 위해 우리는 단순하고 복잡한 생산 시나리오를 확장 가능한 단일 아키텍처로 모델링할 수 있는 생산 흐름 및 활동 접근 방식을 선택합니다. 활동 개념을 자세히 살펴보면 작업 현장과 물류 작업자와 같은 활동 개념을 필요로 하는 사용자를 위한 새로운 단순성을 알 수 있습니다. 재고 트랜잭션 대신 활동 기반 작업에 대해 보고함으로써 모든 린 제조 변형에 대한 통합 사용자 인터페이스는 비즈니스 복잡성을 사용자 인터페이스에서 속한 곳으로 이전합니다. 즉, 린 제조의 중추인 생산 흐름입니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]