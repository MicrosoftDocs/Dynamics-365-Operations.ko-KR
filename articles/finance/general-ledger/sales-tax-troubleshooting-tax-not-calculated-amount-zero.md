---
title: 세금이 계산되지 않거나 세액이 0임
description: 이 항목에서는 세액이 0(영)이거나 세금이 계산되지 않을 때 도움이 될 수 있는 문제 해결 정보를 제공합니다.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 45aa5931b5d958dd32bd165b414957fa7b366d077cef67621221ce19b56b67d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450787"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>세금이 계산되지 않거나 세액이 0임

[!include [banner](../includes/banner.md)]

거래에 0이 아닌 라인 금액이 있을 수 있지만 세금이 계산되지 않거나 계산된 세액이 0입니다. 이 문제를 해결하려면 필요에 따라 다음 섹션의 단계를 따르세요.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>거래에서 세금 코드가 올바르게 선택되었는지 확인합니다

거래에서 올바른 세금 코드를 선택하지 않거나 세금 코드를 하나도 선택하지 않으면 세금이 계산되지 않습니다. 다음 단계에 따라 거래에 세금 코드가 올바르게 선택되었는지 확인합니다. 

1. 거래 라인, **라인 세부 정보** 빠른 탭, **설정** 탭, **판매세** 섹션의 **품목 판매세 그룹** 및 **판매세 그룹** 필드에서 올바른 세금 그룹이 선택되었는지 확인합니다. 올바른 세금 그룹이 선택되지 않은 경우 맞는 그룹을 선택합니다.

    [![품목 판매세 그룹 및 판매세 그룹 필드.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. **세금** \> **간접세** \> **판매세** \> **판매세 그룹** 으로 이동합니다.
3. 적절한 판매세 그룹을 선택한 다음 **설정** 빠른 탭에서 **판매세 코드** 필드의 세금 코드를 기록해 둡니다.

    [![판매세 그룹 페이지.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. **세금** \> **간접세** \> **판매세** \> **품목 판매세 그룹** 으로 이동합니다.
5. 적절한 품목 판매세 그룹을 선택한 다음 **설정** 빠른 탭에서 **판매세 코드** 필드의 세금 코드가 판매세 그룹의 세금 코드와 일치하는지 확인합니다.

    [![품목 판매세 그룹 페이지.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. 세금 코드가 일치하지 않으면 그룹 중 하나에 대한 판매세 코드를 업데이트합니다.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>선택한 세금 코드가 면세가 아니고 올바른 세율 값을 가지고 있는지 확인합니다

세금 코드가 면세이나 세율이 0(영)인 경우 세금 계산 결과는 0이 됩니다. 다음 단계에 따라 선택한 세금 코드가 면세인지 확인하고 올바른 세율이 적용되는지 확인합니다.

1. **세금** \> **간접세** \> **판매세** \> **판매세 그룹** 으로 이동합니다.
2. 적절한 판매세 그룹을 선택한 다음 **설정** 빠른 탭에서 **면세** 확인란이 선택 취소되었는지 확인합니다. 선택되어 있으면 선택을 취소합니다.

    [![판매세 그룹 페이지의 면세 확인란.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. **세금** \> **간접세** \> **판매세** \> **판매세 코드** 로 이동합니다.
4. 적절한 판매세 코드를 선택한 다음 **값** 필드의 세율 값이 0(영)이 아닌지 확인합니다. 0인 경우 올바른 세율로 설정되도록 필드를 업데이트합니다.

    [![판매세 코드 값 페이지의 값 필드.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>0이 올바른 세액인지 확인

일부 시나리오에서는 세액 0(영)이 맞습니다. 다음 단계에 따라 거래의 세액이 0이 맞는지 확인합니다.

1. **총계정원장** \> **원장 설정** \> **총계정원장 매개 변수** 로 이동합니다.
2. **판매세** 탭의 **계산 방법** 필드에서 **합계** 가 선택되어 있는지 확인합니다.

    [![총계정원장 매개 변수 페이지의 계산 방법 필드.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. **세금** \> **간접세** \> **판매세** \> **판매세 코드** 로 이동합니다.
4. 해당 판매세 코드를 선택하고 **계산** \> **한계 기준** 을 선택한 다음 한계 기준이 **송장 잔액의 순액** 또는 **기타 판매세 금액 포함 송장 총액** 으로 설정되어 있는지 확인합니다. 자세한 내용은 [기타 판매세 금액 포함 송장 총액](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts)을 참조하세요.
5. 2단계와 4단계에서 올바른 값이 설정되어 있으면 거래 총액이 0(영)인지 확인합니다. 총 금액이 0인 경우 세액 0이 예상되는 결과입니다. 세금 계산은 송장 잔액의 총액을 기준으로 하고 해당 금액이 라인 단위가 아니기 때문에 세금 계산 후 각 라인에 세액 0이 할당됩니다.

## <a name="determine-whether-customization-exists"></a>사용자 지정이 있는지 확인

이전 섹션의 단계를 완료했지만 문제가 발견되지 않는 경우 사용자 지정이 있는지 확인하세요. 사용자 지정이 없으면 Microsoft 서비스 요청을 작성하여 추가 지원을 받으세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
