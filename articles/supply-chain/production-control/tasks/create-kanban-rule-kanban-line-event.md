---
title: 칸반 라인 이벤트를 사용하여 칸반 규칙 생성
description: 이 절차에서는 칸반 라인 이벤트 설정을 사용하여 프로세스 활동에서 풀을 트리거하여 칸반 규칙을 생성합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7aaf959db0f0a136fc615f9a57ec787ef6cf2ad
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449185"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>칸반 라인 이벤트를 사용하여 칸반 규칙 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 칸반 라인 이벤트 설정을 사용하여 프로세스 활동에서 풀을 트리거하여 칸반 규칙을 생성합니다. 칸반 규칙은 각 25개 이상의 수량이 있는 칸반 프로세스 활동에 의해 트리거됩니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 공정 엔지니어 또는 가치 흐름 관리자가 린 호나경에서 새 제품 또는 수정된 제품의 생산을 준비할 때 사용합니다.


## <a name="create-a-kanban-rule"></a>칸판 규칙 만들기
1. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 보충 전략 필드에서 '이벤트'를 선택합니다.
    * 이렇게 하면 수요에서 직접 간판을 생성합니다. 주문 제작 시나리오를 정의하는 규칙을 설정하는 데 사용됩니다.  
4. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * SpeakerAssemblyAndPolish를 입력 또는 선택합니다. 제조 칸반 규칙의 첫 번째 활동은 생산 흐름의 프로세스 활동입니다. 활동을 선택하면 활동의 유효 일자가 칸반 규칙의 유효 일자로 복사됩니다.  
5. 세부 정보 섹션을 확장합니다.
6. 제품 필드에 'L0001'을 입력합니다.
7. 이벤트 섹션을 확장합니다.
8. 칸반 라인 이벤트 필드에서 '자동'을 선택합니다.
    * 그러면 요청 시 이벤트 칸반이 생성됩니다.  이 필드는 다운스트림 프로세스 활동에 필요한 자재를 보충하는 칸반 규칙을 구성하는 데 사용됩니다. 자동을 선택하면 수요와 함께 이벤트 칸반이 생성됩니다. 이 설정은 같은 날에 생산을 실행할 것으로 예상되는 경우 권장됩니다.  
9. 최소 이벤트 수량을 '25'로 설정합니다.
    * 이벤트 칸반은 수요 수량이 이 필드보다 크거나 같을 때 생성됩니다. 이것은 한 기계에서는 이 필드보다 적은 주문 수량을 생산하고 다른 기계에서는 이 필드보다 많은 주문 수량을 생산하려는 경우에 유용합니다.  
10. 저장을 클릭합니다.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>판매 주문 생성 및 칸반 체인 트리거
1. 영업 및 마케팅 > 판매 주문 > 모든 판매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 고객 계정 필드에서 값을 입력하거나 선택합니다.
    * 고객 계정 US-003, Forest Wholesales를 선택합니다.  
4. 확인을 클릭합니다.
5. 품목 번호 필드에 'L0001'을 입력합니다.
    * L0001은 칸반 규칙을 생성한 항목입니다.  
6. 수량을 '27'로 설정합니다.
    * 27은 칸반 규칙의 최소 수량인 25보다 높기 때문에 이벤트 칸반이 트리거됩니다.  
7. 사이트 필드에 '1'을 입력합니다.
8. 창고 필드 필드에 값을 입력하거나 선택합니다.
    * 창고 13을 선택합니다.  
9. 저장을 클릭합니다.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>칸반 규칙에 의해 생성된 칸반 보기
1. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 칸반 섹션을 확장합니다.
    * 생성된 칸반 규칙에 따라 활동을 처리하기 위해 27에 대한 칸반이 생성되었음을 알 수 있습니다.  
    * 마지막 단계입니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]