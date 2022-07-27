---
title: 업데이트 프로세스
description: Microsoft Dynamics 365 Human Resources는 애플리케이션 및 플랫폼 변경에 대해 지속적인 비접촉식 서비스 업데이트를 제공하는 진정한 SaaS(Software as a Service)입니다.
author: andreabichsel
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2af1f710ca010041bd684bca8ecfa6f20ac30d46
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452050"
---
# <a name="update-process"></a>업데이트 프로세스

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Microsoft Dynamics 365 Human Resources는 지속적인 비접촉식 서비스 업데이트를 제공하는 진정한 SaaS(Software as a Service)입니다. 이러한 업데이트에는 정규 업데이트를 포함하여 서비스에 중요한 개선 사항을 제공하는 애플리케이션 및 플랫폼 변경 사항이 모두 포함되어 있습니다.

## <a name="update-policy"></a>정책 업데이트

업데이트는 모든 환경에 정기적으로 릴리스됩니다. Human Resources는 지원 가용성에 대해 일관되고 예측할 수 있는 지침을 제공하는 [Microsoft 수명 주기 정책](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy)에 따라 지원됩니다.

## <a name="release-cadence"></a>릴리스 주기 

Human Resources 업데이트는 모든 환경에 자동으로 적용됩니다. Human Resources는 두 가지 유형의 릴리스를 제공합니다.

- **서비스 업데이트**: 버그 수정 및 새로운 기능이 포함된 업데이트가 2주마다 진행됩니다. 서비스 업데이트에는 릴리스 시 적용 가능한 플랫폼 업데이트도 포함됩니다. 플랫폼 업데이트가 언제 출시되는지 알아보려면 [표 3: 플랫폼 릴리스](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md#table-3-platform-releases)를 참조하세요. 격주 업데이트는 지역에 걸쳐 단계적으로 글로벌 롤아웃됩니다. 격주 업데이트에 대한 자세한 내용은 [Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)을 참조하세요.

    지원되는 모든 데이터 센터는 달리 명시되지 않는 한 2주마다 업데이트됩니다. 미국, 호주, 유럽, 영국, 아시아 및 캐나다 지역은 격주 업데이트에 포함됩니다. 

- **Dataverse 솔루션 업데이트**: 이러한 업데이트는 필요에 따라 약 6주마다 수행됩니다. 여기에는 Dataverse의 새 엔터티와 기존 엔터티에 대한 변경 사항이 포함됩니다. 이러한 업데이트는 격주 업데이트와 동일한 지역에 릴리스되며 약 6주에 걸쳐 모든 데이터 센터로 복제됩니다. 솔루션 업데이트는 격주 서비스 업데이트와 일치하거나 일치하지 않을 수 있습니다.

> [!NOTE]
> 솔루션 업데이트가 릴리스되면 모든 데이터 센터에서 사용할 수 있습니다. 업데이트가 자동으로 복제될 때까지 기다리고 싶지 않으면 데이터 센터의 모든 환경에서 이러한 업데이트를 수동으로 적용할 수 있습니다.

필요한 경우 Human Resources는 다음 유형의 수정 사항도 제공합니다.

- **수정(핫픽스)**: 격주 서비스 업데이트 릴리스와 함께 또는 별도로 수행될 수 있는 버그 수정

- **긴급 수정**: 사전 대응 및 사후 핫픽스는 본질적으로 독립 실행형이고 라이브 사이트 문제를 해결하기 위한 구성 전용 또는 코드 변경을 포함할 수 있으며 격주 서비스 업데이트 릴리스와 별도로 수행될 수 있습니다.

릴리스는 내부 환경에서 검토, 테스트 및 검증됩니다. 빌드가 승인되면 프로덕션에 배포됩니다.

## <a name="release-cadence-exceptions-in-2021"></a>2021년 릴리스 주기 예외

2021년 11월과 12월의 출시 일정은 휴일을 고려하여 다음과 같습니다.

- 11월 출시: 11월 1일~11월 14일
- 12월 출시: 11월 29일~12월 12일
 
2주 릴리스 주기는 2022년 1월 10일에 평소와 같이 계속됩니다.

## <a name="communications"></a>커뮤니케이션

다음 위치에서 Human Resources의 진행 중인 작업과 릴리스한 내용을 확인할 수 있습니다.

- [Dynamics 365 Human Resources 로드맵](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Dynamics 365 및 릴리스 계획](/dynamics365/release-plans/)

- [Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)

- [Lifecycle Services(LCS)에서 문제 검색](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md)(플랫폼 관련 버그만 해당)

- [Human Resources 블로그](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Human Resources Yammer 커뮤니티](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>샌드박스 환경의 미리 보기 기능

프로덕션 환경에서 활성화하기 전에 샌드박스 환경에서 미리 보기 기능을 검증할 수 있습니다. 기능 활성화에 대한 자세한 내용은 [기능 관리 개요](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.

모든 새로운 기능은 최소 30일, 일반적으로 30~60일 동안 미리 보기로 유지됩니다. 주요 기능은 일반적으로 미리 보기 기간 이후 매년 10월과 4월에 사용할 수 있습니다. 기능 관리 작업 영역에 새로운 기능이 표시되면 바로 켤 수 있습니다. 일부 기능은 기본적으로 켜져 있을 수 있습니다.

때때로 필수 기능은 기본적으로 켜지며 끌 수 없습니다(예: 기능 관리 작업 영역).

기능이 정식 제공되면 프로덕션 환경에서 켜거나 끌 수 있습니다. 기능 관리 작업 영역에는 미리 보기 기능이 필수가 되는 시기가 표시됩니다. 이 날짜는 일반적으로 반년 릴리스 계획에 맞춰 10월 1일 또는 4월 1일로 정합니다. 필수 기능은 끌 수 없습니다. 필수가 될 때까지 모든 환경에서 기능을 켜고 끌 수 있습니다.

샌드박스 또는 평가판 환경에서 기능을 미리 보는 것이 좋습니다. 현재 프로덕션 환경 또는 데이터베이스의 복사본을 샌드박스 환경에 만드는 것이 가장 좋습니다. 그러면 데이터와 함께 새 기능을 완전히 경험할 수 있습니다.

샌드박스 환경의 프로비저닝에 대한 자세한 내용은 [Human Resources 프로젝트 프로비전](hr-admin-setup-provision.md)을 참조하세요. 테스트 환경을 제거하려면 [인스턴스 제거](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment)를 참조하세요. 

## <a name="report-bugs"></a>버그 보고

미리 보기 기능을 테스트하거나 새로운 기능을 사용하는 동안 예상대로 작동하지 않는 항목을 찾을 수 있습니다. 버그를 발견하면 [Microsoft Dynamics 365 고객 지원팀](https://dynamics.microsoft.com/support/)에 알려주세요.

## <a name="see-also"></a>참고 항목

[Dynamics 365 및 Power Platform 릴리스 계획](/dynamics365/release-plans)</br>
[Dynamics 365 Human Resource의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[소프트웨어 수명 주기 정책](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]