---
title: 판매 주문에서 린 페깅
description: 이 절차는 칸반으로 품목이 생산되는 판매 라인에서 페깅 트리를 검증하는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8eca21f8bd988ca352c07e839295b3edd9669929
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449332"
---
# <a name="lean-pegging-from-sales-orders"></a>판매 주문에서 린 페깅

[!include [banner](../../includes/banner.md)]

이 절차는 칸반으로 품목이 생산되는 판매 라인에서 페깅 트리를 검증하는 데 중점을 둡니다. 페깅 트리를 검증한 후 모든 칸반 작업이 계획됩니다. 이는 주문 접수자가 생산을 즉시 시작할 수 있도록 해야 하는 주문 시나리오에 유용합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 린 회사에서 일하는 고급 주문 접수자를 위한 것입니다.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>칸반 통제 품목에 대한 판매 주문 생성
1. 모든 판매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 고객 계정 필드에서 값을 입력하거나 선택합니다.
    * US-001을 사용합니다.  
4. 확인을 클릭합니다.
5. 품목 번호 필드에 'L0001'을 입력합니다.
6. 수량을 30으로 설정합니다.
    * 이벤트 칸반 규칙을 트리거하려면 수량이 24보다 커야 합니다.  

## <a name="open-a-pegging-tree"></a>페깅 트리 열기 
1. 제품 및 공급을 클릭합니다.
2. 페깅 트리 보기를 누릅니다.
    * 페깅 트리에는 판매 주문 라인에 필요한 모든 레벨의 페깅이 표시됩니다. 이 경우 두 가지 수준의 칸반과 필요한 모든 구성 요소가 있습니다.  

## <a name="plan-the-pegging-tree"></a>업스트림 페깅 트리 계획
1. 트리에서 'Sales line 000832\Kanban 000558'을 선택합니다.
2. 칸반 작업 섹션을 확장합니다.
    * 칸반 작업의 작업 상태는 계획되지 않음입니다.  
3. 전체 페깅 트리 계획을 누릅니다.
    * 이것은 페깅 트리의 모든 칸반 작업을 계획하고 직무 상태를 계획되지 않음에서 계획됨으로 변경합니다.  
4. 페이지를 새로 고칩니다.
    * 칸반 작업 상태가 계획되지 않음에서 계획됨으로 변경되었음을 알 수 있습니다.  
5. 트리에서 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'를 선택합니다.
    * 전체 페깅 트리가 계획되므로 두 번째 칸반에 대한 작업도 계획됩니다. 칸반 작업 상태가 계획되지 않음에서 계획됨으로 변경됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]