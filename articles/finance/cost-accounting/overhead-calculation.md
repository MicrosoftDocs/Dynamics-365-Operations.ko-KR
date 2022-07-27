---
title: 간접비 계산
description: 이 항목에서는 간접비를 계산하고 할당하는 일반적인 프로세스에 관해 설명합니다.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 60bce611ae1f6ed5d63860793cd5d1da3c421a9e
ms.sourcegitcommit: e3290eb58ae569a59d6ae2e6922e7d8be8f1980f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "8450991"
---
# <a name="overhead-calculation"></a>간접비 계산

[!include [banner](../includes/banner.md)]

이 항목에서는 간접비를 계산하고 할당하는 일반적인 프로세스에 관해 설명합니다.

## <a name="term-definition"></a>용어 정의

간접비는 사업을 운영하기 위해 발생하지만 특정 사업 활동, 제품 또는 서비스에 직접 귀속될 수 없는 비용입니다. 간접비는 이윤 창출 활동의 생성에 중요한 지원을 제공합니다. 다음은 간접비의 몇 가지 예입니다.

-   임대료
-   전기
-   관리 급여

## <a name="overhead-calculation-overview"></a>간접비 계산 개요
간접비 계산은 원가 회계 정책을 올바른 순서로 실행합니다. 원가 회계 정책이 변경되었거나 특정 오류가 감지된 경우 같은 회계 기간에 대해 간접비 계산을 여러 번 실행할 수 있습니다. 각각의 간접비 계산 실행은 저장되고 다양한 버전의 계산을 비교할 수 있도록 고유한 버전 ID를 받습니다. 간접비 계산이 생성하는 비용 항목에는 회계 날짜가 부여됩니다. 이 회계 날짜는 계산에 사용된 회계 기간의 종료 날짜와 일치합니다. 고유 버전 ID는 다음 요소로 구성됩니다.

-   버전 유형
-   날짜 및 시간
-   원가 회계 원장
-   회계 연도
-   회계 기간

간접비 계산은 버전과 독립적으로 실행됩니다. 따라서 실제 버전보다 먼저 예산 버전을 계산할 수 있습니다. 간접비 계산은 다음 그림과 같이 4단계로 구성됩니다. 각 단계에서 분개장 항목이 있는 분개장 헤더가 생성됩니다. 이 분개장 헤더는 각 계산 단계에 대한 입력 데이터를 유지합니다. 정책 및 규칙이 각 분개장 라인에 적용되고 비용 항목이 출력으로 생성됩니다. 따라서 항상 완전한 추적이 가능합니다. 

[![간접비 계산.](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>전기 간접비 계산 및 할당
재무 회계에서는 전기와 같은 일부 비용을 일시금으로 등록합니다. 따라서 원가 회계에 대한 자세한 관리 통찰력이 제공되지 않습니다. 원가 회계에서 모든 조직 구성 단위 및 수준에 걸쳐 올바른 관리 통찰력을 제공하려면 비용이 조직 구성 단위를 통과해야 합니다. 이 흐름은 정확한 소비 기록이나 공정한 평가를 기반으로 해야 합니다. 총계정원장에서 전기 비용은 다음 테이블과 같이 게시될 수 있습니다.

<table>
<thead>
<tr>
<th>회계 날짜</th>
<th colspan="2">Cost center</th>
<th colspan="2">주 계정</th>
<th>금액(회계 통화)</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017년 1월 3일</td>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>1단계: 비용 동작 계산 처리

기본적으로 원본 데이터에서 비용 항목을 가져오면 원가 회계에서 **미분류** 비용 동작 분류를 받습니다. 비용 행동 정책 규칙을 적용하여 비용 항목을 **고정 비용** 또는 **변동 비용** 으로 재분류할 수 있습니다.

#### <a name="define-the-cost-behavior-rule"></a>비용 동작 규칙 정의

비용의 일부는 고정 요금이고 나머지 비용은 소비 기반인 경우가 있습니다. 전기 요금이 종종 이 정의와 일치합니다. 일정 기본 요금에 더해 킬로와트시(Kwh)당 사용 요금을 지불합니다. 예를 들어 고정 비용 수수료가 1,000.00인 경우 비용 동작은 규칙은 다음과 같이 정의됩니다.

-   고정 금액 1,000.00
    -   0 &lt;= 1,000.00 = 고정
    -   1000,01 &lt; N = 변동

##### <a name="journal"></a>분개장

<table>
<thead>
<tr>
<th>분개장</th>
<th>분개장 유형</th>
<th colspan="3">회계 달력 기간</th>
<th>버전</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>비용 동작 계산 분개장</td>
<td>회계</td>
<td>2017</td>
<td>기간 1</td>
<td>간접비 계산 / 2017-01-02 오후 11:51:00 / 원장 / 2017 / 기간 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>분개장 항목(비용 개체 잔액 분개장 항목)

<table>
<thead>
<tr>
<th>회계 날짜</th>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017년 1월 3일</td>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>미분류</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>비용 항목

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
<th>회계 날짜</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>미분류</td>
<td>10,000.00</td>
<td>2017년 1월 3일</td>
</tr>
<tr>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>미분류</td>
<td>-10,000.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>1,000.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>9,000.00</td>
<td>2017년 1월 31일</td>
</tr>
</tbody>
</table>

자세한 내용은 [비용 동작 정책을 만들고 비용 제어 장치에 할당](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)을 참조하세요.
### <a name="step-2-process-the-cost-distribution-calculation"></a>2단계: 비용 분배 계산 처리

비용 분배는 관련 할당 기준을 적용하여 하나의 비용 개체에서 하나 이상의 다른 비용 개체로 비용을 재분배하는 데 사용됩니다. 비용 분배를 비용 할당과 비교하면 비용 분배가 항상 원래 비용의 기본 비용 요소 수준에서 발생한다는 점에서 다릅니다.

#### <a name="define-the-cost-distribution-rule"></a>비용 분배 규칙 정의

재무 회계에서는 전기 요금을 종종 일시금으로 등록합니다. 원가 회계에서 이 접근 방식은 그리 상세하지 않습니다. 변동 비용은 공정하게 개별 비용 대상에 분배되어야 합니다. 가장 논리적인 할당 기준은 전력 소비량(Kwh)입니다. 전기라는 이름으로 통계 차원 구성원이 작성되고 전기 소비가 기록됩니다. 기본적으로 모든 통계 차원 구성원은 할당 기준으로 사용할 수 있습니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>1,000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>6,000</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>0</td>
</tr>
</tbody>
</table>

다음 표에는 변동 비용 할당 기준으로 전력 사용량을 적용한 결과가 나옵니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>크기</th>
<th>할당 요소</th>
<th>금액</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>1,000</td>
<td>(1,000 ÷ 7,000) × 9,000.00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>6,000</td>
<td>(6,000 ÷ 7,000) × 9,000.00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>0</td>
<td>(0 ÷ 7,000) × 9,000.00</td>
<td>0.00</td>
</tr>
</tbody>
</table>

고정 비용은 전기를 소비한 개별 비용 개체에 균등하게 분배되어야 합니다. 공식 할당 기준에서 전기 통계 차원 구성원을 사용하여 이 결과를 얻을 수 있습니다. (전기 &gt; 0.00) 다음 표는 전기 소비를 변동 비용의 할당 기준으로 적용한 결과를 보여줍니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>공식</th>
<th>크기</th>
<th>할당 요소</th>
<th>금액</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>(1,000 &gt; 0.00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1,000.00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>(6,000 &gt; 0.00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1,000.00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>(0 &gt; 0.00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1,000.00</td>
<td>0.00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>분개장

<table>
<thead>
<tr>
<th>분개장</th>
<th>분개장 유형</th>
<th colspan="3">회계 달력 기간</th>
<th>버전</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>비용 분배 계산 분개장</td>
<td>회계</td>
<td>2017</td>
<td>기간 1</td>
<td>간접비 계산 / 2017-01-02 오후 11:51:00 / 원장 / 2017 / 기간 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>분개장 항목(비용 개체 잔액 분개장 항목)

<table>
<thead>
<tr>
<th>회계 날짜</th>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017년 1월 31일</td>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>1,000.00</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>9,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>비용 항목

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
<th>회계 날짜</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>-1,000.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>500.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>500.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC099</td>
<td>기본 비용 센터</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-9,000.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>1,285.71</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>7,714.29</td>
<td>2017년 1월 31일</td>
</tr>
</tbody>
</table>

자세한 내용은 [비용 분배 정책을 만들고 비용 제어 장치에 할당](tasks/create-assign-cost-distribution-policy-cost-control-unit.md)을 참조하세요. 

### <a name="step-3-process-the-overhead-rate-calculation"></a>3단계: 간접비 비율 계산 처리

간접비 비율은 하나 이상의 특정 비용 개체에 부과하는 데 사용됩니다. 요금은 미리 결정된 비용 비율과 할당된 할당 기준의 규모에 기반을 둡니다. 

#### <a name="define-the-overhead-rate"></a>간접비 비율 정의

비용 개체 CC001 HR은 내부 프로젝트 집합에 기여합니다. 소비된 규모를 측정하기 위해 HR 프로젝트라는 통계 차원 구성원이 생성됩니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>시간</th>
</tr>
</thead>
<tbody>
<tr>
<td>프로젝트 1</td>
<td>프로젝트 1</td>
<td>3</td>
</tr>
<tr>
<td>프로젝트 2</td>
<td>프로젝트 2</td>
<td>1</td>
</tr>
</tbody>
</table>

비용 프로젝트 기여에 따라 미리 결정된 비용 비율이 정의되었습니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>비용 요소</th>
<th>비용 동작</th>
<th>단위</th>
<th>비율</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>변동 비용</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

다음 표는 HR 프로젝트를 할당 기준으로 적용했을 때의 결과입니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>크기</th>
<th>비용 요소</th>
<th>할당 요소</th>
<th>금액</th>
</tr>
</thead>
<tbody>
<tr>
<td>프로젝트 1</td>
<td>프로젝트 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10.00</td>
<td>30.00</td>
</tr>
<tr>
<td>프로젝트 2</td>
<td>프로젝트 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10.00</td>
<td>10.00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>분개장

<table>
<thead>
<tr>
<th>분개장</th>
<th>분개장 유형</th>
<th colspan="3">회계 달력 기간</th>
<th>버전</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>간접비 계산 분개장</td>
<td>회계</td>
<td>2017</td>
<td>기간 1</td>
<td>간접비 계산 / 2017-01-02 오후 11:51:00 / 원장 / 2017 / 기간 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>분개장 항목(간접비 계산을 위한 분개장 항목)

<table>
<thead>
<tr>
<th>회계 날짜</th>
<th colspan="2">비용 개체</th>
<th>크기</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017년 1월 31일</td>
<td>프로젝트 1</td>
<td>내부 프로젝트 1</td>
<td>3.00</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>프로젝트 2</td>
<td>내부 프로젝트 2</td>
<td>1.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>비용 항목

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
<th>회계 날짜</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-30.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>프로젝트 1</td>
<td>내부 프로젝트 1</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>30.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-10.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>프로젝트 2</td>
<td>내부 프로젝트 2</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>10.00</td>
<td>2017년 1월 31일</td>
</tr>
</tbody>
</table>

자세한 내용은 [간접비 계산 수행](cost-rollup.md#perform-overhead-calculation)을 참조하세요.

### <a name="step-4-process-the-cost-allocation-calculation"></a>4단계: 비용 할당 계산 처리

할당은 할당 기준을 적용하여 비용 개체의 잔액을 다른 비용 개체에 할당하는 데 사용됩니다. Finance는 상호 할당 방식을 지원합니다. 상호 할당 방식에서는 보조 비용 개체가 교환하는 상호 용역을 완전히 인식합니다. 시스템은 할당을 수행할 올바른 순서를 자동으로 결정합니다. 비용 개체의 잔액은 단일 할당 기준으로 할당됩니다. 비용 개체 차원 및 해당 구성원에 대한 할당이 지원됩니다. 할당 순서는 비용 제어 장치에 의해 제어됩니다. 

[![상호 방식.](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>비용 할당 정의

다음은 비용 흐름을 추적하는 방법을 설명하는 간단한 예입니다. 비용 개체 CC001 HR이 여러 비용 개체에 기여하고 있습니다. 소비된 규모를 측정하기 위해 HR 서비스라는 통계 차원 구성원이 생성됩니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>HR 서비스</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10</td>
</tr>
</tbody>
</table>

비용 개체 CC002 재무가 여러 비용 개체에 기여합니다. 소비된 규모를 측정하기 위해 재무 서비스라는 통계 차원 구성원이 생성됩니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>재무 서비스</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>35</td>
</tr>
</tbody>
</table>

비용 개체 CC003 어셈블리가 여러 비용 개체에 기여합니다. 소비된 규모를 측정하기 위해 어셈블리 서비스라는 통계 차원 구성원이 생성됩니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>어셈블리 서비스(시간)</th>
</tr>
</thead>
<tbody>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>60</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>20</td>
</tr>
</tbody>
</table>

비용 개체 CC004 패키징이 여러 비용 개체에 기여합니다. 소비된 규모를 측정하기 위해 패키징 서비스라는 통계 차원 구성원이 생성됩니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>패키징 서비스(시간)</th>
</tr>
</thead>
<tbody>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>80</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>15</td>
</tr>
</tbody>
</table>

> [!NOTE]
> 제품이 소비하는 생산 시간과 같은 통계적 측정값은 원본 데이터에서 파생될 수 있습니다. 자세한 내용은 [통계 측정 공급자 템플릿](statistical-measure-provider-template.md#statistical-measure-provider-template)을 참조하세요. 총 비용(고정 비용과 변동 비용)의 할당 기준으로 HR 서비스를 적용한 결과는 다음과 같습니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>크기</th>
<th>할당 요소</th>
<th>금액</th>
<th>비용 동작</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>35</td>
<td>(35 ÷ 100) × 500.00</td>
<td>175.00</td>
<td>고정 비용</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>55</td>
<td>(55 ÷ 100) × 500.00</td>
<td>275.00</td>
<td>고정 비용</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10</td>
<td>(10 ÷ 100) × 500.00</td>
<td>50.00</td>
<td>고정 비용</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>35</td>
<td>(35 ÷ 100) × 1,245.71</td>
<td>436.00</td>
<td>변동 비용</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>55</td>
<td>(55 ÷ 100) × 1,245.71</td>
<td>685.14</td>
<td>변동 비용</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10</td>
<td>(10 ÷ 100) × 1,245.71</td>
<td>124.57</td>
<td>변동 비용</td>
</tr>
</tbody>
</table>

총 비용(고정 비용과 변동 비용)의 할당 기준으로 재무 서비스를 적용한 결과는 다음과 같습니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>크기</th>
<th>할당 요소</th>
<th>금액</th>
<th>비용 동작</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>65</td>
<td>(65 ÷ 100) × (500.00 + 175.00)</td>
<td>438.75</td>
<td>고정 비용</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>35</td>
<td>(35 ÷ 100) × (500.00 + 175.00)</td>
<td>236.25</td>
<td>고정 비용</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>65</td>
<td>(65 ÷ 100) × (7,714.29 + 436.00)</td>
<td>5,297.69</td>
<td>변동 비용</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>35</td>
<td>(35 ÷ 100) × (7,714.29 + 436.00)</td>
<td>2,852.60</td>
<td>변동 비용</td>
</tr>
</tbody>
</table>

총 비용(고정 비용과 변동 비용)의 할당 기준으로 어셈블리 서비스를 적용한 결과는 다음과 같습니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>크기</th>
<th>할당 요소</th>
<th>금액</th>
<th>비용 동작</th>
</tr>
</thead>
<tbody>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275.00 + 438.75)</td>
<td>535.31</td>
<td>고정 비용</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275.00 + 438.75)</td>
<td>178.44</td>
<td>고정 비용</td>
</tr>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5,297.69 + 685.14)</td>
<td>4,487.12</td>
<td>변동 비용</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5,297.69 + 685.14)</td>
<td>1,495.71</td>
<td>변동 비용</td>
</tr>
</tbody>
</table>

총 비용(고정 비용과 변동 비용)의 할당 기준으로 패키징 서비스를 적용한 결과는 다음과 같습니다.

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th>크기</th>
<th>할당 요소</th>
<th>금액</th>
<th>비용 동작</th>
</tr>
</thead>
<tbody>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50.00 + 236.25)</td>
<td>241.05</td>
<td>고정 비용</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50.00 + 236.25)</td>
<td>45.20</td>
<td>고정 비용</td>
</tr>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2,852.60 + 124.57)</td>
<td>2,507.09</td>
<td>변동 비용</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2,852.60 + 124.57)</td>
<td>470.08</td>
<td>변동 비용</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>분개장 항목(비용 개체 잔액 분개장 항목)

<table>
<thead>
<tr>
<th>분개장</th>
<th>분개장 유형</th>
<th colspan="3">회계 달력 기간</th>
<th>버전</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>비용 할당 분개장</td>
<td>회계</td>
<td>2017</td>
<td>기간 1</td>
<td>간접비 계산 / 2017-01-02 오후 11:51:00 / 원장 / 2017 / 기간 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>분개장 라인

<table>
<thead>
<tr>
<th>회계 날짜</th>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017년 1월 31일</td>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>500.00</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>1,245.71</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>675.00</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>8,150.29</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>713.75</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>5,982.83</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC003</td>
<td>포장</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>286.25</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>CC003</td>
<td>포장</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>2,977.17</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>제품 1</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>776.36</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>제품 1</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>6,994.21</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>제품 2</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>223.64</td>
</tr>
<tr>
<td>2017년 1월 31일</td>
<td>제품 2</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>비용 항목

<table>
<thead>
<tr>
<th colspan="2">비용 개체</th>
<th colspan="2">비용 요소</th>
<th>비용 동작</th>
<th>금액</th>
<th>회계 날짜</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>-500.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>175.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>275.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>50,00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-1,245.71</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>436.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>685.14</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>124.57</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>-675.00</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>438.75</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>236.25</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC002</td>
<td>Finance</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-8,150.29</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>5,297.69</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC004</td>
<td>포장</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>2,852.60</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>-713.75</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>535.31</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>178.44</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-5,982.83</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>4,487.12</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>1,495.71</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>-286.25</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>241.05</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>10001</td>
<td>전기</td>
<td>고정 비용</td>
<td>45.20</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>CC003</td>
<td>어셈블리</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>-2,977.17</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 1</td>
<td>제품 1</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>2,507.09</td>
<td>2017년 1월 31일</td>
</tr>
<tr>
<td>제품 2</td>
<td>제품 2</td>
<td>10001</td>
<td>전기</td>
<td>변동 비용</td>
<td>470.08</td>
<td>2017년 1월 31일</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>결론
재무 회계에서 전기 요금 10,000.00이 더미 비용 센터 ID에 게시됩니다. 따라서 비용 회계사는 이 비용을 할당해야 한다고 알게 됩니다. 비용 회계에서 비용은 적용된 정책 및 규칙에 따라 조직 단위 및 수준에 걸쳐 흐릅니다. 각 비용이 비용 할당에 대한 최상의 평가를 제공하는 할당 기준과 연결되었습니다.

비용 요소 | 비용 개체<br>CC099 | 비용 개체<br>CC001 | 비용 개체<br>CC002 | 비용 개체<br>CC003 | 비용 개체<br>CC004 | 비용 개체<br>프로젝트 1 | 비용 개체<br>프로젝트 2 | 비용 개체<br>제품 1 | 비용 개체<br>제품 2 | 합계
---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:
10001 전기 | 0.00 | 0.00 | 0.00 | 0.00 |  | 30.00 | 10.00 | 7,770.57 | 2,189.43 | 10,000.00 |
미분류 | 0.00 |  |  |  |  |  |  |  |  |  |
고정 비용 | 0.00 | 0.00 | 0.00 | 0.00 | 0.00 |  |  | 776.36 | 223.64 | 1,000.00 |
변동 비용 | 000 | 0.00 | 0.00 | 0.00 | 0.00 | 30.00 | 10.00 | 6,994.21 | 1,965.79 | 9,000.00 |

> [!NOTE]
> 이 항목에서는 기본 비용 요소인 10001 전기가 비용 개체를 통해 흐르는 방식을 보여줍니다. 따라서 이 간접비는 조직의 가장 낮은 수준에 할당됩니다. 즉, 가장 낮은 수준의 비용 개체가 비용을 부담합니다. 비용 개체 간 비용의 시각적 흐름이 필요한 경우 비용 롤업 정책 규칙을 사용하여 비용 흐름을 시각화할 수 있습니다. 자세한 내용은 [비용 롤업 정책 및 간접비 계산](cost-rollup.md)을 참조하세요.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
