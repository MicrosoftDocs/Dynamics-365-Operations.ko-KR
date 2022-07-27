---
title: 회사 간 기준 일정 계획
description: 이 토픽에서는 회사 간 기준 일정 계획에 대해 설명합니다.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: e28051097905503e291e0c15a50e9363b39b2daa
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447745"
---
# <a name="intercompany-master-scheduling"></a>회사 간 기준 일정 계획

[!include [banner](../../includes/banner.md)]

회사 간 기준 일정 계획은 요구 사항을 계산하고 여러 내부 회사에 걸쳐 계획된 회사 간 주문을 생성하는 수단입니다. 회사 간 기준 일정 계획은 지정한 반복 횟수 동안 수행됩니다. Microsoft Dynamics 365 Supply Chain Management가 회사 간 마스터 일정을 수행할 수 있도록 하려면 각 회사 간 기준 일정을 설정해야 합니다. 여기서는 Microsoft Dynamics 365 Supply Chain Management가 회사 간 구매 주문을 자동으로 생성합니다. 이는 다시 회사 간 판매 주문의 자동 생성으로 이어지며, 이는 다시 새로운 수요로 이어집니다.

각 회사간 회사의 **기준 일정 계획** 매개 변수에서 회사 간 기준 일정 계획 및 회사쪽 스케줄링 순서를 설정합니다.

회사 간 체인 전체에 수요를 전파하려면 계획된 구매 주문이 자동으로 확정되도록 매개 변수를 설정해야 합니다. 즉, 주문은 시간이나 수량 측면에서 변경할 수 없습니다. 보장 그룹에 **확정 타임펜스** 를 설정하거나 마스터 플랜에서 **확정 타임펜스** 를 설정합니다. **확정 타임펜스** 가 설정되어 있지 않으면 회사 간 구매 주문이 자동으로 생성되지 않습니다. 기준 일정 계획을 처음 실행해야만 계획 주문이 생성됩니다. 그러나 회사 간 구매 주문이 생성되지 않으므로 회사 간 판매 주문이 생성되지 않으므로 더 이상 회사 간 구매 주문이 생성되지 않습니다.

회사 간 기준 일정 계획을 시작하면 Microsoft Dynamics 365 Supply Chain Management는 각 회사에서 하나의 기준 일정 계획을 수행합니다. 그런 다음 지정된 반복 횟수에 도달할 때까지 각 내부 회사에서 두 번째 마스터 스케줄링을 수행합니다. 최대 30회 반복이 가능합니다. 그러나 더 많은 반복을 선택할수록 예약 시간이 더 오래 걸립니다.

회사의 마스터 스케줄링은 회사 간 스케줄링 순서, 즉 프로그램이 각 회사 간 간의 마스터 스케줄의 우선순위를 지정하는 순서에 의해 제어되기 때문에 어느 회사 간에서 회사 간 마스터 스케줄링을 시작할 수 있습니다. 회사간 스케줄링 순서는 회사에서 마스터 스케줄링이 수행되는 순서를 결정하기 때문에 회사간 마스터 스케줄링이 시작되는 위치는 중요하지 않습니다. 각 반복에서 현재 회사가 마지막으로 실행됩니다.

> [!NOTE]
> 가장 좋은 방법은 회사 간 마스터 일정이 한 Microsoft Dynamics 365 Supply Chain Management 회사에서 시작되도록 허용하는 것입니다.

**회사 간 기준 일정 계획** 페이지에서 기준 일정 계획 시퀀스를 시작할 수 있습니다. 이 기준 일정 계획은 모든 회사 간 회사의 첫 번째 반복에 대해 선택한 요구 사항 계산을 업데이트하는 원칙에 따라 기준 일정 계획을 처음 실행합니다. 후속 반복은 다음 반복에 대해 선택한 보조 원칙을 사용하며 이 원칙은 지정한 반복 횟수에 도달할 때까지 적용됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
