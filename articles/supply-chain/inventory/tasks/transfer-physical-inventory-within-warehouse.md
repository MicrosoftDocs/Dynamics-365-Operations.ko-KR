---
title: 창고 내 실제 재고 이전
description: 이 절차는 창고의 한 위치에서 다른 위치로 품목의 이동을 등록하기 위해 재고 이전 분개장을 만들고 전기하는 프로세스를 안내합니다.
author: yufeihuang
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf5a3711cfcd6e5a2ddce09af8569ea26c3502c8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449353"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>창고 내 실제 재고 이전

[!include [banner](../../includes/banner.md)]

이 절차는 창고의 한 위치에서 다른 위치로 품목의 이동을 등록하기 위해 재고 이전 분개장을 만들고 전기하는 프로세스를 안내합니다. 이 작업을 시작하기 전에 재고 이전을 위해 재고 분개장 이름을 설정해야 합니다. 표시된 예제 값을 사용하여 데모 데이터 회사 USMF에서 이 절차를 수행하거나 제품 및 위치가 설정된 경우 자체 데이터를 사용할 수 있습니다. 이러한 작업은 일반적으로 창고 직원이 수행합니다.


## <a name="create-an-inventory-transfer-journal"></a>재고 이전 분개장 생성
1. **탐0색 창** 에서 **재고 관리 > 분개장 > 항목 > 이전** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **이름** 필드에 값을 입력하거나 선택합니다.
4. **확인** 을 클릭합니다. 각 분개장 라인에 대해 '시작' 및 '끝' 차원을 지정하는 옵션이 있습니다. 이것은 이 분개장 유형에 필수적입니다. 다른 규칙을 사용하여 항목을 위치로 전송할 수 있습니다. 이 예에서는 동일한 창고 내의 항목을 번호판 제어 위치에서 번호판 제어 위치가 아닌 위치로 이전합니다.   

## <a name="create-journal-lines"></a>분개장 라인 생성
1. **분개장 라인 빠른 탭** 에서 **새로 만들기** 를 클릭합니다.
2. **품목 번호** 필드에서 값을 입력하거나 선택합니다. USMF를 사용하는 경우 'A0001'을 선택할 수 있습니다.  
3. **출발 사이트** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 '2'를 선택할 수 있습니다.  
4. **도착 사이트** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 '2'를 선택할 수 있습니다.  
5. **출발 창고** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 '24'를 선택할 수 있습니다.  
6. **도착 창고** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 '24'를 선택할 수 있습니다.  
7. **출발 위치** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 'FL-001'을 선택할 수 있습니다.  
8. **도착 위치** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 'BULK-001'을 선택할 수 있습니다.  
9. **수량** 필드에 숫자를 입력합니다.
10. **라인 세부 정보** 빠른 탭에서 **인벤토리 차원** 탭을 클릭합니다.
11. **시작 재고 차원** 의 **번호판** 필드에 값을 입력하거나 선택합니다. USMF를 사용하는 경우 '24'를 선택할 수 있습니다.  
12. **저장** 을 클릭합니다.

## <a name="post-the-inventory-transfer-journal"></a>재고 이전 분개장 기장
1. **작업 창** 에서 **전기** 를 클릭합니다.
2. **확인** 을 클릭합니다.

## <a name="view-inventory-transactions"></a>재고 거래 조회
1. **인벤토리** 를 클릭합니다.
2. **거래** 를 클릭합니다. 여기에서 분개장을 게시할 때 생성된 거래를 볼 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]