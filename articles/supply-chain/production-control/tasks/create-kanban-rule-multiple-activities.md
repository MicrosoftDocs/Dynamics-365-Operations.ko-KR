---
title: 여러 활동에 대한 칸반 규칙 만들기
description: 이 절차에서는 생산 흐름의 여러 활동을 포함하는 칸반 규칙을 만드는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f55034f4f0557023ce0c659c1e8258214cf8bfa3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448195"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>여러 활동에 대한 칸반 규칙 만들기

[!include [banner](../../includes/banner.md)]

이 절차에서는 생산 흐름의 여러 활동을 포함하는 칸반 규칙을 만드는 방법을 보여줍니다. 이 작업을 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 작업은 공정 엔지니어 또는 가치 흐름 관리자가 린 호나경에서 새 제품 또는 수정된 제품의 생산을 준비할 때 사용합니다.


## <a name="create-a-new-kanban-rule"></a>새 칸판 규칙 만들기
1. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 보충 전략 필드에서 '예약됨'을 선택합니다.
4. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * SpeakerAssemblyAndPolish를 선택합니다.  
5. 다중 활동 확인란을 선택합니다.
    * 목적은 칸반 규칙에 둘 이상의 활동을 포함하는 것입니다. 마지막 계획 활동을 선택할 때 생산 흐름에서 경로를 선택합니다.  
6. 마지막 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * SpeakerTestAndPackaging을 선택합니다. 값을 선택하면 페이지가 자동으로 열립니다. 칸반 흐름 SpeakerAssemblyAndPolish > SpeakerTestAndPackaging을 선택합니다. 확인을 클릭합니다.  
7. 세부 정보 섹션을 확장합니다.
8. 제품 필드에서 값을 입력하거나 선택합니다.
    * 항목 L0006을 선택합니다.  

## <a name="create-kanban-and-view-jobs"></a>칸반 생성 및 작업 보기
1. 칸반 섹션을 확장합니다.
2. 추가를 클릭합니다.
3. 새 칸반 수 필드에 '1'을 입력합니다.
    * 이렇게 하면 칸반이 하나 생성됩니다.  
4. 제품 수량을 '3'으로 설정합니다.
    * 칸반이 3개의 제품을 처리합니다.  
5. 기한 날짜/시간 필드에 날짜와 시간을 입력합니다.
    * 오늘 입력할 수 있습니다.  
6. 만들기를 클릭합니다.
7. 세부 정보를 클릭합니다.
    * 칸반에는 생산 흐름에서 두 개의 프로세스 작업이 있습니다. 첫 번째는 SpeakerAssemblyAndPolish이고 두 번째는 SpeakerTestAndPackaging입니다.  
    * 마지막 단계입니다!  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]