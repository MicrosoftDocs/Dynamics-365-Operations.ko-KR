---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 10월 6일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2020년 10월 6일)의 새로 추가되거나 변경된 기능에 대해 설명합니다.
author: jcart1106
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ac64218e48d2713b91af1541f94083aef3f815a2
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452041"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 10월 6일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다. 업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3636에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 휴가 일정에 대한 추가 정보 | [휴가 일정 보기에 대한 추가 정보 제공](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [팀 및 회사 일정 보기](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

>[!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
| --- | --- | --- |
| 448806 | HCM 매개 변수에서 **기본 식별 유형** 을 **RecID** 로 내보냄 | Human Resources 매개 변수 엔터티의 이러한 변경은 **기본 식별 유형** 을 표시하는 추가 열을 추가합니다. |
| 492923 | 작업 녹화가 Lifecycle Services (LCS)에 저장되지 않음 | 이제 작업 녹화를 LCS에 저장할 수 있습니다. |
| 429950 | 직위를 변경하는 동안 고정 보상이 올바르게 만료되지 않음 | **작업자 전환** 페이지에서 작업자의 직위 변경 시 보상 종료 날짜가 해당 직위 종료 하루 전으로 설정되었습니다. 이제 보상 종료 날짜가 직위 종료 날짜와 같습니다. |
| 467214 | **지급 비율 환산 이름** 이 **연간** 으로 설정되어야 **급여 분석** 이 표시됨 | 이름이 **연간** 이 아닌 급여 지급 비율은 보상 분석이 표시되지 않았습니다. 이 업데이트로 보상 분석은 이제 모든 지급 비율 변환을 사용합니다. **시간별** 또는 **급여** 로 보고서를 실행할 때 시간별이 아닌 기간을 사용하는 모든 지급 비율 변환이 **급여** 필터에 포함됩니다. **시간별** 필터에는 기간이 **시간별** 인 지급 비율만 포함됩니다. |
| 482464 | **검토** 를 볼 때 필터를 적용한 후 **세부 정보** 보기가 그리드 보기로 변경되지 않음 | 필터를 적용하면 검토 그리드가 예상대로 표시됩니다. |
| 483184 | **휴가 등록** 기록에서 **조정된 시작 날짜** 로 **계층 기반** 을 선택하면 Human Resources에서 휴가 적립을 생성하지 않음 |이제 휴가 적립을 생성할 때 **조정된 시작 날짜** 가 채워지고 사용됩니다.  |
| 509731 | 미래에 퇴직할 근로자에 대한 휴가 신청에서 퇴직일 이후에 휴가를 신청할 경우 문제 발생 | 이제 휴가 요청이 퇴직 날짜 이전인 경우 미래에 퇴직할 직원에 대해 휴가 요청을 제출할 수 있습니다. |
| 510716 | 보상 분석의 **남성 평균 시급** 에 남성 및 여성 직원이 모두 포함됨 | 보상 분석에서 **보상 인구 통계 분석** 의 **남성 평균 시급** 에 여성 평균 급여가 포함되었습니다. 이제 남성만 포함됩니다. |
| 511348 | 복리후생 셀프 서비스는 오늘부터 혜택 기간 종료일까지 유효한 복리후생 계획만 표시해야 함 | 만료된 복리후생 계획이 직원의 **복리후생 등록** 페이지에 표시되었습니다. 이 수정으로 이러한 계획은 표시되지 않습니다. |
| 512706 | 다음 필드를 읽기 전용으로 설정합니다.<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | 작업이 완료된 후 차원 세부 정보에 대한 **추가** 및 **제거** 버튼이 잘못 활성화되었습니다. **직위 작업 세부 정보** 페이지에 대한 이번 업데이트로 작업이 완료된 후 필드를 편집할 수 없게 되었습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams의 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |
| 향상된 워크플로 요청 및 승인 | [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [나에게 할당된 작업 항목 목록을 배치하는 구성 옵션](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Human Resources를 위한 Dataverse의 가상 테이블 | [Dataverse에서 Dynamics 365 Human Resources 핵심 데이터 확장](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Dataverse 가상 엔터티 구성](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>업데이트 예정

다음 새 기능이 향후 릴리스로 예정되어 있습니다.

- **Dataverse에 검사 목록 엔터티 포함**: 온보딩, 오프보딩, 전환 및 비즈니스 프로세스에 대한 검사 목록 엔터티는 Dataverse에서 곧 사용할 수 있습니다.

- **복리후생 관리 사유 코드**: 복리후생 관리 사유 코드는 곧 Human Resources의 기존 사유 코드와 결합됩니다. 복리후생 관리에서 사유 코드를 15자 넘게 만든 경우 복리후생 관리 **사유 코드** 양식에서 사유 코드의 이름을 15자 이하로 변경해야 합니다. 이름을 업데이트하면 인사 관리의 기존 사유 코드 양식 아래에 사유 코드가 나타납니다. 이 변경은 향후 사용할 수 있으며 기존 기능에는 영향을 미치지 않습니다.

- **관리자 셀프 서비스 사용자 지정 링크**: 관리자를 지원하기 위해 관리자 셀프 서비스의 기능을 확장하고 있습니다. **내 팀** 탭에 사용자 지정 링크를 추가하는 기능을 추가하고 있습니다. 이 기능은 직원 셀프 서비스의 **내 정보 탭** 에 있는 사용자 지정 링크 기능과 비슷합니다. 자세한 내용은 [관리자 셀프 서비스의 사용자 지정 링크](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)를 참조하세요.

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)를 참조하세요.

## <a name="additional-resources"></a>추가 리소스

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]