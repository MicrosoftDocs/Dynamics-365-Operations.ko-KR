---
title: 사용자가 워크플로 관련 전자 메일 메시지를 받을 수 있도록 합니다
description: 워크플로 관련 이벤트가 발생할 때 사용자에게 이메일 메시지를 보내도록 시스템을 구성할 수 있습니다.
author: jasongre
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 368fe2fbf1f8a1adcabe37ced5ed942f9fb86fc8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460636"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>사용자가 워크플로 관련 전자 메일 메시지를 받을 수 있도록 합니다

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

워크플로 관련 이벤트가 발생할 때 사용자에게 이메일 메시지를 보내도록 시스템을 구성할 수 있습니다. 예를 들어 승인을 위해 문서가 사용자에게 할당되면 전자 메일 메시지를 사용자에게 보낼 수 있습니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.

1. **탐색 창 > 모듈 > 시스템 관리 > 사용자 > 사용자** 로 이동합니다.
2. 목록에서 원하는 기록을 찾아 선택합니다.
3. **작업 창** 에서 **사용자 옵션** 을 클릭합니다.
4. **워크플로** 탭을 클릭합니다. **알림** 섹션이 확장되어 있어야 합니다. **알림** 섹션에서 워크플로 관련 이벤트에 대해 사용자에게 알림을 받는 방법을 지정할 수 있습니다.  
5. **광고 항목 워크플로 알림 유형** 필드에서 옵션을 선택합니다.
    - 그룹화 - 개별 항목에 대한 알림이 단일 이메일 메시지로 그룹화됩니다.
    - 개별 – 각 항목에 대해 이메일 메시지가 전송됩니다.  
    - 사용자가 클라이언트에서 알림을 받도록 하려면 **이메일로 알림 보내기** 체크박스를 선택합니다.  
6. **저장** 을 클릭합니다.
7. 페이지를 닫습니다.

> [!NOTE]
> 워크플로 전자 메일 템플릿은 워크플로가 시스템 수준(회사별이 아님) 또는 조직 수준(회사별) 워크플로인지 여부에 따라 시스템 전자 메일 템플릿 또는 조직 전자 메일 템플릿에서 제공됩니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]