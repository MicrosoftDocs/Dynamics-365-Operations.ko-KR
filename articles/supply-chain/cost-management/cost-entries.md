---
title: 비용 항목
description: 이 문서에서는 비용 항목과 작성 시점에 대한 정보를 제공합니다. 비용 항목은 주어진 이벤트의 수량과 비용을 등록하는 레코드입니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 53e2dd7375daf0d33ff61b870fecfdaa44dd0838
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448858"
---
# <a name="cost-entries"></a>비용 항목

[!include [banner](../includes/banner.md)]

이 문서에서는 비용 항목과 작성 시점에 대한 정보를 제공합니다. 비용 항목은 주어진 이벤트의 수량과 비용을 등록하는 레코드입니다.

비용 항목은 활성 재무 인벤토리 차원에 기록된 인벤토리 트랜잭션의 집계입니다.

## <a name="examples"></a>예
### <a name="example-1-no-cost-entries-are-created"></a>예시 1: 비용 항목이 생성되지 않음

전송 저널 이벤트가 등록되었습니다. 이벤트는 위치 A에서 위치 B로 항목 A의 한 부분을 전송합니다. 위치 재고 차원은 비용 개체의 일부로 간주되지 않습니다. 따라서 이벤트는 두 개의 재고 트랜잭션을 생성하고 비용 항목은 생성하지 않습니다.

### <a name="example-2-cost-entries-are-created"></a>예시 2: 비용 항목이 생성됨

전송 저널 이벤트가 등록되었습니다. 이벤트는 사이트 1에서 사이트 2로 항목 A 1개를 전송합니다. 사이트 인벤토리 차원은 비용 개체의 일부로 간주됩니다. 따라서 이벤트는 두 개의 재고 트랜잭션과 비용 항목을 생성합니다.

### <a name="example-3-one-cost-entry-is-created"></a>예 3: 비용 항목 1개가 생성됨

구매 오더에 대한 제품 수령 이벤트가 등록됩니다. 이벤트는 10.00 US 달러(USD)의 단가로 항목 A 100개를 등록합니다. 품목 A는 일련 번호를 사용하여 재고 관리 목적을 추적하기 때문에 입고되는 각 품목에 대해 고유한 일련 번호가 생성됩니다. 따라서 이벤트는 100개의 재고 트랜잭션과 1개의 비용 항목을 생성합니다.

## <a name="cost-entries-page"></a>비용 항목 페이지
새로운 **비용 항목** 페이지에서 수량 및 비용 등록을 보고 제어할 수 있습니다. 이 페이지는 **재고 거래** 및 **재고 정산** 페이지를 보완합니다. 기록은 이벤트에 대한 시간순으로 등록됩니다. 따라서 문서와 관련된 특정 이벤트 또는 모든 이벤트의 누적 비용을 빠르게 찾고 제어할 수 있습니다. 다음은 예입니다.

-   상품 A에 대한 상품 수령 이벤트가 등록되었습니다. 10.00 USD의 단가에 100개를 수령했습니다.
-   송장 이벤트가 등록된 후 며칠이 지나면 비용이 11.00 USD로 증가합니다. 따라서 총 비용은 1,100 USD입니다. 100 USD의 차이를 설명하기 위해 두 번째 바우처가 생성됩니다.
-   며칠 후, 운송비를 충당하기 위한 15.00 USD의 잡비가 구매 주문서에 등록됩니다.

| 바우처 | 날짜       | 참조      | 번호 | 로트 ID  | 수량 | 금액  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01-01-2015 | 구매 주문 | 100001 | 0000101 | 100.00   | 1000.00 |
| 00002   | 20-01-2015 | 구매 주문 | 100001 | 0000101 |          | 100.00  |
| 00003   | 31-01-2015 | 조정     | 100001 | 0000101 |          | 15.00   |

**비용 항목** 페이지에서 문서 ID 및 문서 날짜별로 필터링할 수 있습니다. 

> [!NOTE]
> 비용 항목은 [비용 개체](cost-object.md) 또는 출시된 제품에 대해서만 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[원가 개체](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]