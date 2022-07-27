---
title: 품목 도착 분개를 사용한 기본 입고 가능 품목에 대한 품목 등록
description: 이번에는 재고 관리 모듈에서 '기본 창고'를 사용할 때 품목 도착 분개를 사용하여 품목을 등록하는 방법을 보여줍니다.
author: Mirzaab
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76dd2bfd57db7dfd5c2baf59a864e59a509a64e0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449044"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a>품목 도착 분개를 사용한 기본 입고 가능 품목에 대한 품목 등록

[!include [banner](../../includes/banner.md)]

이번에는 재고 관리 모듈에서 '기본 창고'를 사용할 때 품목 도착 분개를 사용하여 품목을 등록하는 방법을 보여줍니다. 이는 일반적으로 접수 직원이 수행합니다. 표시된 예시 값을 사용하여 데모 데이터 회사 USMF에서 이 절차를 실행할 수 있습니다.  USMF를 사용하지 않는 경우 이 가이드를 시작하기 전에 미결 구매 주문 라인이 있는 확인된 구매 주문이 있어야 합니다. 라인에 있는 품목은 재고가 있어야 합니다. 그리고 품목은 사이트와 창고가 활성화된 창고 치수 그룹과 연결되어야 합니다.


## <a name="create-item-arrival-journal-header"></a>품목 도착 분개 헤더 생성
1. 재고 관리 > 분개 기입 > 제품 출발 > 제품 도착으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력합니다.
    * USMF를 사용하는 경우 WHS를 입력할 수 있습니다. 다른 데이터를 사용하는 경우 선택한 이름의 분개에는 다음 속성이 있어야 합니다. 피킹 위치 확인은 아니요로 설정해야 하고 검역 관리는 아니요로 설정해야 합니다.  
4. 포장 명세서 필드에 값을 입력합니다.
    * 공급업체에서 발행한 포장 명세서의 포장 명세서 ID입니다. 고유 번호를 추가합니다.  
5. 번호 필드에서 구매 주문을 선택합니다.
6. 확인을 클릭합니다.

## <a name="add-lines-to-item-arrival-journal"></a>품목 도착 분개에 라인 추가
1. 기능을 클릭합니다.
2. 라인 생성을 클릭합니다.
    * 라인은 이 분개에 수동으로 입력하거나 자동으로 생성할 수 있습니다. 이는 자동으로 생성하는 방법을 보여줍니다.  
3. 수량 초기화 확인란을 선택하거나 선택 취소합니다.
    * 이는 구매 발주 라인에서 등록되지 않은 수량으로 분개 라인의 수량을 초기화합니다.  
4. 확인을 클릭합니다.

## <a name="post-the-journal"></a>분개 전기
1. 전기를 클릭합니다.
2. 확인을 클릭합니다.

## <a name="generate-the-product-receipt"></a>제품 영수증 생성
1. 기능을 클릭합니다.
2. 제품 영수증을 클릭합니다.
3. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]