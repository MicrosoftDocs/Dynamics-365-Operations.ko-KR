---
title: 생활 이벤트 변경 처리
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources에서 생활 이벤트 변경을 처리하는 방법을 설명합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb894d9886c095d760efe66abcf773a975a99caa
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452374"
---
# <a name="process-life-event-changes"></a>생활 이벤트 변경 처리


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources에서 두 가지 생활 이벤트 변경에 대한 생활 이벤트 변경을 처리합니다.

- 생일 변경
- 자격 규칙 재정의 만료 변경 

1. **복리후생 관리** 작업 영역의 **처리** 에서 **생활 이벤트 변경 처리** 를 선택합니다.

2. **생활 이벤트 변경 프로세스 실행** 대화 상자에서 다음 필드의 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | 등록 기간 | 생활 이벤트 변경을 처리하는 등록 기간. |
   | 법인 | 생활 이벤트 변경을 처리하는 법인. |

3. 백그라운드에서 프로세스를 실행하려면 **백그라운드에서 실행** 을 선택하고 다음 작업을 수행합니다.

   1. 프로세스에 대한 정보를 입력합니다.

   2. 되풀이 작업을 설정하려면 **되풀이** 를 선택하고 되풀이 정보를 입력한 다음 **확인** 을 선택합니다.

   3. 작업 알림을 설정하려면 **알림** 을 선택하고 수신할 알림을 선택한 다음 **확인** 을 선택합니다.

   4. **확인** 을 선택합니다. 프로세스는 설정한 매개 변수로 실행됩니다.

4. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
