---
title: 조달 FAQ
description: 이 항목에서는 Supply Chain Management의 조달 기능에 대한 자주 묻는 질문(FAQ)에 대한 답변을 제공합니다.
author: Henrikan
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 99d44f2409d8207ed7a0fb1fc92a99de42240e86
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448987"
---
# <a name="procurement-faq"></a>조달 FAQ

[!include [banner](../includes/banner.md)]

이 항목에서는 Supply Chain Management의 조달 기능에 대한 자주 묻는 질문(FAQ)에 대한 답변을 제공합니다.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>내가 생성한 구매 주문만 표시할 수 있습니까?

이 기능은 현재 사용할 수 없습니다.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>재고를 예약하고 구매 주문서에 등록된 인벤토리에 대해 트랜잭션을 생성할 수 있습니까?

### <a name="issue-description"></a>문제 설명

항목이 구매 주문서에 *등록됨* 상태인 경우에도 인벤토리를 예약할 수 있습니다. 즉, 등록된 인벤토리에 대해 트랜잭션을 생성할 수 있습니다.

### <a name="reproduce-the-issue"></a>문제 재현

다음 절차는 문제를 재현하는 한 가지 방법을 보여줍니다.

1. 구매 주문을 만듭니다.
2. 구매 주문 라인을 등록합니다.
3. 등록된 인벤토리에 대해 예약 또는 트랜잭션을 생성할 수 있습니다.

### <a name="issue-resolution"></a>문제 해결

이 동작은 의도적으로 설계된 것입니다. 등록된 항목이 창고나 인벤토리에 물리적으로 도착하여 예약이 가능할 것으로 예상됩니다.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>구매 주문을 취소한 사용자를 찾을 수 있나요?

이 정보는 구매 주문이 변경 관리 대상인 경우에만 추적됩니다. 변경 관리를 사용하면 누가 변경(취소)을 제출했는지, 누가 승인했는지 확인할 수 있습니다.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>구매 계약을 기존 구매 주문에 연결할 수 없는 이유는 무엇입니까?

구매 주문이 생성될 때 구매 계약이 구매 주문과 연결되어야 합니다. 그렇지 않으면 구매 주문 라인을 구매 계약 라인과 연관시킬 수 없습니다.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>"수동으로 입력한 가격 및 할인 업데이트 또는 외부 문서" 메시지를 트리거하는 검사는 무엇입니까?

배달 날짜를 변경하면 "수동으로 입력한 가격 및 할인 또는 외부 문서 업데이트"라는 메시지가 표시될 수 있습니다. 배달 날짜가 변경되면 다른 거래 또는 판매 계약이 실행되어 가격이 변경될 수 있기 때문에 이 메시지가 표시됩니다. 배달 날짜를 변경하면 창고 일정 및 기타 관련 정보에도 영향을 미칠 수 있습니다.

날짜 또는 일부 다른 매개 변수가 변경될 때마다 메시지가 트리거됩니다. 메시지의 목적은 이러한 변경으로 인해 발생할 수 있는 가격 변경을 인지하고 있는지 확인하는 것입니다.

메시지는 무역 협정 평가(TAE) 프롬프트입니다. 전체 설명은 [무역 계약 평가 정책](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper)을 참조하세요.

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>범주 기반 품목이 있는 구매 주문 라인에 대해 둘 이상의 송장을 전기할 수 없는 이유는 무엇입니까?

송장을 전기하려면 수량은 필수입니다. 따라서 라인의 전체 수량이 부분 금액에 대해서만 송장이 발행된 경우 다른 송장에서 나머지 금액을 송장 처리할 수 없습니다.
