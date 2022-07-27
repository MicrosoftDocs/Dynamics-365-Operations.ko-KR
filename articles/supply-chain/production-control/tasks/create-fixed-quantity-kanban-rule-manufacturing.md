---
title: 제조용 고정 수량 칸반 규칙 생성
description: 이 절차는 린 환경의 작업 셀에서 변환 활동을 트리거하기 위한 고정 제조 간판 규칙을 생성하는 데 필요한 설정에 중점을 둡니다.
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
ms.openlocfilehash: 16299427a8a6c74e43d7f0eb3ecb3edf4a8f08f0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448954"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>제조용 고정 수량 칸반 규칙 생성

[!include [banner](../../includes/banner.md)]

이 절차는 린 환경의 작업 셀에서 변환 활동을 트리거하기 위한 고정 제조 간판 규칙을 생성하는 데 필요한 설정에 중점을 둡니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 공정 엔지니어 또는 가치 흐름 관리자가 새 제품 또는 수정된 제품의 생산을 준비할 때 사용합니다.


## <a name="create-new-kanban-rule"></a>새 칸판 규칙 만들기
1. 칸반 규칙으로 이동합니다.
2. 새로 만들기를 클릭합니다.
    * 기본 유형은 제조이고 보충 전략은 고정입니다. 이러한 매개 변수는 변경할 필요가 없습니다.  
3. 첫 번째 계획 활동 필드에서 값을 입력하거나 선택합니다.
    * 이것은 이 칸반 규칙에 따라 생성된 칸반에 대해 수행될 활동입니다.  'SpeakerTestAndPackaging'을 선택합니다.  
4. 세부 정보 섹션을 확장합니다.
5. 제품 필드에서 값을 입력하거나 선택합니다.
    * L0050을 선택합니다.  
6. 측정 단위 필드에서 값을 입력하거나 선택합니다.
    * 분을 선택합니다.  
7. 리드 타임 필드에 숫자를 입력합니다.
    * 5를 입력합니다.  

## <a name="set-quantities"></a>수량 설정
1. 수량 섹션을 펼칩니다.
2. 기본 수량을 '10'으로 설정합니다.
    * 각 간판에 대해 이전될 수량입니다.  
3. 제품 수량 변수 확인란을 선택합니다.
    * 이를 통해 기본 수량과 차이가 있는 선택된 칸반을 완성할 수 있습니다.  8에서 12 사이의 수량으로 칸반을 완료할 수 있도록 하려면 두 차이를 모두 2로 설정합니다.  
4. 아래의 차이를 '2'로 설정합니다.
    * 이렇게 하면 10 - 2 = 8까지 내릴 수 있습니다.  
5. 위의 차이를 '2'로 설정합니다.
    * 이렇게 하면 10 + 2 = 12까지 올릴 수 있습니다.  
6. 고정된 칸반 수량 필드에 숫자를 입력합니다.
    * 활성화되어야 하는 칸반의 양입니다. 이 경우 5개의 칸반이 각각 10개씩 처리합니다.  
7. 경고 경계 최소 필드에 '2'를 입력합니다.
    * 대상에 있어야 하는 전체 칸반의 최소량을 추적하는 데 사용됩니다. 예를 들어 칸반 수량 개요에 사용됩니다.  
8. 경고 경계 최대 수량 필드에 '4'를 입력합니다.
    * 대상에 있어야 하는 전체 칸반의 최대량을 추적하는 데 사용됩니다. 예를 들어 칸반 수량 개요에 사용됩니다.  
9. 자동 계획 수량 필드에 '1'을 입력합니다.
    * 1로 설정하면 모든 칸반이 자동으로 계획됨을 의미합니다.   3을 입력하면 3개의 빈 칸반이 계획할 준비가 될 때까지 칸반이 계획되지 않습니다. 이것은 작업을 그룹화하고 너무 많은 설정을 피하는 데 유용합니다.  

## <a name="create-kanbans"></a>칸반 만들기
1. 칸반 섹션을 확장합니다.
2. 저장을 클릭합니다.
    * 칸반을 생성하기 전에 칸반 규칙을 저장해야 합니다.  
3. 추가를 클릭합니다.
    * 활성 칸반이 없으므로 제안된 '새 칸반 수'는 5입니다. 이는 '고정 칸반 수량'과 동일합니다.  
4. 만들기를 클릭합니다.
    * 이렇게 하면 5개의 칸반이 생성됩니다.  
    * 이 제조 칸판 규칙에 대해 각각 10개씩 5개의 칸판이 생성되었습니다. 이 절차의 마지막 단계입니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]