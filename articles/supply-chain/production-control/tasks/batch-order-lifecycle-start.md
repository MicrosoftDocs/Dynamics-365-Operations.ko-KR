---
title: 생성에서 시작까지의 일괄 주문 수명 주기
description: 이 절차는 배치 주문 라이프 사이클의 첫 번째 부분을 안내합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7ca259ca8f176cd5bc76081836adcb7d272972b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449197"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>생성에서 시작까지의 일괄 주문 수명 주기

[!include [banner](../../includes/banner.md)]

이 절차는 배치 주문 라이프 사이클의 첫 번째 부분을 안내합니다.

생성, 비용 추정 및 초과 생산 작업 스케줄링에서 배치 주문의 실제 시작까지.



이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 



다른 데이터 세트로 절차를 실행하기 위한 전제 조건은 활성 공식 및 경로 버전이 있는 릴리스된 제품입니다.


## <a name="create-a-batch-order"></a>배치 주문 만들기
1. 모든 생산 주문으로 이동합니다.
2. 새 배치 주문을 클릭합니다.
3. 품목 번호 필드에서 값을 입력하거나 선택합니다.
4. 만들기를 클릭합니다.
5. 빠른 필터를 사용하여 'b' 값으로 생산 필드를 필터링합니다.

## <a name="view-production-formula-and-expected-co-products"></a>생산 공식 및 예상되는 부산물 보기
1. 작업 창에서 생산 주문을 클릭합니다.
2. 수식을 클릭합니다.
3. 페이지를 닫습니다.
4. 공동 제품을 클릭합니다.
5. 페이지를 닫습니다.

## <a name="estimate-the-batch-order"></a>배치 주문 추정
1. 견적을 클릭합니다.
2. 확인을 클릭합니다.
3. 작업 창에서 비용 관리를 클릭합니다.
4. 계산 세부 정보 보기를 클릭합니다.
5. 페이지를 닫습니다.

## <a name="release-the-batch-order"></a>배치 주문 릴리스
1. 작업 창에서 생산 주문을 클릭합니다.
2. 릴리스를 클릭합니다.
3. 확인을 클릭합니다.

## <a name="schedule-production-jobs"></a>생산 작업 예약
1. 작업 창에서 예약을 클릭합니다.
2. 작업 예약을 클릭합니다.
3. 유한 용량 필드에서 아니요를 선택합니다.
4. 유한 자재 필드에서 아니요를 선택합니다.
5. 확인을 클릭합니다.
6. 작업 창에서 생산 주문을 클릭합니다.
7. 모든 작업을 클릭합니다.
8. 페이지를 닫습니다.

## <a name="start-the-batch-order"></a>배치 주문 시작
1. 시작을 클릭합니다.
2. 일반 탭을 클릭합니다.
3. 지금 포스트 피킹 목록 필드에서 아니요를 선택합니다.
4. 확인을 클릭합니다.
5. 작업 창에서 보기를 클릭합니다.
6. 불출 목록을 클릭합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. 페이지를 닫습니다.
9. 페이지를 닫습니다.
10. 경로 카드를 클릭합니다.
11. 목록에서 선택한 행의 링크를 클릭합니다.
12. 페이지를 닫습니다.
13. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]