---
title: 칸반 작업으로 자재 전송
description: 이 절차는 자재를 이전하기 위해 인출 칸반 작업을 실행하는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11771bbedc9fe4bdfaaa074c449cd329ce1a1d8f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448069"
---
# <a name="transfer-materials-with-kanban-jobs"></a>칸반 작업으로 자재 전송

[!include [banner](../../includes/banner.md)]

이 절차는 자재를 이전하기 위해 인출 칸반 작업을 실행하는 데 중점을 둡니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 창고 작업자를 위한 것입니다.


## <a name="display-transfer-jobs"></a>전송 작업 표시
1. 전송 작업을 위해 생산 관리 > 칸반 > 칸반 보드로 이동합니다.
2. 필터 섹션을 펼치거나 접습니다.
    * 필터 섹션에서 생산 흐름, 활동 이름, 창고 및 위치에서, 창고 및 위치까지를 필터링하여 보고 싶은 작업을 지정할 수 있습니다.  
3. 보내는 창고 필드에 '11'를 입력합니다.
4. 받는 위치 필드에 '12'를 입력합니다.

## <a name="start-a-transfer-job"></a>전송 작업 시작
1. 목록에서 선택한 행(있는 경우)을 선택 취소합니다.
2. 목록에서 행 4를 선택합니다.
    * 상태가 계획되지 않은 첫 번째 작업을 선택합니다. 이것이 선택된 유일한 작업인지 확인하세요.  
3. 시작을 클릭합니다.
    * 아이콘은 작업이 시작되었음을 나타냅니다.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>두 번째 전송 작업 선택 및 수량 변경
1. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 여러 작업을 선택할 수 있지만 지금은 5행을 선택합니다.  
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이전 단계의 작업이 선택된 유일한 작업인지 확인하세요. 다른 모든 작업을 선택 해제합니다.  
3. 나중에 참조할 수 있도록 작업 수량 필드의 값을 기록해 둡니다.
4. 작업 수량을 '30'으로 설정합니다.
    * 경고에 유의하세요! 30을 이전할 수 없습니다. 칸반 규칙의 설정에 따라 원래 수량만 이전할 수 있습니다.  
5. 작업 수량 필드에 이전에 기록된 값을 사용합니다.
    * 작업 수량을 이전 값으로 설정합니다.  

## <a name="start-the-second-transfer-job"></a>두 번째 전송 작업 시작
1. 시작을 클릭합니다.
    * 그러면 5행의 작업 전송이 시작됩니다.  

## <a name="complete-both-transfer-jobs"></a>두 전송 작업 모두 완료
1. 목록에서 행 4를 선택합니다.
    * 이제 4행과 5행에서 두 개의 전송 작업이 선택됩니다.  
2. 완료를 클릭합니다.
    * 이렇게 하면 두 작업의 전송이 완료됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]