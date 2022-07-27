---
title: 철회 칸반 규칙 만들기
description: 이 절차는 린 환경에서 자재를 이전하기 위한 철회 칸반 규칙을 만드는 데 필요한 설정을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba30e9d09e9eeb0cd7428aafc1195d6b7e7caaa4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448729"
---
# <a name="create-a-withdrawal-kanban-rule"></a>철회 칸반 규칙 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 린 환경에서 자재를 이전하기 위한 철회 칸반 규칙을 만드는 데 필요한 설정을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 신규 또는 수정된 자재의 보충을 준비하는 프로세스 엔지니어 또는 가치 흐름 관리자를 위한 것입니다.


## <a name="create-new-kanban-rule"></a>새 칸판 규칙 만들기
1. 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 유형 필드에서 '철회'를 선택합니다.
    * 철회 유형은 칸판 규칙에서 자재 또는 상품을 이전하는 데 사용됩니다.  
4. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * ReplenishSpeakerComponents를 선택합니다.   이 활동은 창고 11, 위치 11에서 창고 12 및 위치 12로 구성품을 이동하도록 설정됩니다.  
5. 제품 필드에서 값을 입력하거나 선택합니다.
    * M0007을 선택합니다.  
6. 리드 타임 필드에 숫자를 입력합니다.
    * 예를 들어 60을 입력합니다.  
7. 측정 단위 필드에서 값을 입력하거나 선택합니다.
    * 예를 들어, 분을 입력합니다.  

## <a name="set-quantities-for-kanban"></a>칸반 수량 설정
1. 기본 수량을 '5'로 설정합니다.
    * 각 간판에 대해 이전될 수량입니다.  
2. 고정된 칸반 수량 필드에 '2'을 입력합니다.
    * 활성화되어야 하는 칸반의 양입니다. 이 경우 2개의 칸반이 각각 5개씩 전송합니다.  
3. 경고 경계 최소 필드에 '1'을 입력합니다.
    * 대상에 있어야 하는 전체 칸반의 최소량을 추적하는 데 사용됩니다. 예를 들어 칸반 수량 개요에 사용됩니다.  
4. 경고 경계 최대 수량 필드에 '2'을 입력합니다.
    * 대상에 있어야 하는 전체 칸반의 최대량을 추적하는 데 사용됩니다. 예를 들어 칸반 수량 개요에 사용됩니다.  

## <a name="create-kanbans"></a>칸반 만들기
1. 저장을 클릭합니다.
    * 칸반을 생성하기 전에 칸반 규칙을 저장해야 합니다.  
2. 추가를 클릭합니다.
    * 제안된 '새 칸반 수'가 '고정 칸반 수량'과 동일한 2이기 때문에 활성 칸반이 없습니다.  
3. 만들기를 클릭합니다.
    * 이렇게 하면 두 개의 칸반이 생성됩니다.  
    * 이 철회 칸판 규칙에 대해 각각 5개씩 2개의 칸판이 생성되었습니다.  이 절차의 마지막 단계입니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]