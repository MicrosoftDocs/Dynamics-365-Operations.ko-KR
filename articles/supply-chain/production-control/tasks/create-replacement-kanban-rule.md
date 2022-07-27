---
title: 교체 칸반 규칙 만들기
description: 이 절차는 특정 날짜에 기존 칸반 규칙을 새 칸반 규칙으로 바꾸는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2db44c1b43a6dc5e0ab37a7756c4eecaab468e15
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448273"
---
# <a name="create-a-replacement-kanban-rule"></a>교체 칸반 규칙 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 특정 날짜에 기존 칸반 규칙을 새 칸반 규칙으로 바꾸는 데 중점을 둡니다. 이는 생산 흐름 또는 보충 규칙의 변경을 조정하고 예약해야 할 때 유용합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 프로세스 엔지니어 또는 가치 흐름 관리자가 변경된 생산 흐름 또는 새로운 보충 규칙에 대한 생산을 준비할 때 사용하도록 고안되었습니다. 이 작업은 칸반 규칙 000022를 새 규칙으로 대체하고 새 규칙의 최대 수량을 48개에서 100개로 늘립니다.


## <a name="select-a-kanban-rule-to-replace"></a>대체할 칸반 규칙 선택
1. 칸반 규칙으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 칸반 규칙 000022를 선택합니다.  

## <a name="create-a-replacement-kanban-rule"></a>교체 칸반 규칙 만들기
1. 칸반 규칙 바꾸기를 클릭합니다.
2. 유효 날짜 필드에 날짜와 시간을 입력합니다.
    * 지금부터 일주일 후와 같이 미래 날짜를 선택합니다. 새 칸반 규칙이 활성화되고 이전 칸반 규칙을 대체하는 날짜와 시간입니다.  
    * 칸반 규칙이 생산 흐름의 경로를 변경하면 다른 활동을 선택할 수 있습니다.  이 절차에서는 활동을 그대로 유지합니다.  
3. 확인을 클릭합니다.
    * 칸반 규칙 000022를 대체하기 위해 새 칸반 규칙이 생성됩니다.  
    * 유효 날짜는 칸반 규칙을 대체할 때 선택한 날짜에 따라 설정됩니다.  
4. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 대체된 칸반 규칙 000022를 선택합니다.  
    * 대체된 칸반 규칙의 날짜는 만료 날짜이기 때문에 만료 날짜와 동일합니다.  
5. 목록에서 행 1을 선택합니다.
    * 목록 맨 위에 있는 새 칸반 규칙을 선택합니다. 가장 높은 칸반 규칙 번호를 가진 칸반 규칙입니다.  
6. 목록에서 선택한 행의 링크를 클릭합니다.
    * 칸판 규칙 번호를 클릭하여 칸판 규칙을 엽니다.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>대체 칸반 규칙의 최대 수량 수정
1. 최대 수량을 '100'로 설정합니다.
    * 수량 빠른 탭을 확장하여 최대 수량 필드를 확인합니다. 최대 수량을 100으로 변경하면 최대 100개의 간판을 처리할 수 있습니다.    이 작업의 마지막 단계입니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]