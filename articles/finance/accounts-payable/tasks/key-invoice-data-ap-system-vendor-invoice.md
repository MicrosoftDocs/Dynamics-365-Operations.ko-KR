---
title: 공급업체 송장을 사용하는 AP의 주요 송장 데이터
description: 이 작업 가이드는 구매 주문에서 공급업체 송장을 만들고 구매 주문, 영수증 및 송장을 매칭한 결과(3방향 매칭)를 보는 데 도움이 됩니다.
author: abruer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3e27ed41ff1fa44d5e8779cb5e81e45d02110eb3b37be3a3b9938cabfc395bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450844"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a>공급업체 송장을 사용하는 AP의 주요 송장 데이터

[!include [banner](../../includes/banner.md)]

이 작업 가이드는 구매 주문에서 공급업체 송장을 만들고 구매 주문, 영수증 및 송장을 매칭한 결과(3방향 매칭)를 보는 데 도움이 됩니다.


## <a name="create-a-purchase-order"></a>구매 주문 만들기
1. 탐색 창에서 **모듈 > 지급 계정 > 구매 주문 > 모든 구매 주문** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **공급업체 계정** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
4. 선택할 공급업체를 찾습니다. 예를 들어 US-104까지 아래로 스크롤합니다.
5. 공급업체 US-104를 선택합니다.
6. **확인** 을 클릭합니다.
7. **항목 번호** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
8. 재고 항목을 선택합니다. 예를 들어 품목 번호 1000을 선택합니다.
9. **라인 세부 정보** 빠른 탭을 확장합니다.
10. **설정** 탭을 클릭합니다. 매칭 없음, 2방향 매칭 또는 3방향 매칭을 사용하도록 매칭 정책을 재정의할 수 있습니다.  
11. 작업 창에서 **구매** 를 클릭합니다.
12. **확인** 을 클릭합니다.

## <a name="receive-the-products"></a>제품 수령
1. 작업 창에서 **수령** 을 클릭합니다.
2. **제품 영수증** 을 클릭합니다.
3. **제품 영수증** 필드에 제품 영수증 번호를 입력합니다. 예를 들어 PR123을 입력합니다.
4. **확인** 을 선택하여 제품 영수증을 게시합니다.
5. 페이지를 닫습니다.

## <a name="create-a-vendor-invoice"></a>공급업체 송장 만들기
1. 탐색 창에서 **모듈 > 지급 계정 > 구매 주문 > 구매 주문을 받았지만 송장이 발부되지 않음** 으로 이동합니다.
2. 작성한 구매 주문을 선택합니다.
3. 작업 창에서 **송장** 을 클릭합니다.
4. **송장** 을 클릭합니다.
5. **번호** 필드에 송장 번호를 입력합니다.
6. **송장 설명** 필드에 값을 입력합니다.
7. **송장 날짜** 필드에 날짜를 입력합니다.
8. **단가** 필드에 1200을 입력합니다.
9. **라인 추가** 를 클릭합니다.
10. **항목 번호** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
11. 목록에서 설치비 품목 번호를 찾습니다. 예: S0001
12. 설치비 품목 번호를 선택합니다. 변경한 이후로 매칭이 수행되지 않았음을 유의하세요.  
13. **일치 상태 업데이트** 를 클릭합니다.
14. 작업 창에서 **검토** 를 클릭합니다.
15. **세부 정보 매칭** 을 클릭합니다. 서비스가 있는 새 라인은 일치할 필요가 없으므로 상태가 "수행되지 않음"으로 유지됩니다.  
16. 수령한 재고 항목에 대한 제품 입고를 선택합니다. 상품 영수증에 있는 라인은 일치했지만 수량이나 가격이 일치하지 않아 실패합니다.  
17. **단가 필드** 에 숫자를 입력합니다. 이제 단가가 일치하므로 상태가 통과로 업데이트됩니다. 정책에서 불일치를 허용하거나 일치가 단지 경고인 경우에도 송장을 게시할 수 있습니다.  
18. 페이지를 닫습니다.
19. **게시** 를 클릭합니다.
20. 양식을 닫습니다. 구매 주문은 더는 구매 주문을 받았지만 송장이 발부되지 않음으로 나열되지 않습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]