---
title: 회사 간 계획
description: 이 토픽에서는 회사 간 계획에 대해 설명하고 Microsoft Dynamics 365 Supply Chain Management의 계획 최적화를 사용하여 회사 간 계획을 구성하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2bf69a5d0d6e070374277e2d82d5fbf6eb4b8704895ffe31aa7e2d2d3546bb16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447292"
---
# <a name="intercompany-planning"></a>회사 간 계획

[!include [banner](../../includes/banner.md)]

일부 조직의 경우 물류 운영은 조직의 다른 법인(회사)에 의존합니다. 이러한 작업은 회사 간 판매 및 구매를 사용하여 처리됩니다. 각 법인에는 별도의 계정과 목표가 있기 때문입니다.

이 토픽에서는 회사 간 계획에 대해 설명하고 Microsoft Dynamics 365 Supply Chain Management의 계획 최적화를 사용하여 회사 간 계획을 구성하는 방법에 대해 설명합니다.

이 토픽에서는 다음과 같은 중요한 회사 간 용어를 사용합니다.

- **업스트림** – 회사 또는 공급망의 상대적 참조. 원자재 공급자 방향으로의 움직임을 나타냅니다.
- **다운스트림** – 회사 또는 공급망의 상대적 참조. 고객의 방향으로의 움직임을 나타냅니다.
- **계획된 회사 간 수요** – 다운스트림 회사의 제품에 대한 계획된 수요를 기반으로 하는 회사의 제품에 대한 계획된 수요입니다.

기준 계획에서 한 회사의 계획에는 다른 회사 계획의 계획 주문과 관련된 계획된 회사 간 수요가 포함될 수 있습니다. 이 기능은 회사 전체의 계획 주문에 대한 완전한 가시성을 제공하기 때문에 유용합니다. 또한 필요한 모든 계획 공급 주문이 생성되지만 계획 주문이 회사 간 수요에 대해 확정될 필요는 없습니다.

계획 다운스트림 수요가 포함된 기준 계획에서 기준 계획을 실행하는 경우 관련 회사 간 공급업체의 계획 구매 주문이 계획에 수요로 포함됩니다.

## <a name="required-setup"></a>필수 설정

회사 간 계획을 사용하려면 다음과 같은 방식으로 시스템을 준비해야 합니다.

1. 관련 제품은 모든 관련 회사에서 출시되어야 합니다. 자세한 내용은[ Microsoft Learn의 Dynamics 365 Supply Chain Management에서 회사 간 거래 구성 및 사용](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/)을 참조하세요.
1. 다운스트림 수요는 업스트림 회사 및 고객에 대한 관련 기본 재고 차원(현장 및 창고)과 회사 간 관계가 있는 공급업체의 구매로 처리되어야 합니다. 자세한 내용은[ Microsoft Learn의 Dynamics 365 Supply Chain Management에서 회사 간 거래 구성 및 사용](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/)을 참조하세요.
1. 업스트림 회사의 마스터 플랜에는 계획된 다운스트림 수요가 포함되어야 하며 관련 회사 및 마스터 플랜은 다운스트림 계획에 지정되어야 합니다.

## <a name="include-planned-downstream-demand"></a>계획된 다운스트림 수요 포함

계획된 다운스트림 수요를 포함하도록 기준 계획을 구성하려면 다음 단계를 따르세요.

1. **기준 계획 \> 설정 \> 계획 \> 기준 계획** 으로 이동합니다.
1. 마스터 플랜을 선택하거나 생성합니다.
1. **회사 간 계획** 빠른 탭에서 다음 필드를 설정합니다.

    - **계획된 다운스트림 수요 포함** - 기준 계획에 대한 회사 간 계획을 활성화하려면 이 옵션을 *예* 로 설정합니다.
    - **다운스트림 계획** – **계획된 다운스트림 수요 포함** 옵션을 *예* 로 설정한 경우 도구 모음과 그리드를 사용하여 다른 회사에서 원하는 기준 계획을 추가합니다.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>다단계 페깅을 사용하여 회사 간 페깅

다단계 페깅에서는 공급에 의해 처리되는 초기 수요 출처를 보기 위해 회사 전체에 페깅을 볼 수 있습니다.

다단계 페깅 정보를 보려면 다음 단계를 따르세요.

1. **기준 계획 \> 기준 계획 \> 계획 주문** 으로 이동합니다.
1. 계획 주문을 선택하거나 엽니다.
1. 작업 창의 **보기** 탭에 있는 **요구 사항** 그룹에서 **다단계 페깅** 을 선택합니다.

### <a name="intercompany-example-that-involves-two-companies"></a>두 회사가 관련된 회사 간 예

이 예에서는 DEMF 회사의 판매 주문을 처리하기 위해 USMF 회사에서 계획 생산 주문을 생성합니다. USMF에서 직접 수요는 계획된 회사 간 수요입니다. 이 수요가 USMF에 나타나도록 하기 위해 기준 계획은 먼저 DEMF에서 실행된 다음 USMF에서 실행됩니다.

다음 그림은 이 예가 계획된 생산 주문에 대한 **다중 레벨 페깅** 페이지에 나타나는 방식을 보여줍니다.

![두 회사가 관련된 회사 간 예.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>세 회사가 관련된 회사 간 예.

이 예에서는 FRRT 회사의 판매 주문을 처리하기 위해 USMF 회사에서 계획 생산 주문을 생성합니다. DEMF 및 USMF 회사에서 직접 수요는 계획된 회사 간 수요입니다. 이 수요가 USMF에 나타나도록 하기 위해 기준 계획은 먼저 FRRT에서 실행된 다음 DEMF에서 실행되고 마지막으로 USMF에서 실행됩니다.

다음 그림은 이 예가 계획된 생산 주문에 대한 **다중 레벨 페깅** 페이지에 나타나는 방식을 보여줍니다.

![세 회사가 관련된 회사 간 예.](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]