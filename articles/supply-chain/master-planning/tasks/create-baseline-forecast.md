---
title: '가이드: 기준 예측 생성'
description: 생산 계획자는 시계열 예측 모델을 사용하거나 과거 수요를 복사하여 기준선 예측을 생성할 수 있습니다.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 843e0b3827851e1251a2c77269859bb7903f69ec
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449098"
---
# <a name="guide-create-a-baseline-forecast"></a>가이드: 기준 예측 생성

[!include [banner](../../includes/banner.md)]

생산 계획자는 시계열 예측 모델을 사용하거나 과거 수요를 복사하여 기준선 예측을 생성할 수 있습니다. 이 절차에서는 하나의 품목 할당 키를 사용하여 모든 제품에 대한 베이스라인 예측을 생성하기 위해 과거 수요를 복사하는 방법을 보여줍니다.

## <a name="set-up-an-item-allocation-key"></a>항목 할당 키 설정

1. **기준 계획 > 설정 > 회사 간 계획 그룹** 으로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 *10* 인 *이름* 필드를 필터링합니다.
    * 수요 예측은 법인 전체에서 실행됩니다. 그렇기 때문에 하나의 회사 간 계획 그룹에서 예측을 생성하려는 모든 회사를 설정해야 합니다.  
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. **항목 할당 키** 를 선택합니다.
    * 모두 선택 예측을 생성하려는 항목 할당 키.  
5. 목록에서 선택한 행을 표시합니다.
    * D_Aloc 항목 할당 키를 선택합니다.  
6. **>** 선택.
7. 페이지를 닫습니다.
8. 페이지를 닫습니다.

## <a name="set-up-the-demand-forecasting-parameters"></a>수요 예측 매개 변수 설정

1. **기준 계획 > 설정 > 수요 예측 > 수요 예측 매개 변수** 로 이동합니다.
2. **예측 알고리즘 매개 변수** 섹션을 펼칩니다.
3. **예측 생성 전략** 필드에서 **과거 수요 복사** 를 선택합니다.
4. **저장** 을 선택합니다.

## <a name="create-a-baseline-forecast"></a>기준 예측 생성

1. **기준 계획 > 예측 > 수요 예측 > 통계 기준선 예측 생성** 으로 이동합니다.
2. **시작 날짜** 필드에 날짜를 입력합니다.
    * 2015년 1월 1일부터 시작하는 판매 주문이 있는 경우 이 날짜를 입력합니다. 그렇지 않은 경우 판매 주문의 가장 빠른 날짜를 입력합니다.  
3. **종료 날짜** 필드에 날짜를 입력합니다.
    * 판매 주문의 마지막 날짜를 입력합니다(예: *2015-03-31*).  
4. **시작 날짜** 필드에 날짜를 입력합니다.
    * *2015-04-01* 을 입력합니다. 이 날짜는 다음 예측 버킷의 시작 날짜로 자동 계산됩니다.  
5. **포함할 레코드** 섹션을 펼칩니다.
6. **필터** 를 선택합니다.
7. 목록에서 선택한 행을 표시합니다.
    * **필드** = *회사간 기획 그룹* 인 행을 표시합니다.  
8. **기준** 필드에 값을 입력합니다.
    * 첫 번째 작업에서 사용한 회사 간 계획 그룹(예: *10*)을 입력합니다.  
9. 목록에서 원하는 레코드를 찾아 선택합니다.
    * **필드** = *항목 할당 키* 인 행을 선택합니다.  
10. **기준** 필드에 값을 입력합니다.
11. **확인** 을 선택합니다.
12. **고급 매개 변수** 섹션을 펼칩니다.
13. **예측 버킷** 필드에서 *월* 을 선택합니다.
14. **예측 범위** 필드에서 *3* 을 입력합니다.
15. **동결 타임펜스** 필드에 *1* 을 입력합니다.
16. **확인** 을 선택합니다.

## <a name="visualize-the-demand-forecast"></a>수요 예측 시각화

1. **기준 계획 > 예측 > 수요 예측 > 조정된 수요 예측** 으로 이동합니다.
2. 집계 보기 테이블에서 행 1, 열 2의 셀을 선택합니다. 예측을 생성한 두 번째 달입니다.
3. **QtyCell** 을 *400* 으로 설정합니다.
    * 셀에 예측된 것과 다른 숫자(예: 400)를 입력합니다.  
4. 예측을 수동으로 조정했습니다. 다음 단계에서 그래픽 표시를 확인합니다.
5. **예측 라인 상세내역** 을 선택합니다.
    * 이 페이지에서 정확도 값, 과거 수요 및 예측을 볼 수 있습니다. 예측을 변경할 수도 있습니다.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]