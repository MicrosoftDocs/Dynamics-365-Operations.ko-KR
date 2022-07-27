---
title: 계획 최적화에서 사용하는 날짜 및 시간 매개 변수
description: 이 토픽에서는 계획 최적이 작업 중에 사용하는 날짜 및 시간 매개 변수에 대한 정보를 제공합니다.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: dc44778dba0a5b914c524ff2ad026ab2f8eb88aa
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "8449407"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>계획 최적화에서 사용하는 날짜 및 시간 매개 변수

[!include [banner](../../includes/banner.md)]

이 토픽에서는 계획 최적이 작업 중에 사용하는 날짜 및 시간 매개 변수에 대한 정보를 제공합니다.

기본 제공 기준 계획 엔진은 모든 집계에서 트랜잭션 날짜를 사용하는 반면 계획 최적화를 날짜로 변환되는 날짜 및 시간 값으로 작동합니다. 이러한 동작의 차이는 예를 들어 계획 최적화가 현재 날짜 이전에 생성된 것으로 간주하기 때문에 기준 계획이 실행되는 날 자정에 생성된 예측 트랜잭션이 포함되지 않는 상황으로 이어질 수 있습니다.

## <a name="parameters-for-issue-and-demand-transactions"></a>발행 및 수요 트랜잭션에 대한 매개 변수

다음 테이블에는 계획 최적화가 발행 및 수요 트랜잭션을 처리할 때 사용하는 매개 변수가 나열되어 있습니다.

| 매개 변수 | 계획 최적화의 매개 변수 이름 | 설명 | Microsoft Dynamics 365 Supply Chain Management의 해당 필드(ReqTrans 테이블) |
|---|---|---|---|
| 예정된 발행 시간 | `PlannedIssueTime` | 문제가 현재 계획된 날짜입니다. | **현재까지**(`FuturesDate`) 및 **지연된 시간**(``FuturesTime`) |
| 요청된 발행 시간 | `RequestedIssueTime` | 사용자가 요청하고 Supply Chain Management에서 설정한 발행 날짜입니다. 이 매개 변수는 출신되거나 승인된 계획 주문에만 적용할 수 있습니다. 계획 주문의 경우 기본적으로 비어 있습니다. | **요청된 날짜**(`ReqDateDlvOrig`) |
| 요청된 발행 시간 | `RequiredIssueTime` | 계획 최적화에 의해 조정되는 필수 발행 날짜입니다. 계획 최적화가 실행될 때 요청된 발행 시간이 과거인 경우 요구된 발행 시간은 오늘 날짜보다 빠르지 않은 첫 번째 공개 날짜로 조정됩니다. 요청한 발행 시간이 캘린더에서 차단됨으로 표시된 경우 필요한 발행 시간은 해당 날짜 이전의 첫 번째 오픈 날짜로 조정됩니다. | **요구 날짜**(`ReqDate`) 및 **요구 시간**(`ReqTime`) |
| 문제 시간 지연 | `IssueTimeDelay` | 계획된 출고 시간과 승인 및 출시된 주문에 대한 요청된 출고 시간 또는 필요한 출고 시간 사이의 시간 차이입니다. | **지연(일)**(`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>입고 및 공급 거래에 대한 매개 변수

다음 테이블에는 입고 및 공급 트랜잭션을 처리할 때 계획 최적화가 사용하는 매개 변수가 나열되어 있습니다.

| 매개 변수 | 계획 최적화의 매개 변수 이름 | 설명 | Supply Chain Management의 해당 필드(ReqTrans 또는 ReqPO 테이블) |
|---|---|---|---|
| 예정된 이용 가능 시간 | `PlannedAvailabilityTime` | 수령을 사용할 수 있도록 계획된 일자입니다. | **요구 날짜**(`ReqDate`) 및 **요구 시간**(`ReqTime`) |
| 예정된 접수 시간 | `PlannedReceiptTime` | 영수증이 해당 위치에 도착하는 날짜입니다. | 주문이 아직 해제되지 않은 경우 **현재까지**(`FuturesDate`), **지연된 시간** (`FuturesTime`) 및 **배송 날짜** (`ReqDateDlv`) 또는 **요청된 날짜** (`ReqDateDlvOrig`). |
| 필수 이용 가능 시간 | `RequiredAvailabilityTime` | 계획 최적화에 의해 조정되는 필수 가용성 날짜입니다. | **요구 날짜**(`ReqDate`) 및 **요구 시간**(`ReqTime`) |
| 예상 접수 시간 | `ExpectedReceiptTime` | 출고된 입고의 예상 입고 일자입니다. 값은 Supply Chain Management에서 사용자가 설정하며 계획 최적화에 의해 조정되지 않습니다. 이 매개 변수는 출시된 입고에만 적용됩니다. | **요청된 날짜**(`ReqDateDlvOrig`) |
| 필요한 입고 시간 | `RequiredReceiptTime` | 계획 최적화에 의해 조정되는 필수 입고 날짜입니다. | **요구 날짜**(`ReqDate`) 및 **요구 시간**(`ReqTime`) |
| 계획된 주문 시간 | `PlannedOrderingTime` | 계획 최적화에서 계산한 주문 날짜입니다. | **주문일**(`ReqDateOrder`) 및 **주문 시간**(`ReqTimeOrder`) |
| 계획된 활동 시작 시간 | `PlannedActivityStartTime` | 이 영수증에 대한 활동이 시작되어야 하는 날짜입니다. | **시작 날짜**(`SchedFromDate`) |
| 입고 시간 지연 | `ReceiptTimeDelay` | 계획된 입고 시간과 필요한 입고 시간 사이의 시차입니다. | **지연(일)**(`FuturesDays`) 및 **지연 시간**(`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>계획 최적화에서 사용하는 날짜 및 시간 매개 변수

다음 그림의 계획은 일 수준이지만 계획 최적화는 더 자세한 수준에서 실행됩니다. 예를 들어 마진은 시간 단위일 수 있으므로 계획 주문 시간은 2021년 1월 22일 11시 35분 등이 될 수 있습니다.

### <a name="example-1-simple-scenario"></a>예시 1: 간단한 시나리오

요청된 발행 시간이 1월 22일인 판매 주문 1은 구매 주문 1에 포함됩니다. 다음과 같은 설정이 사용됩니다.

- 리드 타임 없음
- 일정 없음(모든 요일 열려 있음)
- 여유 없음

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![단순 시나리오](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>예시 2: 리드 타임 시나리오

요청된 발행 시간이 1월 22일인 판매 주문 1은 구매 주문 1에 포함됩니다. 다음과 같은 설정이 사용됩니다.

- 리드 타임 3일
- 일정 없음(모든 요일 열려 있음)
- 여유 없음

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![예시 2: 리드 타임 시나리오.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>예 3: 여유 시나리오

요청된 발행 시간이 1월 22일인 판매 주문 1은 구매 주문 1에 포함됩니다. 다음과 같은 설정이 사용됩니다.

- 리드 타임 3일
- 4일 주문 여유
- 5일 가용성 마진
- 일정 없음(모든 요일 열려 있음)

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![여유 시나리오.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>예 4: 지연 시나리오

요청된 발행 시간이 1월 22일인 판매 주문 1은 구매 주문 1에 포함됩니다. 이 예에서는 예 3과 동일한 설정을 사용하지만 계획 날짜가 1월 15일로 이동되었습니다. 계획된 주문 시간이 오늘 날짜 이전이어야 하므로 역방향 스케줄링(빨간색 마커)이 실패합니다. 따라서 마스터 플랜은 향후 일정을 잡아야 하며 지연이 발생합니다.

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![지연 시나리오.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>예 5: 전송 시나리오

1월 22일에 요청된 발행 시간이 있는 창고 1의 판매 주문 1은 계획 구매 주문이 포함된 창고 2의 이전 주문1에 포함됩니다. 다음과 같은 설정이 사용됩니다.

- 이전 리드 타임 3일(창고 1)
- 구매 리드 타임 2일(창고 2)
- 일정 없음(모든 요일 열려 있음)

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![전송 시나리오.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>예 6: 일정 시나리오의 리드 타임

요청된 발행 시간이 1월 22일인 판매 주문 1은 구매 주문 1에 포함됩니다. 다음과 같은 설정이 사용됩니다.

- 리드 타임 3일
- 발행 일정(금요일 휴무)
- 예약 가능 일정(목요일과 금요일 휴무)
- 입고 일정(화요일, 수요일, 일요일 휴무)
- 리드 타임 일정(목요일과 금요일 휴무)
- 주문 일정(월요일 및 토요일 오픈)

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![일정 시나리오의 리드 타임.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>예 7: 일정 시나리오의 지연

요청된 발행 시간이 1월 22일인 판매 주문 1은 구매 주문 1에 포함됩니다. 이 예에서는 예 6과 동일한 설정을 사용하지만 계획 날짜가 1월 13일로 이동되었습니다. 계획된 주문 시간이 오늘 날짜 이전이어야 하므로 역방향 스케줄링(빨간색 마커)이 실패합니다. 따라서 마스터 플랜은 향후 일정을 잡아야 하며 지연이 발생합니다.

다음 그림은 이 시나리오를 보여줍니다. (더 큰 버전을 열려면 그림을 선택하세요.)

[![일정 시나리오의 지연](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
