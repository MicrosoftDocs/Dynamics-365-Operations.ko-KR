---
title: 생활 이벤트 처리
description: Microsoft Dynamics 365 Human Resources의 직원 수명 주기 동안 각 직원은 다양한 생활 이벤트 변경을 경험할 수 있습니다.
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
ms.openlocfilehash: 9155795edf657d6589539e58d4c1536f7e9d64c3
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452569"
---
# <a name="process-life-events"></a>생활 이벤트 처리


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources의 직원 수명 주기 동안 각 직원은 다양한 생활 이벤트 변경을 경험할 수 있습니다. 예를 들어 결혼, 고용 변경 또는 피부양/수혜자 변경이 있습니다. 생활 이벤트를 사용하려면 **복리후생 매개 변수** 페이지에서 생활 이벤트를 활성화하고 생활 이벤트 유형을 설정하고 계획 유형에 대한 생활 이벤트 옵션을 설정해야 합니다.

생활 이벤트를 처리하려면 채용 기간에 이미 공개 등록을 한 번 이상 실행했어야 합니다. 미국에서 공개 등록은 일반적으로 1년에 한 번입니다. 미국 이외의 지역에서는 채용 시 공개 등록이 실행될 수 있습니다. 작업자가 생활 이벤트를 처리하기 위해 복리후생 계획을 선택할 필요는 없지만 공개 등록 처리에는 포함되어 있어야 합니다. 

향후 날짜에 발생하는 생활 이벤트가 있는 작업자가 있으면 생활 이벤트 처리를 사용하세요. 이 이벤트는 처리되지 않은 모든 생활 이벤트를 처리합니다(예: 향후 생활 이벤트 또는 한 작업자에게만 해당되지 않는 생활 이벤트 추가 – 한 예로 신규 복리후생이 있음). 실시간 생활 이벤트는 숨겨져 있습니다.

예를 들어 오늘이 2월 1일이고 2월 14일에 작업자 Joe Smith가 법인을 변경할 예정인 경우 2월 15일에 생활 이벤트 처리를 실행하면 시스템은 2월 15일까지의 모든 이벤트를 처리합니다. 

1. **복리후생 관리** 작업 영역의 **처리** 에서 **생활 이벤트 처리** 를 선택합니다.

2. **생활 이벤트 프로세스 실행** 대화 상자에서 다음 필드의 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **등록 기간** | 생활 이벤트를 처리하는 등록 기간. |
   | **법인** | 생활 이벤트를 처리하는 법인. |
   | **생활 이벤트 날짜** | 시스템은 등록 기간 이 날짜까지 발생한 모든 이벤트를 처리합니다. |
   | **작업자** | 생활 이벤트를 처리하는 작업자. 이 필드를 비워두면 모든 작업자의 생활 이벤트가 처리됩니다. |

3. 백그라운드에서 프로세스를 실행하려면 **백그라운드에서 실행** 을 선택하고 다음 작업을 수행합니다.

   1. 프로세스에 대한 정보를 입력합니다.

   2. 되풀이 작업을 설정하려면 **되풀이** 를 선택하고 되풀이 정보를 입력한 다음 **확인** 을 선택합니다.

   3. 작업 알림을 설정하려면 **알림** 을 선택하고 수신할 알림을 선택한 다음 **확인** 을 선택합니다.

   4. **확인** 을 선택합니다. 프로세스는 설정한 매개 변수로 실행됩니다.

4. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
