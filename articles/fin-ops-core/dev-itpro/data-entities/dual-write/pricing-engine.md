---
title: Supply Chain Management 가격 책정 엔진과 주문형 동기화
description: 이 항목에서는 Microsoft Dynamics 365 Sales에서 Microsoft Dynamics 365 Supply Chain Management의 가격 책정 엔진을 사용하는 방법에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6b0cc8f403be866ff00b89a33f6c59089c987bb0
ms.sourcegitcommit: 9c19898e1f41495f804c7f07e2636b53a098c4c1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2022
ms.locfileid: "8460969"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Supply Chain Management 가격 책정 엔진과 주문형 동기화

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management에는 거래 계약, 가격 목록, 고객 충성도 프로그램, 판촉 및 할인을 처리하는 가격 책정 엔진이 포함됩니다. 가격 책정 엔진은 복잡한 규칙을 사용하여 주어진 견적이나 주문에 대한 최적의 가격을 결정합니다. 이중 쓰기를 사용하는 경우 Microsoft Dynamics 365 Sales의 **견적** 및 **주문** 페이지에 있는 Supply Chain Management에서 정적 가격 책정 또는 가격 책정 엔진을 사용합니다.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Sales에서 Supply Chain Management의 가격 책정 엔진 사용

1. Sales에서 **판매 \> 주문** 으로 이동합니다.
1. **새로 만들기** 를 선택하여 새 주문을 생성하거나 **내 주문** 목록에서 기존 주문을 선택합니다.
1. 새 주문 라인을 추가합니다.
1. 새 주문을 생성하는 경우 작업 창에서 **가격 주문** 을 선택합니다. 기존 주문을 업데이트하는 경우 작업 창에서 **다시 계산** 을 선택합니다.
1. 다음 열은 자동으로 채워집니다.

    - 세부 금액
    - 할인 %
    - 할인
    - 선적금 금액
    - 적금 금액
    - 총 세금
    - 총 금액

> [!NOTE]
> 견적을 작성할 때도 유사한 프로세스가 적용됩니다.

## <a name="how-it-works"></a>작동 원리

Sales에서 주문을 생성하면 해당 주문은 Sales에 입력한 값을 사용하여 Supply Chain Management에 즉시 동기화됩니다. Sales에서 **가격 주문** 또는 **가격 견적** 을 선택하면 Supply Chain Management는 Supply Chain Management에 정의된 무역 계약 규칙에 따라 각 주문 라인의 가격과 총 주문을 계산합니다. 그런 다음 새로 계산된 값이 Sales로 다시 동기화됩니다.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Supply Chain Management에서 무역 계약 평가 옵션 설정

Sales에서 생성된 주문의 가격을 계산할 때 거래 계약을 준수하거나 무시하도록 Supply Chain Management를 구성할 수 있습니다. 이 옵션을 설정하려면 다음 단계를 따르세요.

1. Supply Chain Management 환경에 로그인합니다.
1. **수취 계정 \> 설정 \> 수취 계정 매개 변수** 로 이동합니다.
1. **가격** 탭의 **무역 협정 평가** 빠른 탭에서 필요에 따라 **수동 입력** 정책의 행을 추가 또는 제거합니다. 이 정책의 존재 여부는 Supply Chain Management 가격 책정 엔진이 판매에 입력된 판매 가격을 자동으로 무효화할지 여부를 제어합니다.

    - **수동 입력** 정책이 **무역 계약 평가** 설정에 *없는* 경우 Supply Chain Management가 가격 마스터입니다. 사용자가 Sales의 작업 창에서 **가격 주문** 또는 **가격 견적** 을 선택하면 Supply Chain Management 가격 책정 엔진이 호출되고 Sales에 입력된 판매 가격이 Supply Chain Management에서 계산된 판매 가격과 같지 않으면 덮어씁니다.
    - **수동 입력** 정책이 **무역 계약 평가** 설정에 *있는* 경우 Sales가 가격 마스터입니다. Sales에 입력한 판매가는 사용자가 Sales의 작업 창에서 **가격 주문** 또는 **가격 견적** 선택 시 자동으로 덮어쓰는 것을 방지합니다.
    - Sales에서 **단가** 및/또는 **할인** 값이 *0*(영)인 주문 라인 또는 견적 라인은 특별한 경우로 취급됩니다. 관련 무역 계약 가격을 사용할 수 있는 경우 Supply Chain Management는 **무역 거래 평가** 설정과 관련없이 *항상* 이러한 필드에 적용합니다.

    이러한 각 경우의 예는 다음 시나리오를 참조하세요.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>예시 시나리오 1: 수동 입력 옵션이 없는 무역 계약 평가

이 시나리오에서 Supply Chain Management의 **무역 계약 평가** 설정은 **수동 입력** 정책을 포함하지 *않습니다*. Sales 사용자가 Sales에 0이 아닌 판매 가격이 있는 주문 라인을 입력하고 Supply Chain Management의 항목에 대해 정의된 판매 가격이 없습니다.

1. Sales에서 사용자는 **단가** 값이 1 미국 달러(USD)인 주문 라인을 생성합니다.
1. 주문 라인은 판매 가격이 1 USD인 Supply Chain Management와 동기화됩니다.
1. Sales에서 사용자는 작업 창의 **가격 주문** 을 선택합니다.
1. Supply Chain Management는 관련 가격 및 할인을 검색한 다음 합계를 계산합니다. 항목에 Supply Chain Management의 판매 가격이 없기 때문에 0 USD의 판매 가격이 되도록 계산에서 라인을 업데이트합니다.
1. 라인의 새 판매 가격이 판매로 다시 동기화됩니다.
1. 결과는 판매 가격이 0 USD인 Sales의 주문 라인입니다.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>예시 시나리오 2: 수동 입력 옵션이 있는 무역 계약 평가

이 시나리오에서 Supply Chain Management의 **무역 계약 평가** 설정은 **수동 입력** 정책을 *포함합니다*. 판매 사용자는 판매에 판매 가격이 0이 아닌 주문 라인을 입력합니다. Supply Chain Management에는 주문 품목에 대해 판매 가격 2 USD를 설정하는 무역 계약이 포함됩니다.

1. Sales에서 사용자는 **단가** 값이 1USD인 항목에 대한 주문 라인을 생성합니다.
1. 주문 라인은 판매 가격이 1 USD인 Supply Chain Management와 동기화됩니다.
1. Sales에서 사용자는 작업 창의 **가격 주문** 을 선택합니다.
1. Supply Chain Management의 **무역협정 평가** 설정에는 **수동 입력** 정책이 포함되므로 해당 무역 협정이 다른 판매 가격을 지정하더라도 판매 가격은 변경되지 않습니다.
1. 판매 가격은 판매 및 Supply Chain Management에서 변경되지 않습니다.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>예제 시나리오 3: Sales에서 판매 가격이 0인 품목에 대한 거래 계약 평가

이 시나리오에서 Supply Chain Management의 **무역 계약 평가** 설정은 **수동 입력** 정책을 *포함합니다*. 판매 사용자는 판매에 판매 가격이 0(영)인 주문 라인을 입력합니다. Supply Chain Management에는 주문 품목에 대해 판매 가격 2 USD를 설정하는 무역 계약이 포함됩니다.

1. Sales에서 사용자는 **단가** 값이 0 USD 및 **라인 할인** 값이 0 USD인 주문 라인을 생성합니다.
1. 주문 라인은 판매 가격이 0 USD인 Supply Chain Management와 동기화됩니다.
1. 판매 가격이 0인 주문 라인을 받았기 때문에 **수동 입력** 옵션이 활성화되어 있어도 Supply Chain Management는 가격 책정 엔진이라고 부릅니다. 가격 책정 엔진은 무역 계약에 의해 설정된 2 USD의 판매 가격을 반환하고 Supply Chain Management의 주문 라인을 업데이트합니다.
1. 업데이트된 판매 가격이 아직 판매의 주문 라인에 동기화되지 않았습니다.
1. Sales에서 사용자는 작업 창의 **가격 주문** 을 선택합니다.
1. Supply Chain Management의 주문 라인은 현재 판매로 다시 동기화된 2 USD의 판매 가격을 유지합니다. 따라서 Sales의 주문 라인 값 **단가** 가 0 USD에서 2 USD로 업데이트됩니다.
1. Sales에서 사용자는 새로운 **라인 할인** 값 0.50 USD를 입력합니다. 이제 Sales는 라인의 **확장 금액** 값이 1.50 USD임을 계산합니다.
1. 주문 라인은 **라인 할인** 값이 0.50 USD인 Supply Chain Management와 동기화됩니다.
1. Sales에서 사용자는 작업 창의 **가격 주문** 을 선택합니다.
1. Sales의 주문 라인에 대한 가격이나 할인은 변경되지 않습니다.

## <a name="limitations"></a>제한 사항

Sales의 열을 채우면 다음 제한 사항이 적용됩니다.

- Supply Chain Management의 요금 및 요금 할당 설정은 Sales에서 복제되지 않습니다.
- 가격 책정은 Supply Chain Management의 판매 주문 라인 페이지에 있는 **소매 채널** 열에 지정된 특별 소매 가격을 고려하지 않습니다.
- Supply Chain Management의 **무역 수당 관리** 섹션에 정의된 할인은 고려되지 않습니다.
- 가격 책정은 판매 계약을 고려하지 않습니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
