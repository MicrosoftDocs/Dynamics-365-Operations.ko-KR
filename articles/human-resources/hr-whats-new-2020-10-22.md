---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 10월 22일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2020년 10월 22일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: jcart1106
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b36354b14faf59aacb4a619dfb6f243335e6a297
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452053"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 10월 22일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다. 업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3680에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 플랫폼 업데이트 10.0.14(38) | -- | [금융 및 운영 앱 버전 10.0.14의 플랫폼 업데이트(2020년 11월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14.md) |
| 조직 및 인사 관리 워크플로 환경 향상 | [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [나에게 할당된 작업 항목 목록을 배치하는 구성 옵션](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호| 문제  | 설명|
| --- | --- | --- |
| 437922 | DMF 엔터티를 사용하여 FMLA 시간을 가져오면 읽기 전용 오류가 발생함. | FMLA 시간 엔터티를 사용하면 FMLA 사례와 연결된 시간 가져오기에 실패했습니다. 가져온 시간이 사례의 남은 시간을 초과하지 않도록 논리를 추가했습니다. |
| 512019 | **마지막 이월** 금액이 잘못됨. | **휴가** 페이지에서 **날짜 기준** 을 다음 회계 기간의 첫날로 변경하면 **연간 휴가** 유형에 **마지막 이월** 금액이 잘못 표시됩니다. 이제 정확한 금액이 표시됩니다. |
| 458639 | **작업자 연락처** 엔터티가 변경 추적 모드를 지원하지 않음. | BYOD(Bring Your Own Database) 시나리오에서 사용할 수 있도록 **작업자 연락처** 엔터티를 업데이트했습니다.|
| 505347 | 간소화된 작업자 기능이 활성화된 경우 교육 관리자가 직원에 대한 휴가 요청을 제출할 수 있음. | HR 보조원과 HR 관리자 이외의 역할은 직원에 대한 휴가 요청을 제출할 수 없습니다. |
| 513490 | 복리후생 관리 로깅: 적용 옵션이 없는 계획에 대한 로깅이 추가됨. | **보장 옵션이 없는 계획** 을 위한 로깅 결과를 활성화했습니다. 이제 **처리 결과** 테이블이 표시되고 올바르게 상단에 정렬됩니다. |
| 517021 | **계획 유형** 에 유형당 하나의 등록이 있는 경우 **계획 유형** 코드가 같은 여러 계획을 선택할 수 없음. | 하나의 등록만 허용되는 계획 선택 제한을 변경했습니다. 이제 **계획 유형** 이 아닌 **계획 유형 코드** 수준에 제한이 적용됩니다. 이 변경으로 둘 다 같은 유형인 HSA 및 FSA와 같은 계획이 허용되지만 별도의 **계획 유형 코드** 를 제공할 수 있습니다. 이렇게 하면 같은 등록 기간에 대해 둘 다 선택할 수 있습니다. |
| 444791 | 보상 계획에 **액세스 제한** 이 켜져 있으면 직원 셀프 서비스에서 보상을 볼 수 없음. | 직원 셀프 서비스 **보상** 카드에서 직원이 **액세스 제한** 이 켜져 있고 특정 역할에 할당된 계획에 등록된 경우 현재 보상 금액과 증가율이 "0"으로 표시되었습니다. 직원과 관리자가 항상 자신과 직속 부하 직원의 보상 세부 정보를 볼 수 있도록 이 문제를 해결했습니다. |
| 457542 | 과정이 종료된 후 과정 세부 정보를 업데이트해도 과정을 수강한 직원에게는 정보가 같게 업데이트되지 않음. | 이제 과정을 닫았다가 다시 연 후 과정 세부 정보를 변경하면 직원 정보가 올바르게 업데이트됩니다. |
| 515342 | **CDSLeaveRequestDetailEntity** 를 통해 데이터를 삽입할 수 없음. 회사를 찾을 수 없거나 존재하지 않습니다. | 이제 **CDSLeaveRequestDetailEntity** 를 사용하여 데이터를 삽입할 수 있습니다. |
| 514743 | Microsoft Exchange를 사용할 때 **이메일 매개 변수** 양식에서 오류가 발생함. | 이메일 공급자가 **Exchange** 로 설정된 경우 **이메일 매개 변수** 페이지에 "파일 또는 어셈블리를 로드할 수 없습니다..."라는 메시지가 표시됩니다. 이 수정으로 **이메일 매개 변수** 페이지를 예상대로 로드되고 저장됩니다. |


## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams의 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |
| 향상된 워크플로 요청 및 승인 | [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [나에게 할당된 작업 항목 목록을 배치하는 구성 옵션](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Human Resources를 위한 Dataverse의 가상 테이블 | [Dataverse에서 Dynamics 365 Human Resources 핵심 데이터 확장](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Dataverse 가상 엔터티 구성](hr-admin-integration-common-data-service-virtual-entities.md) |
| LinkedIn Talent Hub와 통합 | [LinkedIn Talent Hub와 통합](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [LinkedIn Talent Hub와 통합](./hr-admin-integration-linkedin.md) |
| 관리자 셀프 서비스의 사용자 지정 링크 | [관리자 셀프 서비스의 사용자 지정 링크](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [관리자 셀프 서비스의 사용자 지정 링크](./hr-employee-manager-self-service-custom-links.md) |

## <a name="coming-soon"></a>업데이트 예정

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.


## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]