---
title: 작업 및 작업 일정을 사용하여 생산 주문 일정 잡기
description: 이 토픽은 작업 예약 및 작업 예약을 통해 생산 주문 예약에 중점을 둡니다.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91fe5aa398cd94e38beea017d6d60ecb44f17e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448717"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>작업 및 작업 일정을 사용하여 생산 주문 일정 잡기

[!include [banner](../../includes/banner.md)]

이 토픽은 작업 예약 및 작업 예약을 통해 생산 주문 예약에 중점을 둡니다. 작업(operation) 일정을 사용하면 작업이 생성되지 않지만 작업(job) 일정을 사용하면 작업이 생성됩니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 개별 제조 환경에서 작업하는 생산 관리자, 생산 계획자 또는 작업 현장 감독자를 위한 것입니다.


## <a name="create-a-production-order"></a>생산 주문 생성
1. 탐색 창에서 **모듈 > 생산 제어 > 생산 주문 > 모든 생산 주문** 으로 이동합니다.
2. **새로운 생산 주문** 을 선택합니다.
3. **품목 번호** 필드에서 값을 입력하거나 선택합니다. 품목 번호 **D0001** 을 선택합니다.  
4. **만들기** 를 선택합니다.

## <a name="schedule-operations-for-the-production-order"></a>생산 주문에 대한 작업 예약
1. 새로 생성된 행을 표시합니다.      
2. 작업 창에서 **예약** 을 선택합니다.
3. **작업 예약** 을 선택합니다.
4. **일정 방향** 필드에서 **일정 날짜부터 앞으로** 를 선택합니다.
5. **예약 날짜** 필드에 날짜를 입력합니다. 예를 들어 오늘과 일주일을 더한 미래 날짜를 선택합니다. 선택한 예약 방향으로 생산 주문은 이 날짜부터 앞으로 예약됩니다.  
6. **확인** 을 선택합니다.
7. 목록에서 선택한 행을 표시합니다. 상태가 **예약됨** 으로 변경됩니다. 
8. **모든 작업** 을 선택합니다. 작업 예약으로 생성되는 작업은 없습니다.  
9. 페이지를 닫습니다.

## <a name="schedule-jobs-for-the-production-order"></a>생산 주문에 대한 작업 예약
1. 작업 창에서 **예약** 을 선택합니다.
2. **작업 예약** 을 선택합니다.
3. **일정 방향** 필드에서 **일정 날짜부터 앞으로** 를 선택합니다.
4. **예약 날짜** 필드에 날짜를 입력합니다. 예를 들어 오늘과 일주일을 더한 미래 날짜를 선택합니다. 선택한 예약 방향으로 생산 주문은 이 날짜부터 앞으로 예약됩니다.  
5. **확인** 을 선택합니다.
6. 작업 창에서 **생산 주문** 을 선택합니다.
7. **모든 작업** 을 선택합니다. 활성 경로를 기반으로 작업 예약으로 5개의 작업이 생성됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]