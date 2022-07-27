---
title: 칸반 규칙에 칸반 수량 계산 정책 추가
description: 이 절차에서는 칸반 수량 계산 정책을 생성하고 이를 칸반 규칙에 추가하여 칸반 크기와 수량을 최적화하는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a844d455b1e583f234ddc47280f5cac8ee0ab852
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449200"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>칸반 규칙에 칸반 수량 계산 정책 추가

[!include [banner](../../includes/banner.md)]

이 절차에서는 칸반 수량 계산 정책을 생성하고 이를 칸반 규칙에 추가하여 칸반 크기와 수량을 최적화하는 데 중점을 둡니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 가치 흐름 관리자를 위한 것입니다. 이 절차는 칸반 수량 제안 계산 절차를 생성하기 위한 전제 조건입니다. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>칸반 수량 계산 정책 생성
1. 생산 관리 > 정기 작업 > 칸반 수량 계산 > 칸반 수량 계산 정책으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력합니다.
    * 예를 들어 Speaker2016을 입력합니다.  
4. 기준 계획 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 수요를 계산하려면 StaticPlan을 선택합니다.  
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 저장을 클릭합니다.
8. 최소 칸반 수량 필드에 '1'을 입력합니다.
    * 칸반 수량 계산에 포함된 칸반의 추가 수입니다.  
9. 안전계수를 '1'로 설정합니다.
    * 이는 안전재고의 추가 수량을 계산하는 데 사용되는 요소입니다.  
10. 앞으로의 일 필드에 '30'을 입력합니다.
    * 수요 계산에 포함된 칸반 수량 계산 일자 이전의 일수입니다.  
11. 이후의 일 필드에 '30'을 입력합니다.
    * 수요 계산에 포함된 칸반 수량 계산 일자 이후의 일수입니다.  계산에 사용된 공식은 실제 값과 함께 표시됩니다. 예를 들어 칸반 수량 = ((평균 일일 수요 x 리드 타임 x 2.00) / 취급 단위당 제품 수량) + 1  
12. 페이지를 닫습니다.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>칸반 규칙에 칸반 수량 계산 정책 추가
1. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이 절차에 대해 칸반 규칙 000020를 선택합니다.  
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. Kanban 수량 계산 정책 섹션의 확장을 토글합니다.
5. 추가를 클릭합니다.
    * 이전 하위 작업에서 방금 생성한 칸반 수량 계산 정책을 추가합니다.  
6. 목록에서 선택한 행을 표시합니다.
7. 이름 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
    * 이전 하위 작업에서 방금 생성한 정책 Speaker2016을 선택합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]