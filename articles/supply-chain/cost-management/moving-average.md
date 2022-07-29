---
title: 이동 평균
description: 이동 평균은 평균 원칙에 기초한 영구 원가계산법으로, 재고 발행 비용은 구매 비용이 변동하더라도 변하지 않습니다. 차액은 대문자로 표시되며 비례 계산을 기반으로 합니다. 남은 금액은 경비 처리됩니다.
author: AndersGirke
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6721c01fd0ad3eec30de99dee3b5e98de6bd3b52
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448024"
---
# <a name="moving-average"></a>이동 평균

[!include [banner](../includes/banner.md)]

이동 평균은 평균 원칙에 기초한 영구 원가계산법으로, 재고 발행 비용은 구매 비용이 변동하더라도 변하지 않습니다. 차액은 대문자로 표시되며 비례 계산을 기반으로 합니다. 남은 금액은 경비 처리됩니다.

이동 평균을 사용하는 경우 재고 정산 및 재고 표시가 지원되지 않습니다. 재고 마감은 재고 모델 그룹으로 이동 평균이 있는 제품에 영향을 미치지 않으며 트랜잭션 간에 정산을 생성하지 않습니다.

다음은 이동 평균 비용을 원가 계산 방법으로 사용할 때의 전제 조건입니다.

1. **항목 모델 그룹** 페이지에서 **재고 모델** 필드에 **이동 평균** 이 선택된 항목 모델 그룹을 설정합니다.

    > [!NOTE]
    > 기본적으로 **이동 평균** 을 선택하면 **실제 인벤토리 전기** 및 **재무 인벤토리 전기** 필드도 선택됩니다.

1. **전기** 페이지에서 계정을 **이동 평균의 가격 차이** 에 할당합니다. 비용이 비례적으로 지출되어야 하는 경우 **이동 평균의 가격 차이** 계정을 사용합니다. 이것은 다음 두 가지 시나리오에서 발생합니다.
    - 원래 재고 수량과 현재 보유 수량 사이에 차이가 있기 때문에 구매 영수증과 구매 송장 사이에 비용 차이가 있습니다.
    - 트랜잭션은 재고를 음수에서 0으로 만들고 거래 비용과 현재 이동 평균 비용 사이에 차이가 있습니다.

1. **전기** 페이지에서 계정을 **재고** 탭의 **이동 평균에 대한 비용 재평가** 계정에 할당합니다. 제품의 이동 평균 비용을 새 단가로 조정하려는 경우 **이동 평균에 대한 비용 재평가** 계정을 사용합니다.

1. **출시된 제품** 페이지에서 이동 평균 항목 모델 그룹을 제품에 할당합니다.

    > [!NOTE]
    > 재고 마감 프로세스는 회계 기간만 마감합니다. 이동 평균이 항목 모델 그룹으로 할당된 제품에는 영향을 주지 않습니다.

## <a name="convert-to-the-moving-average-costing-method"></a>이동 평균 원가 계산 방법으로 변환

이동 평균 재고 평가 방법을 사용하도록 제품을 변환할 수 있습니다. 이러한 유형의 변환은 일반적으로 현재 연도의 마지막 달이 마감된 후 연말에 수행됩니다. 제품의 현재 원가 계산 모델을 사용하여 수행됩니다. 평균 비용 또는 표준 비용을 기반으로 하는 원가 계산 방법에서 이동 평균을 기반으로 하는 방법으로 재고 원가 계산 방법을 변경할 수 있습니다.

원가 계산 방법을 표준 원가 계산 방법에서 이동 평균 방법으로 변경하는 경우 다음 작업을 완료해야 합니다.

1. 재고 수량과 값을 0(영)으로 낮추도록 조정합니다.
1. 재고 금액과 수량이 0(영)이 되면 항목 모델 그룹을 이동 평균으로 변경합니다.
1. 수량과 값을 재고로 되돌리도록 조정하세요.

재고 원가 계산 방법을 이동 평균 방법에서 선입선출(FIFO) 방법, 후입선출(LIFO) 방법 또는 가중 평균 방법으로 변경할 수 없습니다.

> [!NOTE]
> 표준 비용에서 이동 가중 평균으로 변환하는 것은 수동 프로세스입니다.

다음 예는 이동 평균 원가 계산 방법 사용의 효과를 보여줍니다. 네 가지 구성이 있습니다.

- 구매 주문 및 비례적으로 지출된 비용 차이
- 이동 평균 제품 및 재고 조정
- 생산이 있는 이동 평균
- 소급 트랜잭션이 있는 이동 평균

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>구매 주문 및 비례적으로 지출된 비용 차이

이동 평균을 사용하면 제품의 비용이 구매 영수증에 의해 결정됩니다. 구매 청구서를 전기할 때 구매 영수증과 구매 청구서의 비용 차이가 있는 경우 차이는 현재 재고 제품에 비례하여 조정되고 나머지 금액은 비용 처리됩니다.

이 예에서는 하나의 비용으로 구매 주문이 생성되어 입고되고 구매 청구서가 다른 비용으로 전기됩니다.

1. 수량 2와 단가 10.00에 대한 구매 주문을 생성합니다.
1. 제품 구매 영수증을 생성합니다.
1. 수량 1과 단가 10.00에 대한 판매 주문을 생성합니다.
1. 수량 2와 단가 12.00에 대한 구매 청구서를 생성합니다.

단가 차이 2.00은 구매 청구서가 전기될 때 이동 평균 계정의 가격 차이에 전기됩니다. 그 이유는 2개의 제품을 20.00에 구매했기 때문입니다. 제품 중 하나가 10.00의 단가에 판매되었습니다. 구매 청구서가 수량 2인 단가 12.00으로 전기되었습니다. 제품의 단가는 14.00에 게시될 수 없습니다.

## <a name="moving-average-product-and-inventory-adjustment"></a>이동 평균 제품 및 재고 조정

제품의 이동 평균 비용 조정이 필요한 경우 오늘부터 재고 조정이 가능합니다. 제품의 이동 평균 비용을 수정하기 위해 재고 조정을 소급할 수 없습니다. 후속 트랜잭션을 통해 비용 흐름을 가질 수 없습니다.

이 예에서 이동 평균 비용은 제품에 대해 조정됩니다.

1. 이동 평균 비용을 조정할 제품을 선택합니다. 

 > [!NOTE]
 > **이동 평균에 대한 재평가** 페이지는 제품에 사용할 수 있는 인벤토리를 검사합니다. 선택한 제품의 전기 수량은 1, 전기 값은 12.00, 전기 단가는 12.00, 단가는 12.00입니다.
    
1. **단가** 필드를 16.00으로 업데이트합니다. 시스템은 나머지 필드를 계산합니다.
1. 조정이 게시됩니다.

> [!NOTE]
> 오늘 날짜를 기준으로 이동 평균 비용만 조정할 수 있습니다.

**바우처 정산** 페이지에서 이동 평균에 대한 비용 재평가 계정에 게시된 4.00 조정을 볼 수 있습니다.

## <a name="moving-average-with-production"></a>생산이 있는 이동 평균

이동 평균은 생산 항목을 지원합니다. 프로덕션 환경에서 이동 평균을 사용하려는 경우 **프로덕션 제어 매개 변수** 페이지에서 **예상 비용 가격 사용** 을 선택합니다. 이는 실제 BOM 계산 원가 대신 추정 시 계산된 원가를 사용한다는 의미입니다.

## <a name="moving-average-with-a-backdated-transaction"></a>소급 트랜잭션이 있는 이동 평균

소급 거래에는 현재 이동 평균 비용이 할당되고 제품의 물리적 수량은 업데이트되지만 제품의 이동 평균 비용은 영향을 받지 않습니다. 이 이동 평균 예에서는 이동 평균 제품에 대한 트랜잭션이 게시됩니다.

1. 수량 1 및 비용 20.00에 대한 이동 평균 제품에 대한 재고 조정을 생성합니다.
1. 제품의 재고 트랜잭션 내역은 다음과 유사합니다.
    - 재고 트랜잭션은 1, 원가는 16.00, 전기일은 1월 15일, 거래일은 1월 15일입니다.
    - 재고 조정은 1, 원가는 20.00, 전기일은 1월 15일, 거래일은 1월 15일입니다.
1. 조정 전기

**재고 트랜잭션** 페이지에서 제품의 현재 이동 평균이 16.00이므로 4.00이 비용 처리되었음을 알 수 있습니다. 과거에 전기할 수 있지만 비용의 차이는 비용 처리되므로 이동 평균 비용은 영향을 받지 않습니다.

## <a name="negative-inventory-balances"></a>마이너스 재고 잔고

트랜잭션 후의 신규 현재고 수량이 음수인지 0인지 양수인지에 따라 트랜잭션이 다르게 처리됩니다.

### <a name="new-balance-is-negative-or-zero"></a>새 잔액이 음수 또는 0

신규 현재고 수량이 음수이거나 0인 경우 트랜잭션은 현재 평균 원가로 비용 계산됩니다. 구매 가격과 현재 평균 비용 사이에 차이가 있는 경우 **이동 평균의 가격 차이** 에 전기됩니다.

### <a name="new-balance-is-positive"></a>새로운 잔액이 양수

트랜잭션 후 신규 현재고 수량이 양수이면 다음 테이블에 요약된 것처럼 트랜잭션이 두 부분으로 분할되고 비용이 다르게 책정됩니다.

| 부분 | 설명 |
|---|---|
| 음수에서 0까지의 수량 | 재고는 현재고 잔액을 음수에서 0으로 증가시키는 입고 수량 부분에 대한 트랜잭션 비용이 아닌 항목의 현재 이동 평균 비용을 사용합니다. 트랜잭션 비용과 현재 이동 평균 비용의 차이는 **이동 평균의 가격 차이** 에 전기됩니다. |
| 0에서 양수까지의 수량 | 재고는 현재고 잔액을 0에서 양수로 증가시키는 입고 수량 부분에 대해 트랜잭션 원가를 사용합니다.                                                  |

## <a name="inventory-value-report"></a>재고 가치 보고서

이 이동 평균 예에서 재고 가치 보고서는 제품에 대한 현재 이동 평균 계산을 지원하기 위해 인쇄됩니다. 재고 가치 보고서는 제품의 이동 평균 비용 계산을 지원하는 비용과 함께 시간순으로 트랜잭션을 인쇄할 수 있습니다. 보고서에는 제품의 이동 평균 비용이 표시됩니다. **재고 가치 보고서** 대화 상자에서 날짜 간격을 사용하여 보고서를 정렬할 **트랜잭션 시간** 또는 **전기 날짜** 를 선택할 수 있습니다. **전기 날짜** 옵션은 보고서가 전통적으로 인쇄되는 방식입니다. **트랜잭션 시간** 옵션은 트랜잭션이 보고되고 제품의 이동 평균 비용이 업데이트된 실제 날짜입니다. 시간 경과에 따른 이동 평균 비용 계산을 보려면 **트랜잭션 시간 정렬** 옵션을 사용하여 재고 가치 보고서를 인쇄할 수 있습니다. 다음 테이블은 **트랜잭션 시간 정렬** 옵션이 사용될 때 보고서가 인쇄되는 제품에 대한 트랜잭션을 표시합니다.

| 트랜잭션 시간 | 날짜         | 트랜잭션 유형           | 수량 | 금액 | 평균 단가 |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 10월 1일    | 기초 잔액          | 0        | 0.00   | 0.00              |
| 10월 8일        | 9월 28일 | 소급 영수증          | 1        | 16.00  | 16.00             |
| 10월 3일        | 10월 3일    | 구매 영수증           | 2        | 20.00  | 12.00             |
| 10월 5일        | 10월 5일    | 판매 주문                | -1       | -10.00 | 13.00             |
| 10월 7일        | 10월 7일    | 구매 청구서           |          | 2.00   | 14.00             |
| 10월 8일        | 10월 8일    | 이동 평균 재평가 |          | 4.00   | 16.00             |
|                  | 10월 31일   | 합계                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> **트랜잭션 시간 정렬** 옵션을 사용하여 총계정원장과 재고를 조정할 수 없습니다. 보고서는 **전기 날짜** 옵션을 사용하여 인쇄해야 합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]