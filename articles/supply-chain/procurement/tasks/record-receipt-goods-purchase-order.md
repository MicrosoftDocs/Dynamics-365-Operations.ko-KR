---
title: 구매 주문에 제품 수령 기록
description: 이번에는 구매 주문에 직접 제품 수령을 기록하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ec37082ffa7816d1b07cadc595eec6e8373920a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447811"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>구매 주문에 제품 수령 기록

[!include [banner](../../includes/banner.md)]

이번에는 구매 주문에 직접 제품 수령을 기록하는 방법에 대해 설명합니다. 창고에 제품 영수증을 등록하고 나중에 구매 주문에 기록하는 것도 가능합니다. 이 작업은 일반적으로 구매 에이전트 또는 미지불 금액 조정자가 수행합니다. 이 가이드에 표시된 예제는 USMF 데모 데이터 회사에서 사용할 수 있습니다. 예시에는 작업 가이드로 절차를 재생할 수 있도록 간단한 구매 주문을 만드는 단계가 포함되어 있습니다. 자체 데이터에 대한 절차를 사용하는 경우 **상품 수령 기록** 하위 작업에서 시작합니다.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>제품 수령을 위한 새 구매 주문 준비
1. **탐색 창 > 모듈 > 조달 및 소싱 > 구매 주문 > 모든 구매 주문** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **공급업체 계정** 필드에서 `US-101`을 입력합니다.
4. **확인** 을 선택합니다.
5. **품목 번호** 필드에 `M0001`을 입력합니다.
6. **수량** 필드에 `5`을(를) 입력합니다.
7. 작업 창에서 **구매** 를 선택합니다.
8. **확인** 을 선택합니다.

## <a name="record-receipt-of-goods"></a>제품 수령 기록
1. 작업 창에서 **수령** 을 선택합니다.
2. **제품 영수증** 을 선택합니다. **수량** 필드를 사용하면 수령하려는 수량에 대해 다른 옵션을 선택할 수 있습니다. 예를 들어, 창고에 이전에 수량이 등록된 경우 **등록 수량** 을 선택할 수 있습니다. 이 예에서는 **주문 수량** 값을 사용합니다.
3. **개요** 섹션을 확장합니다.
4. **제품 영수증** 필드에 값을 입력합니다. 이 필드는 제품 영수증 저널에 대한 바우처로 사용될 참조를 입력하는 데 사용됩니다.  
5. **라인** 섹션을 펼칩니다.
6. **수량** 을 '4'로 설정합니다. 여기에서 주문의 각 라인에 대해 입고되는 수량을 수동으로 지정할 수 있습니다.  
7. **확인** 을 선택합니다. 이제 제품이 구매 주문에 입고된 것으로 기록되었으며 이를 반영하는 문서로 제품 입고 분개가 생성되었습니다. 제품 수령 작업을 사용하여 구매 주문으로 생성된 분개를 검토하고 언제 수령했는지 확인할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]