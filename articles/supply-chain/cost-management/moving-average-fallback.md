---
title: 이동 평균 대체 비용 시퀀스
description: 이 항목에서는 Microsoft Dynamics 365 Supply Chain Management의 이동 평균 계산을 위한 대체 비용 시퀀스에 대한 정보를 제공합니다.
author: AndersGirke
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: d91b3b4b8d49e59aa03d62f4dd101b5a1ec18c41
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448090"
---
# <a name="moving-average-fallback-cost-sequence"></a>이동 평균 대체 비용 시퀀스

[!include [banner](../includes/banner.md)]

재고 비용을 계산할 수 있는 한 가지 방법은 _이동 평균_ 을 사용하는 것입니다. 각 재고 항목에는 최대 3개의 비용 값을 연결할 수 있습니다.

- **마지막 발행** – 재고가 음수가 되기 전에 할당된 마지막 발행 비용
- **활성 비용** – 원가 계산 버전에서 활성화된 최신 원가
- **항목 가격** – 출시된 제품에 대해 지정된 비용

이러한 비용 값 중 이동 평균 계산에 사용해야 하는 값을 결정하기 위해 시스템은 _대체 비용 시퀀스_ 를 사용하여 값에 대한 우선 순위를 설정합니다. 선호 비용 값을 사용할 수 없는 경우 시스템은 다음 선호 값을 사용하는 식입니다.

이전 버전의 Microsoft Dynamics 365 Supply Chain Management에서 시스템은 고정된 대체 비용 시퀀스를 사용했습니다(_마지막 발행 – 활성 비용 – 항목 가격_). 버전 10.0.11에서 이 시퀀스는 여전히 기본 시퀀스입니다. 그러나 세 가지 사용 가능한 대체 비용 시퀀스 중에서 선택할 수 있는 기능을 켤 수도 있습니다. 이 기능은 정기적으로 음수 재고 값을 사용하는 조직에 특히 유용할 수 있습니다.

대체 비용 시퀀스에 대한 선택기를 사용할 수 있도록 하려면 사용자(또는 관리자)가 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 _이동 평균 대체 비용 시퀀스_ 라는 기능을 켜야 합니다.

이동 평균 계산을 위한 대체 비용 순서를 선택하려면 다음 단계를 따르십시오.

1. **매개 변수** 페이지를 엽니다.
2. **재고 회계** 탭의 **이동 평균** 섹션에서 **대체 비용 시퀀스** 필드를 다음 값 중 하나로 설정합니다.

    - **마지막 발행 – 활성 비용 – 항목 가격** – 이 시퀀스가 기본 시퀀스입니다. _이동 평균 대체 비용 시퀀스_ 기능이 켜져 있지 않은 경우에 사용되는 것과 동일한 시퀀스입니다.
    - **활성 비용 – 마지막 발행**
    - **활성 비용 – 항목 가격** – 조직에서 재고가 정기적으로 음수가 되는 동시에 트랜잭션 볼륨이 높은 비즈니스 프로세스를 사용하는 경우 성능 문제가 발생할 수 있습니다. 이 설정은 이러한 성능 문제를 완화하는 데 도움이 될 수 있습니다.

![재고 회계 매개 변수.](media/inventory-accounting-parameters.png "재고 회계 매개 변수")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]