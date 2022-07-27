---
title: 칸반 수량 제안 계산
description: 이 절차에서는 칸반 수량 계산을 사용하여 특정 칸반 규칙에 대해 칸반 크기와 수량을 최적화하는 데 중점을 둡니다.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18d2a8dd2a8c132873744ba890ca6b1eb1fd34b6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448279"
---
# <a name="calculate-kanban-quantity-suggestions"></a>칸반 수량 제안 계산

[!include [banner](../../includes/banner.md)]

이 절차에서는 칸반 수량 계산을 사용하여 특정 칸반 규칙에 대해 칸반 크기와 수량을 최적화하는 데 중점을 둡니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 가치 흐름 관리자를 위한 것입니다. 칸반 규칙에 새 칸반 수량 계산 정책 추가 절차를 완료해야 합니다.


## <a name="create-a-kanban-quantity-calculation"></a>칸반 수량 계산 생성
1. 생산 관리 > 정기 작업 > 칸반 수량 계산 > 칸반 수량 계산으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 'Speaker2016'을 입력합니다.
4. 이름 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 칸반 규칙에 새 칸반 수량 계산 정책 추가 절차에 만들었던 정책을 선택합니다. 예를 들어 Speaker2016을 선택합니다.  
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. 규칙 활성 날짜 필드에서 날짜와 시간을 '2012-12-17T08:00:00'으로 설정합니다.
    * 이 날짜는 칸반 수량 계산에 포함되는 고정 칸반 규칙을 결정하는 기준이 됩니다.  
7. 이행 수요 기간 시작 날짜 필드에서 날짜와 시간을 '2012-11-17T09:00:00'으로 설정합니다.
    * 칸반 수량을 계산하기 위해 과거 수요 트랜잭션이 포함된 일자입니다.  
8. 이행 수요 기간 종료 날짜 필드에서 날짜와 시간을 '2012-12-17T07:59:59'으로 설정합니다.
    * 칸반 수량을 계산하기 위해 미래 수요 트랜잭션이 포함된 일자입니다.  
9. 수요 기간 시작 날짜 필드에서 날짜와 시간을 '2012-12-17T08:00:00'으로 설정합니다.
    * 칸반 수량을 계산하기 위해 현재 수요 트랜잭션이 포함된 일자입니다.  
10. 수요 기간 종료 날짜 필드에서 날짜와 시간을 '2013-01-16T07:59:59'으로 설정합니다.
    * 칸반 수량을 계산하기 위해 현재 수요 트랜잭션이 포함되기까지의 일자입니다.  

## <a name="generate-kanban-quantity-proposal"></a>칸반 수량 제안 생성
1. 저장을 클릭합니다.
2. 생성을 클릭합니다.
    * 칸반 규칙 000020에 대한 칸반 수량 제안 라인을 생성합니다.  

## <a name="run-kanban-quantity-calculation"></a>칸반 수량 계산 실행
1. 계산을 클릭합니다.
    * 칸반 수량 제안이 계산됩니다.  
2. 확인을 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
    * 제안된 칸반 수량은 2입니다.  

## <a name="change-product-quantity-and-calculate-again"></a>제품 수량 변경 및 다시 계산
1. 제품 수량을 '5'로 설정합니다.
2. 계산을 클릭합니다.
3. 확인을 클릭합니다.
    * 칸반 수량이 5이면 제안이 칸반 수량 4로 변경됩니다.  
    * 이는 제품 수량이 적을수록 수요를 충족시키기 위해 더 많은 칸반이 필요하기 때문에 발생합니다.  

## <a name="update-kanban-rule"></a>칸반 규칙 업데이트
1. 규칙 적용 날짜 필드에 날짜와 시간을 입력합니다.
    * '규칙 활성 날짜 기준'을 미래 날짜로 설정합니다. 예: 오늘 + 1년.  
2. 업데이트를 클릭합니다.
3. 확인을 클릭합니다.
4. 페이지를 닫습니다.

## <a name="validate-change-on-kanban-rule"></a>칸반 규칙 변경 확인
1. 제품 정보 관리 > 린 제조 > 칸반 규칙으로 이동합니다.
2. 목록에서 선택한 행의 링크를 클릭합니다.
    * 이전 하위 작업에서 생성된 칸반 규칙을 선택합니다. 숫자로 정렬된 목록의 첫 번째 칸반 규칙이어야 합니다.  
3. 세부 정보 섹션의 확장을 토글합니다.
    * 이 규칙이 이 날짜까지 활성화되지 않음을 의미하는 유효 날짜를 확인합니다.  
4. 수량 섹션의 확장을 토글합니다.
    * 이는 칸반 수량 계산에 입력한 기본 수량입니다.  
    * 이는 칸반 수량 계산에서 고정 칸반 수량 4입니다.  
5. ListPanel 탭을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]