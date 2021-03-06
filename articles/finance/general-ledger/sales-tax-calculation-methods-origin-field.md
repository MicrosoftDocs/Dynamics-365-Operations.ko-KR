---
title: 기준 필드의 판매세 계산 방법
description: 이 문서에서는 판매세 코드 페이지의 기준 필드에 있는 옵션과 판매세 코드에 대해 선택한 옵션에 따라 판매세가 계산되는 방법에 관해 설명합니다.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ac37858c68996c6c8140303327003d93bd357b512f9c634650b7e9df1284496
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450745"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>기준 필드의 판매세 계산 방법

[!include [banner](../includes/banner.md)]

이 문서에서는 판매세 코드 페이지의 기준 필드에 있는 옵션과 판매세 코드에 대해 선택한 옵션에 따라 판매세가 계산되는 방법에 관해 설명합니다.

판매세 코드 페이지에서 작성하는 각 판매세 코드에 대해 기본 필드의 과세 기준 금액에 적용할 계산 방법을 선택해야 합니다.

## <a name="percentage-of-net-amount"></a>순액 비율
순액 비율 계산 방법은 기준 필드의 기본값입니다. 기타 판매세를 제외하고 판매세가 구매 또는 판매 금액의 백분율로 계산됩니다.
### <a name="example"></a>예

세율은 25%입니다. 송장 라인은 10개 품목의 수량을 각각 1.00으로 표시하고 고객에게 10% 라인 할인이 허용됩니다. 순액: (10 x 1.00) -10% = 9.00 판매세: 9.00 x 25% = 2.25 총 금액: 9.00 + 2.25 = 11.25

## <a name="percentage-of-gross-amount"></a>총액 비율
총액 비율 방식을 선택하면 판매세가 총 판매액의 백분율로 계산됩니다. 총액은 라인 순액에 기준 = 총액 비율인 세금을 제외한 라인에 대한 모든 세금 및 수수료를 더한 것입니다.
### <a name="example"></a>예

세무 당국이 품목에 특별 관세를 부과했습니다. 관세 금액은 판매세가 계산되기 전 순액에 추가됩니다. 다음 판매세 코드를 적용합니다.
-   DUTY 1 = 10%, 순액 비율 계산 방법 사용
-   DUTY 2 = 20%, 순액 비율 계산 방법 사용
-   SALESTAX = 25%, 총액 비율 계산 방법 사용

순액이 10.00인 경우 DUTY 1은 1.00(10.00 x 10%)이고 DUTY 2는 2.00(10.00 x 20%)입니다. 금액은 다음과 같습니다. 총액: 순액 + DUTY 1 금액 + DUTY 2 금액(10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 총 관세 및 판매세: 1.00 + 2.00 + 3.25 = 6.25 총 금액: 10.00 + 6.25 = 16.25

| **메모**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 기준 = 총액 비율인 하나의 세금 코드만 거래에 사용할 수 있습니다. 한 거래에 대해 이러한 세금 코드가 두 개 이상 결정되면 판매세를 계산할 수 없다는 오류가 표시됩니다. |


## <a name="percentage-of-sales-tax"></a>판매세 비율

기준 필드에서 판매세 비율을 선택하면 판매세가 판매세 필드에서 선택한 판매세의 비율로 계산됩니다. 판매세 필드의 판매세에 선택한 판매세가 먼저 계산됩니다. 두 번째 판매세는 첫 번째 판매세 금액을 기준으로 계산됩니다.
### <a name="example"></a>예

다음 판매세 코드를 적용합니다.
-   DUTY 1 = 10%, 순액 비율 방법 사용
-   DUTY 2 = 20%, 판매세 비율 방법 사용, 판매세 필드의 판매세에 DUTY 1 포함
-   SALESTAX = 25%, 총액 비율 방법 사용

순액: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 총액: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 총 관세 및 판매세: 1.00 + 0.20 + 2.80 = 4.00 총 금액: 10.00 + 4.00 = 14.00

| **메모**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 세금 계산에 다단계 세금은 불가능합니다. 다른 세금을 기준으로 이미 계산된 세금을 기준으로 세금을 계산할 수 없습니다. 한 거래의 세금 코드에 대한 여러 단일 수준 세금은 계산할 수 있습니다. |

## <a name="amount-per-unit"></a>단위당 금액
기준 필드에서 단위당 금액을 선택하면 판매세는 문서 라인에 입력된 수량을 곱한 단위당 고정 금액으로 계산됩니다. 단위 필드에서 단위를 선택해야 합니다. 단위당 금액은 판매세 코드 값 페이지에 지정됩니다.
### <a name="example"></a>예

판매세 코드가 단위 = 상자당 USD 1.20으로 설정되고 송장 라인에 25개의 상자가 판매되면 판매세는 25 x 1.20 = 30.00으로 계산됩니다

| **메모**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 거래가 판매세 코드에 지정된 단위와 다른 단위로 입력된 경우 단위 변환 페이지에서 설정한 단위 변환에 따라 자동으로 변환됩니다. |

###  <a name="amount-per-unit-additional-option"></a>단위당 금액, 추가 옵션

계산 탭에서 계산된 세금 단위당 금액이 다른 세금 코드보다 먼저 계산되고 기준 = 순액 비율이 계산되는 다른 세금 코드 전에 순액에 추가되는지를 선택할 수 있습니다.

### <a name="examples"></a>예

거래에 대해 2개의 세금 코드를 계산한다고 가정합니다.

-   DUTY: 기준 = 단위당 금액 및 판매세, 값은 단위 = 개당 5.00으로 설정됩니다
-   SALESTAX: 기준은 아래 예와 같이 값이 25%로 설정됩니다

품목 1개를 10.00의 단가로 판매합니다
#### <a name="example-1"></a>예시 1

SALESTAX: 기준 = 총액 비율 방법으로 SALESTAX는 총액의 비율로 계산되기 때문에 판매세 전 계산 옵션은 효과가 없습니다. DUTY: 1 x 5.00 = 5.00 총액: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 총 판매세: 5.00 + 3.75 = 8.75 총 금액: 10.00 + 8.75 = 18.75

#### <a name="example-2"></a>예시 2

SALESTAX: 기준 = 순액 비율로 DUTY 계산에 대해 판매세 전 계산 옵션이 선택되지 않았습니다. 순액: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 총 판매세: 5.00 + 2.50 = 7.50 총 금액: 10.00 + 7.50 = 17.50

#### <a name="example-3"></a>예시 3

SALESTAX: 기준 = 순액 비율로 DUTY 계산에 대해 판매세 전 계산 옵션이 선택되었습니다. 순액: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 총 판매세: 5.00 + 3.75 = 8.75 총 금액: 10.00 + 8.75 = 18.75

#### <a name="example-4"></a>예시 4

예시 3과 예시 1의 결과는 관세가 하나뿐이므로 같습니다. 두 개의 관세가 있고 그중 하나만 판매세 계산을 위한 순액에 포함된다고 가정합니다. DUTY 1: 5.00, 단위당 금액 방법을 사용하고 판매세 전 계산 옵션이 선택되어 있습니다. DUTY 2: 2.50, 단위당 금액 방법을 사용하고 판매세 전 계산 옵션을 선택하지 않은 경우 판매세: 25%, 순액 비율 방법 사용 순 금액: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 판매세가 적용되는 순 금액: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 관세를 포함한 총 판매세: 5.00 + 2.50 + 3.75 = 11.25 총 금액: 10.00 + 11.25 = 21.25 순액의 합계에 대해 25% SALESTAX 계산 (10.00) + DUTY 1 (5.00) = 15.00. DUTY 2는 판매세 계산 후 세액에 가산됩니다.

## <a name="calculated-percentage-of-net-amount"></a>계산된 순액 비율
순 금액의 계산된 비율은 문서 또는 분개장에 대한 판매세 포함 금액 매개 변수의 설정에 따라 세금 계산을 다르게 처리합니다.
### <a name="example-1"></a>예시 1

문서/분개장이 판매세 포함 금액으로 설정된 경우 거래 라인 금액: 10.00 세율: 25% 판매세: 거래 라인 금액 x 세율(10.00 x 25%) = 2.50 과세 기준 금액(원금): 거래 라인 금액 - 판매세 (10.00 - 2.50) = 7.50

### <a name="example-2"></a>예시 2

문서/분개장이 판매세 미포함 금액으로 설정된 경우 거래 라인 금액: 10.00 세율: 25% 판매세: (거래 라인 금액 x 세율) / (100 - 세율) (10.00 x 25%) / (100% - 25%) = 3.33 과세 표준 금액(원금): 거래 라인 금액 = 10.00



## <a name="additional-resources"></a>추가 리소스

[한계 기준 및 계산 방법 기반의 판매세율](marginal-base-field.md)

[판매세 코드의 전체 금액 및 간격 계산 옵션](whole-amount-interval-options-sales-tax-codes.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]