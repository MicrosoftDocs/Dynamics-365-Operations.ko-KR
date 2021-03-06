---
title: 기본 제공 기준 계획과 계획 최적화의 차이점
description: 이 항목에는 계획 최적화가 아직 지원하지 않고 계획 최적화 적합 분석 페이지에 나열되지 않은 기능이 나열되어 있습니다.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 575aef709a0ac3b0cf8150f1e816dac04c069814
ms.sourcegitcommit: ddcab9726e9dbcf3296cb0988b97a3ae7ccb3dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2022
ms.locfileid: "8450109"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>기본 제공 기준 계획과 계획 최적화의 차이점

[!include [banner](../../includes/banner.md)]

계획 최적화 결과는 기본 제공 기준 계획 엔진의 결과와 다를 수 있습니다. 차이점은 보류 중인 기능으로 인해 발생할 수 있습니다. 이 항목에는 계획 최적화가 아직 지원하지 않고 **[계획 최적화 적합 분석](planning-optimization-fit-analysis.md)** 페이지에 나열되지 않은 기능이 나열되어 있습니다].

| 기능 | 계획 최적화의 현재 동작 |
|---|---|
| 공칭 무게 제품 | 공칭 무게 제품은 일반 제품으로 간주됩니다.|
| 확장 가능한 규모 | 확장 가능한 치수는 **재고 규모 그룹** 또는 **추적 규모 그룹** 페이지에서 **규모별 적용 범위 계획** 확인란이 선택되어 있 경우에도 계획 주문에서 비어 있습니다. |
| 필터링된 생산 실행 | 자세한 내용은 [생산 계획 - 필터](production-planning.md#filters)를 참조하세요. |
| 예측 계획 | 예측 계획은 지원되지 않습니다. 기준 계획에 예측 모델이 할당된 기준 계획을 사용하는 것이 좋습니다. |
| 계획 주문의 번호 시퀀스 | 계획 주문의 번호 시퀀스는 지원되지 않습니다. 계획 주문 번호는 서비스 측에서 생성됩니다. 계획 주문 번호는 일반적으로 10자리로 표시되지만 시퀀스는 실제로 20자로 구성되며 10자리는 계획 실행 횟수에 할당되고 나머지 10자리는 계획 주문 횟수에 할당됩니다. |
| 계획 복사, 계획 삭제 및 계획 버전 정리 | <p>다음 항목은 탐색 창의 **기준 계획 \> 기준 계획 \> 계획 유지** 에서 비활성화됩니다.</p><ul><li>계획 복사</li><li>계획 삭제</li><li>계획 버전 정리</li></ul> |
| 반품 주문 | 반품 주문은 고려되지 않습니다. |
| 예약 관련 기능 | 자세한 내용은 [무한 용량으로 예약](infinite-capacity-planning.md#limitations)을 참조하세요. |
| 안전 재고 이행 | 계획 최적화는 항상 **항목 적용 범위** 페이지의 **최소 충족** 필드에 대해 *오늘 날짜 + 조달 시간* 옵션을 사용합니다. 이는 안전 재고에 대한 조달 시간이 포함되지 않은 경우 낮은 보유 재고에 대해 생성된 계획 주문이 리드 타임으로 인해 항상 지연되기 때문에 원치 않는 계획 주문 및 기타 문제를 방지하는 데 도움이 됩니다. |
| 안전 재고 페깅 및 순 소요량 | *안전 재고* 요구 사항 유형은 포함되지 않으며 **순 요구 사항** 페이지에 표시되지 않습니다. 안전 재고는 수요를 나타내지 않으며 관련 요구 사항 날짜가 없습니다. 대신 항상 존재해야 하는 재고의 양에 대한 제약을 설정합니다. 그러나 기준 계획 중에 계획 주문을 계산할 때 **최소** 필드 값이 계속 고려됩니다. **순 요구 사항** 페이지의 **누적 수량** 열을 검사하여 이 값이 고려되었는지 확인하는 것이 좋습니다. |
| 운송 캘린더 | **배송 방식** 페이지의 **운송 캘린더** 열에 있는 값은 무시됩니다. |
| 값이 없는 최소/최대 적용 범위 코드| 기본 제공 계획 엔진을 사용하여 최소값 또는 최대값이 설정되지 않은 최소/최대 적용 범위 코드를 사용하는 경우 계획 엔진은 적용 범위 코드를 요구 사항으로 처리하고 각 요구 사항에 대해 하나의 주문을 생성합니다. 계획 최적화를 사용하면 시스템에서 하루에 전체 금액을 충당하기 위해 하루에 하나의 주문을 생성합니다.  |

## <a name="additional-resources"></a>추가 리소스

- [계획 최적화 적합 분석](planning-optimization-fit-analysis.md)
- [계획 최적화에서 사용하지 않는 매개 변수](not-used-parameters.md)
- [계획 최적화에서 사용하는 날짜 및 시간 매개 변수](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
