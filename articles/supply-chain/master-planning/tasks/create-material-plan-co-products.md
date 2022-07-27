---
title: 부산물에 대한 자재 계획 작성
description: 생산 계획자는 배합표 부산물인 품목에 대한 자재 소요량을 계획합니다.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: deae0d7e0295aa02f5ad512f67e9e3d2148c2e33
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449095"
---
# <a name="create-a-material-plan-for-co-products"></a>부산물에 대한 자재 계획 작성

[!include [banner](../../includes/banner.md)]

생산 계획자는 배합표 부산물인 품목에 대한 자재 소요량을 계획합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USP2입니다.

## <a name="create-requirement-for-a-co-product"></a>부산물에 대한 요구 사항 생성

1. **영업 및 마케팅 \> 작업 영역 \> 판매 주문 처리 및 조회** 로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **판매 주문** 을 선택합니다.
1. **고객 계정** 필드에 값을 입력합니다.
    * 예: US-001  
1. **확인** 을 선택합니다.
1. **품목 번호** 필드에 값을 입력합니다.
    * 예: P6003  
1. **수량** 필드에 숫자를 입력합니다.
    * 예: 50000  
1. **저장** 을 선택합니다.

## <a name="create-a-material-plan-for-co-products"></a>부산물에 대한 자재 계획 작성

1. 페이지를 닫습니다.
1. 페이지를 닫습니다.
1. **마스터 플랜** 을 선택합니다.
1. **플랜** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
1. 목록에서 선택한 행의 링크를 선택합니다.
    * 예: MasterPlan  
1. **실행** 을 선택합니다.
1. **포함할 레코드** 섹션을 펼치거나 접습니다.
1. **필터** 를 선택합니다.
1. 목록에서 **필드** = *품목 번호* 인 행을 선택합니다.
1. **기준** 필드에 값을 입력합니다.
    * 예: P6003  
1. **확인** 을 선택합니다.
1. **확인** 을 선택합니다.
1. **계획된 주문** 을 선택합니다.
1. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 'P6000'인 **품목 번호** 필드를 필터링합니다.
    * 판매 주문을 생성한 항목의 부산물이 있는 공식 항목으로 필터링합니다.  
1. 목록에서 선택한 행을 표시합니다.
    * 필터에서 반환된 행을 선택합니다.  
1. 목록에서 선택한 행의 링크를 선택합니다.
1. **페깅** 섹션을 펼칩니다.
1. 목록에서 선택한 행의 링크를 선택합니다.
    * 계획된 주문은 공동 제품의 판매 주문에 페깅됩니다.  
1. 페이지를 닫습니다.

## <a name="create-a-second-requirement-for-a-co-product"></a>부산물에 대한 두 번째 요구 사항 생성

1. **영업 및 마케팅 \> 작업 영역 \> 판매 주문 처리 및 조회** 로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **판매 주문** 을 선택합니다.
1. **고객 계정** 필드에 값을 입력합니다.
    * 예: US-001  
1. **확인** 을 선택합니다.
1. **품목 번호** 필드에 값을 입력합니다.
    * 예: P6003  
1. **수량** 필드에 숫자를 입력합니다.
    * 예: 50000  
1. **저장** 을 선택합니다.

## <a name="create-a-second-material-plan-for-co-products"></a>부산물에 대한 두 번째 자재 계획 작성

1. **플랜** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
2. 목록에서 선택한 행의 링크를 선택합니다.
    * 예: MasterPlan  
3. **실행** 을 선택합니다.
4. **포함할 레코드** 섹션을 펼치거나 접습니다.
5. **필터** 를 선택합니다.
6. 목록에서 **필드** = *품목 번호* 인 행을 선택합니다.
7. *기준* 필드에 값을 입력합니다.
    * 예: P6003  
8. **확인** 을 선택합니다.
9. **확인** 을 선택합니다.
10. **계획된 주문** 을 선택합니다.
11. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 'P6000'인 **품목 번호** 필드를 필터링합니다.
    * 판매 주문을 생성한 항목의 부산물이 있는 공식 항목으로 필터링합니다.  
12. 목록에서 선택한 행을 표시합니다.
    * 필터에서 반환된 행을 선택합니다.  
13. 목록에서 선택한 행의 링크를 선택합니다.
14. **페깅** 섹션을 펼치거나 접습니다.
15. 목록에서 선택한 행의 링크를 선택합니다.
    * 계획된 주문은 공동 제품의 판매 주문에 페깅됩니다.  
16. 페이지를 닫습니다.
17. **마스터 플랜** 을 선택합니다.
18. **기준 계획 \> 설정 \> 기준 계획 매개 변수** 로 이동합니다.
19. **모든 계획 프로세스 비활성화** 필드에서 *아니요* 를 선택합니다.
20. 페이지를 닫습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]