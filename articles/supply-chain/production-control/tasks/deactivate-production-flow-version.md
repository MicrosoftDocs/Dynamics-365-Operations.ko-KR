---
title: 생산 흐름 버전 비활성화
description: 활성 생산 흐름 버전이 더 이상 필요하지 않으면 비활성화할 수 있습니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1691dc644e2e191a9e74980784d6dcf741dcd598
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448939"
---
# <a name="deactivate-a-production-flow-version"></a>생산 흐름 버전 비활성화

[!include [banner](../../includes/banner.md)]

활성 생산 흐름 버전이 더 이상 필요하지 않으면 비활성화할 수 있습니다. 모든 칸반 규칙 및 활동이 종료되어 다시 활성화되지 않을 경우에만 이 옵션을 사용해야 합니다. 이 생산 흐름 버전과 관련된 모든 칸반 규칙의 만료 날짜는 현재 날짜 및 시간으로 업데이트됩니다. 

활성 생산 흐름 버전을 수정하려면 활성 버전의 만료 날짜를 설정하고 새 버전을 만드는 것이 좋습니다. 이렇게 하면 새 버전 및 관련 칸반 규칙을 준비하는 동안 생산 작업을 계속할 수 있습니다. 

활성 생산 흐름 버전을 만료하려면 만료 날짜를 설정해야 합니다. 그런 의미에서 비활성화는 규칙이라기보다 예외에 가깝습니다. 

이 절차를 수행하려면 비활성화할 수 있는 버전이 있는 생산 흐름이 필요합니다. 버전이 완전히 구식이라고 100% 확신하지 않는 한 생산 환경에서 이 작업을 시도하지 마세요.


## <a name="deactivate-a-production-flow-version"></a>생산 흐름 버전 비활성화
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 비활성화를 클릭합니다.
    * 이 생산 흐름 버전이 더 이상 사용되지 않는다고 100% 확신하지 못하는 경우 진행하지 마십시오. 확인을 클릭하면 모든 활성 칸반 규칙이 만료되고 이 생산 흐름 버전의 모든 생산 및 보충 활동이 즉시 중지됩니다.  
6. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]