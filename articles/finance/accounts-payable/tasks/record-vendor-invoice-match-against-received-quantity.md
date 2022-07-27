---
title: 공급업체 송장을 기록하고 수령 수량과 일치
description: 구매 주문의 상품 또는 서비스에 대해 공급업체로부터 송장을 받는 경우 비즈니스 프로세스에서 해당 송장의 지불 승인을 받기 전에 상품 또는 서비스를 받아야 할 수 있습니다.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a3f1463821a43af0d8d5f15225944b080414e4c
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451555"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>공급업체 송장을 기록하고 수령 수량과 일치

[!include [banner](../../includes/banner.md)]

구매 주문의 상품 또는 서비스에 대해 공급업체로부터 송장을 받는 경우 비즈니스 프로세스에서 해당 송장의 지불 승인을 받기 전에 상품 또는 서비스를 받아야 할 수 있습니다. 시작하기 전에 송장 매칭 구성 키가 선택되어 있는지 확인합니다. 

**지급 계정 매개 변수** 페이지에서 **송장 일치 유효성 검사 사용** 옵션을 선택하고 **불일치가 있는 송장 게시** 필드가 **승인 필요** 로 설정되었으며 **라인 일치 정책** 필드가 **3방향 일치** 로 설정되었는지 확인합니다.

이 절차는 USMF 데모 회사를 사용합니다. 지급 계정 관리자 또는 회계 관리자 역할이 이러한 단계를 수행합니다.


## <a name="create-a-purchase-order"></a>구매 주문 만들기
1. 모든 구매 주문으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **공급업체 계정** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
4. **공급업체 계정** 필드에 값을 입력합니다.
5. **확인** 을 클릭합니다.
6. **라인 추가** 를 클릭합니다.
7. **항목 번호** 필드에 값을 입력합니다.
8. 작업 창에서 **구매** 를 클릭합니다.
9. **확인** 을 클릭합니다.

## <a name="post-a-product-receipt"></a>제품 영수증 전기
1. 작업 창에서 **수령** 을 클릭합니다.
2. **제품 영수증** 을 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
4. **제품 영수증** 필드에 값을 입력합니다.
5. **확인** 을 클릭합니다.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>공급업체 송장을 기록하고 제품 영수증과 매칭
1. 작업 창에서 **송장** 을 클릭합니다.
2. **송장** 을 클릭합니다.
3. **번호** 필드에 값을 입력합니다.
4. **기본값: 주문 수량** 을 클릭하여 드롭 대화 상자를 엽니다.
5. **라인의 기본 수량** 필드에서 옵션을 선택합니다.
6. **확인** 을 클릭합니다.
7. **예** 를 클릭합니다.
8. **제품 영수증 매치** 를 클릭합니다.
9. **확인** 을 클릭합니다.
10. 작업 창에서 **검토** 를 클릭합니다.
11. **일치 세부 정보** 를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
