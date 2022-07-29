---
title: 순환 재고 정의
description: 순환 재고는 현재고 항목을 감사하는 데 사용할 수 있는 창고 프로세스입니다.
author: Mirzaab
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45107dca67ac13669c468c4c32fb4adfdab2195b
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449536"
---
# <a name="define-cycle-counting"></a>순환 재고 정의 

[!include [banner](../../includes/banner.md)]

순환 재고는 현재고 항목을 감사하는 데 사용할 수 있는 창고 프로세스입니다. 이 작업 녹화는 기본 집계 작업 우선순위를 설정하고, 피킹 및 집계 작업을 모두 처리하도록 모바일 디바이스 메뉴 항목을 활성화하고, 위치가 비어 있을 때 집계 임계값 트리거를 사용 설정하고, 특정 창고에서 특정 항목에 대한 순환 재고 계획을 사용하는 방법을 보여줍니다. 일반적으로 이러한 작업은 창고 관리자가 수행합니다. USMF 데모 데이터 회사 또는 자체 데이터에서 이 절차를 진행할 수 있습니다.


## <a name="set-the-priority-of-counting-work"></a>집계 작업의 우선 순위 설정
1. **탐색 창** 에서 **모듈 > 창고 관리 > 설정 > 창고 관리 매개 변수** 로 이동합니다.
2. **순환 재고** 탭을 클릭합니다.
3. **기본 순환 재고 작업 우선순위** 필드에 숫자를 입력합니다. 이 단계는 창고의 다른 유형의 작업과 비교하여 순환 재고 작업의 우선순위를 변경합니다. 다른 유형의 작업에 대한 숫자보다 낮은 숫자를 입력하여 순환 재고 작업의 우선순위를 높입니다.  
4. **저장** 을 클릭합니다.
5. 페이지를 닫습니다.

## <a name="enable-the-mobile-device"></a>모바일 디바이스 사용
1. **탐색 창** 에서 **모듈 > 창고 관리 > 설정 > 모바일 디바이스 > 모바일 디바이스 메뉴 항목** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **메뉴 항목 이름** 필드에 값을 입력합니다.
4. **단위** 필드에 값을 입력합니다.
5. **모드** 필드에서 '작업'을 선택합니다.
6. **기존 작업 사용** 옵션을 예로 설정합니다. 이 옵션을 예로 설정하면 모바일 디바이스 메뉴 항목이 사용될 때 시스템이 기존 작업을 찾습니다.  
7. **지시자** 필드에서 '시스템 감독'을 선택합니다. "시스템 지시"가 선택되면 창고 작업자는 정의된 작업 클래스에 있는 작업을 열도록 지시를 받습니다. (이 작업 클래스는 다음에 만들 게 됩니다.)  
8. **작업 클래스** 빠른 탭을 확장합니다. 다음으로 이 모바일 디바이스 메뉴 항목과 함께 사용할 두 개의 작업 클래스를 생성합니다. 메뉴 항목을 사용할 때 이러한 작업 클래스를 쿼리하고 가장 높은 우선 순위의 작업을 사용자에게 보여줍니다.  
9. **새로 만들기** 를 클릭합니다.
10. **작업 클래스 ID** 필드에 값을 선택합니다.
11. **새로 만들기** 를 클릭합니다.
12. **작업 클래스 ID** 필드에 값을 선택합니다.
13. **작업 창** 에서 **저장** 을 클릭합니다.
14. 페이지를 닫습니다.
15. **탐색 창** 에서 **모듈 > 창고 관리 > 설정 > 모바일 디바이스 > 모바일 디바이스 메뉴** 로 이동합니다.
16. 목록에서 원하는 레코드를 찾아 선택합니다.
17. 트리에서 '방금 생성한 메뉴 항목'을 선택합니다.
18. **편집** 을 클릭합니다.
19. 화살표를 클릭하여 메뉴 항목을 메뉴에 추가합니다.
20. **저장** 을 클릭합니다.

## <a name="create-a-counting-threshold"></a>집계 임계값 생성
1. **탐색 창** 에서 **모듈 > 창과 관리 > 설정 > 순환 재고 > 순환 재고 임계값** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **순환 재고 임계값** 필드에 값을 입력합니다.
4. **즉시 순환 재고 처리** 옵션을 예로 설정합니다.
5. **설명** 필드에 값을 입력합니다.
6. **저장** 을 클릭합니다.
7. **위치 선택** 을 클릭합니다.
8. 목록에서 선택한 행을 표시합니다.
9. **기준** 필드에서 값을 선택합니다.
10. **확인** 을 클릭합니다.
11. 페이지를 닫습니다.

## <a name="create-a-cycle-count-plan"></a>순환 재고 계획 생성
1. **탐색 창** 에서 **모듈 > 창과 관리 > 설정 > 순환 재고 > 순환 재고 계획** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **순환 재고 계획 ID** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **최대 순환 재고 수** 필드에 숫자를 입력합니다.
6. **저장** 을 클릭합니다.
7. **위치 선택** 을 클릭합니다.
8. 목록에서 선택한 행을 표시합니다.
9. **기준** 필드에서 값을 선택합니다.
10. **확인** 을 클릭합니다.
11. **순환 재고 주기(일)** 필드에 숫자를 입력합니다. 예를 들어, **순환 재고 주기(일)** 필드가 5로 설정된 경우 순환 재고 작업은 5일마다 생성됩니다. 단, 3일째에 순환 재고 작업을 처리한 경우에는 마지막 순환 재고가 처리된 후 5일 후인 8일에 다음 순환 재고 작업이 생성됩니다.  
12. **저장** 을 클릭합니다.
13. **새로 만들기** 를 클릭합니다.
14. **시퀀스 번호** 필드에 번호를 입력합니다. 정렬은 가장 작은 숫자부터 가장 큰 숫자까지입니다. 값은 0(영)보다 커야 합니다.  
15. 목록에서 선택한 행을 표시합니다.
16. **설명** 필드에 값을 입력합니다.
17. **저장** 을 클릭합니다.
18. **제품 정의** 쿼리를 클릭합니다.
19. 목록에서 선택한 행을 표시합니다.
20. **기준** 필드에서 값을 입력하거나 선택합니다.
21. **확인** 을 클릭합니다.
22. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]