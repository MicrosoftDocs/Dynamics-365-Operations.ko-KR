---
title: 초과 지불에 대한 현금 할인
description: 이 문서에서는 고객이 현금 할인을 받았지만 초과 지불하는 경우 지불이 처리되는 방법을 보여주는 시나리오를 제공합니다.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7e2e3a6805e1c668de8a3fb62e7190ded6fc20d754ecfca23245e2861f6c2cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450160"
---
# <a name="cash-discounts-for-overpayments"></a>초과 지불에 대한 현금 할인

[!include [banner](../includes/banner.md)]

이 문서에서는 고객이 현금 할인을 받았지만 초과 지불하는 경우 지불이 처리되는 방법을 보여주는 시나리오를 제공합니다. 

지불 금액이 송장 금액에서 현금 할인을 뺀 금액보다 많은 경우 송장이 초과 지불된 것으로 간주됩니다. 송장이 초과 지급되었을 때 획득 가능한 현금 할인 차액을 처리하는 방법을 지정하려면 **수취 계정 매개 변수** 페이지의 **현금 할인 관리** 및 **최대 초과 지불 또는 과소 지불** 필드를 사용합니다. 다음 예에서 고객은 송장에 0.50을 초과 지불했습니다.

| 송장 합계 | 현금 할인 가능 | 현금 할인을 포함한 지불 금액 | 고객이 실제로 지불하는 금액 |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105.00        | 10.50                   | 94.50                                               | 95.00                             |

## <a name="cash-discount-administration--specific"></a>현금 할인 관리 = 특정
**자동 거래 계정** 페이지의 **현금 할인 관리** 필드에서 **특정** 을 선택하면 전액 현금 할인이 적용됩니다. 초과 지급 금액은 현금 할인 차액 원장 계정에 전기되거나 고객 계정의 잔액으로 남습니다. 초과 지급 금액이 0.00과 **최대 초과 지불 또는 과소 지불** 필드에 입력한 금액 사이인지 또는 초과 지급 금액이 **최대 초과 지불 또는 과소 지불** 금액보다 많은지 여부에 따라 동작이 달라집니다.

### <a name="scenario-1"></a>시나리오 1

이 시나리오에서 초과 지급 금액은 0.00과 최대 초과 지급 또는 과소 지급 사이입니다. 105.00에 대한 송장을 입력하고 7일 이내에 송장을 결제하면 현금 할인이 가능합니다.

| 송장 합계 | 현금 할인 가능 | 현금 할인을 포함한 지불 금액 |
|---------------|-------------------------|-----------------------------------------------------|
| 105.00        | 10.50                   | 94.50                                               |

고객은 현금 할인 기간 내에 95.00에 대한 지불을 제출합니다. 지불은 105.00에 대한 송장에 대해 정산됩니다. 송장 및 결제가 완료되면 수취 계정에 고객에 대해 다음과 같은 거래가 생성됩니다.

| 거래   | 금액 | 잔액 |
|---------------|--------|---------|
| 송장       | 105.00 | 0.00    |
| 지불       | -95.00 | 0.00    |
| 현금 할인 | -10.50 | 0.00    |

지급 및 정산에 대해 다음 회계 항목이 생성됩니다. **지불**

| 거래처             | 차변 금액 | 대변 금액 |
|---------------------|--------------|---------------|
| 현금                | 95.00        |               |
| 수취 계정 |              | 95.00         |

**정산**

| 거래처                                                                                                          | 차변 금액 | 대변 금액 |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| 현금할인(**현금 할인** 페이지의 **고객 할인을 위한 주 계정** 필드)                 | 10.50        |               |
| 수취 계정                                                                                              |              | 10.50         |
| 고객 현금 할인(**자동 거래 계정** 페이지의 **고객 현금 할인** 필드) |              | 0.50          |
| 수취 계정                                                                                              | 0.50         |               |

### <a name="scenario-2"></a>시나리오 2

이 시나리오에서 초과 지불 금액은 최대 초과 지불 또는 과소 지불 금액을 초과합니다. 105.00에 대한 송장을 입력하고 7일 이내에 송장을 결제하면 현금 할인이 가능합니다.

| 송장 합계 | 현금 할인 가능 | 현금 할인을 포함한 지불 금액 |
|---------------|-------------------------|-----------------------------------------------------|
| 105.00        | 10.50                   | 94.50                                               |

고객은 현금 할인 기간 내에 95.00에 대한 지불을 제출합니다. 지불은 105.00에 대한 송장에 대해 정산됩니다. 송장 및 결제가 완료되면 수취 계정에 고객에 대해 다음과 같은 거래가 생성됩니다.

| 거래   | 금액 | 잔액 |
|---------------|--------|---------|
| 송장       | 105.00 | 0.00    |
| 지불       | -95.00 | -0.50   |
| 현금 할인 | -10.50 | 0.00    |

0.50의 초과 지불 금액은 지불에 대한 미결제 잔액으로 남아 있으며 다른 송장에 대해 정산할 수 있습니다. 지급 및 정산에 대해 다음 회계 항목이 생성됩니다. **지불**

| 거래처             | 차변 금액 | 대변 금액 |
|---------------------|--------------|---------------|
| 현금                | 95.00        |               |
| 수취 계정 |              | 95.00         |

**정산**

| 거래처                                                                                          | 차변 금액 | 대변 금액 |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| 현금할인(**현금 할인** 페이지의 **고객 할인을 위한 주 계정** 필드) | 10.50        |               |
| 수취 계정                                                                              |              | 10.50         |

## <a name="cash-discount-administration--unspecific"></a>현금 할인 관리 = 불특정
**자동 거래 계정** 페이지의 **현금 할인 관리** 필드에서 **불특정** 을 선택하면 현금 할인 금액은 초과 지불 금액만큼 감소합니다. 이 동작은 초과 지불 금액이 **최대 초과 지불 또는 과소 지불** 필드에 입력된 금액을 초과하거나 미만인지 여부에 관계없이 항상 적용됩니다.

### <a name="scenario-3"></a>시나리오 3

이 시나리오에서 105.00에 대한 송장을 입력하고 7일 이내에 송장을 결제하면 현금 할인이 가능합니다.

| 송장 합계 | 현금 할인 가능 | 현금 할인을 포함한 지불 금액 |
|---------------|-------------------------|-----------------------------------------------------|
| 105.00        | 10.50                   | 94.50                                               |

고객은 현금 할인 날짜 내에 95.00에 대한 지불을 제출합니다. 지불은 105.00에 대한 송장에 대해 정산됩니다. 송장 및 결제가 완료되면 수취 계정에 고객에 대해 다음과 같은 거래가 생성됩니다.

| 거래   | 금액 | 잔액 |
|---------------|--------|---------|
| 송장       | 105.00 | 0.00    |
| 지불       | -95.00 | -0.00   |
| 현금 할인 | -10.00 | 0.00    |

현금 할인 금액이 10.50에서 10.00으로 감소합니다. 결제 및 송장은 정산된 것으로 간주됩니다. **지불**

| 거래처             | 차변 금액 | 대변 금액 |
|---------------------|--------------|---------------|
| 현금                | 95.00        |               |
| 수취 계정 |              | 95.00         |

**정산**

| 거래처                                                                                          | 차변 금액 | 대변 금액 |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| 현금할인(**현금 할인** 페이지의 **고객 할인을 위한 주 계정** 필드) | 10.50        |               |
| 수취 계정                                                                              |              | 10.50         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]