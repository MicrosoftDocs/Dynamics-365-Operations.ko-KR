---
title: Dynamics 365 Supply Chain Management용 고객 포털 개요(비디오 포함)
description: 이 토픽에서는 고객 포털을 소개하고 이를 사용해야 하는 사람과 작동 방식에 대해 설명합니다.
author: Henrikan
ms.date: 06/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 50bdbe6c5f5d23f49bdf8040f2c7811a28da3f32
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449830"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Dynamics 365 Supply Chain Management용 고객 포털 개요

[!include [banner](../includes/banner.md)]


## <a name="what-is-the-customer-portal"></a>고객 포털이란 무엇입니까?

최신 공급망 시스템은 통합에 의존합니다. 재고, 고객 수요 및 영업 부서가 별도의 사일로에 상주하지 않고 통합되어야 합니다. 고객 포털은 Microsoft Dynamics 365 Supply Chain Management를 실행하는 조직이 이러한 통합을 강화하고 고객에게 보다 효과적으로 정보를 제공하는 데 도움이 됩니다.

고객 포털은 회사가 판매 주문 처리와 관련된 시나리오를 위해 외부에서 B2B(기업 간) 웹 사이트를 만들 수 있도록 하는 [Power Apps 포털](/powerapps/maker/portals/overview) 템플릿입니다. 템플릿은 [이중 쓰기](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), Supply Chain Management 및 Power Apps 포털을 사용하여 외부 기업 고객이 회사의 Dynamics 365 환경에서 데이터를 보고 생성할 수 있도록 합니다.

고객 포털 템플릿에는 Power Apps의 포털 기능이 제공하는 모든 사용자 지정 기능이 있습니다. 템플릿을 쉽게 수정하여 회사 브랜드를 표현하고 향상된 기능을 추가하고 사용자 경험을 변경할 수 있습니다. 템플릿이 즉시 제공하는 모든 기능은 원하는 대로 수정할 수 있습니다.

> [!IMPORTANT]
> 그 자체로는 템플릿이 완전히 작동할 것으로 예상되지 않습니다. 기업 고객이 Supply Chain Management의 데이터에 참여할 수 있도록 외부 웹 사이트를 만들려고 하는 고객을 위한 조력자 역할을 합니다.

> [!NOTE]
> 고객 포털 문서는 Supply Chain Management 설치를 위해 고객 포털을 설정할 관리자, 사용자 지정자 및 시스템 통합자를 대상으로 합니다. _고객_ 및 _사용자_ 라는 용어를 사용하여 Supply Chain Management를 실행하는 조직의 고객이자 최종 포털 자체를 사용할 사람을 설명합니다.

## <a name="video"></a>비디오

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

[Dynamics 365 Supply Chain Management의 고객 포털 템플릿 개요](https://youtu.be/nPrqoLuHfV8) 비디오의 고객 포털 템플릿 개요(위 참조)는 YouTube에서 제공되는 [금융 및 운영 재생 목록](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)에 포함되어 있습니다.

## <a name="who-should-use-it"></a>사용 대상은 누구입니까?

고객 포털은 Supply Chain Management를 실행하고 다음과 같은 특성을 가진 회사를 위해 설계되었습니다.

- Supply Chain Management 시스템에서 기업 고객에게 직접 주문 처리 정보(예: 주문 상태 또는 계정 정보)를 전달하는 외부 웹 사이트를 구축하기를 원합니다.
- Dynamics AX 2012에서 Supply Chain Management로 전환하고 있으며 이전에는 [AX 2012 고객 셀프 서비스 포털](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal)을 사용했습니다.

다음 유형의 조직은 고객 포털 구현에 적합하지 **않습니다**.

- 기업이 아닌 고객을 위한 웹 사이트를 구축하려는 기업. 이러한 회사는 [Dynamics 365 Commerce전자 상거래 웹 사이트](../../commerce/create-ecommerce-site.md)를 만드는 것을 고려해야 합니다.
- 이미 유사한 목적으로 기존 Power Apps 포털 웹 사이트를 사용하고 있는 회사. 이러한 회사는 고객 포털에서 추가 혜택을 받지 못합니다. 고객 포털은 이중 쓰기, Supply Chain Management 및 Power Apps 포털 간에 "점을 연결"하려는 고객을 위한 가이드 및 출발점 역할을 하는 템플릿으로 제공됩니다. 이 목적을 수행하는 웹 사이트를 이미 설정한 경우 고객 포털 템플릿을 사용하여 해당 웹 사이트를 다시 프로비저닝하는 것으로부터 많은 가치를 얻지 못할 수 있습니다.

## <a name="how-does-it-work"></a>작동 방식은 무엇입니까?

고객 포털은 Power Apps 포털 템플릿으로 제공됩니다. Power Apps 포털 및 이중 쓰기에 따라 다릅니다.

[Power Apps 포털](/powerapps/maker/portals/overview)은 사용자가 조직 외부의 사용자가 로그인할 수 있는 외부 웹 사이트를 만들 수 있는 기능입니다. 포털을 만드는 데 필요한 코딩은 거의 또는 전혀 필요하지 않습니다. 고객 포털은 Microsoft에서 사용할 수 있는 많은 [Dynamics 365 포털 템플릿](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) 중 하나입니다.

[이중 쓰기](/powerapps/maker/portals/overview)는 고객 참여 앱과 금융 및 운영 앱 간의 거의 실시간 상호 작용을 제공하는 즉시 사용 가능한 인프라 제품입니다. 이중 쓰기는 금융 및 운영 앱과 Microsoft Dataverse 간의 양방향 통합을 제공합니다. 따라서 앱 전반에 걸쳐 통합된 사용자 경험을 제공합니다. 고객 포털은 이중 쓰기와 동기화된 테이블에 따라 다릅니다. Supply Chain Management의 데이터가 고객 포털에 표시되기 전에 해당하는 모든 테이블에 대해 이중 쓰기가 활성화되어야 합니다.

![고객 포털 종속성.](media/customer-portal-elements.png "고객 포털 종속성")

고객 포털은 Power Apps 포털을 사용하여 Supply Chain Management 설치의 데이터를 사용하는 외부 웹 사이트를 구축하려는 조직의 출발점 역할을 합니다. 조직이 이중 쓰기, Supply Chain Management 및 Power Apps 포털을 연결하는 데 도움이 됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]