---
title: BOM 라인 이벤트 칸반 규칙 만들기
description: 이 작업은 혼합된 린 및 클래식 생산 환경에서 생산 BOM 라인에 대한 공급을 보장하기 위해 이벤트 칸반 규칙을 생성하는 데 필요한 설정에 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14cef6279b756ff71872747dfb1ca9e5c8cd8fcc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448783"
---
# <a name="create-a-bom-line-event-kanban-rule"></a>BOM 라인 이벤트 칸반 규칙 만들기

[!include [banner](../../includes/banner.md)]

이 작업은 혼합된 린 및 클래식 생산 환경에서 생산 BOM 라인에 대한 공급을 보장하기 위해 이벤트 칸반 규칙을 생성하는 데 필요한 설정에 중점을 둡니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 공정 엔지니어 또는 가치 흐름 관리자가 새 제품 또는 수정된 제품의 생산을 준비할 때 사용합니다.


## <a name="create-a-new-kanban-rule"></a>새 칸판 규칙 만들기
1. 생산 관리 > 정기 작업 > 칸반 수량 계산 > 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 유형 필드에서 '철회'를 선택합니다.
    * 출금 유형은 이전 칸반을 생성하는 데 사용됩니다.  
4. 보충 전략 필드에서 '이벤트'를 선택합니다.
    * 이벤트 전략은 이벤트를 기반으로 칸반 전송을 생성하기 위해 선택됩니다. 작업 가이드의 뒷부분에서 생산 오더를 추정하여 트리거할 것입니다.  
5. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * ReplenishSpeakerComponents를 입력 또는 선택합니다. 이 이전 활동에는 입고(출력) 창고와 위치 12가 있습니다. 이는 자재가 창고 12의 위치 12로 이동됨을 의미합니다.  
6. 세부 정보 섹션을 확장합니다.
7. 제품 필드에 M0001을 입력하거나 선택합니다.
8. 이벤트 섹션을 확장합니다.
9. BOM 라인 이벤트 필드에서 '자동'을 선택합니다.
    * BOM 라인 이벤트 필드를 자동으로 설정하면 생산 오더 BOM 라인에 대한 자재 요구를 충족하기 위해 간판이 생성됩니다.  
10. 페이지를 닫습니다.

## <a name="create-and-modify-a-new-production-order"></a>새 생산 오더 생성 및 수정
1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
2. 새로운 생산 주문을 클릭합니다.
3. 품목 번호 필드에서 값을 입력하거나 선택합니다.
    * 'L0001'을 입력 또는 선택합니다. 품목 L0001이 품목 L0001에 대한 BOM에 포함되어 있으므로 품목 L0001을 사용합니다.  
4. 만들기를 클릭합니다.
5. 목록에서 L0001 행의 링크를 클릭합니다
6. BOM을 클릭합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. 편집을 클릭합니다.
9. 라인 유형 필드에서 '고정 공급'을 선택합니다.
    * 페깅된 공급을 선택하여 칸반의 공급 생성을 트리거합니다.  
10. 리소스 소비 필드에서 아니요를 선택합니다.
    * 자원 소비 확인란을 선택 취소하면 창고를 변경할 수 있습니다.  
11. 인벤토리 차원 섹션을 확장합니다.
12. 창고 필드에 '12'를 입력합니다.
    * 창고는 출금 활동에 대한 출력 창고이므로 12로 설정됩니다.  
13. 위치 필드에 '12'를 입력합니다.
    * 위치는 출금 활동에 대한 출력 위치이므로 12로 설정됩니다.  
14. 페이지를 닫습니다.
15. 페이지를 닫습니다.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>생산 오더 추정 및 생성된 칸반 보기
1. 견적을 클릭합니다.
    * 생산 오더를 추정하면 품목 M0001을 공급하기 위해 연관된 칸반이 생성됩니다.  
2. 확인을 클릭합니다.
3. 페이지를 닫습니다.
4. 페이지를 닫습니다.
5. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
    * 항목 M0001에 대해 생성된 이벤트 칸반 규칙을 선택합니다.  
7. 칸반 섹션을 확장합니다.
8. 목록에서 선택한 행을 표시합니다.
    * 예상 생산 오더에 대해 M0001을 공급하기 위해 생성된 간판을 확인합니다.  
    * 마지막 단계입니다!  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]