---
title: 크레딧 노트에 대한 할인이 있는 부분 공급업체 결제 정산
description: 이 문서에서는 크레딧 메모가 송장에 대해 결제되는 시나리오를 설명합니다.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 553150a59d132bb1d8b563e03456995cbc8d2be5f36bab0c1fe6b8bbbf77dce1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450376"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-credit-notes"></a>크레딧 노트에 대한 할인이 있는 부분 공급업체 결제 정산

[!include [banner](../includes/banner.md)]

이 문서에서는 크레딧 메모가 송장에 대해 결제되는 시나리오를 설명합니다.

Fabrikam의 공급업체는 크레딧 메모에 대해 현금 할인을 제공합니다. 공급업체 3050은 14일 이내에 송장이 결제되면 Fabrikam이 1%의 현금 할인을 받을 수 있도록 합니다.

## <a name="invoice-and-credit-memo"></a>송장 및 크레딧 메모
6월 29일, April은 공급업체 3050에 대한 1,000.00의 송장을 생성합니다. 7월 2일, 그녀는 200.00의 크레딧 노트를 만듭니다. **공급업체** 페이지에서 April이 **트랜잭션 정산** 페이지를 엽니다. **트랜잭션 정산** 페이지를 사용하여 결제하기 위해 크레딧 메모와 송장을 모두 표시할 수 있습니다. 2.00의 할인은 크레딧 노트에 계산됩니다. 따라서 크레딧 메모의 총 가치는 198.00으로 줄어듭니다.

| 표시                     | 현금 할인 사용 | 바우처   | 거래처 | 날짜      | 마감일  | 송장 | 트랜잭션 통화 금액 | 통화 | 정산할 금액 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| 선택됨                 | 기본            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070   | -1,000.00                      | USD      | -990.00          |
| 선택 및 강조 표시됨 | 기본            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 |         | 200.00                         | USD      | 198.00           |

크레딧 노트에 대한 할인 정보는 **열린 트랜잭션 결제** 페이지의 하단에 표시됩니다.

| 필드                        | 값     |
|------------------------------|-----------|
| 현금 할인 날짜           | 7/13/2015 |
| 현금 할인 금액         | 2.00      |
| 현금 할인 사용            | 기본    |
| 현금 할인 적용됨          | 0.00      |
| 적용할 현금 할인 금액 | 2.00      |

April이 **게시** 를 클릭합니다. 그런 다음 완료된 정산을 검토합니다. April은 198.00의 크레딧 노트가 적용되었고 2.00의 할인이 이루어진 것을 알 수 있습니다. 따라서 총계는 200.00입니다.

| 표시                     | 현금 할인 사용 | 바우처   | 거래처 | 날짜      | 마감일  | 송장  | 트랜잭션 통화 금액 | 통화 | 정산할 금액 |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| 선택 및 강조 표시됨 | 기본            | Inv-10070 | 3050    | 6/29/2015 | 7/29/2015 | 10070    | -1,000.00                      | USD      | -200.00          |
| 선택됨                 | 기본            | CR-10070  | 3050    | 7/2/2015  | 7/29/2015 | CR-10070 | 200.00                         | USD      | 198.00           |

April은 **모든 공급업체** 페이지에서 공급업체를 선택한 다음 작업 창에서 **트랜잭션** 을 클릭하여 **공급업체 트랜잭션** 페이지에서 공급업체 트랜잭션을 검토할 수 있습니다. 이 페이지에서 April은 송장의 잔액이 -800.00인 것을 봅니다. 또 198.00의 크레딧 노트와 2.00의 할인을 확인합니다.

| 바우처    | 트랜잭션 유형 | 날짜      | 송장 | 트랜잭션 통화 차변 금액 | 트랜잭션 통화 크레딧 금액 | 잔액 | 통화 |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | 송장          | 6/29/2015 | 10070   |                                      | 1,000.00                              | -800.00 | USD      |
| Inv-10071  |                  | 7/2/2015  | CR10071 | 200.00                               |                                       | 0.00    | USD      |
| DISC-10071 |  현금 할인   | 7/2/2015  |         | 2.00                                 |                                       | 0.00    | USD      |
| DISC-10071 |  현금 할인   | 7/2/2015  |         |                                      | 2.00                                  | 0.00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]