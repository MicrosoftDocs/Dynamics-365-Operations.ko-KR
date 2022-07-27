---
title: 프로세스 작업에 대한 칸반 규칙 변경
description: 이 절차는 지정된 칸반에 대해 사용된 칸반 규칙을 변경하는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13798e3521efacda896ca88a39faf36ac979d42c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448732"
---
# <a name="change-kanban-rules-for-a-process-job"></a>프로세스 작업에 대한 칸반 규칙 변경

[!include [banner](../../includes/banner.md)]

이 절차는 지정된 칸반에 대해 사용된 칸반 규칙을 변경하는 데 중점을 둡니다. 부하 자원을 평준화하거나 고장난 경우에 유용합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 가치 흐름을 담당하는 린 제조 회사에서 일하는 기획자를 위한 것입니다.


## <a name="copy-kanban-rule"></a>칸반 규칙 복사
1. 칸반 규칙으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * L0001에 대해 이벤트 칸반 규칙 000022를 선택합니다.  
3. 칸반 규칙 복제를 클릭합니다.
4. 확인을 클릭합니다.

## <a name="change-kanban-rule"></a>칸반 규칙 변경
1. 페이지를 닫습니다.
2. 칸반 작업 예약으로 이동합니다.
3. 목록에서 선택한 행을 표시합니다.
    * 칸반 000177로 라인을 선택합니다.  
4. 대체 칸반 규칙 사용을 클릭합니다.
5. 다음을 클릭합니다.
6. 칸반 규칙 필드에서 값을 입력하거나 선택합니다.
    * 이전에 생성한 칸반 규칙을 선택합니다. 가장 높은 번호를 가진 칸반 규칙입니다.  
7. 마침을 클릭합니다.
    * 이제 칸반 작업이 다른 칸반 규칙을 사용하고 있습니다. 로드 작업 셀의 수평을 맞추는 데 유용할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]