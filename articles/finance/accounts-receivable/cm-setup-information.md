---
title: 신용 관리 설정
description: 이 토픽에서는 신용 관리에 필요한 설정에 대해 설명합니다.
author: JodiChristiansen
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6977789b039c3e77e6d697e32bf4cac69c35a901
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8451585"
---
# <a name="credit-management-setup"></a>신용 관리 설정 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>신용 관리 워크플로

**신용 및 수금 \> 설정 \> 신용 관리 워크플로** 로 이동하여 신용 한도 조정을 관리하는 데 사용되는 워크플로를 정의합니다.

- 단일 승인을 통해 신용 한도 조정 배치를 승인할 수 있는 워크플로를 생성할 수 있습니다.
- 신용 한도 조정이 개별적으로 승인될 수 있도록 라인 수준에서 워크플로를 추가할 수 있습니다.
- 보류를 워크플로 프로세스로 자동 라우팅하는 릴리스 워크플로를 만들 수 있습니다.

## <a name="blocking-rules"></a>차단 규칙

### <a name="ranking-payment-terms"></a>지불 조건 순위 지정

주문의 지불 조건이 고객의 기본 지불 조건과 일치하지 않는 경우 판매 주문을 보류할 수 있습니다. 그러나 지불 조건은 다르지만 주문을 보류하고 싶지 않을 정도로 유사할 때가 있습니다. 지불 조건의 순위를 지정하여 일부 조건은 순위가 같도록 하고 다른 조건은 더 높거나 낮게 지정할 수 있습니다.

지불 조건에 대한 순위가 활성 상태이고 주문의 지불 조건이 고객의 기본 지불 조건보다 높은 순위인 경우 판매 주문이 보류됩니다.

결제 조건 순위를 설정하려면 **신용 및 수금 \> 설정 \> 신용 관리 설정 \>지불 조건 순위** 로 이동합니다.  

### <a name="ranking-settlement-discounts"></a>정산 할인 순위 지정

주문의 현금 할인이 고객의 기본 현금 할인과 일치하지 않는 경우 판매 주문을 보류할 수 있습니다. 그러나 현금 할인은 다르지만 주문을 보류하고 싶지 않을 정도로 유사할 때가 있습니다. 현금 할인의 순위를 지정하여 일부 조건은 순위가 같도록 하고 다른 조건은 더 높거나 낮게 지정할 수 있습니다.

현금 할인에 대한 순위가 활성 상태이고 주문의 현금 할인이 고객의 기본 현금 할인보다 높은 순위인 경우 판매 주문이 보류됩니다.

결제 조건 순위를 설정하려면 **신용 및 수금 \> 설정 \> 신용 관리 설정 \>정산 할인 순위** 로 이동합니다  

## <a name="reasons"></a>이유

신용 관리에는 여러 유형의 이유가 사용됩니다.

- 보류 이유는 판매 주문이 적용된 이유를 나타냅니다.
- 보류에서 릴리스되면 릴리스 이유가 주문에 할당됩니다.
- 상태 이유는 계정 상태가 고객에게 할당된 이유를 나타냅니다.

**신용 관리 이유** 페이지(**신용 및 수금 \> 설정 \> 신용 관리 설정 \> 신용 관리 이유**)에서 이유를 설정할 수 있습니다.

1. **이유 유형** 필드에서 **보류**, **릴리스** 또는 **상태** 의 이유 유형을 선택합니다.
2. **이유** 필드에 이유에 대한 이름을 입력합니다.
3. **설명** 필드에 이유 코드에 대한 설명을 입력합니다.

## <a name="credit-management-groups"></a>신용 관리 그룹

신용 관리 그룹은 동일한 신용 관리 속성을 가진 고객 또는 고객 그룹을 식별하는 데 사용됩니다. 예를 들어 신용 관리 그룹을 사용하여 고객에 대한 차단 및 제외 신용 관리 규칙을 결정할 수 있습니다.

**신용 관리 그룹** 페이지(**신용 및 수금 \> 설정 > 신용 관리 설정 \> 신용 관리 그룹**)에서 신용 관리 그룹을 생성할 수 있습니다.

1. **새로 만들기** 를 선택하여 라인을 생성합니다.
2. 그룹의 ID를 입력합니다. ID는 최대 10자까지 가능합니다.
3. **설명** 필드에 그룹에 대한 이름을 입력합니다. 이름은 최대 60자까지 가능합니다.

**모든 고객** 페이지(**수취 계정 \> 고객 \> 모든 고객**)의 **신용 및 수금** 빠른 탭에서 신용 관리 그룹이 고객에게 할당됩니다.

## <a name="account-statuses"></a>계정 상태

계정 상태를 생성하여 고객 계정의 신용 상태를 식별할 수 있습니다. 송장 발행 및 배송 보류 프로세스에 대한 상태와 영향을 정의할 수 있습니다. 계정 상태를 사용하여 고객에 대한 차단 규칙을 결정할 수도 있습니다.

**계정 상태** 페이지(**신용 및 수금 \> 설정> 신용관리 설정 \> 계정 상태**)에서 계정 상태를 만들 수 있습니다.

1. 계정 상태를 추가하고 고객의 신용 상태를 나타내는 설명을 입력합니다. 예를 들어 **정상** 을 사용하여 고객이 양호한 상태이고 미결 주문이 표준 신용 관리 처리 대상임을 나타냅니다.
2. **송장 발행** 및 **배송 보류** 필드에서 이 계정 상태의 고객에 대해 발생해야 하는 보류 유형을 선택합니다. 신용 한도 규칙이 적용될 때 모든 처리를 보류하거나 송장 처리만 보류하거나 처리를 보류할 수 있습니다.

## <a name="scoring-groups"></a>스코어링 그룹

**스코어링 그룹** 을 설정하여 위험 요소와 위험 요소를 측정하는 데 사용되는 기준을 정의할 수 있습니다. 고객에 대한 정보를 스코어링 그룹에 적용하면 위험 요소별로 점수가 계산되어 고객을 위험 그룹에 배치하는 데 사용됩니다. 위험 그룹은 신용 가치를 식별하고 자동 신용 한도를 계산하는 데 사용할 수 있습니다.

**스코어링 그룹** 페이지(**신용 및 수금 \> 설정 \> 신용 관리 설정 \> 위험 \> 스코어링 그룹**)에서 스코어링 그룹을 생성할 수 있습니다.

1. 스코어링 그룹을 만들고 이름을 입력합니다.
2. 스코어링 그룹을 자세히 설명하려면 설명을 입력합니다.
3. 그룹 유형을 선택합니다. 8개의 미리 정의된 유형이 있습니다. **사용자 정의** 를 선택하여 조직에 더 적합한 그룹 유형을 정의할 수도 있습니다.
4. 점수 유형을 선택하여 스코어링 그룹이 위험 점수를 계산하는 방법을 정의합니다. 다음 옵션을 사용할 수 있습니다.

    - **범위** – 이 옵션을 사용하여 점수를 계산하는 데 사용해야 하는 값 범위를 정의합니다.
    - **사용자 정의** – 이 옵션을 사용하여 점수에 사용해야 하는 값 목록을 수동으로 정의합니다.

5. **범위** 를 점수 유형으로 선택한 경우 값의 범위와 해당 점수를 정의하는 행을 추가합니다.

    1. **최저 값** 필드에 범위에서 가장 낮은 값을 지정합니다.
    2. **최고 값** 필드에 범위에서 가장 높은 값을 지정합니다.
    3. **점수** 필드에 제공된 값이 "최소"/"최고" 범위에 있을 때 할당해야 하는 점수를 입력합니다.

    **사용자 정의** 를 점수 유형으로 선택한 경우 사용자 정의 값과 해당 점수를 정의하는 행을 추가합니다.

    1. **값** 필드에는 고객 정보에서 제공해야 하는 사용자 정의 값을 입력합니다.
    2. **점수** 필드에 제공된 값이 "최소"/"최고" 범위에 있을 때 할당해야 하는 점수를 입력합니다.

## <a name="risk-classification"></a>위험 분류

위험 점수를 기반으로 고객에게 할당할 수 있는 위험 평가를 정의할 수 있습니다. 위험 점수는 고객 정보를 각 점수 그룹과 비교하여 계산됩니다. 점수를 합산하고 총점을 위험 그룹 설정의 값과 비교하여 고객이 속한 위험 그룹을 식별합니다. 그런 다음 위험 그룹 점수는 고객에 대한 신용 관리 차단 및 제외 규칙을 정의하는 데 사용됩니다.

**위험 평가** 페이지(**신용 및 수금 \> 설정 \> 신용 관리 설정 \> 위험 \> 위험 분류**)에서 위험 그룹을 설정할 수 있습니다.

1. 위험 그룹 ID를 입력하십시오.
2. 위험 그룹을 자세히 설명하려면 설명을 입력합니다.
3. 위험 그룹에 속하는 고객을 결정하는 데 사용되는 점수 범위를 입력합니다.
4. 위험 그룹 표시기를 선택하여 위험 그룹을 나타내는 기호를 지정합니다.

## <a name="guaranteeinsurance-types"></a>보증/보험 종류

**보증/보험 종류** 페이지(**신용 및 수금 \> 설정 \> 신용 관리 설정 \> 보험 및 보증 \> 보험 및 보증 유형**)에서 보증/보험 종류를 설정할 수 있습니다.

1. 보증인 또는 보험 브로커의 이름을 식별하는 보증 또는 보험 종류를 입력합니다.
2. 보증인/보험 브로커에 대한 설명을 입력합니다.

## <a name="coverage-types"></a>보장 유형

보장 유형을 사용하여 보험 정책을 추가로 분류할 수 있습니다. 보증과 함께 사용할 수 없습니다.

**보장 유형** 페이지(**신용 및 수금 \> 설정 \> 신용 관리 설정 \> 보험 및 보증 \> 보장 유형**)에서 보장 유형을 추가할 수 있습니다.

1. 보장 유형을 입력하여 보험 또는 보증으로 추가해야 하는 보장 유형을 식별합니다.
2. 적용 범위 유형을 설명하는 설명을 입력합니다.

## <a name="automatic-credit-limits"></a>자동 신용 한도

**자동 신용 한도** 페이지(**신용 및 수금 \> 설정 \> 신용 관리 설정 \> 위험 \> 자동 신용 한도**)에서 자동 신용 한도 기준을 만들 수 있습니다.

1. 자동 신용 한도가 할당되어야 하는 위험 그룹을 선택합니다.
2. 자동 신용 한도에 대한 통화를 선택합니다. 동일한 위험 그룹에 대해 서로 다른 통화로 여러 자동 신용 한도를 생성할 수 있습니다.
3. 이 자동 신용 한도에 사용할 수 있는 최대 회사 수익을 나타내는 수익 금액을 입력하십시오. 신용 한도가 생성되면 수익 금액이 **재무** 페이지(**수취 계정 \> 모든 고객 \> 고객 선택 \> 일반 \> 통계 \> 재무**)에 있는 수익 값과 비교됩니다. 시스템은 **개요** 섹션의 최신 값을 사용합니다.

다음 단계에 따라 선택한 기준에 따라 생성될 신용 한도를 나타내는 라인을 추가하십시오.

1. 신용 한도를 계산하는 데 사용해야 하는 고객 정보를 정의하는 스코어링 그룹을 선택합니다.
2. 스코어링 그룹 정보를 평가하는 방법을 정의하는 비교 연산자를 선택하십시오.
3. 스코어링 그룹에 대해 지정된 값과 비교해야 하는 값을 입력하십시오.
4. 고객 정보가 스코어링 그룹에 대해 지정된 값과 일치하는 경우 지정해야 하는 신용 한도를 입력합니다. 예를 들어 **낮음** 스코어링 그룹에 대한 자동 신용 한도를 생성합니다. 사업 연도가 스코어링 그룹 중 하나인 경우 고객이 5년 동안 사업을 했다면 100,000 신용 한도를 지정하는 한 라인과 10년 동안 사업을 했다면 200,000 신용 한도를 지정하는 다른 라인을 정의할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
