---
title: 인벤토리 가시성 팁
description: 이 토픽에서는 인벤토리 가시성 추가 기능을 설정하고 사용할 때 고려해야 할 몇 가지 팁을 제공합니다.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1f6ade36ac184a3c8bf790fc0d899ea01d90c8d2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2022
ms.locfileid: "8449614"
---
# <a name="inventory-visibility-tips"></a>인벤토리 가시성 팁

[!include [banner](../includes/banner.md)]

다음은 인벤토리 가시성 추가 기능을 설정하고 사용할 때 고려해야 할 몇 가지 팁입니다.

- 현재 인벤토리 가시성 추가 기능은 Microsoft Dynamics LCS(Lifecycle Services)를 사용하여 만든 Microsoft Dataverse 환경만 지원합니다. Dataverse 환경이 다른 방식(예: Power Apps 관리 센터 사용)으로 생성되었고 Dynamics 365 Supply Chain Management 환경에 연결된 경우 먼저 인벤토리 가시성 제품 팀에 매핑 문제를 수정하도록 요청해야 합니다. [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com)으로 팀에 문의할 수 있습니다. 귀하의 환경이 인벤토리 가시성을 설치할 준비가 되면 팀에서 알려드릴 것입니다.
- 둘 이상의 LCS 환경이 있는 경우 각 환경에 대해 다른 Azure AD(Azure Active Directory) 애플리케이션을 만듭니다. 동일한 애플리케이션 ID와 테넌트 ID를 사용하여 다른 환경에 인벤토리 가시성 추가 기능을 설치하면 이전 환경에서 토큰 문제가 발생합니다. 설치된 인벤토리 가시성 추가 기능의 마지막 인스턴스만 유효합니다.
- 인벤토리 가시성은 현재 클라우드 호스팅 환경에서 지원되지 않습니다. Tier-2+ 환경에서만 지원됩니다.
- API(애플리케이션 프로그래밍 인터페이스)는 현재 `ProductID` 값으로 최대 100개의 개별 항목 쿼리를 지원합니다. 여러 `SiteID` 및 `LocationID` 값을 각 쿼리에 지정할 수도 있습니다. 최대 제한은 `NumOf(SiteID) * NumOf(LocationID) <= 100`로 정의됩니다.
- 대량 API는 각 요청에 대해 최대 512개의 레코드를 반환할 수 있습니다.
- `fno` 데이터 원본은 Supply Chain Management를 위해 예약되어 있습니다. 재고 가시성 추가 기능이 Supply Chain Management 환경과 통합된 경우 [데이터 원본](inventory-visibility-configuration.md#data-source-configuration)에서 `fno`와 관련된 구성을 삭제하지 않는 것이 좋습니다.
- 인벤토리 가시성은 `fno` 데이터 원본에 대한 데이터를 변경할 수 없습니다. 데이터 흐름은 단방향이므로 `fno` 데이터 원본에 대한 모든 수량 변경은 Supply Chain Management 환경에서 가져와야 합니다. 따라서 API를 사용하여 `fno` 데이터 원본에 대한 현재 변경 또는 예약 요청을 보낼 수 없습니다.
- Supply Chain Management 환경에 하나 이상의 새 측정값을 추가하는 경우 인벤토리 가시성에도 추가해야 합니다. 그러나 새 측정값에 대한 모든 수량 변경은 Supply Chain Management 환경에서 가져와야 합니다.
- 현재 [파티션 구성](inventory-visibility-configuration.md#partition-configuration)은 데이터 배포 방식을 나타내는 두 가지 기본 차원(`SiteId` 및 `LocationId`)으로 구성됩니다. 동일한 파티션에서 작업하면 더 낮은 비용으로 더 높은 성능을 제공할 수 있습니다. 솔루션에는 기본적으로 이 파티션 구성이 포함됩니다. 따라서 *직접 정의할 필요가 없습니다.* 기본 파티션 구성을 사용자 지정하지 마세요. 삭제하거나 변경하면 예상치 못한 오류가 발생할 수 있습니다.
- 파티션 구성에 정의된 기본 차원은 [제품 인덱스 계층 구성](inventory-visibility-configuration.md#index-configuration)에 정의하면 안 됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
