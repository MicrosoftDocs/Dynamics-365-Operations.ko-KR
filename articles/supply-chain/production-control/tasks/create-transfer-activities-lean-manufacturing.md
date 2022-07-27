---
title: 린 제조를 위한 이전 활동 만들기
description: 린 제조를 위한 이전 활동을 만듭니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eee0fd510639f2dad78fecb6395c0e31154db6b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448075"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>린 제조를 위한 이전 활동 만들기

[!include [banner](../../includes/banner.md)]

린 제조를 위한 이전 활동을 만듭니다. 

전제 조건: 

1. 활성 상태가 아닌 생산 흐름 및 버전을 생성해야 합니다.

2. 시작 및 종료 창고 및 위치를 생성해야 합니다. 선택적으로 보충 또는 보충 작업 셀을 생성해야 합니다.


## <a name="find-the-production-flow-version"></a>생산 흐름 버전 찾기
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 생산 흐름에는 초안 상태의 버전이 있어야 합니다.  
3. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="create-a-new-activity"></a>새 활동 만들기
1. 활동을 클릭합니다.
    * 선택한 생산 흐름에 초안 버전이 있는지 확인하고 해당 버전을 선택하세요.  
2. 새 계획 활동 만들기를 클릭합니다.
3. 다음을 클릭합니다.
4. 이름 필드에 값을 입력합니다.
5. 활동 유형 필드에서 '이전'을 선택합니다.
6. 절차 수량 필드에 숫자를 입력합니다.
7. 다음을 클릭합니다.

## <a name="select-the-work-cells"></a>작업 셀 선택
1. 보충 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 작업 셀 출력 위치를 전송 활동의 시작 위치로 사용하려면 작업 셀을 선택합니다. 이동 활동의 대상 위치를 설정하는 보충된 작업 셀에서도 동일한 작업을 수행할 수 있습니다.  
2. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="define-the-inventory-updates"></a>재고 업데이트 정의
1. 제품 유형 필드에서 옵션을 선택합니다.
    * 이전한다고 해서 제품 유형이 변경되는 것은 아닙니다. 완제품 또는 반제품을 이전할 수 있습니다(생산 흐름과 칸반 흐름의 두 활동 간 이전).     완제품을 이전할 때 선택 또는 입고로 인해 재고 트랜잭션이 발생하는지 선택할 수 있습니다.  

## <a name="define-the-transfer-locations"></a>이전 위치 정의
1. 다음을 클릭합니다.
2. 창고 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 위치 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 화물 운송 필드에서 '배송업체'를 선택합니다.
    * 옵션은 다음과 같습니다. 배송업체 - 배송 창고를 운영하는 조직, 수령인 - 입고 창고를 운영하는 조직, 운송업체 - 제3자 공급업체. 운영 조직이 공급업체인 경우 이전 활동에는 하도급 계약이 필요합니다.  
8. 다음을 클릭합니다.

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