---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 9월 3일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2020년 9월 3일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d1cc3a64e6c345df7727f5ca7336821388c9dbcf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452056"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 9월 3일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3504에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 Lifecycle Services(LCS) 지원 번호를 나타냅니다.

Human Resources의 예정된 기능에 대한 자세한 내용은 [Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)를 참조하세요. Human Resources의 업데이트 프로세스에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Human Resources 전반에 걸쳐 새로운 기본 재무 차원 그리드 및 대화 패턴(469495)

이제 다음 영역에서 재무 차원의 새 패턴을 사용할 수 있습니다.

- 직위 조치(양식: **HcmPositionActionDetail**)
- 급여 소득 코드(양식: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>휴가 및 부재 양식 개선 사항이 활성화되지 않은 경우 항목이 회사 휴가 일정에 표시되지 않음(484406)

이 릴리스는 회사 휴가 일정에 휴가 항목이 표시되지 않는 문제를 수정합니다. 이 문제는 기능 관리 옵션 **휴가 및 부재 일정 향상** 이 활성화되지 않은 경우에만 발생합니다.

### <a name="benefitplanemployeeentity-issue-467597"></a>BenefitPlanEmployeeEntity 문제(467597)

이 릴리스는 **BenefitsPlanEmployee** 엔터티에 관한 문제를 수정합니다. 이제 작업자 등록을 가져올 때 **보장 코드** 및 **계획 유형 코드** 가 맞게 설정됩니다. 이 문제로 인해 직원 복리후생 계획이 직원 셀프 서비스의 **근로자 복리후생 계획** 양식과 **공개 등록** 양식에 잘못 표시됐습니다.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>전자 파일 1094-C가 XML을 출력할 때 문자가 누락됨(435190)

이 변경은 IRS에 제출할 때 1094-C 출력 파일에 필요한 문자가 누락되는 문제를 수정합니다.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>직원 변동 보상 테이블이 고정 보상 양식에 매핑됨(476117)

이 변경은 고정 보상 필드를 고정 보상 양식과 연결합니다. 변동 보상 필드는 이제 변동 보상 양식에서만 사용할 수 있습니다.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>해당 휴가 유형의 최소 잔액이 음수인 경우 등록 전에 휴가 요청이 허용됨(469917)

이 변경으로 인해 등록에 음수 최소 잔액이 있는 경우에도 계획에 등록되기 전에 휴가 요청을 입력할 수 없습니다. 계획이 활성화된 경우에만 요청을 입력하거나 제출할 수 있습니다.

### <a name="document-templates-dont-download-457279"></a>문서 템플릿이 다운로드되지 않음(457279)

이 변경으로 이제 모든 문서 템플릿을 다운로드할 수 있습니다. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>데이터가 보상 계획 보고서의 지급 비율 필드에 행이 아닌 열 머리글로 표시됨(476077)

이제 분석 보고서가 **지급 비율** 에 올바른 정보를 표시합니다.

## <a name="in-preview"></a>미리 보기

### <a name="human-resources-application-in-teams"></a>Teams의 Human Resources 애플리케이션

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 1 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)
- Human Resources 설명서의 [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)

### <a name="human-resources-app-in-teams-preview-features"></a>Teams의 Human Resources 미리 보기 기능
 
-  **알림**: 휴가 요청의 제출자 및 승인자는 Teams의 Human Resources 앱에서 알림을 받습니다. 승인자는 휴가 요청을 승인하거나 거부할 수 있게 됩니다. 요청이 승인되거나 거부되면 제출자에게 알림이 전송됩니다. 자세한 내용은 다음을 참조하세요.
   - Dynamics 365 2020 릴리스 웨이브 2 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)
   - Human Resources 설명서의 [Teams의 Human Resources 앱에서 알림 활성화](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams)
   - Human Resources 설명서의 [개별 사용자에 대해 Teams 알림 켜거나 끄기](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)
   - Human Resources 설명서의 [Teams 알림](./hr-teams-leave-app.md#respond-to-teams-notifications)
   - Human Resources 설명서의 [팀의 휴가 일정 보기](./hr-teams-leave-app.md#view-your-teams-leave-calendar)
 
- **관리자 휴가 일정**: 관리자는 일정 보기에서 직속 부하 직원의 승인된 휴가와 보류 중인 휴가를 볼 수 있게 됩니다. 이 보기를 사용하면 팀 구성원이 언제 자리를 비우는지 쉽게 이해할 수 있습니다. 자세한 내용은 다음을 참조하세요.
   - Dynamics 365 2020 릴리스 웨이브 2 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams)
   - Human Resources 설명서의 [팀의 휴가 일정 보기](./hr-teams-leave-app.md#view-your-teams-leave-calendar)

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>나에게 할당된 작업 항목 목록을 배치하는 구성 옵션(477004)

이제 대시보드의 오른쪽 열에 **나에게 할당된 작업 항목** 목록을 배치하는 새로운 옵션을 사용할 수 있습니다. 이 변경으로 모든 작업 항목과 할 일 목록이 같은 영역에 표시됩니다. 기능 관리에서 **미리 보기 - 워크플로 환경 향상** 을 켜서 이 기능을 활성화합니다. 미리 보기 기능을 켜는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

이 기능은 또한 인사 조치 양식에 나타나는 워크플로 옵션을 승격합니다. 워크플로 옵션은 빠른 액세스를 위해 빠른 작업 탭 위에도 나타납니다. 자세한 내용은 다음을 참조하세요. 

- Dynamics 365 2020 릴리스 웨이브 2 계획의 [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements)

![나에게 할당된 작업 항목](./media/hr-workflow-work-items-assigned-to-me.png)

![워크플로 항목 빠른 액세스.](./media/hr-workflow-quick-access.png)

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
