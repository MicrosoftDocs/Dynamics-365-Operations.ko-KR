---
title: 작업 셀에 자재를 사용할 수 없는 경우 프로세스 칸반 작업 준비
description: 이 절차는 일부 자재를 작업 셀에 사용할 수 없는 경우 프로세스 칸반 작업을 준비하는 데 중점을 두므로 창고에서 자재를 선택해야 합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f75cdbc6ce6f7e427bf266c90428d73c065eac3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448933"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>작업 셀에 자재를 사용할 수 없는 경우 프로세스 칸반 작업 준비

[!include [banner](../../includes/banner.md)]

이 절차는 일부 자재를 작업 셀에 사용할 수 없는 경우 프로세스 칸반 작업을 준비하는 데 중점을 두므로 창고에서 자재를 선택해야 합니다. "자재를 사용할 수 있을 때 프로세스 칸반 작업 준비" 절차는 이 절차를 생성하기 위한 전제 조건입니다. 이 절차는 시스템 운영자를 위한 것입니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.

1. 공정 작업을 위해 생산 관리 > 칸반 > 칸반 보드로 이동합니다.
2. 작업 셀 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
    * 작업 셀 1250을 선택합니다.  
4. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 칸반 000356을 선택합니다.  
5. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 목록에서 행 4를 선택 취소합니다. 또는 "자재를 사용할 수 있을 때 프로세스 칸반 작업 준비" 작업을 완료하지 않은 경우 행 4를 선택합니다.  
6. 불출 목록 섹션의 확장을 토글합니다.
    * 공급 상태의 항목 없음 아이콘은 작업 셀에 대해 항목 P0002 중 48개가 누락되었음을 나타냅니다.  

## <a name="transfer-materials-to-work-cell"></a>작업 셀에 재료 전송
1. 이전 작업 섹션의 확장을 토글합니다.
2. 빠른 필터를 사용하여 'P0002' 값으로 품목 번호 필드를 필터링합니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 시작을 클릭합니다.
    * 이전이 진행 중입니다.  
5. 완료를 클릭합니다.
    * 이제 칸반 작업의 불출 목록에서 품목 P0002를 사용할 수 있습니다. 즉, 필요한 모든 재료로 칸반을 준비할 수 있습니다.  
6. 준비를 클릭합니다.
    * 직무 상태의 아이콘은 작업이 이제 준비되었음을 나타냅니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]