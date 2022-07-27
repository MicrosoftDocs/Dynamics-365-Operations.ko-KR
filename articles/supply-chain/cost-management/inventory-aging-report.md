---
title: 재고 에이징 보고 예시 및 로직
description: 이 토픽에서는 재고 에이징 보고서의 결과를 해석하는 방법을 보여주는 몇 가지 예를 제공합니다.
author: AndersGirke
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 59c1740f6e07be08ad9379d4ccb6aeca29220d557aceb38bf6faef946e16fee7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447028"
---
# <a name="inventory-aging-report-examples-and-logic"></a>재고 에이징 보고 예시 및 로직

[!include [banner](../includes/banner.md)]

이 토픽에서는 **재고 에이징** 보고서의 결과를 해석하는 방법을 보여주는 몇 가지 예를 제공합니다. 이 보고서는 선택한 항목 또는 항목 그룹에 대한 현재고 수량 및 재고 금액을 여러 기간 버켓으로 분류합니다. 이 토픽에서는 보고서의 내부 논리도 보여줍니다.

이 토픽의 예는 표준 **재고 에이징** 보고서에 표시되는 결과를 보여줍니다. 그러나 일반적으로 특히 처리해야 하는 항목과 창고가 많은 경우 이 보고서의 [재고 에이징 보고서 저장](inventory-aging-report-storage.md) 버전을 사용하는 것이 좋습니다. 재고 에이징 보고서 저장소는 생성한 각 보고서를 저장하고 결과를 대화형 페이지 및 차트로 표시하며 저장된 보고서를 내보낼 수 있습니다.

## <a name="sample-data-that-is-used-in-these-examples"></a>이 예에서 사용된 샘플 데이터

이 토픽의 예는 이 섹션에서 설명하는 샘플 재고 트랜잭션 데이터를 기반으로 합니다.

### <a name="storage-dimension-setup"></a>재고 규모 설정

예제 시스템에는 다음과 같은 스토리지 차원 설정이 포함되어 있습니다.

| 이름      | 활성 | 실제 재고 | 재무 재고 |
|-----------|--------|--------------------|---------------------|
| 사이트      | 예    | 예                | 예                 |
| 창고 | 예    | 예                | 아니요                  |

### <a name="inventory-model"></a>재고 모델

예제 시스템의 경우 출시된 제품의 재고 모델은 *FIFO* 이고 재고 모델의 **비용 가격** 설정은 *물리적 가치 포함* 으로 설정됩니다.

### <a name="inventory-transactions"></a>재고 거래

예제 시스템에는 품목 번호가 *1000* 인 출시된 제품에 대한 다음 재고 트랜잭션이 포함되어 있습니다.

| 참조      | 사이트 | 창고 | 수령   | 문제 | 실제 날짜 | 회계 날짜 | 수량 | 비용 금액 | 실제 비용 금액 |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| 구매 주문 | 1    | 11        | 구매 |       | 3월 15일      | 3월 15일       | 10       | 1,000       | 1,000                |
| 구매 주문 | 2    | 21        | 구매 |       | 3월 15일      | 3월 15일       | 10       | 2,000       | 2,000                |
| 구매 주문 | 1    | 11        | 수령함  |       | 4월 15일      |                | 5        |             | 375                  |
| 이전 주문 | 1    | 11        |           | 판매됨  | 5월 2일         | 5월 2일          | -5       | -458.33     | -458.33              |
| 이전 주문 | 1    | 12        | 구매 |       | 5월 2일         | 5월 2일          | 5        | 458.33      | 458.33               |
| 판매 주문    | 1    | 12        |           | 판매됨  | 5월 3일         | 5월 3일          | -1       | -91.67      | -91.67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>각 기간 버켓의 수량 및 금액 계산 방법

이전 섹션에서 설명한 샘플 데이터를 사용하여 다음 설정이 있는 **재고 에이징** 보고서를 실행할 수 있습니다.

- **기준 날짜:** *2020년 5월 9일*
- **사이트:** *보기*
- **창고:** *아니요*
- **품목 번호** *합계*
- **에이징 기간:** 월별 버킷을 생성하려면 이 필드를 설정하세요.

이 경우 생성되는 보고서의 내용은 다음 예와 유사합니다.

<table>
<thead>
<tr>
    <th rowspan="2">품목 번호</th>
    <th rowspan="2">사이트</th>
    <th rowspan="2">현재고 수량</th>
    <th rowspan="2">보유 가치</th>
    <th rowspan="2">재고 가치 수량</th>
    <th rowspan="2">재고 가치</th>
    <th rowspan="2">평균 단가</th>
    <th colspan="2">5/8/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1: 수량</th>
    <th>P1: 금액</th>
    <th>P2: 수량</th>
    <th>P2: 금액</th>
    <th>P3: 수량</th>
    <th>P3: 금액</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>10000 합계</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

이 예제 보고서에서 다음 세부 정보를 확인하세요.

- 보고서에 표시되는 **재고 가치 수량**, **재고 가치** 및 **평균 단가** 값은 재무 재고 차원(이 경우 **사이트**)에 대한 값입니다.

    예를 들어 사이트 1의 경우 보고서에는 다음 정보가 표시됩니다.

    - **재고 가치 수량** 값은 *14*(= 10 + 5 – 5 + 5 – 1)입니다.
    - **재고 가치 수량** 값은 *1,283.33*(= 1,000 + 375 – 458.33 + 458.33 – 91.67)입니다.
    - **평균 단가** 값은 *91.67* 입니다.
    - 각 기간 버켓의 **현재고 값** 과 **금액** 값은 **평균 단가 값** 을 사용하여 계산됩니다.

- 보고서는 각 기간 버켓에 대해 입고된 총 재고 수량을 요약하여 각 기간 버켓에 대한 현재고 수량을 결정합니다. 그런 다음 FIFO(선입선출) 원칙을 적용하여 항목이 사용하는 재고 모델에 관계없이 총 발행 수량을 차감합니다.

동일한 보고서를 다시 실행하지만 이번에는 **사이트** 및 **창고** 필드를 모두 *보기* 로 설정하면 새 보고서는 다음 예와 유사합니다.

<table>
<thead>
<tr>
    <th rowspan="2">품목 번호</th>
    <th rowspan="2">사이트</th>
    <th rowspan="2">창고</th>
    <th rowspan="2">현재고 수량</th>
    <th rowspan="2">보유 가치</th>
    <th rowspan="2">재고 가치 수량</th>
    <th rowspan="2">재고 가치</th>
    <th rowspan="2">평균 단가</th>
    <th colspan="2">5/8/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1: 수량</th>
    <th>P1: 금액</th>
    <th>P2: 수량</th>
    <th>P2: 금액</th>
    <th>P3: 수량</th>
    <th>P3: 금액</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>10000 합계</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

이번에는 사이트 1이 창고 11에 대한 행과 창고 12에 대한 행의 두 행으로 분할됩니다. 그러나 **창고** 는 재무 재고 차원이 아니기 때문에 **재고 금액 수량**, **재고 금액** 및 **평균 단가** 값은 동일합니다.

또한 사이트 1의 수량 분포가 다릅니다. 실행한 첫 번째 보고서에서 시스템은 동일한 사이트에서 발생한 이전 주문을 무시하고 사이트 1의 **3/31/2020 - 3/1/2020** 기간 버켓에서 판매 송장의 수량을 차감했습니다. 그러나 새 보고서에서 시스템은 창고 12의 **5/8/2020 - 5/1/2020** 기간 버켓에서 판매 송장 수량을 공제합니다.

## <a name="effects-of-inventory-closing"></a>재고 마감의 효과

5월에 대한 재고 마감을 실행한 다음 이전 보고서를 다시 실행하지만 **기준 날짜** 필드를 *2020년 5월 31일* 로 설정하면 다음 결과를 확인할 수 있습니다.

- **재고 가치** 및 **평균 단가** 값이 업데이트됩니다.
- 이에 따라 모든 기간 버켓의 **현재고** 값 및 모든 **금액** 값이 업데이트됩니다.

새 보고서는 다음 예와 유사합니다.

<table>
<thead>
<tr>
    <th rowspan="2">품목 번호</th>
    <th rowspan="2">사이트</th>
    <th rowspan="2">창고</th>
    <th rowspan="2">현재고 수량</th>
    <th rowspan="2">보유 가치</th>
    <th rowspan="2">재고 가치 수량</th>
    <th rowspan="2">재고 가치</th>
    <th rowspan="2">평균 단가</th>
    <th colspan="2">5/31/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1: 수량</th>
    <th>P1: 금액</th>
    <th>P2: 수량</th>
    <th>P2: 금액</th>
    <th>P3: 수량</th>
    <th>P3: 금액</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0.00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>10000 합계</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]