---
title: 판매 주문 송장 생성
description: 이 항목에서는 송장 병합 및 배치 처리를 포함하여 판매 주문 송장을 발행하는 방법에 대해 설명합니다.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6712779ca64f5934edd37730597541679b86e43
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450922"
---
# <a name="create-sales-order-invoices"></a>판매 주문 송장 생성

[!include [banner](../../includes/banner.md)]

이 항목에서는 송장 병합 및 배치 처리를 포함하여 판매 주문 송장을 발행하는 방법에 대해 설명합니다. 이 절차는 USMF 데모 회사를 사용합니다.


## <a name="create-an-invoice-from-a-sales-order"></a>판매 주문에서 송장 생성
1. **탐색 창 > 모듈 > 수취 계정 > 주문 > 배송되었지만 송장이 발행되지 않은 판매 주문** 으로 이동합니다.
2. 목록에서 판매 주문을 선택합니다. 
3. **작업 창** 에서 **송장 > 생성 > 송장** 을 클릭합니다. 이 판매 주문에는 여러 포장 전표가 연결되어 있습니다. 포장 전표 번호 대신 *여러* 라는 단어만 표시됩니다.  
4. **매개 변수** 섹션을 펼칩니다.
    - 송장을 전기하려면 전기를 예로 설정해야 합니다. 전기를 끄고 인보이스를 인쇄할 수도 있습니다. 그러나 송장 대신 견적 송장을 생성하여 동일한 결과를 얻을 수 있습니다.  
    - 이 옵션은 일괄 작업에 사용됩니다. 쿼리는 일괄 작업이 실행될 때 실행됩니다.
5. **인쇄** 필드에서 '이후'를 선택합니다.
6. **송장 인쇄** 에 대해 **예** 를 선택합니다. 인쇄 관리는 송장의 여러 사본을 인쇄하고 이메일을 통해 PDF 파일로 송장을 보낼 수도 있습니다.  
7. **요금 인쇄** 필드에서 '요약'을 선택합니다.
8. **신용 한도 확인** 필드에서 '잔액'을 선택합니다.
9. **취소** 를 클릭합니다.

## <a name="combine-orders-into-a-single-invoice"></a>주문을 단일 송장으로 결합
1. **탐색 창 > 모듈 > 수취 계정 > 주문 > 모든 판매 주문** 으로 이동합니다.
2. 여러 송장이 열려 있는 고객을 찾습니다.
3. 동일한 고객의 여러 미결 판매 주문을 선택합니다.
4. **작업 창** 에서 **송장 > 생성 > 송장** 을 클릭합니다.
5. **매개 변수** 섹션을 펼칩니다.
6. **수량** 필드에서 '모두'를 선택합니다. 개요 섹션에 두 개의 송장이 나열됩니다. 이제 하나의 송장으로 병합해 보겠습니다.  
7. **요약 업데이트** 필드에서 '송장 계정'을 선택합니다.
8. 판매 주문을 단일 송장으로 병합하려면 **정렬** 을 클릭합니다. 이제 두 개의 판매 주문이 단일 송장으로 병합됩니다.   
9. **취소** 를 클릭합니다.
10. **예** 를 클릭합니다.

## <a name="post-invoices-in-a-batch"></a>배치로 송장 전기
1. **탐색 창 > 모듈 > 수취 계정 > 송장 > 배치 송장 발행 > 송장** 으로 이동합니다.
2. **선택** 을 클릭합니다.
3. **확인** 을 클릭합니다.
4. **배치** 를 클릭합니다.
5. **배치 처리** 에서 **예** 를 선택합니다.
6. **되풀이** 를 클릭합니다.
7. **일** 을 선택합니다.
8. **확인** 을 클릭합니다.
9. **확인** 을 클릭합니다.
10. **취소** 를 클릭합니다.
11. **예** 를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
