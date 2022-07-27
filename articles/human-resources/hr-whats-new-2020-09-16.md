---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 9월 16일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2020년 9월 16일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cd3424db6bf918b4041f6d12e5d840bc3a8dfef7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452020"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 9월 16일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3557에 적용된 변경 사항. 일부 기능에서 괄호 안의 숫자는 참조를 위한 Lifecycle Services(LCS) 지원 번호를 나타냅니다.

## <a name="included-in-this-release"></a>이번 릴리스에 포함된 사항

-  [저장된 보기 - 일반 공급](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- 자세한 내용은 [저장된 보기](../fin-ops-core/fin-ops/get-started/saved-views.md)를 참조하세요. 

- **직위 작업** 양식에 업데이트된 차원 그리드와 새 대화 상자가 있음(469495).

- **Human Resources 매개 변수** 의 **고급 액세스** 에서 **작업자 정보에 대한 액세스 제한** 을 예로 설정하면 이제 복리후생 양식에 해당 작업자만 표시됨(393384).

- **WorkCalendar** 엔터티의 새 일정 생성 옵션(477055):<br>- 기본 종료 시간<br>- 기본 시작 시간<br>- 금요일이 근무일임<br>- 월요일이 근무일임<br>- 토요일이 근무일임<br>- 일요일이 근무일임<br>- 목요일이 근무일임<br>- 화요일이 근무일임<br>- 수요일이 근무일임<br>- 작업 일정 공휴일 ID

- **LeaveBankTransactionV1** 엔터티에 이제 사유 코드가 포함됨(477823).

- 이제 작업 녹화를 저장할 수 있음(492923).

- 이제 **HCMWorkerContactEntity** 에서 데이터가 정상적으로 게시됨(427620).

- **보상** 빠른 탭이 이제 **작업자 조치** 양식의 계약자 작업자 유형에 대해 표시됨(482494).

- **고정 보상** 을 설정하면 이제 **수준** 및 **계획** 필드가 필수입니다. 이 필드를 비워 두면 오류 메시지가 표시됨(482497).

- **복리후생** 의 **계획 유형** 필드가 이제 드롭다운 목록임(488768).

- 이제 시스템 관리자는 Human Resources에서 사용자 지정 필드가 삭제된 경우 알림을 받음(481408).

- 직원 해고 프로세스 동안 Human Resources는 예상대로 작동하고 잠긴 것으로 나타난 후 선택한 회사를 변경하지 않음(479877). 

- 관리자는 더는 개인 설정을 통해 숫자 열을 추가할 수 없음(485317).

- 관리자는 더는 만료되는 식별 번호에서 데이터 범위 필터를 제거할 수 없음(485321).

- **보고 대상** 필드가 비어 있어도 직위로 마우스를 가져가면 직위 세부 정보가 표시됨(433328).

- 직원은 이제 직원 셀프 서비스에서 복리후생 계획 정보를 볼 수 있음(481676).

- 직원은 이제 등록된 모든 과정을 볼 수 있음(429048).

- 이제 **전문 자격증** 페이지에 대한 보기 옵션을 제한할 수 있습니다. 현재 법인, 작업자 상태 및 작업자 유형별로 보기 옵션을 제한할 수 있음(451501). 


## <a name="in-preview"></a>미리 보기

### <a name="human-resources-app-in-teams"></a>Teams의 Human Resources 앱

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 1 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)
- Human Resources 설명서의 [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)

### <a name="human-resources-app-in-teams-preview-features"></a>Teams의 Human Resources 미리 보기 기능
 
-  **알림**: 휴가 요청의 제출자 및 승인자는 Teams의 Human Resources 앱에서 알림을 받습니다. 승인자는 휴가 요청을 승인하거나 거부할 수 있습니다. 요청이 승인되거나 거부되면 제출자에게 알림이 전송됩니다. 자세한 내용은 다음을 참조하세요.
   - Dynamics 365 2020 릴리스 웨이브 2 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)
   - Human Resources 설명서의 [Teams의 Human Resources 앱에서 알림 활성화](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams)
   - Human Resources 설명서의 [개별 사용자에 대해 Teams 알림 켜거나 끄기](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)
   - Human Resources 설명서의 [Teams 알림](./hr-teams-leave-app.md#respond-to-teams-notifications)
   - Human Resources 설명서의 [팀의 휴가 일정 보기](./hr-teams-leave-app.md#view-your-teams-leave-calendar)
 
- **관리자 휴가 일정**: 관리자는 일정 보기에서 직속 부하 직원의 승인된 휴가와 보류 중인 휴가를 볼 수 있습니다. 이 보기를 사용하면 팀 구성원이 언제 자리를 비우는지 쉽게 이해할 수 있습니다. 자세한 내용은 다음을 참조하세요.
   - Dynamics 365 2020 릴리스 웨이브 2 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)
   - Human Resources 설명서의 [팀의 휴가 일정 보기](./hr-teams-leave-app.md#view-your-teams-leave-calendar)

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>나에게 할당된 작업 항목 목록을 배치하는 구성 옵션(477004)

이제 대시보드의 오른쪽 열에 **나에게 할당된 작업 항목** 목록을 배치하는 새로운 옵션을 사용할 수 있습니다. 이 변경으로 모든 작업 항목과 할 일 목록이 같은 영역에 표시됩니다. 기능 관리에서 **미리 보기 - 워크플로 환경 향상** 을 켜서 이 기능을 활성화합니다. 미리 보기 기능을 켜는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

이 기능은 또한 인사 조치 양식에 나타나는 워크플로 옵션을 승격합니다. 워크플로 옵션은 빠른 액세스를 위해 빠른 작업 탭 위에도 나타납니다. 자세한 내용은 다음을 참조하세요. 

- Dynamics 365 2020 릴리스 웨이브 2 계획의 [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements)

![나에게 할당된 작업 항목](./media/hr-workflow-work-items-assigned-to-me.png)

![워크플로 항목 빠른 액세스.](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>휴가 및 부재 일정

이 릴리스에는 휴가 및 부재 일정에 대한 추가 캘린더 옵션이 포함되어 있습니다. 자세한 내용은 [팀 및 회사 일정 보기](./hr-employee-self-service-calendar.md)를 참조하세요.

## <a name="coming-soon"></a>업데이트 예정

### <a name="checklist-entities-included-in-dataverse"></a>Dataverse에 포함된 검사 목록 엔터티

온보딩, 오프보딩, 전환 및 비즈니스 프로세스에 대한 검사 목록 엔터티는 Dataverse에서 곧 사용할 수 있습니다.

### <a name="benefits-management-reason-codes"></a>복리후생 관리 사유 코드 사용

복리후생 관리 사유 코드는 곧 Human Resources의 기존 사유 코드와 결합됩니다. 복리후생 관리에서 사유 코드를 15자 넘게 만든 경우 복리후생 관리 **사유 코드** 양식에서 사유 코드의 이름을 15자 이하로 변경해야 합니다. 이름을 업데이트하면 인사 관리의 기존 사유 코드 양식 아래에 사유 코드가 나타납니다. 이 변경은 향후 사용할 수 있으며 기존 기능에는 영향을 미치지 않습니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
