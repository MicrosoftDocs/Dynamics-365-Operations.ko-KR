---
title: '다음에서 제거되거나 더 이상 사용되지 않는 기능: Dynamics 365 Supply Chain Management'
description: 이번에는 Dynamics 365 Supply Chain Management에서 제거되었거나 제거할 예정인 기능에 대해 설명합니다.
author: kamaybac
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: e7350e697beec42b349082df06b77a89d526c27c
ms.sourcegitcommit: ddcab9726e9dbcf3296cb0988b97a3ae7ccb3dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2022
ms.locfileid: "8450112"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>다음에서 제거되거나 더 이상 사용되지 않는 기능: Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Dynamics 365 Supply Chain Management에 대해 새로 제거되거나 사용되지 않는 기능이 문서화되면 업데이트됩니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

이 목록은 자체 계획을 위해 이러한 제거 및 사용 중단을 고려하는 데 도움을 주기 위한 것입니다.

> [!NOTE]
> 재무 및 운영 앱의 개체에 대한 자세한 정보는 [기술 참조 보고서](/dynamics/s-e/)에서 찾을 수 있습니다. 이러한 보고서의 여러 버전을 비교하여 각 버전의 재무 및 작동 앱에서 변경되거나 제거된 개체에 대해 알아볼 수 있습니다.


## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Supply Chain Management 10.0.19 릴리스에서 제거되거나 더 이상 사용되지 않는 기능

### <a name="job-card-device"></a>직업 카드 장치

| &nbsp;  | &nbsp;  |
|---|---|
| **지원 중단/제거 이유** | [작업 카드 장치](../production-control/config-job-card-device.md)는 새로운 [생산 현장 실행 인터페이스](../production-control/production-floor-execution-configure.md)로 대체됩니다. |
| **다른 기능으로 대체되었습니까?**   | 예, [작업 카드 장치](../production-control/config-job-card-device.md)는 새로운 [생산 현장 실행 인터페이스](../production-control/production-floor-execution-configure.md)로 교체됩니다. |
| **영향을 받는 제품 영역** | Supply Chain Management - 생산 관리 |
| **배포 옵션** | 클라우드 및 온프레미스 |
| **상태** | 더 이상 사용되지 않습니다. 작업 카드 장치는 버그 및 보안 수정과 함께 지원을 받지만 기능 향상은 더 이상 제공되지 않습니다. 2022년 4월 이후에는 작업 카드 장치가 더 이상 지원되지 않으며 고객은 새로운 생산 현장 실행 인터페이스로 이동해야 합니다. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Supply Chain Management 10.0.18 릴리스에서 제거되거나 더 이상 사용되지 않는 기능

### <a name="dynamics-365-for-finance-and-operations---warehousing-the-warehouse-app"></a>Dynamics 365 for Finance and Operations - 입고(창고 앱)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 2021년 4월부터 *Dynamics 365 for Finance and Operations - Warehousing*(창고 앱)이 더 이상 사용되지 않으며 2022년 4월 이후에는 지원되지 않습니다. 이제 Supply Chain Management 버전 10.0.17과 함께 출시된 *Warehouse Management mobile app* 으로 대체되었습니다. 새 앱은 완전히 대체되지만 동일한 기본 프레임워크를 사용하므로 마이그레이션이 쉽습니다. 필요한 경우 두 앱을 나란히 사용하여 사용자가 새 앱 사용 방법을 배우면서 점차적으로 조정할 수 있습니다.<br><br>새로운 Warehouse Management mobile app에 대한 자세한 정보는 [Warehouse Management mobile app](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) 및 [Warehouse Management mobile app 설치 및 연결](../warehousing/install-configure-warehouse-management-app.md)을 참조하세요. |
| **다른 기능으로 대체되었습니까?**   | 예, 새로운 Warehouse Management mobile app으로 대체되었습니다. |
| **영향을 받는 제품 영역**         | Supply Chain Management - 창고 앱 |
| **배포 옵션**              | 클라우드 및 온프레미스 |
| **상태**                         | 더 이상 사용되지 않습니다. 창고 앱은 버그 및 보안 수정에 대한 지원을 받지만 기능 향상은 더 이상 제공되지 않습니다. 2022년 4월 이후에는 이전 창고 앱이 더 이상 지원되지 않으며 고객은 새로운 Warehouse Management mobile app으로 이동해야 합니다. 그러면 이전 창고 앱이 Microsoft Store 및 Google Play 스토어에서 제거됩니다.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Supply Chain Management 10.0.15 릴리스에서 제거되거나 더 이상 사용되지 않는 기능

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer Dynamics 365에 대한 11 지원은 더 이상 사용되지 않습니다.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 2020년 12월부터 모든 Dynamics 365 제품에 대한 Microsoft Internet Explorer 11 지원은 더 이상 사용되지 않으며 Internet Explorer 11은 2021년 8월 이후에 지원되지 않습니다.<br><br>이는 Internet Explorer 11 인터페이스를 통해 사용하도록 설계된 Dynamics 365 제품을 사용하는 고객에게 영향을 미칩니다. 2021년 8월 이후에는 이러한 Dynamics 365 제품에 대해 Internet Explorer 11이 지원되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 고객은 Microsoft Edge(으)로 전환하는 것이 좋습니다.|
| **영향을 받는 제품 영역**         | 모든 Dynamics 365 제품 |
| **배포 옵션**              | 모두|
| **상태**                         | 더 이상 사용되지 않습니다. Internet Explorer 11은 2021년 8월 이후에 지원되지 않습니다.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>제조 시나리오를 위한 내장된 Supply Chain Management 기준 계획 엔진 사용

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 기준 계획 실행 중 성능을 향상하고 SQL 데이터베이스 부하를 최소화하기 위해 기본 제공 Supply Chain Management 기준 계획 엔진이 계획 최적화으로 대체됩니다. 계획 최적화를 사용하면 근무 시간 중에도 수행할 수 있는 빠른 계획 실행이 가능합니다. 이를 통해 계획자는 수요 또는 계획 매개 변수의 변경에 즉시 대응할 수 있습니다. |
| **다른 기능으로 대체되었습니까?**   | 예, 계획 최적화는 기존의 기본 제공 Supply Chain Management 기준 계획 엔진을 대체합니다. |
| **영향을 받는 제품 영역**         | Supply Chain Management - 마스터 플래닝 |
| **배포 옵션**              | 클라우드 전용 계획 최적화는 온-프레미스 배포에서 지원되지 않습니다. |
| **상태**                         | 더 이상 사용되지 않습니다. 2022년 4월 1일까지 기본 제공 Supply Chain Management 기준 계획 엔진에 대해 제조 시나리오가 더 이상 지원되지 않습니다. 해당 날짜를 기준으로 Microsoft는 기본 제공 계획 엔진에 대한 제조 시나리오에 대한 모든 활성 개발을 중단하고 새로운 기능을 릴리스하지 않으며 중요한 버그 수정만 릴리스합니다. 이 날짜 이후에는 제조 시나리오에 대한 지원이 필요한 모든 회사에서 기준 계획 계산에 계획 최적화를 사용해야 합니다. 계획 최적화는 2022년 10월까지 제조 시나리오를 완전히 지원할 것으로 예상됩니다. 자세한 내용은 [계획 최적화 설명서](../master-planning/planning-optimization/planning-optimization-overview.md)를 참조하세요.<br><br>Supply Chain Management의 온프레미스 배포가 있는 회사는 2022년 4월 이후에도 제조 시나리오에 기본 제공 기준 계획 엔진을 계속 사용할 수 있습니다. 그러나 더 이상 향상된 기능은 제공되지 않습니다. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Supply Chain Management 10.0.11 릴리스에서 제거되거나 더 이상 사용되지 않는 기능

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>유통 시나리오를 위해 내장된 Supply Chain Management 기준 계획 엔진 사용

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 기준 계획 실행 중 성능을 향상하고 SQL 데이터베이스 부하를 최소화하기 위해 기본 제공 Supply Chain Management 기준 계획 엔진이 계획 최적화으로 대체됩니다. 계획 최적화를 사용하면 근무 시간 중에도 수행할 수 있는 빠른 계획 실행이 가능합니다. 이를 통해 계획자는 수요 또는 계획 매개 변수의 변경에 즉시 대응할 수 있습니다. |
| **다른 기능으로 대체되었습니까?**   | 예, 계획 최적화는 기존의 기본 제공 Supply Chain Management 기준 계획 엔진을 대체합니다. |
| **영향을 받는 제품 영역**         | Supply Chain Management - 마스터 플래닝 |
| **배포 옵션**              | 클라우드 전용 계획 최적화는 온-프레미스 배포에서 지원되지 않습니다. |
| **상태**                         | 더 이상 사용되지 않습니다. 2021년 4월 1일까지 기본 제공 Dynamics 365 Supply Chain Management 기준 계획 엔진으로 배포 시나리오가 더 이상 지원되지 않습니다. 배포 시나리오의 경우 고객은 기준 계획 계산에 계획 최적화을 사용해야 합니다. 자세한 내용은 [계획 최적화 설명서](../master-planning/planning-optimization/planning-optimization-overview.md)를 참조하세요. Dynamics 365 Supply Chain Management의 온프레미스 배포 고객은 2021년 4월 이후 배포 시나리오에 Supply Chain Management 기준 계획 엔진을 계속 사용할 수 있습니다. 그러나 더 이상 향상된 기능은 제공되지 않습니다. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>제거되거나 더 이상 사용되지 않는 기능에 대한 이전 공지

이전 릴리스에서 제거되거나 더 이상 사용되지 않는 기능에 대한 자세한 내용은 [이전 릴리스에서 제거되거나 사용되지 않는 기능](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md)을 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
