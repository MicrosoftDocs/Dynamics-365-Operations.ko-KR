---
title: Dynamics 365 Human Resources 인프라 통합 FAQ
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources 및 금융 및 운영 앱의 인프라 통합에 대해 자주 묻는 질문과 답변을 제공합니다.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c022bb15975a1411230d28067a2225c95c0573bf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452038"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Dynamics 365 Human Resources 인프라 통합 FAQ

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Microsoft Dynamics 365 Human Resources 및 금융 및 운영 앱의 인프라 통합에 대해 자주 묻는 질문과 답변을 제공합니다.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Dynamics 365 Human Resources 인프라 통합이란?

Dynamics 365 Human Resources는 Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce 및 Dynamics 365 Project Operations와 같은 다른 금융 및 운영 앱과 다른 인프라를 사용하는 독립 실행형 애플리케이션입니다. 인프라 통합은 Dynamics 365 Human Resources를 다른 금융 및 운영 앱과 동일한 인프라로 가져옵니다.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>인프라 통합의 가치와 이점

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>우리 조직에서는 HR 운영을 관리하기 위해 Dynamics 365 Human Resources를 사용합니다. 이러한 변경에는 어떤 이점이 있을까요?

- 이러한 변경 사항은 Dynamics 365의 여러 인적 자원(HR) 기능 집합으로 인한 혼란을 제거합니다.
- Microsoft Power Platform 확장성과 비즈니스 논리 및 기능 옵션을 확장하는 방법을 모두 제공합니다.
- 애플리케이션 수명 주기 관리(ALM), Microsoft Dynamics Lifecycle Services(LCS), 지리적 가용성, 확장성 등의 측면에서 Dynamics 365 Human Resources과 기타 금융 및 운영 앱 간에 일관성을 제공합니다.
- 이를 통해 공유 서비스 및 도구를 활용하고 비용을 절감할 수 있습니다.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>우리 조직에서는 Dynamics 365 Finance, Supply Chain Management, Commerce 또는 Project Operations에서 Human Resources 모듈을 사용합니다. 이러한 변경에는 어떤 이점이 있을까요?

이제 Dynamics 365 Finance에서 HR 모듈을 사용하는 고객도 Dynamics 365 Human Resources에서 이루어진 기능과 투자를 사용할 수 있습니다. 이러한 기능에는 휴가 및 휴직 관리, 복리후생 관리 및 작업 관리가 포함됩니다.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>현재 사용 중인 기능을 잃게 될까요?

Dynamics 365 Human Resources과 금융 및 운영 앱의 HR 모듈 간에는 기능 패리티가 유지됩니다. 비슷한 기능에서 Dynamics 365 Human Resources가 우선합니다. 자세한 내용은 [기능 관리 개요](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.

### <a name="will-the-experience-change-for-my-users"></a>우리 사용자의 환경이 달라질까요?

새로운 HR 기능은 기능 관리를 통해 관리됩니다. 고객이 이를 받아들일지 결정할 것입니다. 경우에 따라 기능이 수정될 수 있습니다. 이러한 경우 설명서가 제공됩니다.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>저는 기존 고객이고 금융 및 운영 인프라의 HR 모듈과 사용자 지정 통합을 통해 Dynamics 365 Human Resources를 모두 사용하고 있는데 어떤 영향이 있을까요?

Dynamics 365 Human Resources와 Dynamics 365 Finance의 HR 모듈 간의 사용자 지정 통합은 더는 필요 없습니다. 모든 HR 데이터는 다른 금융 및 운영 앱과 동일한 데이터베이스에 있습니다.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Dynamics 365 Human Resources에서 금융 및 운영 앱으로의 마이그레이션

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>우리 조직에서는 HR 운영을 관리하기 위해 Dynamics 365 Human Resources를 사용합니다. 새로운 환경으로 마이그레이션하려면 어떤 계획이 필요할까요?

조직에서 Dynamics 365 Human Resources를 사용하지만 다른 금융 및 운영 앱을 사용하지 않는 경우 Human Resources 환경은 새 인프라로 마이그레이션됩니다. 이 마이그레이션 프로세스의 대부분은 자동화됩니다. 데이터베이스를 마이그레이션하고 새 인프라와 동기화하는 프로세스가 준비됩니다.

또한 프로덕션 환경을 마이그레이션하기 전에 마이그레이션 프로세스를 테스트하고 데이터와 환경을 검증하는 도구가 준비됩니다.

조직에서 Dynamics 365 Human Resources와 다른 금융 및 운영 앱을 모두 사용하는 경우 데이터가 새 환경으로 올바르게 마이그레이션되었는지 확인하기 위해 유효성 검사에 더 많은 시간을 할애해야 합니다. 새 인프라로 마이그레이션하면 Human Resources 환경의 데이터가 금융 및 운영 환경과 통합됩니다. 데이터가 충돌하면 충돌 해결 방법을 결정하기 위해 사용자 입력이 필요합니다. 사용자와 관리자는 충돌이 있는 데이터 매핑을 관리하고 프로덕션 환경을 마이그레이션하기 전에 샌드박스 환경에서 마이그레이션을 테스트해야 합니다.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>우리 조직에서는 Dynamics 365 Finance, Supply Chain Management, Commerce 또는 Project Operations에서 Human Resources 모듈을 사용합니다. 새로운 환경으로 마이그레이션하려면 어떤 계획이 필요할까요?

금융 및 운영 앱에서 HR 모듈을 사용하는 조직의 경우 Dynamics 365 Human Resources의 새로운 기능이 표준 단일 버전 업데이트 프로세스를 통해 환경에 적용됩니다. 각 업데이트에서 사용할 수 있게 되면 환경에서 새로운 기능을 볼 수 있을 것입니다. 기능 관리를 사용하여 새 기능을 켤 수 있지만 이러한 기능의 유효성을 검사할 계획을 세워야 합니다. 환경에 대한 다른 업데이트의 유효성을 검사하기 위해 현재 보유하고 있는 프로세스를 따르세요. 금융 및 운영 앱에 업데이트가 적용되는 방법에 대한 자세한 내용은 [단일 버전 개요](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md)를 참조하세요.

### <a name="when-will-my-organization-be-migrated"></a>우리 조직은 언제 마이그레이션될까요?

각 조직의 마이그레이션은 현재 구성과 새 인프라로의 마이그레이션 준비 상태에 따라 달라집니다. 이 날짜는 변경될 수 있습니다.

- 금융 및 운영 앱에서 HR 모듈을 사용하는 조직은 일반 단일 버전 업데이트 프로세스의 일부로 Dynamics 365 Human Resources에 대한 HR 기능을 받습니다. 새로운 기능은 2022년 1월부터 정식 제공될 예정입니다.
- Dynamics 365 Human Resources만 사용하는 조직은 마이그레이션 도구에 액세스할 수 있으므로 2022년 중반부터 테스트를 시작하고 마이그레이션을 시작할 수 있습니다. 새 인프라로의 마이그레이션을 완료해야 하는 날짜는 아직 결정되지 않았습니다. 그러나 마이그레이션 도구를 사용할 수 있는 날짜로부터 최소 1년 후일 것입니다.
- Dynamics 365 Human Resources와 기타 금융 및 운영 앱을 모두 사용하는 조직은 마이그레이션 도구에 액세스할 수 있으므로 2022년 말부터 테스트를 시작하고 마이그레이션을 시작할 수 있습니다. 새 인프라로의 마이그레이션을 완료해야 하는 날짜는 아직 결정되지 않았습니다. 그러나 마이그레이션 도구를 사용할 수 있는 날짜로부터 최소 1년 후일 것입니다.

Dynamics 365 Human Resources의 새로운 기능에 대한 자세한 내용은 [Human Resource의 새로운 기능 또는 변경된 기능](./hr-admin-whats-new.md)을 참조하세요.

### <a name="my-organization-has-not-yet-gone-live-on-dynamics-365-human-resources-should-we-go-live-with-the-human-resources-module-in-the-finance-and-operations-apps-or-with-the-dynamics-365-human-resources-app-on-the-legacy-infrastructure"></a>우리 조직은 아직 Dynamics 365 Human Resources에서 라이브 전환하지 않았습니다. 금융 및 운영 앱의 Human Resources 모듈로 라이브 전환해야 할까요? 아니면 레거시 인프라의 Dynamics 365 Human Resources 앱을 사용하여 라이브 전환해야 할까요?

고려해야 할 중요한 항목은 필요한 HR 기능, 그리고 새 인프라에서 해당 기능을 사용할 수 있는 시점입니다. 조직에 인사 관리를 위한 핵심 기능이 필요한 경우 현재 새 인프라에서 금융 및 운영 앱의 HR 모듈에서 사용할 수 있습니다. 금융 및 운영 앱의 HR 모듈과 Dynamics 365 Human Resources 앱 간의 기능 패리티는 2022년 3월에 정식 제공 예정인 10.0.25 릴리스로 예상됩니다. Teams 앱 및 Dataverse 엔터티 통합과 같은 통합 기능은 이후 릴리스에서 사용할 수 있습니다.

조직의 HR 기능 요구 사항이 조직이 활성화되는 기간 내에 새 인프라에서 사용할 수 있게 되면 금융 및 운영 앱의 Human Resources 모듈에서 활성화하는 것이 더 쉬울 수 있습니다. 그러면 Dynamics 365 Human Resources 애플리케이션에 대한 표준 애플리케이션 업그레이드가 되고 고객이 이미 새 인프라를 사용하게 되므로 마이그레이션이 더 쉬워집니다. 조직이 레거시 인프라에서 Dynamics 365 Human Resources 애플리케이션을 실행하기로 한 경우 새 인프라로 이동하려면 환경 마이그레이션이 필요합니다. 새로운 인프라에서 라이브로 전환하면 이를 피할 수 있습니다.

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Dynamics 365 Human Resources에서만 사용할 수 있는 새로운 기능(예: **휴가 및 휴식** 및 **복리후생 관리**)을 사용하고 있습니다. 이제 이러한 기능을 금융 및 운영 인프라의 Human Resources 모듈에서도 사용할 수 있을까요?

예, Dynamics 365 Human Resources의 모든 모듈은 금융 및 운영 앱에서 그대로 작동하며 100% 기능 패리티가 있습니다. 현재 HR에서 이러한 기능을 사용하는 고객을 위한 전체 마이그레이션 전략의 일환으로 금융 및 운영 인프라에서 계속 작업할 수 있도록 고객 데이터가 마이그레이션됩니다.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>저는 새로운 Dynamics 365 Human Resources 복리후생 관리 기능을 사용합니다. 복리후생 데이터를 사용하여 급여 기능을 활용하기 위해 금융 및 운영 인프라에서 HR 모듈과의 맞춤형 통합을 구축했습니다. 앞으로 이러한 사용자 지정 통합이 필요할까요?

인프라 통합의 일부로 HR 데이터는 다른 금융 및 운영 앱과 동일한 데이터베이스로 가져옵니다. 금융 및 운영 앱의 모듈 간 통합은 더는 필요하지 않습니다.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>우리 조직은 Dynamics 365 Human Resources와 함께 하나 이상의 ISV 솔루션을 사용하고 있습니다. 우리 ISV 솔루션이 자동으로 마이그레이션될까요?

각 독립 소프트웨어 공급업체(ISV) 솔루션의 마이그레이션 환경은 솔루션의 통합 방법에 따라 다릅니다. Microsoft는 새 인프라로의 원활한 전환을 위해 ISV와 긴밀히 협력할 것입니다.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>우리 조직은 Dynamics 365 Human Resources와 LinkedIn Talent Hub 통합을 사용하고 있습니다. 인프라 변경이 완료된 후에도 이 통합이 계속 작동할까요?

아니요, 새 인프라로 마이그레이션한 후에는 LinkedIn Talent Hub 통합이 작동하지 않습니다. LinkedIn Talent Hub 통합 서비스는 레거시 Dynamics 365 Human Resources 인프라와 함께 사용 중지됩니다.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>우리 조직에서는 Teams용 Human Resources 앱을 사용합니다. 인프라 변경이 완료된 후에도 앱이 계속 작동할까요?

예, Teams용 Human Resources 앱은 새 인프라로 마이그레이션한 후에도 계속 작동합니다.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>우리 조직은 Dynamics 365 Human Resources에서 사용자 지정 보안을 구성했습니다. 인프라 변경이 완료된 후에도 맞춤형 보안이 계속 적용될까요?

예, 사용자 지정 보안 구성은 새 인프라로의 데이터 마이그레이션에 포함됩니다.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>데이터 통합자를 사용하여 Dynamics 365 Human Resources와 금융 및 운영 앱 간에 데이터를 이동하고 있습니다. 현재 통합 중인 데이터는 어떤 영향을 받나요?

현재 Dynamics 365 Human Resources에 있는 HR 데이터는 Dataverse와 동기화됩니다. 그런 다음 데이터 통합자를 금융 및 운영 앱과의 단방향 동기화에 사용할 수 있습니다. 새로운 인프라로 마이그레이션한 후 HR 데이터는 금융 및 운영 앱의 기본 데이터가 됩니다. 더는 데이터 통합자가 금융 및 운영 앱과 Human Resources 간에 데이터를 동기화할 필요가 없습니다.

Human Resources를 위한 현재 Dataverse 기본 데이터 테이블은 새 인프라에서 환경의 데이터를 계속 동기화합니다. 엔터티는 이중 쓰기를 지원하도록 변환됩니다. 다른 Dynamics 365 앱을 위해 이러한 테이블에 대해 데이터 통합자를 통해 구성된 다른 모든 데이터 통합은 현재 구성된 대로 계속 작동합니다.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>이중 쓰기를 사용하여 Dataverse와 다른 금융 및 운영 앱 간에 HR 데이터를 이동하고 있습니다. 현재 통합 중인 데이터는 새 인프라로의 마이그레이션에 의해 어떤 영향을 받나요?

HR 데이터는 새로운 인프라 환경의 금융 및 운영 앱에 기본으로 제공됩니다. 이중 쓰기는 새 환경과 Dataverse 환경 간에 HR 데이터를 이동하는 데 사용됩니다.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Dynamics 365 Human Resources에서 하나 이상의 외부 시스템으로 사용자 지정 통합을 구축했습니다. 인프라 변경이 완료된 후 새로운 통합을 개발해야 할까요?

통합 엔드포인트에 따라 다릅니다. 금융 및 운영 앱에서 사용할 수 있는 통합 기술과 최상의 통합 기술을 선택하는 방법에 대한 자세한 내용은 [통합 개요](../fin-ops-core/dev-itpro/data-entities/integration-overview.md)를 참조하세요.

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Dynamics 365 Human Resources용으로 Dataverse를 확장했습니다. 이러한 확장이 자동으로 마이그레이션될까요?

새 인프라의 환경에 결합될 Dynamics 365 Human Resources 및 금융 및 운영 환경이 동일한 Dataverse 환경에 연결되는 경우 두 앱은 마이그레이션 후에도 동일한 Dataverse 환경에 계속 연결됩니다. Dataverse 확장에는 마이그레이션이 필요하지 않습니다.

그러나 Dynamics 365 Human Resources 및 금융 및 운영 환경이 현재 별도의 Dataverse 환경에 연결되어 있는 경우 두 Dataverse 환경을 결합하여 새 인프라의 단일 환경에 연결해야 합니다. 이 Dataverse 마이그레이션의 경우 Human Resources 솔루션의 표준인 Dataverse 테이블을 새로운 Dataverse 환경에 연결하고 다시 동기화할 수 있습니다. Dataverse 환경에 대한 확장은 자동으로 마이그레이션되지 않으며 새 환경에 다시 배포해야 합니다. 관리형 솔루션을 사용하여 Dataverse 확장을 관리하는 것이 좋습니다. 자세한 내용은 [솔루션 소개](/powerapps/developer/data-platform/introduction-solutions)를 참조하세요.

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Microsoft Power Automate 흐름 및/또는 Microsoft Power Apps를 Dynamics 365 Human Resources와 함께 작동하도록 구성했습니다. 인프라 변경이 완료된 후 이러한 Microsoft Power Platform 구성 요소가 마이그레이션되고 자동으로 작동할까요?

Power Apps, Power Automate 흐름 및 기타 Microsoft Power Platform 사용자 지정은 Dataverse 확장과 비슷합니다. 새 인프라로 마이그레이션한 후 자동으로 작동하는지 여부는 Human Resources 앱과 금융 및 운영 앱이 마이그레이션 전에 동일한 Power Apps 환경에 연결되어 있는지에 따라 다릅니다.

앱이 현재 동일한 Power Apps 환경에 연결된 경우 새 인프라로 마이그레이션한 후에도 해당 Power Apps 환경에 계속 연결됩니다. 이 경우 Power Apps, Power Automate 흐름 및 기타 Microsoft Power Platform 사용자 지정은 추가 구성 없이 계속 작동합니다. Dataverse에서 애플리케이션 확장을 관리하려면 관리형 솔루션을 사용하는 것이 좋습니다. 자세한 내용은 [솔루션 소개](/powerapps/developer/data-platform/introduction-solutions)를 참조하세요.

그러나 Human Resources 앱과 금융 및 운영 앱이 별도의 Power Apps 환경에 연결된 경우 마이그레이션의 일부로 결합해야 합니다. 이 작업을 수행하려면 모든 Power Apps 및 기타 사용자 지정을 새 환경에 다시 배포해야 합니다.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Dynamics 365 Human Resources에 대해 Dataverse 가상 테이블을 활성화했습니다. 마이그레이션하는 동안 이러한 테이블은 어떻게 되나요?

마이그레이션 후 새 인프라의 환경이 현재 Dynamics 365 Human Resources에 연결된 Dataverse 환경에 연결된 상태로 유지되는 경우 해당 환경에서 생성된 Dataverse 가상 테이블은 추가 구성 없이 계속 작동합니다.

그러나 마이그레이션 후 새 인프라의 환경이 다른 Dataverse 환경에 연결되면 새 Dataverse 환경에서 가상 테이블을 다시 생성해야 합니다.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>지원자 추적 시스템(ATS) API, 급여 API, Dynamics 365 Human Resources용 Dataverse 가상 테이블 또는 Dataverse 웹 API의 기타 엔터티를 사용하여 통합을 개발했습니다. 인프라 변경이 완료된 후에도 이러한 통합이 계속 작동할까요?

마이그레이션 후 새 인프라의 환경이 현재 Dynamics 365 Human Resources에 연결된 Dataverse 환경에 계속 연결된 경우 Dataverse 웹 API에 맞게 개발된 통합은 마이그레이션이 완료된 후에도 계속 작동합니다.

그러나 마이그레이션 후 새 인프라의 환경이 다른 Dataverse 환경에 연결된 경우 Dataverse 웹 API에 맞게 개발된 모든 통합은 새 Dataverse 환경에 연결되도록 재구성해야 합니다.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>환경이 마이그레이션될 때 Azure 지역에 영향이 있나요?

Human Resources 환경은 일반적으로 마이그레이션 중에 동일한 Azure 지역에 유지됩니다. 유일한 예외는 금융 및 운영 환경이 다른 지역에 있는 금융 및 운영 환경과 통합되는 경우입니다. 이 경우 Human Resources 환경은 금융 및 운영 환경의 Azure 지역으로 마이그레이션됩니다.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>우리 조직은 Dynamics 365 Human Resources의 워크플로로 하나 이상의 비즈니스 프로세스를 해결하고 있습니다. 이러한 워크플로가 자동으로 마이그레이션될까요?

예, 워크플로 구성, 워크플로 기록 및 현재 진행 중인 워크플로가 마이그레이션됩니다.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>마이그레이션 프로세스에 도움이 되는 교육과 리소스는 무엇이 있나요?

마이그레이션 프로세스의 각 단계를 자세히 설명하는 전체 설명서가 제공됩니다. 필요에 따라 비디오 및 워크샵과 같은 추가 교육 리소스도 사용할 수 있습니다.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>우리 조직은 인터페이스의 사용성을 개선하기 위해 Dynamics 365 Human Resources에 저장된 보기를 만들었습니다. 저장된 보기가 자동으로 마이그레이션될까요?

예, 저장된 보기는 새 인프라로 마이그레이션됩니다.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Dynamics 365 Human Resources와 함께 Ceridian을 사용하고 있습니다. 인프라 변경이 완료된 후 Ceridian 통합을 사용할 수 있나요? 

Ceridian과의 통합은 급여 API 기반 통합으로 마이그레이션됩니다. 현재 Dynamics 365 Human Resources에 있는 파일 기반 통합은 금융 및 운영 인프라로 마이그레이션되지 않습니다. 자세한 내용은 [급여 API 통합](./hr-admin-integration-payroll-api-introduction.md)을 참조하세요.

### <a name="how-will-the-migration-affect-the-service-update-process"></a>마이그레이션은 서비스 업데이트 프로세스에 어떤 영향을 미치나요?

마이그레이션하면 ALM 및 서비스 업데이트 측면에서 유연성이 훨씬 높아집니다. 서비스 업데이트는 더 이상 Human Resources 환경에 자동으로 적용되지 않습니다. 대신 서비스는 단일 버전 서비스 업데이트 프로세스와 기능을 따릅니다. 따라서 업데이트를 위한 구성 옵션은 LCS를 통해 사용할 수 있습니다. 자세한 내용은 [단일 버전 개요](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md)를 참조하세요.

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>마이그레이션이 Dynamics 365 Human Resources의 LCS 프로젝트에 어떤 영향을 미치나요?

새 인프라로 마이그레이션하면 Dynamics 365 Human Resources 환경의 관리가 LCS의 금융 및 운영 구현 프로젝트로 이동됩니다. 마이그레이션이 Dynamics 365 Human Resources를 기존 금융 및 운영 환경과 통합하는 경우 Human Resources LCS 프로젝트는 금융 및 운영 앱에 대한 LCS 구현 프로젝트로 병합됩니다. 현재 Dynamics 365 Human Resources만 사용 중인 경우 새 LCS 구현 프로젝트가 생성되고 기존 Human Resources LCS 프로젝트가 새 프로젝트로 마이그레이션됩니다.

새 프로젝트는 금융 및 운영 앱에서 사용하는 것과 동일한 유형의 프로젝트입니다. 환경 관리를 위한 동일한 특징과 기능을 가집니다. 자세한 내용은 [Lifecycle Services 리소스](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)를 참조하세요.

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>작업 기록을 Human Resources의 비즈니스 프로세스 모델러에 연결했습니다. 비즈니스 프로세스 모델러는 어떻게 LCS로 마이그레이션 및 통합되나요?

LCS 프로젝트의 비즈니스 프로세스 라이브러리는 Human Resources를 위한 새 LCS 프로젝트로 마이그레이션됩니다.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>우리 조직은 현재 Dynamics 365 Human Resources만 사용합니다. 인프라 변경이 완료된 후 개발 기능에 대해 자세히 알아볼 수 있는 리소스에는 무엇이 있나요?

Microsoft Power Platform 확장성 옵션과 금융 및 운영 확장성 옵션이 모두 제공되며 개발에 사용할 수 있습니다. 자세한 내용은 [개발 및 사용자 지정 홈페이지](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md)를 참조하세요.

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Dynamics 365 Human Resources에서 기능을 활성화했습니다. 마이그레이션 중에 이러한 기능이 자동으로 활성화되나요?

새 인프라에서 기능이 자동으로 활성화되는지는 기능별로 개별적으로 결정됩니다. 이 정보는 기능 설명서에 포함될 것입니다.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>마이그레이션하는 동안 내 BYOD 데이터베이스는 어떻게 되나요?

BYOD(Bring Your Own Database)를 위한 가져오기 및 내보내기 구성은 새 인프라로 마이그레이션됩니다.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>마이그레이션하는 동안 내 Azure Data Lake는 어떻게 되나요?

현재 금융 및 운영 앱에서 Azure Data Lake Storage에 대해 구성된 내보내기는 마이그레이션 후에도 동일한 구성을 유지합니다.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>우리는 현재 Dynamics AX 2012를 사용하고 있습니다. 현재 사용 가능한 업그레이드 도구를 사용하여 AX 2012의 HR 모듈을 Dynamics 365 Human Resources로 업그레이드할 수 있나요?

예. Dynamics 365 Human Resources는 금융 및 운영 앱을 위한 통합 코드베이스와 인프라에 포함됩니다. Dynamics AX 2012에서 Dynamics 365 Human Resources로의 업그레이드는 최신 버전의 금융 및 운영 앱으로 업그레이드하는 데 사용되는 것과 동일한 업그레이드 경로와 도구를 사용합니다.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Dynamics 365 Human Resources로 문서를 처리하고 있습니다. 마이그레이션하는 동안 이러한 문서는 어떻게 되나요?

문서는 기존 문서 스토리지에 남아 있습니다. 새 인프라의 환경에 다시 매핑됩니다.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Dynamics 365 Human Resources에서 구성한 일괄 작업은 마이그레이션 후 어떻게 되나요?

적용 가능한 일괄 작업은 자동으로 새 인프라로 마이그레이션됩니다.

## <a name="licensing-impact"></a>라이선싱 영향

이 설명서는 사용 권한을 다루는 법적 문서보다 우선하거나 대체하지 않습니다.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>우리 조직에서는 HR 운영을 관리하기 위해 Dynamics 365 Human Resources를 사용합니다. 라이선싱이나 비용이 변경되나요?

Dynamics 365 Human Resources 라이선스를 구매한 고객은 영향을 받지 않습니다. 이 고객에 대한 라이선스 마이그레이션은 없습니다. Human Resources와 관련된 추가 샌드박스 재고 관리 단위(SKU)는 더는 적용되지 않습니다. 대신 고객은 약간 저렴한 비용으로 금융 및 운영 앱 계층 2 샌드박스를 구매할 수 있습니다. Human Resources 샌드박스를 구매한 기존 고객은 추가 비용 없이 금융 및 운영 앱 계층 2 샌드박스로 마이그레이션됩니다.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>우리 조직에서는 Dynamics 365 Finance, Supply Chain Management, Commerce 또는 Project Operations에서 Human Resources 모듈을 사용합니다. 라이선싱이나 비용이 변경되나요?

Dynamics 365 앱의 기존 사용자와 독립 실행형 Dynamics 365 Finance, Supply Chain Management, Commerce 및 Project Operations의 사용자는 2025년 2월 또는 현재 라이선스 계약이 만료일까지(둘 중 더 이른 날짜 적용) 해당 라이선스에 따라 Human Resources에 액세스할 수 있습니다. 비용을 더 절감하는 데 도움이 된다면 더 일찍 Human Resources 라이선스로 전환할 수 있습니다. 2025년 2월부터 기존의 모든 CSP 및 EA 고객은 금융 및 운영 앱에 제공되는 새로운 기능을 활용하려면 HR 모듈을 롤오프하고 Human Resources 라이선스를 구매해야 합니다.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>우리 조직은 Dynamics 365 Finance, Supply Chain Management, Commerce 또는 Project Operations를 사용하고 있습니다. 인프라 통합을 지원하기 위해 추가 환경을 구매해야 하나요?

인프라 변경을 지원하기 위한 추가 환경이 필요 없습니다.

### <a name="where-should-i-go-if-i-have-additional-questions-about-product-licensing"></a>제품 라이선싱에 대한 추가 질문은 어디에 문의해야 하나요?

라이선싱 질문이 있는 경우 [Biz Apps Hub – D365 가격 및 라이선싱](https://businessapplications.transform.microsoft.com/resources/pricing-and-licensing?tab=grandfathering)에서 자세한 정보를 찾을 수 있습니다. 해당 정보가 문제에 도움이 되지 않으면 LicenseQ로 요청을 여세요.
