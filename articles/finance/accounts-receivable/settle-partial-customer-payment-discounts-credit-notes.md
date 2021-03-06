---
title: 크레딧 노트에 대한 할인이 있는 부분 고객 결제 정산
description: 이 문서에서는 원본 송장에 현금 할인도 포함되어 있을 때 크레딧 노트에 현금 할인을 적용하는 시나리오를 설명합니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6476fed0ac10888c51266128f950fc0e1418b13c743894ab0992d051e733c4e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450427"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>크레딧 노트에 대한 할인이 있는 부분 고객 결제 정산

[!include [banner](../includes/banner.md)]

이 문서에서는 원본 송장에 현금 할인도 포함되어 있을 때 크레딧 노트에 현금 할인을 적용하는 시나리오를 설명합니다. 

Fabrikam은 고객이 부분 결제 시 현금 할인 혜택을 받을 수 있도록 하고 있으며, 크레딧 노트(크레딧 메모)도 받을 수 있습니다. 고객이 현금 할인을 받은 송장에 대해 크레딧 노트를 발행할 때 크레딧 노트에 현금 할인을 적용할 수 있습니다. 전체 금액에 대해 신용을 제공하는 대신 고객이 가져간 현금 할인율을 제외한 금액에 대해 고객의 잔액을 신용할 수 있습니다. 정산 매개 변수는 **수취 계정 매개 변수** 페이지에 있습니다.

## <a name="invoice-and-credit-note"></a>송장 및 크레딧 노트
고객 4035는 1,000.00에 대한 송장과 100.00에 대한 크레딧 노트를 가지고 있습니다. 각 문서는 14일 이내에 지불하면 1% 할인이 적용됩니다. Annie는 **고객 트랜잭션** 페이지에서 이 정보를 볼 수 있습니다.

| 바우처    | 트랜잭션 유형 | 날짜      | 송장  | 트랜잭션 통화 차변 금액 | 트랜잭션 통화 크레딧 금액 | 잔액  | 통화 |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | 송장          | 6/28/2015 | 10050    | 1,000.00                             |                                       | 1,000.00 | USD      |
| CCRN-10050 | 크레딧 노트      | 6/28/2015 | CR-10050 |                                      | 100.00                                | -100.00  | USD      |

## <a name="settle-a-credit-note-with-an-invoice"></a>송장으로 크레딧 노트 정산
**고객 트랜잭션** 페이지에서 Annie가 **트랜잭션 정산** 페이지를 엽니다. Arnie는 **트랜잭션 정산** 페이지를 사용하여 송장과 크레딧 노트를 결제할 수 있습니다. 결제 과정의 일부로, Arnie는 현금 할인 날짜와 금액을 봅니다. Annie는 두 개의 문서에 표시를 한 다음 **게시** 를 클릭하여 트랜잭션을 결제합니다. Fabrikam은 신용 메모에 대한 할인을 허용하기 때문에 신용 메모에는 -1.00의 할인이 있습니다.

| 표시     | 현금 할인 사용 | 바우처    | 거래처 | 날짜      | 마감일  | 송장  | 트랜잭션 통화 금액 | 통화 | 정산할 금액 |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| 선택됨 | 기본            | FTI-10050  | 4035    | 6/28/2015 | 7/28/2015 | 10050    | 1,000.00                       | USD      | 990.00           |
| 선택됨 | 기본            | CCRN-10050 | 4035    | 6/28/2015 | 7/28/2015 | CR-10050 | -100.00                        | USD      | -99.00           |

할인 정보는 **트랜잭션 결제** 페이지 하단에 표시됩니다.

- **현금 할인 날짜**: 7/12/2015 
- **현금 할인 금액**: -1.00     
- **현금 할인 사용**: 기본    
- **현금 할인 적용**: 0.00      
- **현금 할인 금액**: -1.00     

정산 금액은 100.00이며, 99.00과 1.00의 할인을 포함합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]