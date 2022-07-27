---
title: 린 제고를 위한 프로세스 활동 만들기
description: 린 제고를 위한 프로세스 활동을 만듭니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 214e54cc93379948e4c25b3b28d835bbbbd40b72
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448276"
---
# <a name="create-process-activities-for-lean-manufacturing"></a>린 제고를 위한 프로세스 활동 만들기

[!include [banner](../../includes/banner.md)]

린 제고를 위한 프로세스 활동을 만듭니다. 

전제 조건: 

1. 활성 상태가 아닌 생산 흐름 및 버전을 생성해야 합니다.

2. 작업 셀을 생성해야 합니다.


## <a name="find-the-production-flow-version"></a>생산 흐름 버전 찾기
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="create-a-new-activity"></a>새 활동 만들기
1. 활동을 클릭합니다.
    * 선택한 생산 흐름에 초안 버전이 있는지 확인하고 해당 버전을 선택하세요.  
2. 새 계획 활동 만들기를 클릭합니다.
3. 다음을 클릭합니다.
4. 이름 필드에 값을 입력합니다.
5. 이름 필드에 값을 입력합니다.
    * 이름은 모든 버전에 대해 지정된 프로덕션 흐름에 대해 고유해야 합니다.  
6. 절차 수량 필드에 숫자를 입력합니다.
    * 어떤 작업을 처리하더라도 인건비를 계산하기 위한 작업당 최소 수량입니다. 작업 수량이 이 수량과 다를 경우 인건비 차이가 생성됩니다.  
7. 다음을 클릭합니다.

## <a name="select-the-work-cell"></a>작업 셀 선택
1. 작업 셀 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
2. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="define-the-inventory-updates"></a>재고 업데이트 정의
1. 현재고 업데이트 체크박스를 선택하거나 선택 취소합니다.
    * 현재고 갱신 = 아니오인 경우 반제품을 받기 위한 활동을 정의할 수 있습니다(활동이 다음 BOM 레벨에 도달하지 않음).    반제품을 소비하도록 선택할 수도 있습니다.  

## <a name="define-the-picking-activities"></a>피킹 활동 정의
1. 다음을 클릭합니다.
2. 목록에서 선택한 행을 표시합니다.
    * 선택한 작업 셀의 입력 위치에 대한 기본 피킹 활동이 생성됩니다.  
3. 추가를 클릭합니다.
    * 작업 셀 입력 활동에서 준비되지 않은 특정 제품에 대한 추가 피킹 활동을 생성할 수 있습니다.  
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 품목 번호 필드에 값을 입력합니다.
6. 창고 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 이 정의를 사용하면 두 번째 피킹 활동에 정의된 품목을 제외하고 활동에서 소비된 모든 자재가 기본 입력 창고 및 위치에서 피킹됩니다. 이 항목은 다른 창고 및 위치에서 선택됩니다.  
7. 목록에서 원하는 레코드를 찾아 선택합니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
9. 등록 스크랩 확인란을 선택하거나 선택 취소합니다.
10. 다음을 클릭합니다.

## <a name="define-the-activity-times"></a>활동 시간 정의
1. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 런타임 정의가 필요합니다. 런타임은 칸반 작업의 비용 및 처리 시간을 계산하는 데 사용됩니다. 런타임은 생산 흐름 버전 작업에서 파생된 사이클 시간으로 계산되는 최대 수용 작업량 및 소비량을 계산하는 데 사용되지 않습니다.  
2. 시간 필드에 숫자를 입력합니다.
3. 단위 필드에 값을 입력합니다.
4. 시간 단위를 선택합니다.
5. 단위 수량 필드에 숫자를 입력합니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 큐 시간은 선택 사항입니다.  
7. 시간 필드에 숫자를 입력합니다.
8. 단위 필드에 값을 입력합니다.
9. 시간 단위를 선택합니다.
10. 단위 수량 필드에 숫자를 입력합니다.
11. 다음을 클릭합니다.
12. 마침을 클릭합니다.
13. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]