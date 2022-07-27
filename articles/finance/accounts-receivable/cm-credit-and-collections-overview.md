---
title: 신용 및 수금 개요
description: 이 토픽에서는 신용 및 수금 기능에 대한 개요를 제공합니다.
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 293a6c507c6abd6009a23403384c3b58a1a55a52
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451384"
---
# <a name="credit-and-collections-overview"></a>신용 및 수금 개요

[!include [banner](../includes/banner.md)]

고객의 신용 한도를 관리하고 필요할 때 수금 활동을 수행할 수 있습니다.

## <a name="credit-management"></a>신용 관리

고객 신용 관리를 사용하면 생성한 신용 규칙에 따라 신용 한도를 관리하고 전기 프로세스를 통해 판매 주문의 흐름을 제어할 수 있습니다.

신용 관리 프로세스에는 다음 단계가 포함될 수 있습니다.

- 고객의 신용 가치에 대한 추가 정보를 제공하기 위해 신용 특성을 업데이트합니다.
- 신용 한도 조정을 사용하여 고객에 대한 신용 한도를 생성합니다.
- 신용 한도 조정을 사용하여 고객에 대한 임시 신용 한도를 생성합니다. 이러한 방식으로 비즈니스 요구 사항에 따라 고객 신용 한도를 일시적으로 늘리거나 줄일 수 있습니다.
- 보험 및 보증에 대한 정보와 같이 신용 한도에 영향을 줄 수 있는 정보를 추가합니다.
- 고객이 단일 신용 한도를 공유할 수 있도록 고객을 연결하는 고객 신용 그룹을 생성합니다.
- 고객에게 위험 점수를 할당한 다음 이 점수를 사용하여 신용 한도 조정을 통해 해당 고객에 대한 신용 한도를 자동으로 생성합니다.
- 위험, 지불 조건, 신용 한도, 연체 금액 및 사용된 신용 한도 비율과 같은 요소를 기반으로 하나 이상의 전기 프로세스 동안 주문을 보류하는 차단 규칙을 만듭니다.
- 보류 중인 판매 주문 목록을 관리하고 보류 사유를 검토하고 문제를 완화합니다.
- 전기 프로세스를 계속할 수 있도록 판매 주문을 릴리스합니다.
- 신용 한도 변경 및 판매 주문 릴리스 승인을 관리하는 워크플로를 설정합니다.

## <a name="collections-management"></a>수금 관리

**수금** 페이지는 수취 계정 수금 정보가 관리되는 중앙 집중식 보기를 제공합니다. 수금 관리자는 이 중앙 집중식 보기를 사용하여 수금을 관리할 수 있습니다. 수금 직원은 사전 정의된 수금 기준을 사용하여 생성된 고객 목록이나 **고객** 페이지에서 수금 프로세스를 시작할 수 있습니다.

수금 설정 또는 작업을 시작하기 전에 다음 개념을 이해해야 합니다.

- 고객 에이징 스냅샷에는 특정 시점의 에이징 잔액 정보가 포함됩니다.
- 수금 고객 풀은 작업을 구성하는 데 도움이 됩니다.
- 수금 직원은 자체 고객 풀을 가질 수 있습니다.
- 목록 페이지는 수금 고객, 활동 및 사례를 구성합니다.
- 고객에 대한 모든 수금 정보는 한 페이지에 있으며 해당 페이지에서 조치를 취할 수 있습니다.
- 이자와 수수료는 한 번에 면제, 복구 또는 취소할 수 있습니다.
- 채무 인하 거래는 한 번에 생성할 수 있습니다.
- 잔고부족(NSF) 지불은 한 번에 처리할 수 없습니다.

이러한 개념에 대한 설명은 [수금 관리 핵심 개념](./cm-collections-concepts.md)을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[고객 신용 관리 매개 변수 설정](./cm-credit-mgmt-setup.md)

[고객 신용 관리 설정 정보](./cm-setup-information.md)

[고객에 대한 신용 관리 정보 추가](./cm-add-credit-mgmt-information-customer.md)

[고객 신용 그룹](./cm-customer-credit-groups.md)

[고객 신용 한도 조정](./cm-credit-limit-adjustments.md)

[판매 주문에 대한 신용 보류](./cm-sales-order-credit-holds.md)

[고객 신용 관리 정기 업무](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
