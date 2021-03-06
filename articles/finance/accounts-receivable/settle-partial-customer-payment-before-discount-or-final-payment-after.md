---
title: 할인일 이전 부분 결제를 할인일 이후 최종 결제로 정산
description: 이 기사에서는 고객의 송장에 대한 결제 정산 효과에 대해 설명합니다. 이 시나리오는 총계정원장이 아닌 하위 원장의 효과에 초점을 맞춥니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10ba8d59855b60b3d05b4c6b44c98905e10487ecdcf7bc459acca73c12bc72d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450430"
---
# <a name="settle-partial-payment-before-discount-date-with-final-payment-after-discount-date"></a>할인일 이전 부분 결제를 할인일 이후 최종 결제로 정산

[!include [banner](../includes/banner.md)]

이 기사에서는 고객의 송장에 대한 결제 정산 효과에 대해 설명합니다. 이 시나리오는 총계정원장이 아닌 하위 원장의 효과에 초점을 맞춥니다.

Fabrikam이 고객 4027에게 상품을 판매합니다. Fabrikam은 송장이 14일 이내에 결제되면 1%의 현금 할인을 제공합니다. 송장은 30일 이내에 결제되어야 합니다. Fabrikam은 부분 결제 시 현금 할인도 제공합니다. 정산 매개 변수는 **수취 계정 매개 변수** 페이지에 있습니다.

## <a name="invoice"></a>송장
6월 25일, Arnie는 고객 4027의 1,000.00에 대한 송장을 입력하고 게시합니다. Annie는 **고객** 페이지의 **트랜잭션** 버튼을 사용하여 이 송장을 볼 수 있습니다.

| 바우처   | 트랜잭션 유형 | 날짜      | 송장 | 트랜잭션 통화 차변 금액 | 트랜잭션 통화 크레딧 금액 | 잔액  | 통화 |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | 송장          | 6/25/2015 | 10020   | 1,000.00                             |                                       | 1,000.00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>현금 할인 날짜 이전 부분 결제
7월 2일에 고객 4027이 송장에 대해 297.00의 부분 결제를 합니다. Fabrikam이 부분 결제에 대해 현금 할인을 제공하고, 부분 결제가 현금 할인 날짜 이전에 이뤄지기 때문에 현금 할인이 가능합니다. 따라서 고객 4027은 3.00의 현금 할인을 받습니다. Arnie는 결제 분개장을 사용하여 고객 4027의 결제를 기록합니다. 그런 다음 Arnie는 **트랜잭션 결제** 페이지를 열어 송장을 결제용으로 표시할 수 있습니다.

| 표시     | 현금 할인 사용 | 바우처   | 거래처 | 날짜      | 마감일  | 송장 | 트랜잭션 통화 차변 금액 | 통화 | 정산할 금액 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| 선택됨 | 기본            | FTI-10020 | 4027    | 6/25/2015 | 7/25/2015 | 10020   | 1,000.00                             | USD      | 297.00           |

할인 정보는 **열린 트랜잭션 정산** 페이지 하단에 표시됩니다. **정산할 금액** 값을 297.00으로 변경하지 않으면 표시되는 **현금 할인 금액** 값이 달라집니다. 그러나 정산 시 자동으로 **정산할 금액**이 조정되므로 결제 시 3.00은 현금 할인으로 간주됩니다.

| 필드                        | 값     |
|------------------------------|-----------|
| 현금 할인 날짜           | 7/09/2015 |
| 현금 할인 금액         | 10.00     |
| 현금 할인 사용            | 기본    |
| 현금 할인 적용됨          | 0.00      |
| 적용할 현금 할인 금액 | 3.00      |

Annie가 이 결제를 게시합니다. 송장의 잔액은 현재 700.00입니다. 고객에게 다음과 같은 트랜잭션을 볼 수 있습니다.

| 바우처    | 트랜잭션 유형 | 날짜      | 송장 | 트랜잭션 통화 차변 금액 | 트랜잭션 통화 크레딧 금액 | 잔액 | 통화 |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | 송장          | 6/25/2015 | 10020   | 1,000.00                             |                                       | 700.00  | USD      |
| ARP-10020  |  결제         | 7/1/2015  |         |                                      | 297.00                                | 0.00    | USD      |
| DISC-10020 |  현금 할인   | 7/1/2015  |         |                                      | 3.00                                  | 0.00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>현금 할인 날짜 이후 남은 결제
할인 기간이 지난 7월 11일에 고객 4027이 이 송장의 나머지 금액을 결제합니다. **트랜잭션 정산** 페이지의 **예상 현금 할인** 필드에 할인 금액이 나타나지 않으며 **현금 할인 금액** 필드의 값은 **0.00** 입니다. 고객 4027이 나머지 700.00을 결제할 때 추가 할인은 받지 않습니다.

| 표시     | 현금 할인 사용 | 바우처   | 거래처 | 날짜      | 마감일  | 송장 | 트랜잭션 통화 차변 금액 | 통화 | 정산할 금액 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| 선택됨 | 기본            | FTI-10020 | 4027    | 6/25/2015 | 7/25/2015 | 10020   | 700.00                               | USD      | 700.00           |

할인 정보는 **열린 트랜잭션 정산** 페이지 하단에 표시됩니다.

| 필드                        | 값     |
|------------------------------|-----------|
| 현금 할인 날짜           | 7/09/2015 |
| 현금 할인 금액         | 0.00      |
| 현금 할인 사용            | 기본    |
| 현금 할인 적용됨          | 3.00      |
| 적용할 현금 할인 금액 | 0.00      |

Arnie가 **현금 할인 사용** 필드의 값을 **항상** 으로 변경하면 **부분 결제에 대한 현금 할인 계산** 설정이 재정의되고 현금 할인이 적용됩니다. 결제 금액은 693.00으로 변경되며, 현금 할인은 나머지 7.00입니다.

| 표시     | 현금 할인 사용 | 바우처   | 거래처 | 날짜      | 마감일  | 송장 | 트랜잭션 통화 차변 금액 | 트랜잭션 통화 크레딧 금액 | 통화 | 정산할 금액 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| 선택됨 | 항상            | FTI-10020 | 4027    | 6/25/2015 | 7/25/2015 | 10020   | 700.00                               |                                       | USD      | 693.00           |

할인 정보는 **열린 트랜잭션 정산** 페이지 하단에 표시됩니다.

| 필드                        | 값     |
|------------------------------|-----------|
| 현금 할인 날짜           | 7/09/2015 |
| 현금 할인 금액         | 7.00      |
| 현금 할인 사용            | 항상    |
| 현금 할인 적용됨          | 3.00      |
| 적용할 현금 할인 금액 | 7.00      |

Arnie가 **현금 할인 사용** 필드의 값을 **정상** 으로 다시 변경합니다. 이 고객에게 남은 현금 할인 7.00을 받지 못하게 하기 때문입니다. 그리고 Annie가 이 결제를 게시합니다. Annie가 **고객 트랜잭션** 페이지를 열 때, 송장의 잔액은 0.00입니다. 두 가지 결제가 있습니다. 하나는 297.00에 3.00 현금 할인이고 다른 하나는 700.00입니다.

| 바우처    | 트랜잭션 유형 | 날짜      | 송장 | 트랜잭션 통화 차변 금액 | 트랜잭션 통화 크레딧 금액 | 잔액 | 통화 |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | 송장          | 6/25/2015 | 10020   | 1,000.00                             |                                       | 0.00    | USD      |
| ARP-10020  |                  | 7/1/2015  |         |                                      | 297.00                                | 0.00    | USD      |
| DISC-10020 |                  | 7/1/2015  |         |                                      | 3.00                                  | 0.00    | USD      |
| ARP-10021  |                  | 7/11/2015 |         |                                      | 700.00                                | 0.00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]