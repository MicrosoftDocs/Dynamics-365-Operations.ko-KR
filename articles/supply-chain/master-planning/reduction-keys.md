---
title: 예측 감소 키
description: 이번에는 감소 키를 설정하는 방법을 보여주는 예를 제공합니다. 여기에는 다양한 감소 키 설정과 각각의 결과에 대한 정보가 포함됩니다. 감소 키를 사용하여 예측 요구 사항을 줄이는 방법을 정의할 수 있습니다.
author: ChristianRytt
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqReduceKeyDefaultDataWizard, ReqReduceKey
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cbed77fd1abc0e4ae26e2b9ddcc01d3f4a84889f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448351"
---
# <a name="forecast-reduction-keys"></a>예측 감소 키

[!include [banner](../includes/banner.md)]

이번에는 예측 요구 사항을 줄이는 데 사용되는 다양한 방법에 대한 정보를 제공합니다. 각 방법의 결과에 대한 예가 포함되어 있습니다. 또한 예측 감소 키를 생성, 설정 및 사용하는 방법도 설명합니다. 일부 방법은 예측 감소 키를 사용하여 예측 요구 사항을 줄입니다.

## <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>예측 요구 사항을 줄이는 데 사용되는 방법

기준 계획에 예측을 포함할 때 실제 수요가 포함될 때 예측 요구 사항을 줄이는 방법을 선택할 수 있습니다. 기준 계획에서는 과거의 예측 요구 사항을 제외합니다. 즉, 오늘 날짜 이전의 모든 예측 요구 사항을 의미합니다.

기준 계획에 예측을 포함하고 예측 요구 사항을 줄이는 데 사용되는 방법을 선택하려면 **기준 계획 \> 설정 \> 계획 \> 기준 계획** 으로 이동합니다. **예측 모델** 필드에서는 예측 모델을 선택합니다. **예측 요구 사항을 줄이는 데 사용되는 방법** 필드에서 방법을 선택합니다. 다음 옵션을 사용할 수 있습니다.

- 없음
- 퍼센트 – 감소 키
- 트랜잭션 – 감소 키
- 트랜잭션 – 동적 기간

다음 섹션에서는 각 옵션에 대한 자세한 정보를 제공합니다.

### <a name="none"></a>없음

**없음** 을 선택하면 기준 일정 계획 중에 예측 요구 사항이 줄어들지 않습니다. 이 경우 기준 계획은 예측 수요(예측 소요량)를 공급하기 위해 계획 주문을 생성합니다. 이러한 계획 주문은 다른 유형의 수요에 관계없이 제안된 수량을 유지합니다. 예를 들어, 판매 주문이 접수되면 기준 계획은 판매 주문을 공급하기 위해 추가 계획 주문을 생성합니다. 예측 요구 사항의 수량은 줄어들지 않습니다.

### <a name="percent--reduction-key"></a>퍼센트 – 감소 키

**퍼센트 - 감소 키** 를 선택하면 감소 키로 정의된 퍼센트 및 기간에 따라 예측 요구 사항이 감소합니다. 이 경우 기준 계획은 기간별 예측 수량 × 감소 키로 수량이 계산되는 계획 주문을 생성합니다. 다른 유형의 수요가 있는 경우 기준 계획은 해당 수요를 공급하기 위해 계획 주문도 생성합니다.

#### <a name="example-percent--reduction-key"></a>예: 퍼센트 – 감소 키

이 예는 감소 키가 감소 키에 의해 정의된 백분율 및 기간에 따라 수요 예측 요구 사항을 줄이는 방법을 보여줍니다.

이 예에서는 기준 계획에 다음 수요 예측을 포함합니다.

| 개월    | 수요 예측 |
|----------|-----------------|
| 1월  | 1000           |
| 2월 | 1000           |
| 3월    | 1000           |
| 4월    | 1000           |

**감소 키** 페이지에서 다음 행을 설정합니다.

| 변경 | 단위  | 백분율 |
|--------|-------|---------|
| 1      | 개월 | 100     |
| 2      | 개월 | 75      |
| 3      | 개월 | 50      |
| 4      | 개월 | 25      |

항목의 적용 범위 그룹에 감소 키를 할당합니다. 그런 다음 **기준 계획** 페이지의 **예측 요구 사항을 줄이는 데 사용되는 방법** 필드에서 **백분율 - 감소 키** 를 선택합니다.

이 경우 1월 1일에 예측 스케줄링을 실행하면 **감소 키** 페이지에서 설정한 백분율에 따라 수요 예측 요구 사항이 소비됩니다. 다음 소요량 수량은 기준 계획으로 이전됩니다.

| 개월                | 계획 주문 수량 | 계산    |
|----------------------|------------------------|----------------|
| 1월              | 0                      | = 0% × 1,000   |
| 2월             | 250                    | = 25% × 1,000  |
| 3월                | 500                    | = 50% × 1,000  |
| 4월                | 750                    | = 75% × 1,000  |
| 5월부터 12월까지 | 1000                  | = 100% × 1,000 |

### <a name="transactions--reduction-key"></a>트랜잭션 – 감소 키

**예측 요구 사항을 줄이는 데 사용된 방법** 필드를 *트랜잭션 - 감소* 키로 설정하면 예측 요구 사항은 감소 키로 정의된 기간 동안 발생하는 적격 수요 트랜잭션만큼 감소합니다.

적격 수요는 **적용 범위 그룹** 페이지의 **예측 감소 기준** 필드에 의해 정의됩니다. **감소 예측 기준** 필드를 *주문* 으로 설정하면 판매 주문 트랜잭션만 적격 수요로 간주됩니다. *모든 트랜잭션* 으로 설정하면 본지사 외 출고 재고 트랜잭션이 적격 수요로 간주됩니다. 회사 간 판매 주문도 적격 수요로 간주되어야 하는 경우 **회사 간 주문 포함** 옵션을 *예* 로 설정합니다.

예측 감소는 감소 주요 기간의 첫 번째(가장 이른) 수요 예측 레코드로 시작됩니다. 적격 재고 거래의 수량이 동일한 감소 주요 기간의 수요 예측 라인 수량보다 많은 경우 재고 거래 수량의 잔액은 이전 기간의 수요 예측 수량을 줄이는 데 사용됩니다(미소비 예측이 있는 경우).

이전 감소 키 기간에 소비되지 않은 예측이 남아 있지 않으면 재고 거래 수량의 잔액이 다음 달의 예측 수량을 줄이는 데 사용됩니다(소비되지 않은 예측이 있는 경우).

**예측 요구 사항을 줄이는 데 사용된 방법** 필드가 *트랜잭션 - 감소 키* 로 설정된 경우 감소 키 라인의 **백분율** 필드 값이 사용되지 않습니다. 감소 키 기간을 정의하는 데 날짜만 사용됩니다.

> [!NOTE]
> 오늘 날짜 또는 그 이전에 게시된 모든 예측은 무시되며 계획 주문을 생성하는 데 사용되지 않습니다. 예를 들어, 해당 월에 대한 수요 예측이 1월 1일에 생성되고 1월 2일에 수요 예측을 포함하는 기준 계획을 실행하는 경우 계산은 1월 1일자 수요 예측 라인을 무시합니다.

#### <a name="example-transactions--reduction-key"></a>예: 트랜잭션 – 감소 키

이 예는 감소 키로 정의된 기간 동안 발생하는 실제 주문이 수요 예측 요구 사항을 줄이는 방법을 보여줍니다.

이 예에서는 **기준 계획** 페이지의 **예측 요구 사항을 줄이는 데 사용되는 방법** 필드에서 **트랜잭션 - 감소 키** 를 선택합니다.

다음 판매 주문이 1월 1일에 존재합니다.

| 개월    | 주문한 조각 수 |
|----------|--------------------------|
| 1월  | 956                      |
| 2월 | 1176                    |
| 3월    | 451                      |
| 4월    | 119                      |

이전 예에서 사용한 것과 동일한 월별 1,000개 수요 예측을 사용하는 경우 다음 소요량 수량이 기준 계획으로 이전됩니다.

| 개월                | 필요한 조각 수 |
|----------------------|---------------------------|
| 1월              | 44                        |
| 2월             | 0                         |
| 3월                | 549                       |
| 4월                | 881                       |
| 5월부터 12월까지 | 1000                     |

### <a name="transactions--dynamic-period"></a>트랜잭션 – 동적 기간

**트랜잭션 - 동적 기간** 을 선택하면 동적 기간 동안 발생하는 실제 주문 거래만큼 예측 요구 사항이 줄어듭니다. 동적 기간은 현재 예측 날짜를 포함하고 다음 예측이 시작될 때 종료됩니다. 이 경우 기준 계획은 예측 수요(예측 소요량)를 공급하기 위해 계획 주문을 생성합니다. 그러나 실제 주문 거래가 이루어지면 예측 요구 사항이 줄어 듭니다. 실제 트랜잭션은 예측된 요구 사항의 일부를 소비합니다.

이 옵션을 사용하면 다음 동작이 발생합니다.

- 감소 키는 필요하지 않거나 사용되지 않습니다. 
- 예측이 완전히 줄어들면 현재 예측에 대한 예측 요구 사항은 0(영)이 됩니다.
- 미래 예측이 없으면 입력된 마지막 예측의 예측 요구 사항이 줄어듭니다.
- 타임펜스는 예측 감소 계산에 포함됩니다.
- 양수 일수는 예측 감소 계산에 포함됩니다.
- 실제 주문 트랜잭션이 예상 요구 사항을 초과하는 경우 나머지 거래는 다음 예측 기간으로 전달되지 않습니다.

#### <a name="example-1-transactions--dynamic-period"></a>예제 1: 트랜잭션 – 동적 기간

다음은 **트랜잭션 - 동적 기간** 방법이 작동하는 방식을 보여주는 간단한 예입니다.

이 예에서는 기준 계획에 다음 수요 예측을 포함합니다.

| 날짜       | 수요 예측 |
|------------|-----------------|
| 1월 1일  | 1000           |
| 2월 1일 | 1000             |

다음 판매 주문도 생성합니다.

| 날짜        | 판매 주문 수량 |
|-------------|----------------------|
| 1월 15일  | 200                  |
| 2월 15일 | 400                  |

이 경우 다음과 같은 계획 주문이 생성됩니다.

| 수요예측일 | 수량 | 설명                           |
|--------------------- |----------|---------------------------------------|
| 1월 1일            | 800      | 예측 요구 사항(= 1,000 – 200) |
| 1월 15일           | 200      | 판매 주문 요구 사항             |
| 2월 1일           | 600      | 예측 요구 사항(= 1,000 – 400) |
| 2월 15일          | 400      | 판매 주문 요구 사항             |

#### <a name="example-2-transactions--dynamic-period"></a>예제 2: 트랜잭션 – 동적 기간

대부분의 경우 트랜잭션이 특정 예측 기간(주, 월 등)의 수요 예측을 줄이도록 시스템이 설정됩니다. 이 기간은 감소 키에 정의됩니다. 그러나 두 수요 예측 라인 사이의 시간은 기간을 *의미* 할 수도 있습니다.

이 예에서는 다음 날짜 및 수량에 대한 수요 예측을 생성합니다.

| 날짜       | 수요 예측 |
|------------|-----------------|
| 1월 1일  | 1000           |
| 5월 1일  | 500             |
| 12월 1일 | 1000           |

이 예측에서는 예측 날짜 사이에 명확한 기간이 없습니다. 첫 번째 날짜와 두 번째 날짜 사이에는 4일 범위가 있고 두 번째 날짜와 세 번째 날짜 사이에는 7일 범위가 있습니다. 이러한 범위는 동적 기간입니다.

다음 판매 주문 라인도 생성합니다.

| 날짜                             | 판매 주문 수량 |
|----------------------------------|----------------------|
| 전년도 12월 15일 | 500                  |
| 3월 1일                        | 100                  |
| 10월 1일                       | 200                  |

이 경우 예측은 다음과 같은 방식으로 축소됩니다.

- 첫 번째 판매 주문은 어떤 기간에도 없기 때문에 예측을 줄이지 않습니다.
- 두 번째 판매 주문은 1월 1일과 1월 5일 사이에 있으므로 1월 1일에 대한 예측을 100만큼 줄입니다.
- 세 번째 판매 주문은 1월 5일과 1월 12일 사이에 있으므로 1월 5일에 대한 예측을 200만큼 줄입니다.

따라서 다음과 같은 계획 주문이 생성됩니다.

| 수요예측일             | 수량 | 설명                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 전년도 12월 15일 | 500      | 판매 주문 요구 사항                                            |
| 1월 1일                        | 900      | 예측 요구 사항 기간 1월 1일 ~ 1월 5일(= 1,000 – 100) |
| 3월 1일                        | 100      | 판매 주문 요구 사항                                            |
| 5월 1일                        | 300      | 예측 요구 사항 기간 1월 5일 ~ 1월 10일(= 500 – 200)  |
| 12월 1일                       | 1000    | 예측 요구 사항 기간 1월 12일 ~ 1월 31일                      |

## <a name="create-and-set-up-a-forecast-reduction-key"></a>예측 감소 키 생성 및 설정

예측 감소 키는 예측 요구 사항을 줄이기 위한 **트랜잭션 - 감소 키** 및 **백분율 - 감소 키** 방법에서 사용됩니다. 감소 키를 만들고 설정하려면 다음 단계를 따르세요.

1. **기준 계획 \> 설정 \> 적용 범위 \> 감소 키** 로 이동합니다.
2. **새로 만들기** 를 선택하여 감소 키를 만듭니다.
3. **감소 키** 필드에 예측 감소 키의 고유 식별자를 입력합니다. 그런 다음 **이름** 필드에 수수료 이름을 입력합니다. 
4. 기간 및 각 기간의 감소 키 백분율을 정의합니다.

    - **적용 날짜** 필드는 기간 생성이 시작되는 일자를 나타냅니다. **적용 날짜 사용** 옵션이 **예** 로 설정된 경우 기간은 유효 일자에 시작됩니다. **아니요** 로 설정하면 기준 계획이 실행되는 날짜에 기간이 시작됩니다.
    - 예측 감소가 발생해야 하는 기간을 정의합니다.
    - 특정 기간 동안 예측 요구 사항을 줄여야 하는 백분율을 지정합니다. 요구 사항을 줄이려면 양수 값을 입력하고 요구 사항을 늘리려면 음수 값을 입력할 수 있습니다.

## <a name="use-a-reduction-key"></a>감소 키 사용

항목의 적용 범위 그룹에 예측 감소 키를 할당해야 합니다. 항목의 적용 범위 그룹에 감소 키를 할당하려면 다음 단계를 따르세요.

1. **기준 계획 \> 설정 \> 적용 범위 \> 적용 범위 그룹** 으로 이동합니다.
2. **기타** 빠른 탭의 **감소 키** 필드에서 적용 범위 그룹에 할당할 감소 키를 선택합니다. 그러면 감소 키는 적용 범위 그룹에 속하는 모든 항목에 적용됩니다.
3. 감소 키를 사용하여 기준 일정 계획 중에 예측 감소를 계산하려면 예측 계획 또는 기준 계획 설정에서 이 설정을 정의해야 합니다. 다음 위치 중 하나로 이동합니다.

    - 기준 계획 \> 설정 \> 계획 \> 예측 계획
    - 기준 계획 \> 설정 \> 계획 \> 기준 계획

4. **예측 계획** 또는 **기준 계획** 페이지의 **일반** 빠른 탭에 있는 **예측 요구 사항을 줄이는 데 사용되는 방법** 필드에서 **백분율 - 감소 키** 또는 **트랜잭션 - 감소 키** 를 선택합니다.

## <a name="reduce-a-forecast-by-transactions"></a>트랜잭션으로 예측 줄이기

**트랜잭션 - 감소 키** 또는 **트랜잭션 - 동적 기간** 을 예측 요구 사항을 줄이는 방법으로 선택하면 예측을 줄이는 트랜잭션을 지정할 수 있습니다. **적용 범위 그룹** 페이지의 **기타** 빠른 탭에 있는 **예측 감소 기준** 필드에서 **모든 트랜잭션** 이 예측을 줄여야 하는 경우 모든 트랜잭션을 선택하거나 판매 주문만 예측을 줄여야 하는 경우 **주문** 을 선택합니다.

## <a name="additional-resources"></a>추가 리소스

[마스터 플랜 개요](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
