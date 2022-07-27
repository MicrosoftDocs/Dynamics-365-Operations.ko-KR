---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 2월 22일)
description: 이 항목에서는 2021년 2월 22일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 379a902489bdccdfa3490a830cc3b0bbf7639e7f0b62079a3ff3a999b0a7c412
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451879"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 2월 22일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3988에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams용 Dynamics 365 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 529994 | **작업자** 양식의 **다음으로 알려짐** 필드를 수정해도 Dataverse 업데이트가 트리거되지 않음 | **작업자** 양식에서 **다음으로 알려짐** 필드가 업데이트될 때 Dataverse가 업데이트되지 않는 문제가 수정되었습니다. |
| 532651 | 보상 분석 PBI 보고서가 모든 회사에 대한 메트릭을 계산할 때 통화 환산을 사용하지 않음 | 보상 분석 PBI 보고서가 통화 변산을 올바르게 수행하지 않는 문제를 수정했습니다. |
| 552226 | 생활 이벤트 처리가 단일 생활 이벤트에 대해 계획을 여러 번 닫고 다시 염.  | 직원이 여러 법인에 있고 생활 이벤트가 발생하면 직원이 속한 각 법인에 대해 생활 이벤트 기록이 생성되는 문제가 수정되었습니다. 생활 이벤트를 처리할 때 처리할 법인을 선택해야 합니다. 그러나 처리 논리는 이 법인에 제한되지 않습니다. 대신 모든 법인에 대해 처리하고 선택한 법인에서 계획을 닫았다가 다시 엽니다. 이 작업은 동일한 법인에서 여러 번 처리하는 생활 이벤트로, 생활 이벤트의 영향을 받는 각 계획을 여러 번 닫고 다시 엽니다. |
| 518064 | 둘 이상을 기본 피지명자로 표시하면 적격 계획에서 한 피부양자만 선택됨 | 여러 기본 피지명자가 적격 계획에서 자동 선택되지 않는 문제가 수정되었습니다. 이제 개인 연락처의 기본 수혜자를 지정할 수도 있습니다. 기본 수혜자는 여러 수혜자가 있는 경우 적격 계획에 100%로 나열됩니다. |
| 552365 | 플랫폼 업데이트 40으로 업그레이드한 후 BYOD(Bring Your Own Database) 내보내기 작업이 실패함 | 플랫폼 업데이트 40을 환경에 적용한 후 BYOD 내보내기가 실패하는 문제가 수정되었습니다. |
| 547123 | 대시보드의 할 일 목록에서 쿼리할 작업 수가 제한됨 | 과도한 수의 작업을 로드하려고 할 때 발생하는 성능 문제를 수정하기 위해 할 일 목록에 표시되는 작업 수가 이제 15개로 제한됩니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 관리자의 휴가에 대한 회사 간 보기 | [관리자의 직원 휴가에 대한 회사 간 보기](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [휴가 및 휴직 매개 변수 구성](./hr-leave-and-absence-parameters.md) |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한 | [직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [개인 정보 편집 제한](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="terminology-updates-for-microsoft-dataverse"></a>Microsoft Dataverse의 용어 업데이트

2020년 11월부터 Common Data Service가 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)로 변경되었습니다. 자세한 내용은 Power Apps 블로그에서 [공식 발표](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/)를 참조하세요. 이 이름 변경과 함께 Dataverse의 일부 용어가 업데이트되었습니다. 예를 들어 *엔터티* 는 이제 *테이블* 이고 *필드* 는 이제 *열* 입니다. 자세한 내용은 [용어 업데이트](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)를 참조하세요.

이 릴리스에서는 이러한 변경 사항을 반영하기 위해 애플리케이션 전체에서 Dynamics 365 Human Resources와 Dataverse의 통합과 관련된 용어가 업데이트되었습니다. 예를 들어 **Common Data Service 통합** 양식은 이제 **Microsoft Dataverse 통합** 입니다.

Dynamics 365 Human Resources와 Microsoft Dataverse 통합에 관한 자세한 내용은 [Microsoft Dataverse 통합 구성](./hr-admin-integration-common-data-service.md) 및 [Microsoft Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요.

## <a name="updates-to-service-deployment"></a>서비스 배포 업데이트

2021년 2월 22일 릴리스부터 지역 서비스 업데이트 배포를 조정하고 있습니다. 조정에는 글로벌 지역이 Human Resources 서비스에 대한 업데이트를 수신하는 순서 순환 및 업데이트 단계 사이의 대기 시간 수정이 포함됩니다. 이러한 변경으로 인해 서비스 안정성, 품질 및 지원 가능성을 개선하기 위해 안전한 배포 관행(SDP)에 더욱 부합하게 되었습니다.

2주 배포 주기를 계속 따를 예정입니다. 그러나 고객은 업데이트가 일반적으로 이전 릴리스와 다른 2주 주기의 요일에 Human Resources 환경에 적용된다는 것을 알 수 있습니다.

서비스 업데이트 프로세스에 대한 자세한 내용은 [업데이트 프로세스](./hr-admin-setup-update-process.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]