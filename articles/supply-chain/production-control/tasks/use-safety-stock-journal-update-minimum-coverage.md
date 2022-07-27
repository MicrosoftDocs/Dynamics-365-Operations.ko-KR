---
title: 안전 재고 분개장을 사용하여 최소 적용 범위 업데이트
description: 이 절차는 과거 거래를 기반으로 최소 적용 범위 제안을 계산한 다음 제안으로 항목 적용 범위를 업데이트하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ae2209fc2412a4a67b46d6eb82ecb70aafc0159
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448633"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>안전 재고 분개장을 사용하여 최소 적용 범위 업데이트

[!include [banner](../../includes/banner.md)]

이 절차는 과거 거래를 기반으로 최소 적용 범위 제안을 계산한 다음 제안으로 항목 적용 범위를 업데이트하는 방법을 보여줍니다. 이것은 안전 재고 분개장을 사용하여 수행됩니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 생산 계획자가 최소 적용 범위를 유지하는 데 도움을 주기 위한 것입니다.


## <a name="create-a-new-safety-stock-journal-name"></a>새 안전 재고 분개장 이름 생성
1. **탐색 창** 에서 **기준 계획 > 설정 > 안전 재고 분개장 이름** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **이름** 필드에 '자재'를 입력합니다.
4. **설명** 필드에 '자재'를 입력합니다.
5. 페이지를 닫습니다.

## <a name="create-a-safety-stock-journal"></a>안전 재고 분개장 생성
1. **탐색 창** 에서 **기준 계획 > 기준 계획 > 실행 > 안전 재고 계산** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **이름** 필드에 값을 입력하거나 선택합니다. 생성한 안전 재고 분개장 이름(예: 자재)을 선택합니다.  
4. **라인 생성** 을 클릭합니다.
5. **시작 날짜** 필드에 날짜를 입력합니다.  
6. **종료 날짜** 필드에 날짜를 입력합니다.
7. **확인** 을 클릭합니다. 그러면 재고 트랜잭션이 있는 차원에 대한 라인이 생성됩니다.  

## <a name="calculate-proposal"></a>제안 계산
1. **제안 계산** 을 클릭합니다.
2. **리드 타임 동안 평균 발행 사용** 옵션을 선택합니다.
3. **곱하기 인수** 를 '10'으로 설정합니다. 곱하기 요소는 제안을 조정하는 데 사용됩니다. 데모 데이터에는 트랜잭션이 몇 개뿐이므로 현실적인 제안을 얻으려면 요소를 설정해야 합니다.  
4. **확인** 을 클릭합니다. 아래로 스크롤하여 M0002 및 M0003을 찾습니다. **계산된 최소값** 수량 열을 봅니다.   

## <a name="update-minimum-quantity"></a>최소 수량 업데이트
1. **새 최소 수량** 필드에 숫자를 입력합니다. 계산된 최소 수량의 값과 일치하도록 새 최소 수량을 업데이트합니다. 계산된 최소값이 0이면 원하는 미래 값을 입력할 수 있습니다. 예를 들어, 창고 12가 있는 M0002에 대해 이 필드에 계산된 최소 수량을 입력할 수 있습니다.  
2. 목록에서 원하는 레코드를 찾아 선택합니다. 예를 들어, 창고 12가 있는 M0002를 선택할 수 있습니다.  
3. **새 최소 수량** 필드에 숫자를 입력합니다. 계산된 최소 수량의 값과 일치하도록 새 최소 수량을 업데이트합니다. 계산된 최소값이 0이면 원하는 미래 값을 입력할 수 있습니다.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>새로운 최소 수량 게시 및 결과 검증
1. **전기** 를 클릭합니다.
2. **확인** 을 클릭합니다.
3. **품목 번호** 필드에 있는 링크를 따라가려면 클릭합니다.
4. **품목 번호** 필드에 있는 링크를 따라가려면 클릭합니다.
5. **작업 창** 에서 계획을 클릭합니다.
6. **항목 적용 범위** 를 클릭합니다. **최소 수량** 은 안전 재고 분개장의 새로운 최소 수량으로 업데이트되었습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]