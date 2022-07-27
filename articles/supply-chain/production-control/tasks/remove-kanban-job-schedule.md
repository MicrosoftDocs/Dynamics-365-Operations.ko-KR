---
title: 일정에서 간판 작업 제거
description: 이번에는 작업 상태를 계획되지 않음으로 되돌려 일정에서 계획된 절차 간판 작업을 제거하는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 838270189e08065f791c9e58888351025e0a6df8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448636"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>일정에서 간판 작업 제거

[!include [banner](../../includes/banner.md)]

이번에는 작업 상태를 계획되지 않음으로 되돌려 일정에서 계획된 절차 간판 작업을 제거하는 데 중점을 둡니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이는 작업 현장 감독자 또는 생산 계획자를 위한 것입니다.


## <a name="find-a-planned-kanban-job"></a>계획된 간판 작업 찾기
1. 생산 관리 > 칸반 > 칸반 작업 예약으로 이동합니다.
2. 작업 셀 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
    * 작업 셀 1250을 선택합니다.  
4. 선택을 클릭합니다.
5. 작업 상태 표시 필드에서 '예약됨'을 선택합니다.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>일정에서 계획된 간판 작업 제거
1. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 계획됨 상태의 작업(예: 2012년 12월 19일의 작업)을 선택합니다.  
2. 작업 창에서 계획을 클릭합니다.
3. 작업 상태 되돌리기를 클릭합니다.
4. 확인을 클릭합니다.
    * 이는 현재 작업 상태를 '계획됨'에서 '계획되지 않음'으로 되돌리고 절차 보드에서 제거합니다.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]