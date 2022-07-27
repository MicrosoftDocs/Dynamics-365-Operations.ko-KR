---
title: 수취 계정에 대한 중앙 집중식 지불
description: 여러 법인을 포함하는 조직은 모든 지불을 처리하는 단일 법인을 사용하여 지불을 생성하고 관리할 수 있습니다. 따라서 동일한 거래가 여러 법인에 입력될 필요가 없습니다. 이 문서에서는 다양한 시나리오에서 중앙 집중식 지불에 대한 전기가 처리되는 방법을 보여주는 예를 제공합니다.
author: ShivamPandey-msft
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5dfa3965cc22c0c3bcf31ae076afb586e12d158ef66464ce933b509aaf9a521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450238"
---
# <a name="centralized-payments-for-accounts-receivable"></a>수취 계정에 대한 중앙 집중식 지불

[!include [banner](../includes/banner.md)]

여러 법인을 포함하는 조직은 모든 지불을 처리하는 단일 법인을 사용하여 지불을 생성하고 관리할 수 있습니다. 따라서 동일한 거래가 여러 법인에 입력될 필요가 없습니다. 이 문서에서는 다양한 시나리오에서 중앙 집중식 지불에 대한 전기가 처리되는 방법을 보여주는 예를 제공합니다.

여러 법인을 가진 조직은 모든 결제를 처리하는 법인을 사용하여 결제를 생성하고 관리할 수 있습니다. 따라서 동일한 거래가 여러 법인에 입력될 필요가 없습니다. 또한 조직은 지불 제안, 정산, 중앙 집중식 지불을 위한 미결 및 마감 거래 편집 프로세스가 능률화되기 때문에 시간을 절약할 수 있습니다. 

중앙 집중식 지불 조직에는 운영을 위한 많은 법인이 있으며 각 운영 법인은 자체 수취 송장 정보를 관리합니다. 모든 운영 법인에 대한 지불은 지불의 법인으로 알려진 단일 법인에서 수취합니다. 정산 과정에서 적용 가능한 외상매입금 및 외상매출금 거래가 생성됩니다. 실현 손익 거래를 받는 조직의 법인과 중앙 집중식 지불과 관련된 현금 할인 거래를 처리하는 방법을 지정할 수 있습니다. 중앙 집중식 지불 분개장 라인에서 **계정 유형** 은 고객으로 설정되어야 합니다. **상쇄 계정 유형** 은 은행 또는 원장으로 설정해야 합니다. 은행 계좌는 현재 회사에 있어야 합니다. 

다음 예는 다양한 시나리오에서 전기가 처리되는 방법을 보여줍니다. 이러한 모든 예에 대해 다음 구성이 가정됩니다.

-   법인은 Fabrikam, Fabrikam East 및 Fabrikam West입니다. 고객 지불은 Fabrikam에 입력됩니다.
-   **회사 간 회계** 페이지의 **현금 할인 후** 필드가 **송장의 법인** 으로 설정됩니다.
-   **회사 간 회계** 페이지의 **환전 후 손익** 필드가 **지불의 법인** 으로 설정됩니다.
-   고객 Northwind Traders는 각 법인의 고객으로 설정됩니다. 다양한 법인의 고객은 동일한 전체 주소록 ID를 공유하므로 동일한 고객으로 식별됩니다.

| 주소록 ID | 고객 계정 | 이름              | 법인  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam East |
| 4050            | 10000            | Northwind Traders | Fabrikam West |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>예 1: 다른 법인 송장의 고객 지불
Fabrikam은 Fabrikam 고객 계정 4000인 Northwind Traders에 대해 600.00의 지불을 받습니다. 지불은 Fabrikam East의 고객 계정 4000에 대한 미결 송장으로 정산됩니다.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>송장이 고객 4000에 대해 Fabrikam East에 전기됩니다

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 수취 계정(Fabrikam East) | 600.00       |               |
| 판매(Fabrikam East)               |              | 600.00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>고객 4000에 대한 지불이 수취되고 Fabrikam에 전기됩니다

| 거래처                        | 차변 금액 | 대변 금액 |
|--------------------------------|--------------|---------------|
| 현금(Fabrikam)                | 600.00       |               |
| 수취 계정(Fabrikam) |              | 600.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                         | 차변 금액 | 대변 금액 |
|---------------------------------|--------------|---------------|
| 수취 계정(Fabrikam)  | 600.00       |               |
| Fabrikam East(Fabrikam)로 발생 |              | 600.00        |

**Fabrikam East 전기**

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| Fabrikam(Fabrikam East)에서 발생   | 600.00       |               |
| 수취 계정(Fabrikam East) |              | 600.00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>예 2: 현금 할인이 있는 다른 법인 송장의 고객 지불
Fabrikam은 Fabrikam 고객 4000인 Northwind Traders에 대해 580.00의 지불을 받습니다. Fabrikam East에는 고객 4000에 대한 미결 송장이 있습니다. 송장에는 20.00 현금 할인이 가능합니다. 지불은 미결 Fabrikam East 송장으로 정산됩니다. 현금 할인은 송장의 법인 Fabrikam East에 전기됩니다.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Fabrikam East 고객 4000에 대한 송장이 Fabrikam East에 전기됩니다

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 수취 계정(Fabrikam East) | 580.00       |               |
| 판매(Fabrikam East)               |              | 580.00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Fabrikam 고객 4000에 대한 지불을 받고 Fabrikam에 전기됩니다

| 거래처                        | 차변 금액 | 대변 금액 |
|--------------------------------|--------------|---------------|
| 현금(Fabrikam)                | 600.00       |               |
| 수취 계정(Fabrikam) |              | 600.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                         | 차변 금액 | 대변 금액 |
|---------------------------------|--------------|---------------|
| 수취 계정(Fabrikam)  | 580.00       |               |
| Fabrikam East(Fabrikam)로 발생 |              | 580.00        |

**Fabrikam East 전기**

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| Fabrikam(Fabrikam East)에서 발생   | 580.00       |               |
| 수취 계정(Fabrikam East) |              | 580.00        |
| 현금 할인(Fabrikam East)       | 20.00        |               |
| 수취 계정(Fabrikam East) |              | 20.00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>예 3: 실현된 환차익이 있는 다른 법인의 송장에 대한 고객 지불
Fabrikam은 Fabrikam 고객 4000인 Northwind Traders에 대해 600.00 유로(EUR)의 지불을 받습니다. 지불은 Fabrikam East의 고객 4000에 대한 미결 송장으로 정산됩니다. 정산 과정에서 환차익 거래가 발생합니다.

-   송장 날짜 기준 EUR-미국 달러(USD) 환율: 1.2062
-   결제일 기준 EUR-USD 환율: 1.2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Fabrikam East 고객 4000에 대한 송장이 Fabrikam East에 전기됩니다

| 거래처                             | 차변 금액            | 대변 금액           |
|-------------------------------------|-------------------------|-------------------------|
| 수취 계정(Fabrikam East) | 600.00 EUR/723.72 USD |                         |
| 판매(Fabrikam East)               |                         | 600.00 EUR/723.72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Fabrikam 고객 4000에 대한 지불을 받고 Fabrikam에 전기됩니다

| 거래처                        | 차변 금액            | 대변 금액           |
|--------------------------------|-------------------------|-------------------------|
| 현금(Fabrikam)                | 600.00 EUR/736.62 USD |                         |
| 수취 계정(Fabrikam) |                         | 600.00 EUR/736.62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                         | 차변 금액            | 대변 금액           |
|---------------------------------|-------------------------|-------------------------|
| 수취 계정(Fabrikam)  | 600.00 EUR/736.62 USD |                         |
| Fabrikam East(Fabrikam)로 발생 |                         | 600.00 EUR/736.62 USD |
| Fabrikam East(Fabrikam)로 발생 | 0.00 EUR/12.90 USD    |                         |
| 실현 이익(Fabrikam)        |                         | 0.00 EUR/12.90 USD    |

**Fabrikam East 전기**

| 거래처                             | 차변 금액            | 대변 금액           |
|-------------------------------------|-------------------------|-------------------------|
| Fabrikam(Fabrikam East)에서 발생   | 600.00 EUR/736.62 USD |                         |
| 수취 계정(Fabrikam East) |                         | 600.00 EUR/736.62 USD |
| 수취 계정(Fabrikam East) | 0.00 EUR/12.90 USD    |                         |
| Fabrikam(Fabrikam East)에서 발생   |                         | 0.00 EUR/12.90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>예 4: 현금 할인 및 실현된 환차익이 있는 다른 법인 송장의 고객 지불
Fabrikam은 Fabrikam East의 미결 송장에 대해 Fabrikam 고객 4000인 Northwind Traders에 대한 지불을 전기합니다. 송장에 사용 가능한 현금 할인이 있고 판매세 거래가 생성됩니다. 지불은 미결 Fabrikam East 송장으로 정산됩니다. 정산 과정에서 환차익 거래가 발생합니다. 현금 할인은 송장의 법인(Fabrikam East)에 전기되고 화차익은 지불 법인(Fabrikam)에 전기됩니다.

-   송장 날짜 기준 EUR-USD 환율: 1.2062
-   결제일 기준 EUR-USD 환율: 1.2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>고객 4000에 대한 자유 텍스트 송장이 전기되고 Fabrikam East에서 세금 거래가 생성됩니다

| 거래처                             | 차변 금액            | 대변 금액           |
|-------------------------------------|-------------------------|-------------------------|
| 수취 계정(Fabrikam East) | 638.22 EUR/769.82 USD |                         |
| 판매(Fabrikam East)               |                         | 600.00 EUR/723.72 USD |
| 판매세(Fabrikam East)           |                         | 38.22 EUR/46.10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>고객 4000에 대한 지불이 수취되고 Fabrikam에 전기됩니다

| 거래처                        | 차변 금액            | 대변 금액           |
|--------------------------------|-------------------------|-------------------------|
| 현금(Fabrikam)                | 626.22 EUR/768.81 USD |                         |
| 수취 계정(Fabrikam) |                         | 626.22 EUR/768.81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                         | 차변 금액            | 대변 금액           |
|---------------------------------|-------------------------|-------------------------|
| 수취 계정(Fabrikam)  | 626.22 EUR/768.81 USD |                         |
| Fabrikam East(Fabrikam)로 발생 |                         | 626.22 EUR/768.81 USD |
| Fabrikam East(Fabrikam)로 발생 | 0.00 EUR/13.46 USD    |                         |
| 실현 이익(Fabrikam)        |                         | 0.00 EUR/13.46 USD    |

**Fabrikam East 전기**

| 거래처                             | 차변 금액            | 대변 금액           |
|-------------------------------------|-------------------------|-------------------------|
| Fabrikam(Fabrikam East)에서 발생   | 626.22 EUR/768.81 USD |                         |
| 수취 계정(Fabrikam East) |                         | 626.22 EUR/768.81 USD |
| 수취 계정(Fabrikam East  | 0.00 EUR/13.46 USD    |                         |
| Fabrikam(Fabrikam East)에서 발생   |                         | 0.00 EUR/13.46 USD    |
| 현금 할인(Fabrikam East)       | 12.00 EUR/14.47 USD   |                         |
| 수취 계정(Fabrikam East) |                         | 12.00 EUR/14.47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>예 5: 기본 지불이 포함된 고객 대변표
Fabrikam은 고객 4000인 Northwind Traders로부터 75.00의 지불을 받습니다. 지불은 Fabrikam West 고객 10000에 대한 미결 송장 및 Fabrikam East 고객 4000에 대한 미결 대변표로 정산됩니다. 지불은 **거래 정산** 페이지에서 기본 지불로 선택됩니다.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>송장이 고객 10000에 대해 Fabrikam West에 전기됩니다

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 수취 계정(Fabrikam West) | 100.00       |               |
| 판매(Fabrikam West)               |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>대변표가 고객 4000에 대해 Fabrikam East에 전기됩니다

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 판매 반품(Fabrikam East)       | 25.00        |               |
| 수취 계정(Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>지불이 고객 4000에 대해 Fabrikam에 전기됩니다

| 거래처                        | 차변 금액 | 대변 금액 |
|--------------------------------|--------------|---------------|
| 현금(Fabrikam)                | 75.00        |               |
| 수취 계정(Fabrikam) |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 지불은 Fabrikam West 송장 및 Fabrikam East 대변표로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액 | 대변 금액 |
|-----------------------------------|--------------|---------------|
| Fabrikam East(Fabrikam)에서 발생 | 25.00        |               |
| 수취 계정(Fabrikam)    |              | 25.00         |
| 수취 계정(Fabrikam)    | 100.00       |               |
| Fabrikam West(Fabrikam)로 발생   |              | 100.00        |

**Fabrikam East 전기**

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 수취 계정(Fabrikam East) | 25.00        |               |
| Fabrikam(Fabrikam East)으로 발생     |              | 25.00         |

**Fabrikam West 전기**

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| Fabrikam (Fabrikam West)에서 발생   | 100.00       |               |
| 수취 계정(Fabrikam West) |              | 100.00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>예 6: 기본 결제가 없는 고객 대변표
Fabrikam은 고객 4000인 Northwind Traders로부터 75.00의 지불을 받습니다. 지불은 Fabrikam West 고객 10000에 대한 미결 송장 및 Fabrikam East 고객 4000에 대한 미결 대변표로 정산됩니다. 지불은 **거래 정산** 페이지에서 기본 지불로 선택되지 않습니다.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>송장이 고객 10000에 대해 Fabrikam West에 전기됩니다

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 수취 계정(Fabrikam West) | 100.00       |               |
| 판매(Fabrikam West)               |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>대변표가 고객 4000에 대해 Fabrikam East에 전기됩니다

| 거래처                             | 차변 금액 | 대변 금액 |
|-------------------------------------|--------------|---------------|
| 판매 반품(Fabrikam East)       | 25.00        |               |
| 수취 계정(Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>지불이 고객 4000에 대해 Fabrikam에 전기됩니다

| 거래처                        | 차변 금액 | 대변 금액 |
|--------------------------------|--------------|---------------|
| 현금(Fabrikam)                | 75.00        |               |
| 수취 계정(Fabrikam) |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 지불은 Fabrikam West 송장 및 Fabrikam East 대변표로 정산됩니다

**Fabrikam 전기**

| 거래처                         | 차변 금액 | 대변 금액 |
|---------------------------------|--------------|---------------|
| 수취 계정(Fabrikam)  | 75.00        |               |
| Fabrikam West(Fabrikam)로 발생 |              | 75.00         |

**Fabrikam East 전기**

| 거래처                              | 차변 금액 | 대변 금액 |
|--------------------------------------|--------------|---------------|
| 수취 계정(Fabrikam East)  | 25.00        |               |
| Fabrikam West(Fabrikam East)로 발생 |              | 25.00         |

**Fabrikam West 전기**

| 거래처                                | 차변 금액 | 대변 금액 |
|----------------------------------------|--------------|---------------|
| Fabrikam (Fabrikam West)에서 발생      | 75.00        |               |
| 수취 계정(Fabrikam West)    |              | 75.00         |
| Fabrikam East(Fabrikam West)에서 발생 | 25.00        |               |
| 수취 계정(Fabrikam West)    |              | 25.00         |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]