---
title: 판매 이벤트 칸반 규칙 만들기
description: 이 절차는 판매 주문 생성 과정 중에 트리거되는 칸반 규칙을 만드는 데 필요한 설정에 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cd2b579e542b9f905fc51b63f2120e5a5c883ae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447934"
---
# <a name="create-a-sales-event-kanban-rule"></a>판매 이벤트 칸반 규칙 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 판매 주문 생성 과정 중에 트리거되는 칸반 규칙을 만드는 데 필요한 설정에 중점을 둡니다. 이벤트 칸반 규칙은 판매 주문 라인에서 발생하는 소요량을 보충합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 공정 엔지니어 또는 가치 흐름 관리자가 새 제품 또는 수정된 제품의 생산을 준비할 때 사용합니다.




## <a name="create-a-new-kanban-rule"></a>새 칸판 규칙 만들기
1. 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 보충 전략 필드에서 '이벤트'를 선택합니다.
    * 이벤트 선택은 칸반 규칙이 판매 주문 라인 생성과 같은 이벤트에 의해 트리거됨을 의미합니다.   이는 각 칸반이 특정 수요를 충족해야 하는 영역에 적용됩니다.  
4. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * 최종 어셈블리를 선택합니다.  
5. 세부 정보 섹션을 확장합니다.
6. 제품 필드에서 값을 입력하거나 선택합니다.
    * L0050을 선택합니다.  

## <a name="define-an-event"></a>이벤트 정의
1. 이벤트 섹션을 확장합니다.
2. 판매 이벤트 필드에서 '자동'을 선택합니다.
    * 자동 판매 이벤트를 선택하면 판매 라인이 제품 및 입고 위치와 일치할 때 이 칸반 규칙이 자동으로 트리거됩니다. 이 절차에서는 창고 13에 있는 제품 L0050입니다.  
3. 최소 이벤트 수량을 '50'으로 설정합니다.
    * 최소 이벤트 수량이 50인 경우 칸반 규칙은 수량이 50개 이상인 이벤트에 의해서만 트리거됩니다.  
4. 생산 흐름 섹션을 확장합니다.
    * 입고 위치는 창고 13입니다. 이는 이 칸반 규칙이 이 위치에 대해 트리거됨을 의미합니다.  
    * 이 예에서 창고 13에 있는 수량 50개 이상의 제품 L0050에 대한 판매 라인은 이 칸반 규칙을 트리거합니다.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>이벤트 칸판 규칙을 트리거하는 판매 라인 만들기
1. 모든 판매 주문으로 이동합니다.
    * 칸반 규칙이 저장되면 경고가 표시됩니다. 즉, 판매 주문 생성 중에 칸반이 실시간으로 생성됩니다.  
2. 새로 만들기를 클릭합니다.
3. 고객 계정 필드에서 값을 입력하거나 선택합니다.
    * 예를 들어 US-003을 선택합니다.  
4. 확인을 클릭합니다.
5. 품목 번호 필드에 'L0050'을 입력합니다.
6. 사이트 필드에 '1'을 입력합니다.
    * 창고 13이 사이트 1에 있으므로 사이트 1을 선택합니다.  
7. 창고 필드 필드에 값을 입력하거나 선택합니다.
    * 창고를 13으로 설정합니다.  
8. 수량을 '75'으로 설정합니다.
    * 50개 이상의 수량을 입력하여 생성된 간판 규칙을 실행합니다.  

## <a name="verify-that-kanban-is-created"></a>칸반이 생성되었는지 확인
1. 제품 및 공급을 클릭합니다.
2. 페깅 트리 보기를 누릅니다.
    * 판매 라인과 동일한 수량의 칸판이 생성됩니다. L0050 생산에 필요한 물질적 이슈도 볼 수 있습니다. 이 절차의 마지막 단계입니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]