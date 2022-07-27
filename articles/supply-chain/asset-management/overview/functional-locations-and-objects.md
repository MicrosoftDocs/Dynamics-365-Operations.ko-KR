---
title: 기능 위치 및 자산
description: 이 토픽에서는 자산 관리의 기능 위치 및 자산에 대해 설명합니다. 자산 관리는 Dynamics 365 Supply Chain Management에서 자산 및 유지 관리 작업을 관리하기 위한 고급 모듈입니다.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0bf90d99a8bd093817f9e804e8075e779428f1fadb3128c5a455ca839dece55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446977"
---
# <a name="functional-locations-and-assets"></a>기능 위치 및 자산

[!include [banner](../../includes/banner.md)]

 

이 토픽에서는 자산 관리의 기능 위치 및 자산에 대해 설명합니다. 자산 관리는 Dynamics 365 Supply Chain Management에서 자산 및 유지 관리 작업을 관리하기 위한 고급 모듈입니다.

## <a name="overview"></a>개요

자산 관리는 다른 금융 및 운영 앱과 함께 여러 모듈과 원활하게 통합됩니다. 다음 그림은 다른 모듈과의 인터페이스를 보여줍니다.

![자산 관리가 다른 모듈과 상호 작용하는 방식을 보여주는 다이어그램.](media/01-overview-image.png)

자산 관리를 사용하면 회사의 여러 유형의 장비를 관리하고 서비스하는 것과 관련된 모든 작업을 효율적으로 관리하고 수행할 수 있습니다. 이 장비에는 기계, 생산 장비 및 차량이 포함됩니다. 자산 관리는 또한 다양한 산업 분야의 솔루션을 지원합니다.

다음 그림은 자산 관리에서 다루는 주요 기능의 개요를 보여줍니다.

![자산 관리의 주요 기능을 보여주는 다이어그램.](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>기능 위치 및 자산

기능 위치는 위치의 자산을 관리하는 데 사용됩니다. 이 관리에는 기능 위치에 대한 자산 비용 추적이 포함됩니다. 기능 위치는 계층적으로 구성되며 위치에는 하위 위치가 있을 수 있습니다. 기능 위치의 구조는 정적입니다. 즉, 위치는 장소를 변경할 수 없습니다. 자산은 기능 위치에 설치할 수 있으며 필요에 따라 나중에 다른 기능 위치에 설치할 수 있습니다.

자산 비용은 항상 자산의 위치를 따릅니다. 즉, 자산을 새 기능 위치에 설치하면 자산은 새 기능 위치와 관련된 재무 차원을 자동으로 사용합니다. 따라서 자산 비용은 항상 자산이 현재 설치된 기능적 위치와 관련됩니다. 재무 차원의 이 자동 처리는 회사가 기능 위치에 대한 프로젝트 제어 및 보고를 수행할 때 비용의 완전한 추적을 보장하는 데 도움이 됩니다.

기능 위치의 계층 구조를 구축하는 방법은 내부 장비를 유지 관리하거나 고객 장비를 서비스하기 위한 회사의 요구 사항에 따라 다릅니다. 다음 그림은 지리적 위치를 기반으로 하는 기능 위치의 예를 보여줍니다.

![지리적 위치에 따른 기능 위치를 보여주는 다이어그램.](media/03-overview-image.png)

다음 그림은 고객을 기반으로 하는 기능 위치의 예를 보여줍니다.

![지리적 위치에 따른 기능 위치를 보여주는 다이어그램.](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]