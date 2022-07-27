---
title: 공급업체에 부분 금액 지불
description: 송장 금액보다 적은 금액을 공급업체에 지불하는 경우가 있습니다. 이 문서에서는 이 상황에 대처하기 위한 다양한 옵션을 설명합니다.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd7b7092e0d0baf48a805bbb0cefb0eb77e49946c6dbc44c9f954781ca1259e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450841"
---
# <a name="vendor-payments-for-a-partial-amount"></a>공급업체에 부분 금액 지불

[!include [banner](../includes/banner.md)]

송장 금액보다 적은 금액을 공급업체에 지불하는 경우가 있습니다. 이 문서에서는 이 상황에 대처하기 위한 다양한 옵션을 설명합니다. 사용할 수 있는 옵션은 비즈니스 요구 사항과 구성에 따라 다릅니다. 

## <a name="cash-discount-amounts"></a>현금 할인 금액

기한 전에 송장 금액을 지불하면 공급업체가 현금 할인을 제공할 수 있습니다. 예를 들어, 송장이 10일 이내에 지불될 경우 2% 현금 할인을 제공하려면 송장에 100.00을 입력합니다. 기한은 30일입니다. 지불 제안이 송장 선택 기준으로 현금 할인을 사용하고 현금 할인 날짜 또는 그 이전에 제안이 실행되면 송장이 지불 대상으로 선택되고 98.00에 대한 지불이 생성됩니다. 수동으로 만든 일회성 지불에 대해서도 현금 할인을 받을 수 있습니다.

## <a name="partial-payments-with-cash-discounts"></a>현금 할인이 포함된 부분 결제
부분 지불할 때 나중에 송장 금액을 완전히 지불하기 위해 부분 지불을 추가로 계획할 수 있습니다. 부분 지불 시 현금 할인을 받으려면 **지불 계정 매개 변수** 페이지에서 **부분 지불 시 현금 할인 계산** 옵션을 **예** 로 설정해야 합니다. 

예를 들어 송장 발행 후 10일 이내에 지불하면 2%의 현금 할인을 받을 수 있습니다. 100.00에 대한 송장이 게시됩니다. 10일 이내에 49.00을 지불하면 지불 분개장에 49.00의 출금을 입력합니다. **미결 거래 정산** 페이지에서 부분 지불을 하면 **받는 현금 할인** 필드에 **1.00** 이 표시됩니다. 

> [!NOTE] 
> 부분 결제를 입력하고 **정산할 금액** 필드에 송장 전체 금액을 그대로 두면 **받는 현금 할인** 필드가 자동으로 재계산됩니다.

## <a name="credit-notes-with-cash-discounts"></a>현금 할인이 포함된 대변표
송장에 기재된 품목 중 일부를 반환하고 대변표를 받을 수 있습니다. 원래 송장에 현금 할인이 적용된 경우 할인 금액을 차감하여 정확한 금액을 환불받을 수 있습니다. **지급 계정 매개 변수** 페이지에서 **대변표에 대한 현금 할인 계산** 옵션이 **예** 로 설정되어 있으면 대변표에 대한 할인이 자동으로 계산됩니다. 

예를 들어 송장 발행 후 10일 이내에 지불하면 2%의 현금 할인을 받을 수 있습니다. 100.00에 대한 송장이 게시됩니다. 상품을 반품하고 대변표를 받으면 대변표에도 정의된 2% 현금 할인과 함께 원래 송장의 전체 금액인 100.00에 대한 대변표를 입력할 수 있습니다.  **거래 정산** 페이지에서 대변표를 조회하면 **정산할 금액** 필드에 **98.00** 이 표시되고 **현금 할인 금액** 필드에 **-2.00** 이 표시됩니다. 할인 금액은 현금 할인 계정에 게시됩니다.

## <a name="overpaymentunderpayment-amounts"></a>초과 지불/과소 지불 금액
아직 지불해야 하는 금액이 매우 적은 경우 부분 지불할 수 있습니다. 예를 들어 공급업체 송장이 1,000.00이고 999.90을 지불했다고 가정하겠습니다. 잔액이 **지불 계정 매개 변수** 페이지에 초과 지불 또는 과소 지불로 지정한 금액보다 적을 경우, 차액이 자동으로 초과 지불/과소 지불 원장 계정에 게시됩니다.


자세한 내용은 [공급업체 지불 개요](../cash-bank-management/tasks/vendor-payment-overview.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]