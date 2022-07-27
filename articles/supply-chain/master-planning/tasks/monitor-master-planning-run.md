---
title: 기준 계획 실행 모니터링
description: 이 항목에서는 생산 계획자가 기준 계획 실행이 진행 중인지 여부를 확인할 수 있는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4db1173b35cd196ab39fae3cac3754439fab84d0
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449962"
---
# <a name="monitor-a-master-planning-run"></a>기준 계획 실행 모니터링

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Gantt 차트를 사용하여 기준 계획 진행 상황 시각화

**기준 계획 진행 상황 보기** 페이지에서 과거 기준 계획 실행의 세부 정보를 Gantt 차트로 볼 수 있습니다. 이 기능은 기준 계획의 다양한 단계에 소요되는 시간을 이해하는 데 도움이 될 수 있습니다. 현재 활성 계획 작업의 경우 **기준 계획 진행 상황 보기** 페이지를 사용하여 진행 상황을 추적하고 예상 남은 시간을 볼 수 있습니다.

### <a name="turn-the-master-plan-progress-visualization-feature-on-or-off"></a>기준 계획 진행 상황 시각화 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.21부터 이 기능은 기본적으로 켜져 있습니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *기준 계획 진행 시각화* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

### <a name="use-the-master-plan-progress-visualization-feature"></a>기준 계획 진행 상황 시각화 기능 사용

**기준 계획 진행 상황 보기** 페이지는 기록 계획 작업과 활성 계획 작업을 모두 표시할 수 있습니다. 

기록 계획 작업을 보려면 두 가지 옵션이 있습니다. 

1. **기준 계획 \> 설정 \> 계획 \> 기준 계획** 을 클릭한 다음 작업 창에서 **기록** 을 선택합니다. 원하는 작업을 선택한 상태에서 **문의** 를 선택한 다음 **진행 상황 보기** 를 선택합니다.
1. **기준 계획 \> 작업 영역 \> 기준 계획** 으로 이동하고 기준 계획 타일에서 **기록** 을 클릭합니다. 원하는 작업을 선택한 상태에서 **문의** 를 선택한 다음 **진행 상황 보기** 를 선택합니다.

활성 계획 작업을 보려면 두 가지 옵션이 있습니다. 
1. **기준 계획 \> 작업 영역 \> 기준 계획** 으로 이동하고 작업 창에서 **완료되지 않은 계획 프로세스** 를 선택합니다. 원하는 작업을 선택한 상태에서 **문의** 를 선택한 다음 **진행 상황 보기** 를 선택합니다.
1. **기준 계획 \> 작업 영역 \> 기준 계획** 으로 이동하고 기준 계획 타일에서 **진행 상황 보기** 를 클릭합니다. 원하는 작업을 선택한 상태에서 **문의** 를 선택한 다음 **진행 상황 보기** 를 선택합니다.

계획 작업이 처리 중인 경우에만 활성 작업을 볼 수 있습니다.

### <a name="analyze-a-master-planning-job"></a>기준 계획 작업 분석

Gantt 차트에서 다음 각 계획 프로세스를 확장하여 소요된 시간에 대한 추가 세부 정보를 볼 수 있습니다.

- 초기화
- 데이터 삭제 및 삽입
- 적용 범위 계획
- 지연
- 작업 메시지
- 마무리
- 자동 확정

Gantt 차트는 작업 메시지 사용의 영향을 확인하려는 경우 유용한 도구입니다.

#### <a name="navigation-in-the-gantt-chart"></a>Gantt 차트의 탐색

- 선택한 그룹을 확장하고 세부 정보를 표시하려면 트리 보기에서 더하기 기호(**+**)를 선택합니다.
- 선택한 그룹을 축소하려면 트리 보기에서 빼기 기호(**–**)를 선택합니다.
- 키보드를 사용하여 탐색할 수 있습니다. **위쪽 화살표** 및 **아래쪽 화살표** 키를 사용하여 행 사이를 이동합니다. **오른쪽 화살표** 및 **왼쪽 화살표** 키를 사용하여 그룹을 확장하고 축소합니다.
- Gantt 차트의 모든 수준을 열거나 닫으려면 **모두 펼치기** 또는 **모두 접기** 를 선택합니다.
- 관련 처리 시간을 보려면 작업 위로 마우스를 가져갑니다. (작업은 Gantt 차트에서 가장 낮은 수준입니다.)

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>작업을 비교하기 위한 추가 기준 계획 실행 보기

**추가 기준 계획 실행 표시** 필드에서 기준 계획 직무를 선택하여 Gantt 차트에서 추가 기준 계획 실행을 보고 두 작업을 비교할 수 있습니다.

#### <a name="bom-level-display"></a>BOM 수준 디스플레이

BOM(Bill of Materials) 수준은 적용 범위 계획, 지연, 조치 및 확정에 대해 다르게 표시됩니다.

- **적용 범위 계획** – BOM 수준이 예상대로 표시됩니다. 위에서 아래로 계산됩니다.

    **예:** BOM 수준 0, 1, 2

- **지연** – BOM 수준은 적용 범위 계획 BOM 수준에 –1을 곱한 값으로 표시됩니다. (즉, 음수 부호가 있습니다.)

    **예:** BOM 수준 –2, –1, 0

- **작업 메시지** – BOM 수준이 예상대로 표시됩니다. 위에서 아래로 계산됩니다.

    **예:** BOM 수준 0, 1, 2

- **자동 확정** – BOM 수준은 999에서 적용 범위 계획 BOM 수준을 뺀 값으로 표시됩니다.

    **예:** BOM 수준 999, 998, 997

다음 표에는 동작이 요약되어 있습니다.

| 표시되는 BOM 수준 | 최종 항목 | 하위 구성 요소 | 원료 |
|---|---|---|---|
| 적용 범위 계획 | 0 | 1 | 2 |
| 지연 | 0 | –1 | –2 |
| 작업 메시지 | 0 | 1 | 2 |
| 자동 확정 | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>진행 상황 시각화

현재 실행 중인 기준 계획 작업을 보면 Gantt 차트의 색상을 통해 진행 상황이 표시됩니다. 파란색 테마에는 다음 색상이 적용됩니다. 다른 색상 테마의 경우 색상이 다릅니다.

- **다크 블루** – 완료된 계획 작업.
- **주황색** – 현재 진행 중인 작업.
- **라이트 블루** – 남은 작업에 대한 추정.

색상은 Gantt 차트에서 가장 낮은 수준에만 표시됩니다. **모두 펼치기** 를 선택하여 기준 계획 작업의 모든 작업을 봅니다. 남은 작업의 추정치는 과거 기준 계획 작업을 기반으로 합니다.

## <a name="run-master-planning-and-track-processing-time"></a>기준 계획 실행 및 처리 시간 추적

1. 기본 대시보드에서 **기준 계획** 을 선택합니다.
1. **계획** 필드에 값을 입력하거나 선택합니다.
1. **실행** 을 선택합니다.
1. **처리 시간 추적** 옵션을 **예** 로 설정합니다.
1. **스레드 수** 필드에 숫자를 입력합니다.
1. **포함할 레코드** 빠른 탭에서 **필터** 를 선택합니다.
1. 그리드에서 **필드** 필드가 **품목 번호** 로 설정된 행을 선택합니다.
1. **기준** 필드에서 값을 입력합니다.
1. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]