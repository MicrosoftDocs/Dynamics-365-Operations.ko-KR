---
title: 서비스를 위한 사내 자산
description: 이 항목에서는 Microsoft Dynamics 365 Field Service를 사용하여 고객 자산과 사내 자산 모두에 서비스를 제공하는 방법을 설명합니다.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 8048a99951eea3fbae34e56c1b444c75ad3d199d
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460902"
---
# <a name="in-house-assets-for-servicing"></a>서비스를 위한 사내 자산

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Field Service는 고객 자산을 서비스하도록 설계되었습니다. Dynamics 365 Supply Chain Management의 자산 관리는 사내 자산을 유지하도록 설계되었습니다. 이 두 앱을 통합하면 Field Service를 사용하여 고객 자산과 사내 자산을 모두 서비스할 수 있습니다. 기능적 위치 또는 계층 구조를 기반으로 자산을 분류하고 상세한 수준에서 서비스를 추적할 수도 있습니다.

자세한 내용은 [Dynamics 365 Field Service 및 Supply Chain Management 통합](/dynamics365/field-service/supply-chain-field-service-integration)을 참조하세요.

## <a name="templates"></a>템플릿

사내 자산에는 다음 표와 같이 데이터 상호 작용 중에 함께 작동하는 핵심 테이블 맵 모음이 포함됩니다.

| 금융 및 운영 앱 | Customer Engagement 앱 | 설명 |
|-----------------------------|-----------------------------------|-------------|
[자산 관리 자산 수명 주기 모델](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[자산 관리 자산 수명 주기 상태](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[자산 관리 자산 유형](mapping-reference.md#124) | msdyn_customerassetcategories | |
[자산 관리 자산](mapping-reference.md#125) | msdyn_customerassets | |
[자산 관리 기능적 위치 수명 주기 모델](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[자산 관리 기능적 위치 수명 주기 상태](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[자산 관리 기능적 위치 유형](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[자산 관리 기능적 위치](mapping-reference.md#136) | msdyn_functionallocations | |
[자산 관리 제조업체](mapping-reference.md#153) | msdyn_manufacturers | |
[자산 관리 모델](mapping-reference.md#154) | msdyn_models | |
[자산 관리 보증](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
