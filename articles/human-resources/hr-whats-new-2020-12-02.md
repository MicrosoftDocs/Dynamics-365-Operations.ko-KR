---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 12월 2일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2020년 12월 2일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e02586ad3e6b4428f2ba826851db6ebc3172bdf1760b483032f5159e7864a81
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451930"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 12월 2일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3788에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 관리자가 직위에 대한 모집 요청을 제출할 수 있음 | [관리자가 열린 직위에 대한 모집 요청을 제출할 수 있음](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [모집 요청 추가](./hr-personnel-recruit.md#add-a-recruiting-request) |
| 인사 관리의 향상된 후보자 프로필 | [인사 관리의 향상된 후보자 프로필](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [후보자 프로필 추가 또는 수정](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| 채용 공급자와의 간소화된 통합 지원 | [채용 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [구직 후보자 모집](./hr-personnel-recruit.md) |
| 관리자 셀프 서비스의 사용자 지정 링크 | [관리자 셀프 서비스의 사용자 지정 링크](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [관리자 셀프 서비스의 사용자 지정 링크](./hr-employee-manager-self-service-custom-links.md) |


### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult에 처리에 사용된 날짜/시간이 포함되어야 함. | 이제 이전에는 누락되었던 마지막 처리에 대한 날짜/시간 스탬프가 BenefitEligibity 처리 결과에 포함됩니다. |
| 526903 | **Human Resources 공유 매개 변수** 에서 **피지명인 자동 선택** 이 켜져 있는 경우 피부양자가 있는 계획에 대한 복리후생 등록이 실패함. | 기본 피지명자을 위한 **피지명인 자동 선택** 옵션이 켜져 있을 때 피부양자를 위한 복리후생 등록이 실패하는 문제가 수정되었습니다. |
| 521922 | **세부 정보 없는 부재 표시** 매개 변수가 팀 부재 일정의 휴가 요청에 대한 세부 정보를 표시함. | **휴가 및 부재 매개 변수** 에서 **세부 정보 없는 부재 표시** 가 **예** 로 설정된 경우, 부재 유형, 부재 유형 색상 및 날짜 세부 정보가 팀 부재 일정에 표시되었습니다. 이 문제가 해결되어 이제 휴가 유형이 표시되지 않고 팀 부재 일정의 모든 휴가 유형에 기본 휴가 유형 색상(진한 파란색)이 사용됩니다. |
| 527316 | 직무, 직위 및 작업자 알림에 대한 직함 변경이 동기화되지 않음. | 직함 관계가 이전에 직무, 직위 및 작업자 엔터티에 추가되었습니다. 이 관계에 대한 동기화는 Human Resources에서 Dataverse로의 동기화에는 작동하지만 Dataverse의 알림에는 작동하지 않습니다. 이 문제가 해결되었습니다. |
| 512275 | **휴가 및 부재 매개 변수** 에서 색상 옵션을 제거함. | 이제 휴가 유형에 색상이 정의되었으므로 **휴가 및 부재 매개 변수** 에서 더는 색상 옵션이 필요하지 않아 제거되었습니다. |
| 437112 | 직원 직위 할당 중 오해의 소지가 있는 오류 메시지 텍스트. | 작업자를 채용하고 활성 상태가 아닌 직위에 작업자를 할당하려고 할 때 오류 메시지를 업데이트했습니다. 업데이트된 메시지는 **지정된 직위는 고용 시작 날짜 현재 활성 상태가 아닙니다. 이 직위의 기간을 확인하십시오.** 입니다. |
| 527816 | **휴가** 페이지와 연관된 성능 문제. | **휴가** 페이지의 성능이 개선되었습니다. |
| 523158 | BenefitPeriodMigrationUpgrade 및 BenefitPlanMigrationUpgrade가 실행되지 않음. | **기간** 및 **계획** 과 연관된 복리후생 마이그레이션 작업이 제대로 실행되지 않는 문제를 수정했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams의 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |
| 향상된 워크플로 요청 및 승인 | [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [나에게 할당된 작업 항목 목록을 배치하는 구성 옵션](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| LinkedIn Talent Hub와 통합 | [LinkedIn Talent Hub와 통합](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [LinkedIn Talent Hub와 통합](./hr-admin-integration-linkedin.md) |
|관리자의 휴가에 대한 회사 간 보기 | [관리자의 직원 휴가에 대한 회사 간 보기](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [휴가 및 휴직 매개 변수 구성](./hr-leave-and-absence-parameters.md) |
|휴가 잔액에 대한 추가 정보 제공| [휴가 잔액에 대한 추가 정보 제공](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [직원 휴가 관리](./hr-leave-and-absence-manage-employee-leave.md) |
| 관리자가 직위에 대한 모집 요청을 제출할 수 있음 | [관리자가 열린 직위에 대한 모집 요청을 제출할 수 있음](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [모집 요청 추가](./hr-personnel-recruit.md#add-a-recruiting-request) |
| 인사 관리의 향상된 후보자 프로필 | [인사 관리의 향상된 후보자 프로필](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [후보자 프로필 추가 또는 수정](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| 채용 공급자와의 간소화된 통합 지원 | [채용 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [구직 후보자 모집](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>업데이트 예정

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]