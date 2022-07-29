---
title: 구매 주문 보관을 위한 위치 지시문 설정
description: 이 토픽에서는 간단한 위치 지시문을 설정하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a363b452cbee539aeee62146f545b1f7c2eb842
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448882"
---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>구매 주문 보관을 위한 위치 지시문 설정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 간단한 위치 지시문을 설정하는 방법에 대해 설명합니다. 표시된 예는 구매 주문을 위해 받은 항목을 어디에 둘 것인지 결정하는 데 사용할 위치 지시문을 생성합니다. 데모 데이터 회사 USMF를 사용하여 언급된 데이터로 이 작업 가이드를 재생할 수 있습니다. 전제 조건: 처분 코드를 생성해야 합니다. 이 절차에서는 Relabel이라는 처리 코드를 사용합니다. 자체 데이터에서 위치 지시문을 생성하는 경우 창고 및 항목에 대한 고급 창고 관리를 설정해야 합니다. 이 절차는 창고 관리자를 위한 것입니다.

1. 탐색 창에서 **모듈 > 창고 관리 > 설정 > 위치 지시문** 으로 이동합니다.
2. **작업 주문 유형** 필드에서 **구매 주문** 을 선택합니다.

## <a name="create-a-location-directive-header"></a>위치 지시문 헤더 생성
1. **새로 만들기** 를 선택합니다.
2. **시퀀스 번호** 필드에 번호를 입력합니다. 이는 선택한 작업 유형에 대해 위치 지시문이 처리되는 시퀀스입니다. 필요한 경우 시퀀스를 수정할 수도 있습니다.  
3. **이름** 필드에 값을 입력합니다. 이 지시문에 대한 고유 식별자입니다.  
4. **작업 유형** 필드에서 **풋** 을 선택합니다. 수행할 작업 유형을 선택합니다. 작업 주문 유형이 구매 주문인 지시문의 경우 **Put** 만이 지원되는 값입니다.  
5. **사이트** 필드에 값을 입력합니다.
6. **창고** 필드에 값을 입력합니다. 지침 코드를 비워 둡니다.  지시문 코드는 Put 유형의 작업 주문 라인을 특정 지시문에 연결하는 데 사용됩니다. 구매 주문의 경우 작업 템플릿이 결정되기 전에 Put 유형의 마지막 작업 주문 라인의 위치가 확인됩니다. 따라서 작업 템플릿의 마지막 줄을 특정 지시문에 연결할 수 없습니다.   
7. **처분 코드** 필드에 값을 입력합니다. 처분 코드는 위치 지시문 사용을 제한하므로 창고 작업자가 모바일 디바이스를 사용하여 항목을 등록하는 동안 이 특정 값을 입력하는 경우에만 위치 지시문이 사용됩니다.  
8. **저장** 을 선택합니다.

## <a name="edit-the-query-for-directive"></a>지시문에 대한 쿼리 편집
1. **쿼리 편집** 을 선택합니다. 이 지시문은 이미 지정한 창고에 등록된 항목과 지정한 처분 코드에 사용하도록 제한되어 있습니다. 쿼리를 사용하여 다른 제약 조건을 추가할 수 있습니다.  
2. **확인** 을 선택합니다.

## <a name="add-directive-lines"></a>지시문 라인 추가
1. **새로 만들기** 를 선택합니다. 이는 선택한 작업 유형에 대해 위치 지시문 라인이 처리되는 시퀀스입니다. 필요한 경우 시퀀스를 수정할 수도 있습니다.  
2. **시작 수량** 필드에 숫자를 입력합니다. 이것은 이 지시문이 유효한 최저 수량입니다.  
3. **도착 수량** 필드에 숫자를 입력합니다.
4. **단위** 필드에 값을 입력합니다. 시작 수량 및 끝 수량의 단위는 로 표시됩니다. 이 필드를 비워 두면 항목의 인벤토리 단위가 사용됩니다.  
5. **위치 수량** 필드에서 옵션을 선택합니다.
    - 없음 또는 번호판 수량: 각 번호판에 등록된 수량입니다.  
    - 단위 수량: 등록된 전체 수량입니다.  
    - 잔여 수량: 구매 주문 라인에서 아직 등록되지 않은 수량입니다.  
    - 예상 수량: 구매 주문 라인에 지정된 총 수량입니다.  
6. **단위로 제한** 확인란을 선택하거나 선택 취소합니다. 이 옵션을 선택하고 **단위로 제한** 페이지에서 단위를 지정하면 해당 측정 단위가 있는 항목만 위치에 넣을 수 있습니다. 예를 들어 측정 단위가 PL(팔레트)인 경우 팔레트의 항목만 지정된 위치에 넣을 수 있습니다.  
7. **분할 허용** 확인란을 선택하거나 선택 취소합니다. 이를 통해 지시문은 수량을 여러 위치로 분할할 수 있습니다.  
8. **저장** 을 선택합니다.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>지시문을 특정 단위로 제한
1. **단위로 제한** 을 선택합니다. 이 버튼은 **단위로 제한** 확인란을 선택한 후 **저장** 을 누른 경우에만 사용할 수 있습니다.  
2. **단위** 필드에 값을 입력합니다.
3. 페이지를 닫습니다.

## <a name="add-a-location-directive-action-line"></a>위치 지시 액션 라인 추가
1. **새로 만들기** 를 선택합니다. 이는 선택한 작업 유형에 대해 위치 지시문 작업 라인이 처리되는 시퀀스입니다. 필요한 경우 시퀀스를 수정할 수도 있습니다.  
2. **이름** 필드에 값을 입력합니다. 이 지시문 작업에 대한 고유 식별자입니다.  
3. **고정 위치 사용** 필드에서 옵션을 선택합니다.
    - 고정 및 비고정 위치: 모든 비고정 위치는 쿼리에 지정된 범위 내에서 제품 자체의 고정 위치뿐만 아니라 유효합니다.  
    - 제품의 고정 위치만: 제품의 고정 위치가 유효하며 모든 제품 변형이 동일한 고정 위치 세트를 공유합니다.  
    - 제품 변형에 대한 고정 위치만: 각 제품 변형에 대해 지정된 고정 위치만 유효합니다.  
4. **전략** 필드에서 옵션을 선택합니다. 구매 주문 유형의 작업 주문은 다음 전략을 지원합니다. 
    - 없음: 항목이 발견된 첫 번째 위치에 배치됩니다.  
    - 통합: 항목이 이미 유사한 항목을 사용할 수 있는 위치에 배치됩니다.  
    - 들어오는 작업이 없는 빈 위치: 항목은 발견된 첫 번째 빈 위치에 배치됩니다. 실제 재고가 없고 예상 들어오는 작업이 없는 경우 위치가 비어 있는 것으로 간주됩니다.  
5. **저장** 을 선택합니다.

## <a name="edit-the-query-for-directive-action-line"></a>지시문 작업 라인에 대한 쿼리 편집
1. **쿼리 편집** 을 선택합니다.
2. **추가** 를 선택합니다.
3. **필드** 필드에 `location profile ID`를 입력합니다. 이 예에서는 위치 프로필 ID를 사용하여 가능한 위치를 제한합니다.  
4. **기준** 필드에 값을 입력합니다.
5. **확인** 을 선택합니다. 창고에서 가능한 모든 시나리오를 다룰 때까지 지시문 라인과 지시문 작업을 계속 추가할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]