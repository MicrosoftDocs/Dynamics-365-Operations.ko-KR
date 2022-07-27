---
title: Microsoft Dynamics 365 앱에는 Human Resources가 표시되지 않음
description: 이 항목에서는 Microsoft Dynamics 365 앱에 Microsoft Dynamics 365 Human Resources가 나열되지 않는 경우 해결하는 방법을 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bdbe6c4065a8266fd30a3b093743ded91524f6a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452572"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Microsoft Dynamics 365 앱에 Human Resources 앱이 표시되지 않음


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**문제**

고객에게 Microsoft Dynamics 365 앱 중 Dynamics 365 Human Resources가 보이지 않습니다.

**해결**

Microsoft Power Apps의 환경에 대한 환경 생성자 역할에 사용자를 추가해야 합니다.

1. Power Apps Plan 2 라이선스를 보유한 관리 사용자가 [Power Apps 관리 포털](https://preview.admin.powerapps.com/)을 열어야 합니다.

2. **환경** 을 선택하고 Human Resources에 맞는 환경을 선택합니다.

3. **보안** 탭의 **환경 역할** 탭에서 **환경 생성자** 를 선택합니다.

    ![환경 역할 탭.](media/environment-roles.png)

4. **사용자** 탭에서 사용자 또는 조직을 추가합니다.

    ![사용자 탭.](media/environment-maker.png)

5. **저장** 을 선택합니다.

6. 이제 사용자가 [Microsoft Dynamics 365](https://home.dynamics.com/)에 로그인해야 합니다.

7. **동기화** 를 선택하여 사용자 앱을 업데이트합니다.

    ![동기화 버튼.](media/get-more.png)

    동기화가 완료되면 Human Resources가 홈 페이지에 표시됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
