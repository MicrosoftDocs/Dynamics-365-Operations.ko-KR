---
title: 사이트 일정 만들기
description: 이 절차에서는 사이트에 대해 아직 시작되지 않은 생산 주문를 예약하는 방법을 보여줍니다.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146531217f7f596a5cb98e271b0356ffeb3d5547
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447997"
---
# <a name="create-a-schedule-for-a-site"></a>사이트 일정 만들기

[!include [banner](../../includes/banner.md)]

이 절차에서는 사이트에 대해 아직 시작되지 않은 생산 주문를 예약하는 방법을 보여줍니다.  데모 데이터 회사 USMF를 사용하여 이 절차를 완료합니다.


## <a name="identify-production-orders-that-are-not-started"></a>시작되지 않은 생산 주문 식별
1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 '1'인 사이트 필드를 필터링합니다.
    * 1은 USMF의 사이트를 나타냅니다. USMF를 사용하지 않는 경우 자신의 회사에서 사이트를 선택합니다.  
3. 상태 열 필터를 엽니다.
4. "정확함" 필터 연산자를 사용하여 "예약됨" 값으로 "상태" 필드에 필터를 적용합니다.

## <a name="create-a-schedule"></a>일정 만들기
1. 목록에서 모든 행을 표시하거나 표시 해제합니다.
2. 작업 창에서 예약을 클릭합니다.
3. 작업 예약을 클릭합니다.
4. 예약 지침 필드에서 '배달 날짜로부터 뒤로'를 선택합니다.
5. 유한 용량 필드에서 아니요를 선택합니다.
6. 유한 자재 필드에서 아니요를 선택합니다.
7. 확인을 클릭합니다.
    * 시간이 좀 걸릴 수 있습니다.  

## <a name="view-the-result-of-scheduled-production-orders"></a>예약된 생산 주문의 결과 보기
1. 목록에서 선택한 행을 표시합니다.
    * 모든 행을 표시할 수 있습니다.  
2. 작업 창에서 생산 주문을 클릭합니다.
3. 모든 작업을 클릭합니다.
    * 이 페이지에서 작업 목록을 볼 수 있습니다. 일정 탭에서 작업의 시작 날짜와 종료 날짜를 볼 수 있습니다.  
4. 자재를 클릭합니다.
    * 이 페이지에서 생산 주문의 작업에 대한 예상 자재 소비와 현재 사용 가능한 재고를 볼 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]