---
title: 칸반 작업 예약
description: 이 절차는 특정 작업 셀에 대한 프로세스 칸반 작업 일정을 잡는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cab3af0802ae6fa942460cfdd9c0819e1d31d4b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449176"
---
# <a name="schedule-kanban-jobs"></a>칸반 작업 예약

[!include [banner](../../includes/banner.md)]

이 절차는 특정 작업 셀에 대한 프로세스 칸반 작업 일정을 잡는 데 중점을 둡니다. "자재를 사용할 수 없을 때 프로세스 칸반 작업 준비" 절차는 이 절차를 생성하기 위한 전제 조건입니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 칸반과 함께 작업하는 작업 현장 감독자 및 생산 계획자를 위한 것입니다.


## <a name="select-kanban-jobs-for-a-work-cell"></a>작업 셀에 대한 칸반 작업 선택
1. 생산 관리 > 칸반 > 칸반 작업 예약으로 이동합니다.
2. 기간 능력 팩트 상자 확장
    * 칸반 팩트 상자를 확장합니다.  
3. 작업 셀 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 선택한 행을 표시합니다.
    * 작업 셀 1250을 선택합니다. 이렇게 하면 작업 셀 1250에 대한 작업만 표시되도록 보기가 필터링됩니다.  
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. 선택을 클릭합니다.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>사용 가능한 첫 번째 기간에 칸반 작업 예약
1. 목록에서 선택한 행을 표시합니다.
    * 계획되지 않음 상태인 목록의 첫 번째 행을 선택합니다. 직무 상태 필드의 점선 아이콘은 계획되지 않음을 나타냅니다.  
2. 예약을 클릭합니다.
    * 이렇게 하면 사용 가능한 첫 번째 기간에 칸반 작업이 예약됩니다.  
    * 칸반 작업은 오늘부터 시작되는 기간에 추가되었기 때문에 목록의 끝으로 이동되었음을 알 수 있습니다.  
    * 오늘부터 시작되는 기간이 만석일 경우 첫 번째 가능한 기간으로 작업이 이동됩니다.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>특정 날짜에 두 개의 칸반 작업 예약
1. 목록에서 행 1을 선택합니다.
    * 직무 상태 필드에서 첫 번째 행이 계획되지 않음 상태임을 확인해야 합니다.  
2. 목록에서 행 2를 선택합니다.
    * 직무 상태 필드에서 두 번째 행이 계획되지 않음 상태임을 확인해야 합니다. 이제 처음 두 개의 작업이 선택되었습니다.  
3. 날짜에서 일정을 클릭하여 드롭 대화 상자를 엽니다.
4. 능력 부족 반응 재정의 체크박스를 선택하거나 선택 취소합니다.
    * 이 옵션을 사용하면 기본 용량 부족 대응을 무시할 수 있습니다.  
5. 용량 부족 대응 필드에서 '요청 기간에 추가'를 선택합니다.
    * 이 옵션을 사용하면 작업 셀이 오버로드될 수 있는지 여부에 관계없이 요청된 기간에 작업이 추가됩니다.  
6. 예약을 클릭합니다.
    * 두 작업 모두 원하는 기간에 추가됩니다.  
    * 기간 용량 섹션에서 기간별 로드를 확인할 수 있습니다. 소비 필드는 이 기간에 계획된 소비를 표시합니다. 이 기간의 계획된 소비량이 가용 용량보다 많을 경우 과부하된 소비가 선택됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]