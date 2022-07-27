---
title: Dynamics 365 Talent - Attract 및 Onboard 앱의 사용 중지
description: 이 항목에서는 Dynamics 365 Talent - Attract 및 Onboard 앱의 사용 중지에 관해 설명합니다.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: df33f35f66e356c3c2a99f0d81ebba1d0f34b5d9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452539"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Dynamics 365 Talent: Attract 및 Onboard 앱의 사용 중지


2019년 12월에 Dynamics 365 Talent - Attract 및 Onboard 앱의 2022년 2월 1일 사용 중단을 발표하여 고객이 2년의 계획 기간을 제공합니다.

이러한 앱의 사용 중지에 관한 자세한 내용은 다음을 참조하세요.
 - [Dynamics 365 Talent - Attract 및 Dynamics 365 Talent: Onboard 앱의 사용 중지](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Dynamics 365 Human Resources로 더 성공적인 인력 구축](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

고객이 다음과 같은 여러 영역에서 데이터 기반 직원 환경을 구축하는 데 필요한 인력 통찰력을 얻을 수 있도록 Dynamics 365 Human Resources를 계속 지원할 것입니다.

- 보상
- 복리후생
- 휴가 및 부재
- 준수
- 급여
- 성과 피드백
- 교육 및 인증
- 셀프 서비스 프로그램

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Dynamics 365 Talent 앱 사용 중지 FAQ

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>2022년 2월 1일부터 Dynamics 365 Talent - Attract 및 Onboard 앱의 사용자 환경은 어떻게 되나요?

애플리케이션을 사용할 수 없고 사용 중지 페이지로 리디렉션됩니다.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>고객은 2022년 2월 1일 이후에도 Dynamics 365 Talent - Attract 및 Onboard 앱의 대한 데이터를 계속 내보낼 수 있나요?
  
아니요, 사용 중지는 2019년 12월에 발표되었으며 필요한 내보내기 기능은 2022년 2월 1일까지 제공되었습니다. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Dataverse에 있는 Dynamics 365 Talent - Attract 및 Onborad 앱의 관련 고객 데이터도 2022년 2월 1일 이후에 삭제됩니까?

아니요, Dataverse 엔터티는 Human Capital Management Talent 솔루션이 삭제되거나 제거되지 않는 한 사용 중지 후에도 고객의 Microsoft Dataverse 환경에 남아 있습니다.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Talent 환경의 이름을 알고 있습니다. Dataverse의 Attract 및 Onboard 데이터를 보려면 어떻게 하나요?

1.  Power Apps: https://make.powerapps.com으로 로그온합니다
2.  Attract 및 Onboard 데이터를 보고 싶은 환경을 선택합니다.
3.  **Dataverse > 테이블** 로 이동합니다. 
4.  **검색** 에 "msdyn_"을 입력합니다. "msdyn_" + 테이블 이름(예: msdyn_candidate)으로 시작하는 테이블 목록이 보이면 Attract 및 Onboard 데이터가 있는 환경을 찾은 것입니다.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Talent 환경의 이름을 모릅니다. Dynamics 365 Talent: Attract 및 Dynamics 365 Talent: Onboard 애플리케이션의 데이터가 있는 환경을 찾으려면 어떻게 해야 하나요?

1)  Power Platform 관리 센터: https://admin.powerplatform.microsoft.com/에 로그인합니다
2)  **환경** 을 선택합니다.
3)  평가할 특정 환경을 선택합니다.
4)  **리소스 > Dynamics 365 앱** 을 선택합니다.
5)  **HCM Talent** 솔루션이 설치된 경우 이 환경에는 Attract 및 Onboard 데이터가 저장되어 있을 것입니다. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> **HCM Talent** 솔루션은 Dynamics 365 Human Resources에서도 사용됩니다.
