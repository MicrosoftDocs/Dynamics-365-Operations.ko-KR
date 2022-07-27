---
title: 칸반 공정 작업 실행
description: 이 절차는 칸반 공정 작업 실행에 중점을 둡니다.
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
ms.openlocfilehash: 7ac6f0f6139fe17532f6fbd996b314e0b14f3d90
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447925"
---
# <a name="execute-kanban-process-jobs"></a>칸반 공정 작업 실행

[!include [banner](../../includes/banner.md)]

이 절차는 칸반 공정 작업 실행에 중점을 둡니다. 첫 번째 작업은 예상 수량으로 완료되었으며 오류가 없습니다. 두 번째 작업은 오류와 함께 완료되었습니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 시스템 운영자를 위한 것입니다.


## <a name="select-a-kanban-job"></a>칸반 작업 선택
1. 공정 작업을 위해 생산 관리 > 칸반 > 칸반 보드로 이동합니다.
2. 작업 셀 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 리소스 그룹이 1250인 행을 클릭합니다. 작업 셀 1250에 대한 작업만 표시하도록 작업 목록을 필터링합니다.
    * 계획된 작업 상태가 있는 행을 표시합니다.  

## <a name="complete-a-job-with-expected-quantity"></a>예상 수량으로 작업 완료
1. 세부 정보 섹션을 펼치거나 접습니다.
    * 이 섹션에는 카드 번호, 품목 번호, 주문 수량 및 활동 이름에 대한 중요한 정보가 표시됩니다.  
2. 생산 지침 섹션을 확장하거나 축소합니다.
    * 이 섹션에는 활동에 대한 생산 지침이 표시됩니다. 지침은 텍스트, 그림, 그림 및 기타 문서가 될 수 있습니다.  
3. 시작을 클릭합니다.
    * 완료되지 않은 작업을 선택합니다. 직무 상태 필드의 상태 아이콘을 사용하여 작업 상태를 봅니다.      
4. 완료를 클릭합니다.
    * 예상 품질로 작업이 완료됩니다.  

## <a name="complete-a-job-with-errors"></a>오류가 있는 작업 완료
1. 시작을 클릭합니다.
    * 작업이 완료되면 목록의 다음 작업이 자동으로 선택됩니다. 이 점이 시작을 클릭하기 전에 작업을 선택할 필요가 없는 이유입니다.  
2. 작업 창에서 제조를 클릭합니다.
3. 완료(세부 정보)를 클릭합니다.
4. 목록에서 선택한 행을 표시합니다.
5. 오류 수량 필드에 숫자를 입력합니다.
6. 상품 수량 필드에 숫자를 입력합니다.
7. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]