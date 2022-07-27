---
title: 부분 위치 순환 재고 프로세스 정의
description: 순환 재고 계획을 사용하여 집계 작업을 생성할 때 해당 위치의 모든 현재고 대신 특정 제품 및 제품 변형만 실사하도록 요청하여 실제 집계 작업을 안내할 수 있습니다.
author: Mirzaab
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c179b7f6e0b8546e20204a971cb2951c7b62d7b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449254"
---
# <a name="define-partial-location-cycle-counting-process"></a>부분 위치 순환 재고 프로세스 정의 

[!include [banner](../../includes/banner.md)]

순환 재고 계획을 사용하여 집계 작업을 생성할 때 해당 위치의 모든 현재고 대신 특정 제품 및 제품 변형만 실사하도록 요청하여 실제 집계 작업을 안내할 수 있습니다. 특정 제품을 필터링함으로써 창고 관리자는 검토 오버헤드를 줄이고 전체적인 실수를 방지하며 시간을 절약할 수 있습니다. 일반적으로 창고 관리자는 일정 작업을 수행합니다. USMF 데모 데이터 회사 또는 자체 데이터에서 이 절차를 진행할 수 있습니다.


## <a name="create-a-cycle-counting-work-template"></a>순환 재고 작업 템플릿 생성
1. 창고 관리 > 설정 > 작업 > 작업 템플릿으로 이동합니다.
2. 작업 주문 유형 필드에서 '순환 재고'를 선택합니다.
3. 새로 만들기를 클릭합니다.
4. 시퀀스 번호 필드에 번호를 입력합니다.
    * 정렬 순서는 가장 작은 숫자부터 가장 큰 숫자까지입니다. 값은 0(영)보다 커야 합니다.  
5. 목록에서 선택한 행을 표시합니다.
6. 작업 템플릿 필드에 값을 입력합니다.
7. 작업 템플릿 설명 필드에 값을 입력합니다.
8. 작업 풀 ID 필드에서 값을 입력하거나 선택합니다.
9. 작업 우선 순위 필드에 숫자를 입력합니다.
10. 저장을 클릭합니다.
11. 새로 만들기를 클릭합니다.
12. 목록에서 선택한 행을 표시합니다.
13. 작업 유형 필드에서 '집계'를 선택합니다.
14. 작업 클래스 ID 필드에서 값을 입력하거나 선택합니다.
15. 저장을 클릭합니다.
16. 작업 줄 바꿈을 클릭합니다.
17. 새로 만들기를 클릭합니다.
18. 시퀀스 번호 필드에 번호를 입력합니다.
    * 정렬 순서는 가장 작은 숫자부터 가장 큰 숫자까지입니다. 값은 0(영)보다 커야 합니다.  
19. 저장을 클릭합니다.
20. 페이지를 닫습니다.
21. 페이지를 닫습니다.

## <a name="create-a-cycle-counting-plan"></a>순환 재고 계획 생성
1. 창고 관리 > 설정 > 순환 재고 > 순환 재고 계획으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 순환 재고 계획 ID 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 최대 순환 재고 수 필드에 숫자를 입력합니다.
6. 작업 템플릿 필드에서 값을 입력하거나 선택합니다.
7. 새로 만들기를 클릭합니다.
8. 시퀀스 번호 필드에 번호를 입력합니다.
    * 정렬 순서는 가장 작은 숫자부터 가장 큰 숫자까지입니다. 값은 0(영)보다 커야 합니다.  
9. 설명 필드에 값을 입력합니다.
10. 저장을 클릭합니다.
11. 제품 정의 쿼리를 클릭합니다.
12. 목록에서 선택한 행을 표시합니다.
13. 기준 필드에서 값을 입력하거나 선택합니다.
14. 확인을 클릭합니다.
15. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]