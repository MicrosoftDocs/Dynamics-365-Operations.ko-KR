---
title: 위탁 보충 주문 만들기
description: 이 항목에서는 공급업체에서 위탁 재고로 예상되는 배송을 추적할 수 있는 위탁 보충 주문을 생성하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9076207b73c6c76cfc44e1e02b21aad4e3f321f8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448738"
---
# <a name="create-a-consignment-replenishment-order"></a>위탁 보충 주문 만들기

[!include [banner](../../includes/banner.md)]

이 항목에서는 공급업체에서 위탁 재고로 예상되는 배송을 추적할 수 있는 위탁 보충 주문을 생성하는 방법에 대해 설명합니다. 또한 위탁 재고가 판매자 소유의 보유 재고로 등록되도록 제품 입고를 기록하는 방법을 보여줍니다. 이 절차는 일반적으로 조달 전문가가 수행합니다. 데모 데이터 회사 USMF에서 이 가이드를 사용할 수 있습니다. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.

## <a name="create-a-consignment-replenishment-order"></a>위탁 보충 주문 만들기
1. 탐색 창에서 **모듈 > 조달 및 소싱 > 위탁 > 위탁 보충 주문** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **공급업체 계정** 필드에서 공급업체 **US-104**(**재고 소유자** 페이지에서 소유자로 등록된 공급업체를 선택해야 함)를 선택합니다. 
4. **확인** 을 선택합니다.
5. **라인 추가** 를 선택합니다.
6. **품목 번호** 필드에서 유형 `M9211CI`(위탁재고로 설정된 품목을 선택해야 함)를 입력합니다.
7. **수량** 필드에 숫자를 입력합니다.
8. **요청한 배송 날짜** 필드에 날짜를 입력합니다. 요청 및 확인된 날짜는 상품의 예상 도착에 대해 MRP 엔진에서 사용됩니다.  
9. **확인된 배송 날짜** 필드에 날짜를 입력합니다.
10. **라인 세부 정보** 섹션을 확장합니다.
11. **재고 차원** 탭을 선택합니다.
12. **인벤토리 차원 소유자** 필드에 소유자를 표시하려면 페이지를 새로 고칩니다. 이제 공급업체 US-104가 소유자로 나열됩니다.  

## <a name="check-the-inventory-transaction-status"></a>재고 거래 현황 확인
1. **재고** 를 선택합니다.
2. **트랜잭션** 을 선택합니다.
3. 원하는 행에서 **영수증** 필드가 **주문됨** 으로 설정된 것을 볼 수 있습니다.  
4. 페이지를 닫습니다.

## <a name="receive-items"></a>항목 수령
1. **제품 영수증** 을 선택합니다.
2. **외부 제품 영수증** 필드에 값을 입력합니다.
3. **수량** 필드에 표시된 숫자보다 낮은 숫자를 입력합니다. 
4. **확인** 을 선택합니다.

## <a name="check-the-on-hand-inventory"></a>보유 재고 확인
1. **재고** 를 선택합니다.
2. **보유** 를 선택합니다.
3. **개요** 를 선택합니다. 판매자 소유의 위탁 재고로 입고된 품목을 현재 보유하고 있습니다. 위탁 보충 오더의 잔여 수량은 **총 주문** 필드에 표시됩니다.  
4. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]