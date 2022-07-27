---
title: 창고의 인벤토리 집계
description: 이 항목에서는 창고의 한 위치에서 특정 품목을 실사하기 위해 재고 실사 분개를 생성하고 전기하는 프로세스에 대해 설명합니다.
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7dd3788d3cbf80bfba373f5b6ce9d2e0ca0c07
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449110"
---
# <a name="count-inventory-in-a-warehouse"></a>창고의 인벤토리 집계

[!include [banner](../../includes/banner.md)]

이 항목에서는 창고의 한 위치에서 특정 품목을 실사하기 위해 재고 실사 분개를 생성하고 전기하는 프로세스에 대해 설명합니다. 이 절차는 창고 관리 모듈에서 사용할 수 있는 창고 기능이 아니라 재고 관리 모듈에서 사용할 수 있는 "기본 창고 보관" 기능에 적용됩니다. 데모 데이터 회사 USMF에서 이 절차를 수행하거나 자신의 데이터를 사용할 수 있습니다. 자신의 데이터를 사용하는 경우 제품 및 위치가 설정되어 있고 저널 계산을 위한 인벤토리 저널 이름을 생성했는지 확인하세요. 재고 실사는 일반적으로 창고 직원이 수행합니다.


## <a name="create-an-inventory-counting-journal"></a>재고 실사 분개 생성
1. **탐색 창 > 모듈 > 재고 관리 > 원장 입력 > 항목 집계 > 집계** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드의 드롭다운 목록에서 사용하려는 재고 실사 분개 이름을 선택합니다. 일부 다른 필드는 선택한 재고 집계 분개 이름 설정에 따라 채워집니다.  
4. **작업자** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
5. 목록에서 사용할 작업자를 **선택** 합니다.
6. **확인** 을 선택합니다.

## <a name="create-journal-lines"></a>분개 라인 생성
1. **새로 만들기** 를 선택합니다.
2. **품목 번호** 필드의 드롭다운 목록에서 원하는 레코드를 선택합니다. 데모 데이터 회사 USMF를 사용하는 경우 **A0001** 을 선택합니다.  
3. **사이트** 필드의 드롭다운 목록에서 원하는 레코드를 선택합니다. 데모 데이터 회사 USMF를 사용하는 경우 사이트 **2** 를 선택합니다.
4. **창고** 필드의 드롭다운 목록에서 원하는 레코드를 선택합니다. 데모 데이터 회사 USMF를 사용하는 경우 창고 **24** 를 선택합니다.  
5. **위치** 필드의 드롭다운 목록에서 원하는 레코드를 선택합니다. 데모 데이터 회사 USMF를 사용하는 경우 위치 **BULK-001** 을 선택합니다.  
6. 집계됨 필드에 숫자를 입력합니다. **보유** 필드에 표시된 숫자와 다른 계산된 숫자를 입력하는 경우 **수량** 필드가 불일치를 표시하도록 업데이트됩니다.  
7. **저장** 을 선택합니다.

## <a name="post-the-inventory-counting-journal"></a>재고 실사 분개 기장
1. **게시** 를 선택합니다. 재고 실사 분개를 게시할 때 실사 금액이 실사에 보고된 금액과 다른 경우 **보유** 필드에 재고 입고 또는 출고가 전기되고 재고 수준 및 값이 변경되고 원장 트랜잭션이 생성됩니다.
2. **확인** 을 선택합니다.

## <a name="view-inventory-transactions"></a>재고 거래 조회
1. **재고** 를 선택합니다.
2. **트랜잭션** 을 선택합니다. 여기에서 재고 실사 저널을 게시할 때 생성될 모든 관련 트랜잭션을 볼 수 있습니다.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]