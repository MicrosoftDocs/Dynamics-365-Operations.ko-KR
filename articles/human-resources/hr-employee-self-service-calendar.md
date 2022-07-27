---
title: 팀 일정 만들기
description: Dynamics 365 Human Resources에서 팀 일정을 보고 만듭니다.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ee39f35f9d81f47c5438ddf48451d24ab0c0ed3
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452113"
---
# <a name="view-team-and-company-calendars"></a>팀 및 회사 일정 보기


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources에서 팀 및 회사 일정을 볼 수 있습니다. 팀 일정은 라인 계층에 정의된 직속 부하 직원만 표시합니다.

## <a name="view-your-team-calendar-as-an-employee"></a>직원으로 팀 일정 보기

- **직원 셀프 서비스** 작업 영역에서 **요약** 아래의 **팀 휴직 일정** 을 선택합니다.

## <a name="view-your-team-calendar-as-a-manager"></a>관리자로 팀 일정 보기

1. **직원 셀프 서비스** 작업 영역에서 **내 팀** 을 선택합니다.

2. **휴가 및 휴직** 을 선택한 다음 **관리자 휴직 일정 보기** 를 선택합니다.

관리자는 **내 팀의 보류 중인 휴가 요청**, **승인된 휴가** 및 **휴가 요청** 에서 팀 일정에 액세스할 수도 있습니다. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>휴직 관리자로 휴직 관리자 일정 보기

> [!NOTE]
> 휴직 관리자 일정을 보려면 먼저 기능 관리에서 **휴가 관리를 위한 휴직 관리자(미리 보기)** 기능을 켜야 합니다. 미리 보기 기능을 켜는 방법에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

휴직 관리자 역할의 사용자는 일정에서 휴가 요청을 볼 수 있습니다. 휴가 일정에 액세스하려면 다음 단계를 따릅니다.

1. **직원 셀프 서비스** 작업 영역에서 **휴가 관리** 를 선택한 다음 **휴직 관리자 일정** 을 선택합니다.

2. **날짜** 필드에 원하는 날짜를 입력합니다.

3. 필요에 따라 보기 옵션을 업데이트합니다.

부재 관리자 일정은 휴가 계층에서 부재 관리자에게 보고하는 직원에 대한 모든 레코드를 표시합니다.

## <a name="view-a-company-calendar"></a>회사 일정 보기

인적 자원 역할이 있는 사람은 회사 일정을 볼 수 있습니다. 회사 일정에는 모든 직원이 표시됩니다. 기본적으로 일정은 오늘 날짜에 28일을 더한 날짜를 표시하지만 날짜 범위를 변경할 수 있습니다. **이름**, **인사 번호** 및 **휴가 유형** 으로 일정을 필터링할 수도 있습니다.

1. **휴가 및 휴직** 작업 영역에서 **연결** 을 선택합니다.

2. **휴가 및 휴직 일정** 을 선택합니다.

인적 자원 역할은 **휴가 및 휴직 요청**, **승인된 휴가** 및 **휴가 요청** 에서 회사 일정에 액세스할 수도 있습니다. 

이제 일정에 추가 필터와 옵션이 포함됩니다. 모든 일정에는 다음에 대한 보기 옵션이 포함됩니다.

- 승인된 요청
- 보류 중인 요청
- 휴가 요청이 있는 직원
- 휴가 요청이 없는 직원
- 직원 생년월일
- 휴가 요청 
- 휴직 요청

**휴가 및 휴직 매개 변수** 페이지의 일정 구성에 따라 사용할 수 있는 보기 옵션이 결정됩니다.

관리자 또는 부서별로 일정을 필터링할 수도 있습니다. 기본 직위 할당은 이러한 필터가 설정될 때 표시되는 직원을 결정합니다. 

> [!IMPORTANT]
> 기능 관리에서 **회사 간 휴가 보기** 기능을 켤 수 있습니다. 그런 다음 **인적 자원 공유 매개 변수** 페이지에서 기능을 활성화하여 일정에 법인 필터를 표시해야 합니다. 자세한 내용은 [휴가 및 부재 매개 변수 구성](hr-leave-and-absence-parameters.md)을 참조하세요.
> 
> 법인별로 일정을 필터링할 수 있습니다. 법인과 관계없이 모든 직원을 보려면 필터 필드를 지운 다음 **Enter** 를 선택합니다. 

일정 설정에 대한 자세한 내용은 [일정 매개 변수 구성](hr-leave-and-absence-parameters.md?configure-calendar-parameters)을 참조하세요.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
