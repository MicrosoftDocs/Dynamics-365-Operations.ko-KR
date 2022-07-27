---
title: 칸반 작업 상태 되돌리기
description: 이 절차는 잘못된 칸반 작업 상태를 되돌리는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 771c3b95be05904c84483473a533c708964fbe62
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448720"
---
# <a name="revert-kanban-job-status"></a>칸반 작업 상태 되돌리기

[!include [banner](../../includes/banner.md)]

이 절차는 잘못된 칸반 작업 상태를 되돌리는 데 중점을 둡니다. 이것은 기계 작업자가 잘못된 작업을 업데이트하거나 실수로 잘못된 상태를 설정한 경우에 유용합니다. 이 절차에서 칸반 작업은 실수로 준비된 것으로 등록되고 상태가 되돌립니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 린 제조 회사에서 일하는 작업장 감독자 또는 기계 작업자를 위한 것입니다.


## <a name="open-process-board-for-the-work-cell"></a>작업 셀용 개방형 프로세스 보드
1. 프로세스 작업을 보려면 칸반 보드로 이동합니다.
2. 작업 셀 필드에서 값을 입력하거나 선택합니다.
    * 작업 셀 1260을 선택합니다.  

## <a name="prepare-kanban-job"></a>칸반 작업 준비
1. 준비를 클릭합니다.
    * 회색으로 표시되어 준비를 클릭할 수 없는 경우 선택한 칸반 작업의 상태가 계획됨인지 확인하세요. 이는 빈 칸반 아이콘으로 표시됩니다. 준비가 실패하면 불출 목록의 모든 재료를 사용할 수 있는지 확인하세요.  
2. 목록에서 준비된 작업을 선택합니다.
    * 방금 준비한 첫 번째 작업을 선택합니다.  
    * 칸반 아이콘 내부에 삼각형으로 표시되어 작업 상태가 준비되었음을 알 수 있습니다.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>준비된 칸반 작업 상태 되돌리기
1. 목록에서 선택한 행을 표시합니다.
    * 준비한 첫 번째 작업을 선택합니다.  
2. 작업 창에서 제조를 클릭합니다.
3. 상태 되돌리기를 클릭합니다.
    * 다음 조건이 참인 경우 대체 칸반 규칙을 사용할 수 있습니다. 보충 전략은 두 규칙에 대해 동일합니다.  - 생산 흐름의 버전은 두 규칙 모두 동일합니다.  - 공급되는 제품은 두 규칙 모두 동일합니다.  - 칸반 규칙의 마지막 활동에 대해 구성된 모든 다운스트림 활동은 두 규칙에 대해 동일해야 합니다.  - 두 규칙에 대해 동일한 제공된 인벤토리 차원을 구성해야 합니다.  - 취급 단위의 상태는 할당되지 않음이어야 합니다.  - 이벤트 칸반의 구성은 동일해야 합니다.  
    * 새 상태가 계획됨인지 확인합니다.  
4. 확인을 클릭합니다.
5. 목록에서 선택한 행을 표시 해제합니다.
    * 같은 직업을 선택합니다.  
    * 칸반 작업에 대한 작업 상태는 빈 칸반 아이콘으로 표시되는 계획됨으로 되돌아갑니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]