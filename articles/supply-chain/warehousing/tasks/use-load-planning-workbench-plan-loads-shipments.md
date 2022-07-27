---
title: 적재 계획 워크벤치를 사용하여 적재 및 선적 계획
description: 이 토픽에서는 적재 계획 워크벤치를 사용하여 판매 주문에 대한 로드를 생성하는 방법을 보여줍니다.
author: Mirzaab
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d641ece709d36d8f3ee29cde47918154835a5bb9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448573"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>적재 계획 워크벤치를 사용하여 적재 및 선적 계획

[!include [banner](../../includes/banner.md)]

이 토픽에서는 적재 계획 워크벤치를 사용하여 판매 주문에 대한 로드를 생성하는 방법을 보여줍니다. 전제 조건으로 먼저 판매 주문을 생성합니다. 이 절차는 운송 코디네이터의 일상 업무의 일부입니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="create-a-sales-order"></a>판매 주문 만들기
1. **탐색 창 > 모듈 > 수취 계정 > 주문 > 모든 판매 주문** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **고객 계정** 에서 드롭다운 단추를 선택하여 조회를 엽니다.
4. 계정 **US-004** 을 선택합니다.
5. **확인** 을 선택합니다.
6. **품목 번호** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
7. 항목 **A0001** 을 선택합니다. **A0001** 이 운송 관리를 위해 활성화됩니다.  
8. **사이트** 필드에서 드롭다운 단추를 선택하여 조회를 연 다음 항목을 선택합니다.
9. **수량** 필드에 숫자를 입력합니다.
10. 이 예에서는 **창고** 필드에 '24'를 입력합니다. 이 창고는 운송 관리 및 고급 창고 관리가 가능합니다.  
11. **저장** 을 선택합니다.
12. 페이지를 닫습니다.

## <a name="create-a-new-load"></a>새 로드 만들기
1. **탐색 창 > 모듈 > 운송 관리 > 계획 > 적재 계획 워크벤치** 로 이동합니다.
2. **판매 라인** 탭을 선택합니다. 이제 방금 생성한 판매 주문에 대한 로드를 빌드합니다. 로드는 구매 주문, 이전 주문 및 판매 주문의 수요와 공급을 기반으로 구축할 수 있습니다.  
3. 작업 창에서 **수요와 공급** 을 선택합니다.
4. **새 로드로** 를 선택합니다.
5. **로드 템플릿 ID** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다. 로드 템플릿은 전체 로드의 무게와 부피에 대한 최대 측정값을 정의합니다. 예를 들어, 로드 템플릿은 컨테이너 또는 트럭의 크기를 나타낼 수 있습니다. 항목을 선택합니다.
6. **확인** 을 선택합니다.

## <a name="rate-and-route-the-load"></a>로드 평가 및 라우팅
1. **평가 및 라우팅** 을 클릭합니다.
2. **평가 경로 워크벤치** 를 선택합니다.
3. **요금 가게** 를 선택합니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. **할당** 을 선택합니다.
6. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]