---
title: 지급 계정의 송장 및 주요 데이터 감사
description: 이 토픽에서는 지급 계정의 송장 및 주요 데이터를 감사하는 방법을 보여줍니다.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f49f8c87f628d68f2c7f355b93cdf5e0a9403251
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451261"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>지급 계정의 송장 및 주요 데이터 감사

[!include [banner](../../includes/banner.md)]

구매 주문의 상품 또는 서비스에 대해 공급업체로부터 송장을 받는 경우 비즈니스 프로세스에서 해당 송장의 지불 승인을 받기 전에 상품 또는 서비스를 받아야 할 수 있습니다. 시작하기 전에 송장 매칭 구성 키가 선택되어 있는지 확인합니다. 

**지급 계정 매개 변수** 페이지에서 송장 매칭 확인 활성화 옵션이 선택되어 있고, **불일치가 있는 송장 전기** 필드가 **승인 필요** 로 설정되어 있으며 **라인 매칭 정책** 필드는 **3방향 매칭** 으로 설정되어 있는지 확인합니다.

이 절차는 USMF 데모 회사를 사용합니다. 지급 계정 관리자 또는 회계 관리자 역할이 이러한 단계를 수행합니다.


## <a name="create-a-purchase-order"></a>구매 주문 만들기
1. **모든 구매 주문** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **공급업체 계정** 필드에 값을 입력합니다.
4. **확인** 을 클릭합니다.
5. **라인 추가** 를 클릭합니다.
6. **항목 번호** 필드에 값을 입력합니다.
7. 작업 창에서 **구매** 를 클릭합니다.
8. **확인** 을 클릭합니다.

## <a name="post-a-product-receipt"></a>제품 영수증 전기
1. 작업 창에서 **수령** 을 클릭합니다.
2. **제품 영수증** 을 클릭합니다.
3. **제품 영수증** 필드에 값을 입력합니다.
4. **확인** 을 클릭합니다.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>공급업체 송장을 기록하고 제품 영수증과 매칭
1. 작업 창에서 **송장 > 송장** 을 클릭합니다.
2. **번호** 필드에 값을 입력합니다.
3. **기본값: 주문 수량** 을 클릭하여 드롭 대화 상자를 엽니다.
4. **라인의 기본 수량** 필드에서 옵션을 선택합니다.
5. **확인** 을 클릭합니다.
6. **예** 를 클릭합니다.
7. **제품 영수증 매치** 를 클릭합니다.
8. **확인** 을 클릭합니다.
9. 작업 창에서 **검토** 를 클릭합니다.
10. **세부 정보 매칭** 을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
