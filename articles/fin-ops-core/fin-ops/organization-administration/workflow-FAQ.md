---
title: 워크플로 FAQ
description: 이 항목에서는 워크플로 시스템에 관해 자주 묻는 질문에 대한 답변을 제공합니다.
author: ChrisGarty
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e9e2000684081035f35ea55e1c773a4f6976d74
ms.sourcegitcommit: 967b93bb42413b5b38b817f924015468312a93a0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460634"
---
# <a name="workflow-faq"></a>워크플로 FAQ

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 항목에서는 워크플로 시스템에 관해 자주 묻는 질문에 대한 답변을 제공합니다.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>작업 항목이 거부될 때 여러 알림이 수신되는 이유는 무엇입니까?
작업 항목이 거부되면 해당 작업 항목은 거부된 것으로 완료됩니다. 다른 작업 항목이 생성되어 작성자에게 할당됩니다. 이는 거부된 작업 항목에 대해 작성자에게 알림이 있고 새 "변경 요청된" 작업 항목에 할당된 사용자에게 별도의 알림이 있음을 의미합니다. 

각 알림은 다른 작업 항목에 대한 것이지만 유사성은 혼동을 일으킬 수 있습니다. 향후 릴리스에서 이를 개선할 방법을 찾고 있습니다.

## <a name="why-are-my-workflow-exports-failing"></a>내 워크플로 내보내기가 실패하는 이유는 무엇입니까?
현재 워크플로 이름이 48자를 초과하지 못하도록 하는 워크플로 내보내기 기능에 제한이 있습니다. 48자보다 긴 이름을 사용하면 "서버가 요청을 인증하지 못했습니다." 오류가 발생하거나 파일 유형 없이 파일을 내보내지 못할 수 있습니다. 다음 블로그 게시물은 [워크플로 내보내기 문제 해결](https://community.dynamics.com/365/financeandoperations/b/elandaxdynamicsaxupgradesanddevelopment/posts/workflow-export-troubleshooting)에 대한 자세한 내용을 제공합니다.

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>워크플로 제출자도 워크플로를 승인할 수 있습니까?
예, 워크플로 제출자는 워크플로가 그렇게 구성된 경우 워크플로를 승인할 수도 있습니다. 이 동작을 방지하려면 **시스템 관리 > 워크플로 > 워크플로 매개변수 > 일반 > 승인자 > 제출자의 승인 허용 안함** 을 **네** 로 설정합니다.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>사용자에게 알림을 제공하기 위해 워크플로에 경고를 추가할 수 있습니까?
다음은 알림을 제공하기 위해 워크플로에 경고를 추가할 때 주의해야 할 몇 가지 주요 영역입니다.
- 경고 대 워크플로 알림 메커니즘
    - 기록 변경에 대한 경고를 설정할 수 있습니다. 워크플로는 레코드를 변경하므로 워크플로로 인한 레코드 변경과 관련된 경고를 설정할 수 있습니다. 그러나 워크플로에는 서로 다른 기본 제공 알림 옵션이 있으므로 경고를 사용하는 것은 이상적이지 않습니다.
- 워크플로의 표준 알림 
    - 워크플로에는 이메일 알림이 내장되어 있습니다. 고객은 사용자에게 이메일을 보내도록 알림을 구성할 수 있습니다. 이러한 알림은 사용자에 대한 알림 센터 메시지로 이어지지 않습니다.
    - 향후 업데이트에서 사용자에게 워크플로 작업 항목을 할당할 수 있도록 Action Center 메시지를 추가할 예정입니다. 
- 워크플로에 알림 추가
    - Action Center 메시지는 X++의 워크플로에서 생성된 메시지와 같이 특정 사용자에 대해 생성할 수 있습니다.
    - [워크플로의 비즈니스 이벤트](../../dev-itpro/business-events/business-events-workflow.md)에는 고객이 Flow를 트리거하는 데 사용할 수 있는 알림에는 원하는 알림이 있습니다.   

요약하면, 사용자가 워크플로 작업 항목을 할당받았을 때 관리 센터에서 적절한 알림을 받지 못한 경우 Microsoft Power Automate에서 [워크플로 비즈니스 이벤트](../../dev-itpro/business-events/business-events-workflow.md)를 활용하여 추가 또는 다른 알림을 제공합니다.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>워크플로 편집기가 AD FS에서 시작할 수 없는 이유는 무엇입니까?
업그레이드된 환경의 AD FS(Active Directory Federation Services)에서 실행하는 경우 워크플로 편집기를 시작하는 데 문제가 있을 수 있습니다. 그렇다면 URL "https://dynamicsaxworkfloweditor/"가 ADFS 설정에서 속성 **Microsoft Dynamics 365 for Operations 온-프레미스 - 워크플로 - 기본 애플리케이션** 에 추가됩니다.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>워크플로 처리에서 SQL 교착 상태가 발생하는 이유는 무엇입니까? 
**워크플로 매개 변수** 페이지의 **배치당 워크플로 항목 수** 에 대한 기본 필드 값은 0입니다. 값이 0이면 기본값이 배치당 20개 항목으로 변경됩니다. 일괄 처리당 항목 수가 많으면(> 40) SQL 교착 상태가 발생할 수 있으므로 이 값을 조정할 때 주의하세요.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>워크플로 확장 오류 기능이란 무엇입니까?
버전 10.0.13의 워크플로 향상된 오류 기능은 다양한 클래스의 워크플로 오류를 구별하기 위해 오류 코드를 추가합니다. 보고된 오류 메시지는 더 명확하게 하기 위해 약간의 차이점을 제외하고 대부분 유사합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
