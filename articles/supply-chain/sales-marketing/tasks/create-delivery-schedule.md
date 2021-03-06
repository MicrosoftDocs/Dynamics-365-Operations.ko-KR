---
title: 배송 일정 만들기
description: 이 절차는 판매 주문에 대한 배송 일정을 생성하는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97dbbcc7173dcece9aea833551e8f985246bdbb2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449167"
---
# <a name="create-delivery-schedule"></a>배송 일정 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 판매 주문에 대한 배송 일정을 생성하는 방법을 보여줍니다. 주문 또는 견적의 수량을 여러 배달로 배송하도록 요청되는 하는 경우 배송 일정을 사용합니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 실행할 수 있습니다.


## <a name="create-delivery-schedule"></a>배송 일정 만들기
1. 모든 판매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 고객 계정 필드에서 값을 입력하거나 선택합니다.
4. 확인을 클릭합니다.
5. 품목 번호 필드에서 값을 입력하거나 선택합니다.
6. 수량 필드에 1보다 큰 숫자를 입력합니다.
7. 판매 주문 라인을 클릭합니다.
8. 배송 일정을 클릭합니다.
    * 배송 일정 페이지는 주문 라인의 총 수량을 고객에게 배송할 배송 수량을 지정할 수 있는 곳입니다.    
    * 기본적으로 시스템은 원래 판매 라인의 총 수량 및 기타 납품 상세내역을 첫 번째 납품 일정 라인에 복사합니다. 이 예에서는 두 번째 배송 날짜를 첫 번째 배송 날짜에서 일주일만큼 오프셋하여 두 개의 배송 일정을 생성합니다.  
9. 수량 필드에 총 수량의 일부인 숫자를 입력합니다.
10. 새로 만들기를 클릭합니다.
11. 수량 필드에 남은 수량을 입력합니다.
12. 요청된 배송 날짜 필드에 첫 번째 배송 라인 날짜로부터 일주일 전 날짜를 입력합니다.
    * 요금 변환 빠른 탭의 두 가지 옵션은 요금이 원래 주문 라인에 할당된 후 배달 일정 라인 전체에 요금을 분배하는 방법을 제어합니다. 총액 복사를 선택하면 동일한 비용 금액이 각 라인에 복사됩니다. 납품 라인에 할당 옵션은 비용을 납품 라인에 균등하게 분배합니다.  
    * 고정 비용만 나눌 수 있지만 변동 비용은 계속 라인에 복사됩니다.  
13. 페이지를 업데이트하려면 커서를 두 번째 배달 라인에서 멀리 이동합니다.
    * 총 및 남은 필드를 보면 납품 일정 라인에 할당된 총 수량을 추적할 수 있습니다. 잔여 수량이 0이면 원래 라인의 전체 수량이 스케줄에 할당된 것입니다.   
14. 확인을 클릭합니다.
    * 이제 납품 일정이 주문 라인에 복사되었습니다.   
    * 상업 라인이라고 하는 원래 주문 라인은 여러 납품이 있는 주문 라인으로 변환되었습니다. 이것은 고유한 아이콘으로 표시되며 납품 라인의 헤더 역할을 합니다.  
    * 납품 라인이라고 하는 두 개의 신규 라인이 하나의 납품 일정을 구성합니다. 주문은 원래 라인이 아니라 이러한 라인에 대해 처리됩니다. 확인 전표, 피킹 목록, 포장 전표 또는 송장과 같은 문서를 인쇄하면 납품 라인만 표시됩니다.   
    * 배달 라인은 배달 날짜, 수량, 배달 모드 및 보관 차원(예: 사이트 및 창고)이 다를 수 있습니다. 그러나 제품 치수는 항상 상용 라인의 치수와 일치해야 하며 변경할 수 없습니다.  
15. 수량 필드에 현재 숫자보다 큰 숫자를 입력합니다.
16. 수량 재계산의 효과를 보려면 상업 라인을 선택합니다.
17. 작업 창에서 선별 및 포장을 클릭합니다.
18. 포장 전표 게시를 클릭합니다.
19. 매개 변수 섹션을 펼칩니다.
20. 수량 필드에서 '전체'를 선택합니다.
    * 포장 전표는 원래 주문 라인이 아닌 두 개의 배송 일정 라인에 대해 생성됩니다.  
21. 포장 전표 인쇄 필드에서 예를 선택합니다.
22. 확인을 클릭합니다.
23. 예를 클릭합니다.
24. 페이지를 닫습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]