---
title: 공급업체 지불에서 계산된 할인보다 더 많이 받기
description: 이 문서에서는 원래 송장에 제공되는 할인보다 많은 금액에 대해 현금 할인이 적용되는 시나리오를 안내합니다. 이 시나리오는 조직이 송장에 대해 더 적은 금액을 지불하기로 공급업체와 합의할 때 발생할 수 있습니다.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52e18e75cfad34829dc78486d2b78b8e4211bb948bc5ddd0be85552bd914010b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450358"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a>공급업체 지불에서 계산된 할인보다 더 많이 받기

[!include [banner](../includes/banner.md)]

이 문서에서는 원래 송장에 제공되는 할인보다 많은 금액에 대해 현금 할인이 적용되는 시나리오를 안내합니다. 이 시나리오는 조직이 송장에 대해 더 적은 금액을 지불하기로 공급업체와 합의할 때 발생할 수 있습니다. 

공급업체 3051은 송장을 7일 이내에 지불하는 경우 Fabrikam에 4%의 현금 할인을 제공합니다. April은 6월 29일에 1,000.00에 대한 송장을 입력합니다. 공급업체는 April이 송장에 제공되는 기본 할인 40.00 대신 60.00의 할인을 받을 수 있도록 합니다. April은 지급 계정 지불 분개장을 사용하여 일회성 지불을 기록합니다. 그녀는 지불을 위해 공급업체를 입력한 다음 **거래 정산** 페이지를 엽니다. 그녀는 송장을 표시하고 **현금 할인 금액** 필드의 값을 **60.00** 으로 변경합니다.

| 표시     | 현금 할인 사용 | 전표   | 거래처 | 날짜      | 마감일  | 송장 | 트랜잭션 통화 금액 | 통화 | 정산할 금액 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| 선택됨 | 기본            | Inv-10040 | 3051    | 2015-06-29 | 2015-07-29 | 10040   | 1,000.00                       | USD      | 940.00           |

할인 정보는 **트랜잭션 결제** 페이지 하단에 표시됩니다.

| 필드                        | 값     |
|------------------------------|-----------|
| 현금 할인 날짜           | 2015-07-12 |
| 현금 할인 금액         | 60.00     |
| 현금 할인 사용            | 기본    |
| 현금 할인 적용됨          | 0.00      |
| 적용할 현금 할인 금액 | 60.00     |

April은 지불 분개장을 게시합니다. 송장은 940.00의 지불과 60.00의 할인을 사용하여 완전히 정산됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]