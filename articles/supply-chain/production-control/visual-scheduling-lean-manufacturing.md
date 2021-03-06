---
title: 린 제조를 위한 시각적 스케줄링
description: 이 토픽에서는 생산 계획자가 칸반 작업에 대한 생산 계획을 제어하고 최적화하는 데 사용할 수 있는 칸반 일정 게시판에 대한 정보를 제공합니다.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization, KanbanBoardUnplannedJobs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af5803793a4874ee73f943d0f059047458c37dc48b7d3276dadc8d8803599fb9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447142"
---
# <a name="visual-scheduling-for-lean-manufacturing"></a>린 제조를 위한 시각적 스케줄링

[!include [banner](../includes/banner.md)]

이 토픽에서는 생산 계획자가 칸반 작업에 대한 생산 계획을 제어하고 최적화하는 데 사용할 수 있는 칸반 일정 게시판에 대한 정보를 제공합니다.

이 토픽에서는 생산 계획자가 칸반 작업에 대한 생산 계획을 제어하고 최적화하는 데 사용할 수 있는 칸반 일정 게시판에 대한 정보를 제공합니다.

칸반 일정 게시판을 사용하면 생산 계획자가 칸반 작업에 대한 생산 계획을 제어하고 최적화할 수 있습니다. 칸반 작업의 흐름을 투명하게 만들고 생산 계획자에게 린 제조 작업 셀에 대한 생산 계획을 최적화하고 조정하는 도구를 제공합니다.

## <a name="visual-scheduling-of-kanban-jobs"></a>칸반 작업의 시각적 일정
칸반 작업은 하나 이상의 칸반 작업으로 구성될 수 있습니다. 칸반 작업에는 두 가지 유형이 있습니다.

-   프로세스
-   이체

**프로세스** 유형의 작업만 예약할 수 있습니다. 칸반 작업 및 활동 시간과 같은 속성은 생산 칸반 플로우에서 정의됩니다. 생산 칸반 플로우에서 칸반 작업은 작업 셀에도 지정됩니다. 작업 셀의 일일 용량은 리소스 그룹에 설정된 작업 셀 용량을 기준으로 계산됩니다. 관련 캘린더의 일일 근무 시간으로 조정됩니다. 칸반 작업이 예약되면 작업은 작업 셀의 용량을 로드합니다. 칸반 일정 게시판은 다음과 같은 주요 기능을 제공합니다.

-   린 작업 셀의 생산 계획에 대한 그래픽 개요. 이 개요는 정의된 기간에 계획된 칸반 프로세스 작업을 보여줍니다.
-   계획되지 않은 칸반 작업을 예약하고 이전에 예약된 작업을 다시 예약할 수 있는 도구입니다.

## <a name="kanban-schedule-board"></a>칸반 일정 보드
**칸반 일정 게시판** 페이지에는 다음 그림과 같이 7개의 주요 요소가 있습니다. 

![칸반 일정 보드.](./media/kanban-schedule-board-1024x554.png)
1.  작업 창
2.  필터 필드
3.  계획되지 않은 작업에 대한 단추
4.  기간 노드
5.  칸반 작업
6.  용량 바
7.  시간 척도

### <a name="view-the-time-scale"></a>시간 척도 보기

보드는 기간으로 나뉘며 각 기간은 노드(4)로 표시됩니다. 세로축은 기간 노드를 나열하고, 가로축은 기간의 길이를 나타내는 시간 척도(7)를 나타냅니다. 기간의 길이는 하루 또는 일주일입니다. 기간 길이는 칸반 일정 게시판(2)에 대해 선택된 작업 셀의 구성에 따라 결정됩니다. 각 기간 노드에 대해 칸반 일정 게시판은 예약된 칸반 작업이 기간을 로드하는 정도를 나타냅니다. 해당 기간의 최대 처리량도 표시됩니다. 예약된 처리량이 최대 처리량을 초과하는 경우 해당 기간은 과부하로 간주되고 빨간색 경고 기호가 나타납니다. 예약된 칸반 작업은 예약된 시작 및 종료 시간(5)이 있는 기간에 나타납니다. 작업의 길이는 활동 시간과 같습니다. 칸반 작업은 활동 시간이 작업 셀의 작업 시간을 초과하는 경우 기간에 겹치는 것으로 나타납니다.

### <a name="view-job-status"></a>작업 상태 보기

칸반 작업에 대한 자세한 정보는 포인터를 작업 위로 가져가면 나타나는 도구 설명에서 확인할 수 있습니다. 기호는 작업 상태에 대한 정보를 제공합니다. 예를 들어 시계 기호는 칸반 작업이 기한이 지났음을 나타냅니다.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>색상을 사용하여 칸반 일정 게시판 보기

칸반 일정 게시판이 제공하는 개요를 향상시키기 위해 색상을 사용하여 칸반 작업을 구별할 수 있습니다. 칸반 작업의 색상은 린 스케줄 그룹에서 구성되며, 여기에서 동일한 순서로 생산되어야 하는 제품을 집계할 수 있습니다. 작업 창의 **보드** 탭에 있는 **테마 색상 사용** 단추를 사용하면 애플리케이션 테마 색상과 린 일정 그룹에 구성된 색상 간에 전환할 수 있습니다. 각 기간에 대해 용량 막대(6)는 해당 기간 동안 칸반 작업으로 로드된 사용 가능한 시간을 나타냅니다. 기간이 과부하되면 용량 막대가 더 두껍고 빨간색으로 나타납니다. 이 모든 기능은 **칸반 일정 게시판** 페이지 상단에 있는 작업 창(1)의 **게시판** 탭에서 사용할 수 있습니다.

## <a name="plan-unplanned-jobs"></a>계획되지 않은 작업 계획
**계획되지 않은 작업 계획** 대화 상자에서 계획되지 않은 칸반 작업을 예약할 수 있습니다. 이 대화 상자를 열려면 계획되지 않은 작업의 현재 수를 표시하는 **계획되지 않은 작업** 단추를 클릭합니다. 또는 작업 창의 **게시판** 탭에서 **계획되지 않은 작업 계획** 을 클릭합니다. 대화 상자에는 작업 셀에 대한 계획되지 않은 칸반 작업 목록이 표시됩니다. **필터** 필드를 사용하여 그리드의 모든 필드를 필터링할 수 있습니다. 예를 들어 특정 제품에 대한 칸반 작업을 필터링할 수 있습니다. 예약할 작업의 필터링된 목록이 있으면 목록에서 해당 작업을 선택한 다음 **확인** 을 클릭합니다. 자동 계획을 사용하여 작업을 예약하려면 **자동 계획** 옵션을 **예** 로 설정합니다. 이 경우 작업은 기한에 따라 기간으로 예약됩니다. 기간별로 작업을 예약할 수도 있습니다. **기간** 필드에서 기간을 선택하기만 하면 됩니다. 다음 그림은 **계획되지 않은 작업 계획** 대화 상자의 예를 보여줍니다. 

![계획되지 않은 작업 계획 대화 상자.](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>같은 기간 내 칸반 작업 순서 지정
기간 내에 하나 이상의 선택한 작업의 순서를 변경할 수 있습니다. 이 기능은 기간 내에 일부 작업의 우선 순위를 지정하려는 경우에 유용할 수 있습니다. 또는 제품 속성이 동일한 작업의 순서를 지정하여 작업 실행을 최적화할 수 있습니다. 끌어서 놓기 작업을 통해 또는 작업 창의 **게시판** 탭에서 **뒤로** 및 **앞으로** 메뉴 항목을 사용하여 순서를 변경할 수 있습니다.

## <a name="reassign-kanban-jobs-across-periods"></a>기간에 걸쳐 칸반 작업 재할당
작업은 한 기간에서 다른 기간으로 재할당될 수 있습니다. 이 기능은 기간이 오버로드되어 여유 용량이 있는 기간으로 로드를 평준화하려는 경우에 유용할 수 있습니다. 끌어서 놓기 작업을 통해 또는 작업 창의 **게시판** 탭에서 **다음 기간** 및 **이전 기간** 메뉴 항목을 사용하여 작업을 재할당할 수 있습니다.

## <a name="open-the-kanban-schedule-board"></a>칸반 일정 보드 열기
다음 페이지의 메뉴 항목을 사용하여 칸반 일정 게시판을 열 수 있습니다.

-   **생산 지역** 페이지
-   **칸반 작업 예약** 페이지로 이동합니다.
-   **생산 흐름 시각화** 페이지


## <a name="additional-resources"></a>추가 리소스

[린 제조를 위한 칸반 작업 스케줄링](lean-manufacturing-kanban-job-scheduling.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]