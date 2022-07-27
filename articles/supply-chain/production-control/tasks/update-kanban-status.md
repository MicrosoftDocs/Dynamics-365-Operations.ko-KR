---
title: 칸반 상태 업데이트
description: 칸반을 실수로 비우거나 받은 칸반을 비워야 하는 경우 칸반 상태를 업데이트해야 합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3fd19febe38d5d0a201d5a50bc57ddb541e12051
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448714"
---
# <a name="update-kanban-status"></a>칸반 상태 업데이트

[!include [banner](../../includes/banner.md)]

칸반을 실수로 비우거나 받은 칸반을 비워야 하는 경우 칸반 상태를 업데이트해야 합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 상점 감독자를 위한 것입니다.


## <a name="find-the-kanban"></a>칸반을 찾습니다.
1. 생산 관리 > 칸반 > 칸반으로 이동합니다.
2. 취급 단위 상태 열 필터를 엽니다.
3. 지우기를 클릭합니다.
    * 이렇게 하면 필터가 재설정됩니다.  
4. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 '000149'인 카드 번호 필드를 필터링합니다.

## <a name="change-emptied-status-to-received-status"></a>비어 있는 상태를 받은 상태로 변경
1. 빈 취급 단위 반전을 클릭합니다.
2. 확인을 클릭합니다.
    * 취급 단위 상태가 수신됨임을 확인합니다.  

## <a name="change-received-status-to-emptied-status"></a>받은 상태를 비어 있는 상태로 변경
1. 빈 칸반을 클릭합니다.
2. 목록에서 선택한 행을 표시합니다.
    * 취급 단위 상태가 비어 있음을 확인합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]