---
title: 최소 재고 이벤트를 사용하여 칸반 규칙 생성
description: 이 절차는 특정 제품이 특정 위치에서 항상 사용 가능하도록 하기 위해 최소 재고 이벤트를 사용하여 칸반 규칙을 생성하는 데 필요한 설정에 중점을 둡니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd7e02a8a3bf62606c680dad91d46658775138df
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447931"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>최소 재고 이벤트를 사용하여 칸반 규칙 생성

[!include [banner](../../includes/banner.md)]

이 절차는 특정 제품이 특정 위치에서 항상 사용 가능하도록 하기 위해 최소 재고 이벤트를 사용하여 칸반 규칙을 생성하는 데 필요한 설정에 중점을 둡니다. 재고 수준이 200개 미만으로 떨어지면 자재를 해당 위치로 옮기는 칸반 규칙이 생성됩니다. 페깅 이벤트 처리를 실행하여 필요한 칸반이 생성됩니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 공정 엔지니어 또는 가치 흐름 관리자가 린 호나경에서 새 제품 또는 수정된 제품의 생산을 준비할 때 사용합니다.


## <a name="create-a-new-kanban-rule"></a>새 칸판 규칙 만들기
1. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 유형 필드에서 '철회'를 선택합니다.
    * 이 유형은 이전 칸반을 생성하는 데 사용됩니다.  
4. 보충 전략 필드에서 '이벤트'를 선택합니다.
    * 이벤트 전략은 이벤트를 기반으로 칸반 전송을 생성하기 위해 사용됩니다. 절차의 뒷부분에서 재고 보충을 사용하여 칸반 이전을 트리거합니다.  
5. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * ReplenishSpeakerComponents를 입력 또는 선택합니다. 이 이전 활동에는 입고(출력) 창고와 위치 12가 있습니다. 이는 자재가 창고 12의 위치 12로 이동됨을 의미합니다.  
6. 세부 정보 섹션을 확장합니다.
7. 제품 필드에서 값을 입력하거나 선택합니다.
    * M0007을 선택합니다.  
8. 이벤트 섹션을 확장합니다.
9. 재고 보충 이벤트 필드에서 '일괄'을 선택합니다.
    * 이렇게 하면 페깅 이벤트 처리 중에 관련 위치에서 자재 요구를 충족하기 위해 칸반이 생성됩니다.  

## <a name="set-the-minimum-quantity-for-the-item"></a>항목의 최소 수량 설정
1. 제품 필드에 있는 링크를 따라가려면 클릭합니다.
2. 품목 번호 필드에 있는 링크를 따라가려면 클릭합니다.
3. 제품 이미지 팩트 상자를 확장합니다.
4. 작업 창에서 계획을 클릭합니다.
5. 항목 적용 범위를 클릭합니다.
6. 새로 만들기를 클릭합니다.
7. 목록에서 선택한 행을 표시합니다.
8. 창고 필드 필드에 값을 입력하거나 선택합니다.
    * 창고를 12로 설정합니다.  
9. 최소값을 '200'으로 설정합니다.

## <a name="run-the-batch-event-creation-job"></a>일괄 이벤트 생성 작업 실행
1. 생산 관리 > 정기 작업 > 칸반 작업 일괄 처리 > 페깅 이벤트 처리로 이동합니다.
2. 확인을 클릭합니다.
3. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
    * 이전에 생성한 칸반 규칙을 선택합니다.  
5. 칸반 섹션을 확장합니다.
    * 필요한 자재를 창고 12로 옮기기 위해 칸반이 생성되었음을 알 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]