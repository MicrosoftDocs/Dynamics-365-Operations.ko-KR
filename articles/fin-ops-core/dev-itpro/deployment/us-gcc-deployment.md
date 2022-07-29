---
title: 미국 정부 커뮤니티 클라우드(GCC)의 Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management
description: 이 항목에서는 자격을 갖춘 정부 및 민간 기관에서 사용할 수 있는 Microsoft Dynamics 365 US Government 제품에 대한 정보를 제공합니다.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 0c8b88e5d190f6dc9beb9342909d1e489d4af10b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461038"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>미국 정부 커뮤니티 클라우드(GCC)의 Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]



일부 Microsoft Dynamics 365 미국 (US) 정부 제품은 자격을 갖춘 정부 및 민간 기관에서 사용할 수 있습니다. 이러한 엔터티는 다음 유형으로 제한됩니다.

- 미국 연방, 주, 지방, 부족 및 준주 정부 기관
- Dynamics 365 US Government를 사용하여 정부 기관 또는 클라우드 커뮤니티의 자격을 갖춘 구성원에게 솔루션을 제공하는 민간 기관
- 정부 규정의 적용을 받는 고객 데이터가 있는 민간 엔터티 및 Dynamics 365 US Government가 규정 요구 사항을 충족하는 적절한 서비스입니다.

자세한 내용은 [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)를 참조하세요.

## <a name="onboarding"></a>Onboarding

Microsoft Dynamics Lifecycle Services(LCS)에서 구현 프로젝트의 초기 온보딩을 완료하려면 [구현 프로젝트 온보딩](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md)의 지침을 따르세요. 그러나 해당 지침에 제공된 공용 LCS에 대한 링크를 사용하지 마세요. 대신 다음 URL을 사용하여 미국 GCC(정부 커뮤니티 클라우드)용 LCS를 엽니다. <https://gov.lcs.microsoftdynamics.us>.

초기 온보딩이 완료된 후 [프로젝트 온보딩](../lifecycle-services/project-onboarding.md)의 지침을 따르세요. 다시 한번 공개 LCS 대신 [GCC용 LCS](https://gov.lcs.microsoftdynamics.us)를 사용합니다.

## <a name="environment-deployment"></a>환경 배포

프로젝트 온보딩을 완료한 후 [재무 및 운영 앱 고객을 위한 Lifecycle Services(LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md)에 설명된 LCS의 추가 기능을 검토할 수 있습니다. 그런 다음 환경 배포로 이동합니다.

- LCS를 통해 Microsoft 관리 환경을 배포하려면 [재무 및 운영 앱 고객을 위한 Lifecycle Services(LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience)의 지침을 따르세요.
- 클라우드 호스팅 환경은 [개발 환경을 배포하고 액세스합니다](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md)를 참조하세요. 또한 [미국 정부 Lifecycle Services 프로젝트에 대한 Azure Resource Manager 온보딩 프로세스를 완료](arm-onbarding-us-goverment.md)에 설명된 대로 커넥터에 대한 Resource Manager 온보딩 프로세스를 완료해야 합니다.

> [!NOTE]
> 미국 정부 LCS 프로젝트의 경우 Azure Government 전용 Azure 구독만 지원됩니다.

## <a name="features-that-arent-available"></a>사용할 수 없는 기능

일부 기능은 GCC에서 배포할 수 없거나 GCC의 Dynamics 365에서 사용할 수 없습니다. 예를 들어 Azure DevOps 서비스는 GCC에서 사용할 수 없습니다. 그러나 온프레미스 Azure DevOps 또는 공개 Azure DevOps 서비스를 사용할 수 있습니다. 기능 가용성에 대한 자세한 내용은 [비즈니스 애플리케이션 미국 정부 기능 가용성](https://aka.ms/BAPFunctionalParity)을 참조하세요.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management가 GCC-High에서 지원됩니까?

아니요. Dynamics 365 Finance 및 Dynamics 365 Supply Chain Management가 GCC에서만 지원됩니까?

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>공개 Azure DevOps를 GCC의 Supply Chain Management와 사용할 수 있나요?

예, 연방 위험 및 승인 관리 프로그램(FEDRAMP)에서 인증한 솔루션에 대한 요구 사항이 없는 경우 공개 Azure DevOps 서비스를 사용할 수 있습니다. 또는 Azure DevOps 서버를 사용할 수 있습니다.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Azure Commercial 구독에 클라우드 호스팅 환경 Tier-1 개발 환경을 배포할 수 있나요?

아니요. [GCC용 LCS](https://gov.lcs.microsoftdynamics.us)에서 클라우드 호스팅 환경을 배포하려면 Azure Government 구독을 사용해야 합니다.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>공유 자산 라이브러리의 패키지가 필요하지만 GCC용 LCS에서 사용할 수 없는 경우 어떻게 해야 합니까?

[공개 LCS](https://lcs.dynamics.com)의 공유 자산 라이브러리에서 동일한 패키지를 다운로드할 수 있습니다. 또는 파트너가 패키지 다운로드를 도울 수 있습니다.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>GCC에서 코드 업그레이드 도구를 사용할 수 있습니까?

아니요, 코드 업그레이드 도구는 현재 GCC에서 사용할 수 없습니다. 그러나 [공개 LCS](https://lcs.dynamics.com)에서 잠재 고객 프로젝트를 생성하고 코드 업그레이드 도구를 사용할 수 있습니다. 잠재 고객 프로젝트에서는 환경을 배포할 수 없습니다.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>파트너가 나를 대신하여 지원 티켓을 열 수 있습니까?

예. 그러나 파트너가 GCC가 아닌 ID를 사용하는 경우 지원 티켓은 공개 지원 대기열로 전달됩니다. LCS에서 고객 GCC 자격을 사용하여 지원 티켓을 여는 것이 좋습니다.

## <a name="see-also"></a>또한, 다음을 참조하세요.

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [비즈니스 애플리케이션 미국 정부 기능 가용성](https://aka.ms/BAPFunctionalParity).
- [Lifecycle Services(LCS) 사용 설명서](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [클라우드 배포 개요](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
