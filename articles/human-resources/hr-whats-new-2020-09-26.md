---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 9월 26일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2020년 9월 26일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8b0260c4d1bafe271a08336ceed7dc3742f1d590
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452014"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 9월 26일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다. 업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3589-hf.3에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

- **이제 플랫폼 업데이트 10.0.13을 사용할 수 있음**: 업데이트에 대한 자세한 내용은 [금융 및 운영 앱 버전 10.0.13의 플랫폼 업데이트(2020년 10월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
| --- | --- | --- |
| 469495 | 기본 재무 차원 그리드 및 대화 상자 업데이트 | Human Resources 전반에 걸쳐 재무 차원 그리드 및 대화 상자가 업데이트됩니다. |
| 474887 | 휴가 요청 작업 항목이 수동 결정에서 잘못된 링크를 연결함 | 워크플로 구성에 수동 결정이 포함된 경우 **나에게 할당된 작업 항목** 에서 휴가 요청으로 이동하면 잘못된 링크가 열리고 현재 사용자에게 수동 결정을 위해 할당된 양식 대신 현재 사용자가 만든 휴가 요청이나 빈 양식이 표시됩니다. |
| 474962 | 휴가 및 부재 매개 변수 엔터티에 레이블이 모호한 필드가 있음 | 휴가 및 부재 매개 변수 엔터티 레이블이 더 명확하게 업데이트되었습니다. |
| 481401 | 적립 날짜 기준이 적립 시작 날짜 이후 및 월말일 경우 적립 처리가 중단됨 | 적립 날짜 기준이 적립 시작 일자 이후 및 월말일 경우 적립 처리가 지연되지 않도록 업데이트되었습니다. |
| 447167 | 만료되는 기록 목록에는 비활성 작업자가 포함됨 | **인사 관리** 의 **만료되는 기록** 탭에 비활성 작업자가 포함됩니다. 이제 활성 작업자만 포함됩니다. |
| 486840 | **나에게 할당된 작업 항목** 에서 잘못된 휴가 요청이 열림 | **나에게 할당된 작업 항목** 에서 휴가 요청을 선택하면 더는 현재 사용자에게 할당된 가장 최근 휴가 요청이 열리지 않습니다. |
| 506868 | Dataverse **직책** 필드가 **직무 직위** 엔터티로 설정되지 않음 | **직무** 및 **직무 직위** 엔터티의 **직책** 필드가 지정되지 않은 것으로 표시됨. 이제 **직책** 필드가 표시됩니다. |
| 430359 | 관리자 및 직원 역할이 할당된 오프보딩 검사 목록 작업에 액세스할 수 없음 | 미래의 퇴직 날짜가 있는 작업자는 직원 또는 관리자 역할만 있는 경우 검사 목록 작업에 액세스할 수 없습니다. 이제 직원 또는 관리자 역할만 있는 사용자는 미래의 퇴직 날짜가 있는 오프보딩 작업에 액세스할 수 있습니다. |
| 458102 | **작업자 급여 정보** 엔터티가 생성될 때 새 직원이 표시되지 않음 | 엔터티를 내보내기 전에 직원의 급여 정보를 열지 않아도 작업자 급여 정보 엔터티에 새 직원이 포함됩니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams의 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |
| 향상된 워크플로 요청 및 승인 | [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [나에게 할당된 작업 항목 목록을 배치하는 구성 옵션](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>업데이트 예정

다음 새 기능이 향후 릴리스로 예정되어 있습니다.

- [관리자 셀프 서비스의 사용자 지정 링크](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)를 참조하세요.

## <a name="additional-resources"></a>추가 리소스

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)
[Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[업데이트 프로세스](hr-admin-setup-update-process.md)
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]