---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 1월 21일)
description: 이 항목에서는 2021년 1월 21일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 01/21/2021
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
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 02f0b0664dcb78d20c2719b4377dcc6047f2bf3392225f1cf9c166a1073ecd59
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451912"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 1월 21일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.


## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3866에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 플랫폼 업데이트 10.0.16(40) | -- | [금융 및 운영 앱 버전 10.0.16의 플랫폼 업데이트(2021년 2월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16.md) |
| 향상된 워크플로 요청 및 승인 | [조직 및 인사 관리 워크플로 환경 향상](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [나에게 할당된 작업 항목 목록을 배치하는 구성 옵션](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Form 1095-C, Form 1095-B 및 레거시 복리후생의 전자 보고를 위한 ACA(Affordable Care Act) 준수 업데이트 | -- | -- | 
| 복리후생 관리는 이제 미국 기반 법인에 대한 ACA 규정 준수 보고를 지원합니다 | -- | [복리후생 관리에서 ACA 보고서 생성](hr-benefits-management-aca-reports.md) |
| 이제 복리후생 관리에 복리후생 요율 계층 및 복리후생 요율 이중 계층 엔터티가 표시됩니다  | -- | -- |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 533079 | 공제를 보려고 하면 탐색 오류 "양식이 잘못 호출되었습니다"가 발생함. | **현재 날짜** 보기로 복리후생 공제를 보는 동안 오류가 수정되었습니다. |
| 543641 | 전자 보고에 우편 번호가 채워지지 않음.  | 보장 코드가 M에서 Q일 때 복리후생 관리를 위한 ACA 전자 보고서에 우편 번호가 표시되지 않는 내부 버그를 수정했습니다. |
| 542815 | 직원이 직원 셀프 서비스의 개인 연락처 화면을 통해 다른 사람의 개인 연락처를 볼 수 있음. | 직원 셀프 서비스 개인 연락처의 **편집** 양식이 단일 개인 연락처만 검색되도록 쿼리를 제한하지 않아 사용자가 키보드 단축키를 사용하여 다른 사람의 연락처를 볼 수 있는 오류가 수정되었습니다. |
| 536157 | IsVirtualEntityPackageInstalled() 호출로 인해 시스템 관리에서 **Microsoft Dataverse 통합** 페이지를 열 수 없음. | 문제로 인해 **Microsoft Dataverse 통합** 페이지가 Human Resources에 로드되지 않습니다. |
| 533079 | 공제를 보려고 하면 탐색 오류 "양식이 잘못 호출되었습니다"가 발생함. | **현재 날짜** 로 볼 때 복리후생 관리를 위한 **공제** 양식에서 발생하는 오류가 수정되었습니다. |
| 537264 | 후보자 기록에서 **개인 정보** 빠른 탭이 누락됨. | 후보자의 개인 정보는 이제 후보자 기록에서 확인할 수 있습니다. |
| 537267 | 내부 후보자 기록에 **전문 경험** 이 표시되지 않음. | 이제 내부 후보자 기록에 **전문 경험** 빠른 탭에 표시됩니다. 이전에는 내부 후보자의 경우 **전문 경험** 이 조직 내 후보자의 고용 이력인 **고용 이력** 으로 대체되었습니다. 둘 다 내부 후보자에게 적용 적용되며 표시해야 합니다. |
| 537067 | **고용주에게 연락할 수 있음** 이 표시되지 않음. | **고용주에게 연락할 수 있음** 컨트롤이 후보자 기록의 **전문 경험 편집** 창에 추가되었습니다. |
| 525957 | 전환이 완료되면 내부 후보자에 대한 **후보자 상태** 가 업데이트되지 않음. | 전환이 완료되면(**작업자를 새 직위 할당으로 전환** 페이지에서 **직위 변경** 또는 **계속** 버튼 선택) 후보자 레코드의 **상태** 가 **채용됨** 으로 변경되어야 합니다. |
| 537051 | 인도 루피와 터키 리라의 통화 기호가 Dataverse와 올바르게 동기화되지 않음 | 인도 루피와 터키 리라의 기호가 이제 Dataverse와 올바르게 동기화됩니다. |
| 534846 | 데이터 관리를 위해 모집 테이블을 활성화해야 함. | 모집 요청 및 후보자를 위해 생성된 새 테이블은 이제 데이터 관리를 위해 활성화됩니다. 이렇게 하면 테이블에 대해 변경 추적을 활성화하여 Dataverse 가상 테이블에서 OData 변경을 추적할 수 있습니다. |
| 533474 | Microsoft.SqlServer.XEvent.dll에 대한 누락된 참조를 수정. | Microsoft.SqlServer.XEvent.dll에 대한 어셈블리 로드 예외에 의해 일부 환경에서 Dataverse 가상 테이블이 설정되는 것이 차단되었습니다. |
| 481122 | **피플** 작업 영역에 퇴직한 직위가 표시됨. | **직위** 작업 영역에 퇴직한 직위가 열린 직위로 표시되었습니다. 퇴직한 직위는 더는 표시되지 않습니다. | 
| 541978 | BaseWorker 엔터티에 기본 이메일 주소를 추가. | 이 변경으로 작업자의 기본 이메일 주소가 HcmWorkerBaseEntity에 추가되었습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams의 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |
| LinkedIn Talent Hub와 통합 | [LinkedIn Talent Hub와 통합](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [LinkedIn Talent Hub와 통합](./hr-admin-integration-linkedin.md) |
| 관리자의 휴가에 대한 회사 간 보기 | [관리자의 직원 휴가에 대한 회사 간 보기](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [휴가 및 휴직 매개 변수 구성](./hr-leave-and-absence-parameters.md) |
|휴가 잔액에 대한 추가 정보 제공| [휴가 잔액에 대한 추가 정보 제공](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [직원 휴가 관리](./hr-leave-and-absence-manage-employee-leave.md) |
| 관리자가 직위에 대한 모집 요청을 제출할 수 있음 | [관리자가 열린 직위에 대한 모집 요청을 제출할 수 있음](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [모집 요청 추가](./hr-personnel-recruit.md#add-a-recruiting-request) |
| 인사 관리의 향상된 후보자 프로필 | [인사 관리의 향상된 후보자 프로필](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [후보자 프로필 추가 또는 수정](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| 채용 공급자와의 간소화된 통합 지원 | [채용 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [구직 후보자 모집](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>업데이트 예정
| 기능 | 세부 정보 |
| --- | --- |
| 복리후생 등록을 위한 이메일 확인 | 이 기능은 직원이 직원 셀프 서비스의 복리후생 등록 환경에서 체크아웃할 때 확인 이메일을 직원에게 전송하는 옵션을 제공합니다. 자세한 내용은 [회사별 복리후생 관리 매개 변수 구성](hr-benefits-setup-parameters-per-company.md)을 참조하세요. |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="terminology-updates-for-microsoft-dataverse"></a>Microsoft Dataverse의 용어 업데이트

2020년 11월부터 Common Data Service가 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)로 변경되었습니다. 자세한 내용은 Power Apps 블로그에서 [공식 발표](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/)를 참조하세요. 이 이름 변경과 함께 Dataverse의 일부 용어가 업데이트되었습니다. 예를 들어 *엔터티* 는 이제 *테이블* 이고 *필드* 는 이제 *열* 입니다. 자세한 내용은 [용어 업데이트](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)를 참조하세요.

이 릴리스에서는 이러한 변경 사항을 반영하기 위해 애플리케이션 전체에서 Dynamics 365 Human Resources와 Dataverse의 통합과 관련된 용어가 업데이트되었습니다. 예를 들어 **Common Data Service 통합** 양식은 이제 **Microsoft Dataverse 통합** 입니다.

Dynamics 365 Human Resources와 Microsoft Dataverse 통합에 관한 자세한 내용은 [Microsoft Dataverse 통합 구성](./hr-admin-integration-common-data-service.md) 및 [Microsoft Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2020 릴리스 웨이브 2 개요](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]