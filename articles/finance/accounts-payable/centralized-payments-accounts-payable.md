---
title: 지급 계정에 대한 중앙 집중식 지불
description: 여러 법인을 포함하는 조직은 모든 지불을 처리하는 단일 법인을 사용하여 지불을 생성하고 관리할 수 있습니다. 따라서 동일한 지불이 여러 법인에 입력될 필요가 없습니다. 이 토픽에서는 다양한 시나리오에서 중앙 집중식 지불에 대한 전기가 처리되는 방법을 보여주는 예를 제공합니다.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df0d2178d1ebd3dcb154e2c4f7821a4007da55d4
ms.sourcegitcommit: 5033d42a2aac852916d726e40bd98a164d1a837d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "8451630"
---
# <a name="centralized-payments-for-accounts-payable"></a>지급 계정에 대한 중앙 집중식 지불

[!include [banner](../includes/banner.md)]

여러 법인을 포함하는 조직은 모든 지불을 처리하는 단일 법인을 사용하여 지불을 생성하고 관리할 수 있습니다. 따라서 동일한 지불이 여러 법인에 입력될 필요가 없습니다. 이 토픽에서는 다양한 시나리오에서 중앙 집중식 지불에 대한 전기가 처리되는 방법을 보여주는 예를 제공합니다.

중앙 집중식 지불 조직에는 운영을 위한 많은 법인이 있으며 각 운영 법인은 자체 공급업체 송장을 관리합니다. 모든 운영 법인에 대한 지불은 지불의 법인으로 알려진 단일 법인에서 생성됩니다. 정산 과정에서 적용 가능한 외상매입금 및 외상매출금 거래가 생성됩니다. 실현 손익 거래를 받는 조직의 법인과 회사 간 지급과 관련된 현금 할인 거래를 처리하는 방법을 지정할 수 있습니다. 중앙 집중식 지불 분개장 라인에서 **계정 유형** 은 공급업체로 설정되어야 합니다. **상쇄 계정 유형** 은 은행 또는 원장으로 설정해야 합니다. 은행 계좌는 현재 회사에 있어야 합니다. 

다음 예는 다양한 시나리오에서 전기가 처리되는 방법을 보여줍니다. 이러한 모든 예에 대해 다음 구성이 가정됩니다.

-   법인은 Fabrikam, Fabrikam East 및 Fabrikam West입니다. 지불은 Fabrikam에서 이루어집니다.
-   **회사 간 회계** 페이지의 **현금 할인 후** 필드가 **송장의 법인** 으로 설정됩니다.
-   **회사 간 회계** 페이지의 **환전 후 손익** 필드가 **지불의 법인** 으로 설정됩니다.
-   공급업체인 Fourth Coffee는 각 법인의 공급업체로 설정됩니다. 다양한 법인의 공급업체는 동일한 전체 주소록 ID를 공유하므로 동일한 공급업체로 식별됩니다.

| 디렉터리 ID | 공급 업체 계정 | 이름          | 법인  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam East |
| 1050         | 3004           | Fourth Coffee | Fabrikam West |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>예 1: 다른 법인 송장의 공급업체 지불
Fabrikam East에는 공급업체 계정 100인 Fourth Coffee에 대한 미결 송장이 있습니다. Fabrikam은 Fabrikam 공급업체 계정 3004인 Fourth Coffee에 지불을 입력하고 전기합니다. 미결 인보이스로 지불이 정산됩니다.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>송장이 공급업체 100에 대해 Fabrikam East에 전기됩니다

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 비용(Fabrikam East)          | 600.00       |               |
| 지급 계정(Fabrikam East) |              | 600.00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>지불이 생성되어 공급업체 3004에 대해 Fabrikam에 전기됩니다

| 거래처                     | 차변 금액 | 대변 금액 |
|-----------------------------|--------------|---------------|
| 지급 계정(Fabrikam) | 600.00       |               |
| 현금(Fabrikam)             |              | 600.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액 | 대변 금액 |
|-----------------------------------|--------------|---------------|
| Fabrikam East(Fabrikam)에서 발생 | 600.00       |               |
| 지급 계정(Fabrikam)       |              | 600.00        |

**Fabrikam East 전기**

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 지급 계정(Fabrikam East) | 600.00       |               |
| Fabrikam(Fabrikam East)으로 발생  |              | 600.00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>예 2: 현금 할인이 있는 다른 법인 송장의 공급업체 지불
Fabrikam East에는 공급업체 100인 Fourth Coffee에 대한 미결 송장이 있습니다. 송장에는 20.00 현금 할인이 가능합니다. Fabrikam은 Fabrikam 공급업체 3004인 Fourth Coffee에 대해 580.00의 지불을 입력하고 전기합니다. 지불은 미결 Fabrikam East 송장으로 정산됩니다. 현금 할인은 송장의 법인 Fabrikam East에 전기됩니다.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Fabrikam East 공급업체 100에 대한 송장이 Fabrikam East에 전기됩니다

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 비용(Fabrikam East)          | 600.00       |               |
| 지급 계정(Fabrikam East) |              | 600.00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>지불이 생성되어 Fabrikam 공급업체 3004에 대해 Fabrikam에 전기됩니다

| 거래처                     | 차변 금액 | 대변 금액 |
|-----------------------------|--------------|---------------|
| 지급 계정(Fabrikam) | 580.00       |               |
| 현금(Fabrikam)             |              | 580.00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액 | 대변 금액 |
|-----------------------------------|--------------|---------------|
| Fabrikam East(Fabrikam)에서 발생 | 580.00       |               |
| 지급 계정(Fabrikam)       |              | 580.00        |

**Fabrikam East 전기**

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 지급 계정(Fabrikam East) | 580.00       |               |
| Fabrikam(Fabrikam East)으로 발생  |              | 580.00        |
| 지급 계정(Fabrikam East) | 20.00        |               |
| 현금 할인(Fabrikam East)    |              | 20.00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>예 3: 실현된 환율 손실이 있는 다른 법인 송장의 공급업체 지불
Fabrikam East에는 공급업체 100인 Fourth Coffee에 대한 미결 송장이 있습니다. Fabrikam은 Fabrikam 공급업체 3004인 Fourth Coffee에 대해 지불을 입력하고 전기합니다. 지불은 미결 Fabrikam East 송장으로 정산됩니다. 정산 과정에서 환차손 거래가 발생합니다.

-   송장 날짜 기준 유로(EUR)-미국 달러(USD) 환율: 1.2062
-   결제일 기준 EUR-USD 환율: 1.2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Fabrikam East 공급업체 100에 대한 송장이 Fabrikam East에 전기됩니다

| 거래처                          | 차변 금액            | 대변 금액           |
|----------------------------------|-------------------------|-------------------------|
| 비용(Fabrikam East)          | 600.00 EUR/723.72 USD |                         |
| 지급 계정(Fabrikam East) |                         | 600.00 EUR/723.72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>지불이 생성되어 Fabrikam 공급업체 3004에 대해 Fabrikam에 전기됩니다

| 거래처                     | 차변 금액            | 대변 금액           |
|-----------------------------|-------------------------|-------------------------|
| 지급 계정(Fabrikam) | 600.00 EUR/736.62 USD |                         |
| 현금(Fabrikam)             |                         | 600.00 EUR/736.62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액            | 대변 금액           |
|-----------------------------------|-------------------------|-------------------------|
| Fabrikam East(Fabrikam)에서 발생 | 600.00 EUR/736.62 USD |                         |
| 지급 계정(Fabrikam)       |                         | 600.00 EUR/736.62 USD |
| 실현 손실(Fabrikam)          | 0.00 EUR/12.90 USD    |                         |
| Fabrikam East(Fabrikam)에서 발생 |                         | 0.00 EUR/12.90 USD    |

**Fabrikam East 전기**

| 거래처                          | 차변 금액            | 대변 금액           |
|----------------------------------|-------------------------|-------------------------|
| 지급 계정(Fabrikam East) | 600.00 EUR/736.62 USD |                         |
| Fabrikam(Fabrikam East)으로 발생  |                         | 600.00 EUR/736.62 USD |
| Fabrikam(Fabrikam East)으로 발생  | 0.00 EUR/12.90 USD    |                         |
| 지급 계정(Fabrikam East) |                         | 0.00 EUR/12.90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>예 4: 현금 할인 및 실현된 환율 손실이 있는 다른 법인 송장의 공급업체 지불
Fabrikam East에는 공급업체 100인 Fourth Coffee에 대한 미결 송장이 있습니다. 송장에 사용 가능한 현금 할인이 있고 판매세 거래가 생성됩니다. Fabrikam은 Fabrikam 공급업체 3004인 Fourth Coffee에 대해 지불을 전기합니다. 지불은 미결 Fabrikam East 송장으로 정산됩니다. 정산 과정에서 환차손 거래가 발생합니다. 현금 할인은 송장의 법인(Fabrikam East)에 전기되고 환차손은 지불 법인(Fabrikam)에 전기됩니다.

-   송장 날짜 기준 EUR-USD 환율: 1.2062
-   결제일 기준 EUR-USD 환율: 1.2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>송장이 전기되고 Fabrikam East에서 공급업체 100에 대한 세금 거래가 생성됩니다

| 거래처                          | 차변 금액            | 대변 금액           |
|----------------------------------|-------------------------|-------------------------|
| 비용(Fabrikam East)          | 564.07 EUR/680.38 USD |                         |
| 판매세(Fabrikam East)        | 35.93 EUR/43.34 USD   |                         |
| 지급 계정(Fabrikam East) |                         | 600.00 EUR/723.72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>지불이 생성되어 공급업체 3004에 대해 Fabrikam에 전기됩니다

| 거래처                     | 차변 금액            | 대변 금액           |
|-----------------------------|-------------------------|-------------------------|
| 지급 계정(Fabrikam) | 588.72 EUR/722.77 USD |                         |
| 현금(Fabrikam East)        |                         | 588.72 EUR/722.77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Fabrikam 지불은 Fabrikam East 송장으로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액            | 대변 금액           |
|-----------------------------------|-------------------------|-------------------------|
| Fabrikam East(Fabrikam)에서 발생 | 588.72 EUR/722.77 USD |                         |
| 지급 계정(Fabrikam)       |                         | 588.72 EUR/722.77 USD |
| 실현 손실(Fabrikam)          | 0.00 EUR/12.66 USD    |                         |
| Fabrikam East(Fabrikam)에서 발생 |                         | 0.00 EUR/12.66 USD    |

**Fabrikam East 전기**

| 거래처                          | 차변 금액            | 대변 금액           |
|----------------------------------|-------------------------|-------------------------|
| 지급 계정(Fabrikam East) | 588.72 EUR/722.77 USD |                         |
| Fabrikam(Fabrikam East)으로 발생  |                         | 588.72 EUR/722.77 USD |
| Fabrikam(Fabrikam East)으로 발생   | 0.00 EUR/12.66 USD    |                         |
| 지급 계정(Fabrikam East) |                         | 0.00 EUR/12.66 USD    |
| 지급 계정(Fabrikam East) | 11.28 EUR/13.61 USD   |                         |
| 현금 할인(Fabrikam East)    |                         | 11.28 EUR/13.61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>예 5: 기본 지불이 포함된 공급업체 대변표
Fabrikam은 공급업체 3004인 Fourth Coffee에 대해 75.00의 지불을 생성합니다. 지불은 Fabrikam West 공급업체 3004에 대한 미결 송장 및 Fabrikam East 공급업체 100에 대한 미결 대변표로 정산됩니다. 지불은 **거래 정산** 페이지에서 기본 지불로 선택됩니다.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>송장이 공급업체 3004에 대해 Fabrikam West에 전기됩니다

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 비용(Fabrikam West)          | 100.00       |               |
| 지급 계정(Fabrikam West) |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>대변표가 공급업체 100에 대해 Fabrikam East에 전기됩니다

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 지급 계정(Fabrikam East) | 25.00        |               |
| 구매 반품(Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>지불이 공급업체 3004에 대해 Fabrikam에 전기됩니다

| 거래처                     | 차변 금액 | 대변 금액 |
|-----------------------------|--------------|---------------|
| 지급 계정(Fabrikam) | 75.00        |               |
| 현금(Fabrikam)             |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 지불은 Fabrikam West 송장 및 Fabrikam East 대변표로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액 | 대변 금액 |
|-----------------------------------|--------------|---------------|
| 지급 계정(Fabrikam)       | 25.00        |               |
| Fabrikam East(Fabrikam)로 발생   |              | 25.00         |
| Fabrikam West(Fabrikam)에서 발생 | 100.00       |               |
| 지급 계정(Fabrikam)       |              | 100.00        |

**Fabrikam East 전기**

| 거래처                           | 차변 금액 | 대변 금액 |
|-----------------------------------|--------------|---------------|
| Fabrikam(Fabrikam East)에서 발생 | 25.00        |               |
| 지급 계정(Fabrikam East)  |              | 25.00         |

**Fabrikam West 전기**

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 지급 계정(Fabrikam West) | 100.00       |               |
| Fabrikam(Fabrikam West)으로 발생  |              | 100.00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>예 6: 기본 지불이 없는 공급업체 대변표
Fabrikam은 공급업체 3004인 Fourth Coffee에 대해 75.00의 지불을 생성합니다. 지불은 Fabrikam West 공급업체 3004에 대한 미결 송장 및 Fabrikam East 공급업체 100에 대한 미결 대변표로 정산됩니다. 지불은 **거래 정산** 페이지에서 기본 지불로 선택되지 않습니다.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>송장이 공급업체 3004에 대해 Fabrikam West에 전기됩니다

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 비용(Fabrikam West)          | 100.00       |               |
| 지급 계정(Fabrikam West) |              | 100.00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>대변표가 공급업체 100에 대해 Fabrikam East에 전기됩니다

| 거래처                          | 차변 금액 | 대변 금액 |
|----------------------------------|--------------|---------------|
| 지급 계정(Fabrikam East) | 25.00        |               |
| 구매 반품(Fabrikam East) |              | 25.00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>지불이 공급업체 3004에 대해 Fabrikam에 전기됩니다

| 거래처                     | 차변 금액 | 대변 금액 |
|-----------------------------|--------------|---------------|
| 지급 계정(Fabrikam) | 75.00        |               |
| 현금(Fabrikam)             |              | 75.00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Fabrikam 지불은 Fabrikam West 송장 및 Fabrikam East 대변표로 정산됩니다

**Fabrikam 전기**

| 거래처                           | 차변 금액 | 대변 금액 |
|-----------------------------------|--------------|---------------|
| Fabrikam West(Fabrikam)에서 발생 | 75.00        |               |
| 지급 계정(Fabrikam)       |              | 75.00         |

**Fabrikam East 전기**

| 거래처                                | 차변 금액 | 대변 금액 |
|----------------------------------------|--------------|---------------|
| Fabrikam West(Fabrikam East)에서 발생 | 25.00        |               |
| 지급 계정(Fabrikam East)       |              | 25.00         |

**Fabrikam West 전기**

| 거래처                              | 차변 금액 | 대변 금액 |
|--------------------------------------|--------------|---------------|
| 지급 계정(Fabrikam West)     | 75.00        |               |
| Fabrikam(Fabrikam West)으로 발생      |              | 75.00         |
| 지급 계정(Fabrikam West)     | 25.00        |               |
| Fabrikam East(Fabrikam West)로 발생 |              | 25.00         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
