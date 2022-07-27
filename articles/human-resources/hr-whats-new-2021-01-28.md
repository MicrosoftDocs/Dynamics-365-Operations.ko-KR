---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 1월 28일)
description: 이 항목에서는 2021년 1월 28일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 01/28/2021
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
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 47a15cbab388d98359828561acefb7c110e8d1da3ec489df21ee0496aa3a0730
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451909"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 1월 28일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.3906에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 사유 코드를 **인사 관리** 작업 영역에 통합 | -- | [사유 코드 설정](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.


| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 539456 | 일정에 **세부 정보 없는 부재 표시** 매개 변수가 활성화된 경우 가리킨 항목 텍스트에 휴가 유형이 나옴. | **세부 정보 없는 부재 표시** 옵션이 활성화된 경우 이제 마우스를 가져가면 요청 날짜가 표시됩니다. |
| 528907 | 직원 역할에 대해 법인에 대한 액세스 권한을 부여하면 관리자는 직원 셀프 서비스의 **내 팀** 영역에서 직원의 휴가 잔액 활동을 볼 수 없음. |이제 이 옵션을 설정하면 관리자가 계속 휴가 잔액 활동을 볼 수 있습니다. |
| 526280 | HcmWorkerEntity, HcmEmployeeEntity 및 HcmContractorEntity에 대한 권한 오류. | 비시스템 관리자 역할의 사용자는 NationalityCountryRegion 필드의 권한 오류로 인해 나열된 엔터티를 내보낼 수 없습니다. 사용자가 이 정보를 내보내려면 HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain 및 HCMContractorEntityView 권한이 계속 필요합니다. |
| 542147 | 직원 셀프 서비스를 통해 은행 계좌를 추가할 때 **은행 계좌 번호** 및 **라우팅 번호** 필드가 필수임. | 직원이 은행 계좌 정보를 추가할 때 **은행 계좌 번호** 및 **라우팅 번호** 필드를 입력해야 하는 오류를 수정했습니다. 이러한 필드는 새 은행 계좌 정보를 저장할 때 더는 필수 항목이 아닙니다. |
| 543641 | 전자 보고에 우편 번호가 채워지지 않음. | 보장 코드 L에서 Q에 대한 ACA 보고서에 우편 번호가 채워지지 않는 버그를 수정했습니다. |
| 545402 | 404 오류를 제거하기 위해 UserBranding.js 파일에 대한 라우팅 변경 추가. | 사용자는 더는 콘솔에서 404 오류를 볼 수 없습니다. |

## <a name="in-preview"></a>미리 보기   

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| Microsoft Teams의 Human Resources 앱 | [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)<br>[Teams에서 휴가 요청 관리](hr-teams-leave-app.md) |
| 관리자의 휴가에 대한 회사 간 보기 | [관리자의 직원 휴가에 대한 회사 간 보기](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [휴가 및 휴직 매개 변수 구성](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 복리후생 등록을 위한 이메일 확인 | 이 기능은 직원이 직원 셀프 서비스의 복리후생 등록 환경에서 체크아웃할 때 확인 이메일을 직원에게 전송하는 옵션을 제공합니다. 이 기능은 2월 1일에 사용할 수 있습니다. 자세한 내용은 [회사별 복리후생 관리 매개 변수 구성](hr-benefits-setup-parameters-per-company.md)을 참조하세요. |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="terminology-updates-for-microsoft-dataverse"></a>Microsoft Dataverse의 용어 업데이트

2020년 11월부터 Common Data Service가 [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)로 변경되었습니다. 자세한 내용은 Power Apps 블로그에서 [공식 발표](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/)를 참조하세요. 이 이름 변경과 함께 Dataverse의 일부 용어가 업데이트되었습니다. 예를 들어 *엔터티* 는 이제 *테이블* 이고 *필드* 는 이제 *열* 입니다. 자세한 내용은 [용어 업데이트](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)를 참조하세요.

이 릴리스에서는 이러한 변경 사항을 반영하기 위해 애플리케이션 전체에서 Dynamics 365 Human Resources와 Dataverse의 통합과 관련된 용어가 업데이트되었습니다. 예를 들어 **Common Data Service 통합** 양식은 이제 **Microsoft Dataverse 통합** 입니다.

Dynamics 365 Human Resources와 Microsoft Dataverse 통합에 관한 자세한 내용은 [Microsoft Dataverse 통합 구성](./hr-admin-integration-common-data-service.md) 및 [Microsoft Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]