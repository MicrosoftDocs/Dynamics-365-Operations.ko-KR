---
title: 고급 필터링 및 쿼리 구문
description: 이번에는 고급 필터/정렬 대화 상자의 필터링 및 쿼리 옵션과 필터 창 또는 그리드 열 머리글 필터의 일치 연산자에 대해 설명합니다.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0fefac5a7a2b299ba606a854824ee456c572487
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460607"
---
# <a name="advanced-filtering-and-query-syntax"></a>고급 필터링 및 쿼리 구문

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이번에는 고급 필터/정렬 대화 상자 또는 필터 창 또는 그리드 열 머리글 필터의 **일치** 연산자를 사용할 때 사용할 수 있는 필터링 및 쿼리 옵션에 대해 설명합니다.

## <a name="advanced-query-syntax"></a>고급 쿼리 구문

<table>
<thead>
<tr>
<th>구문</th>
<th>캐릭터 설명</th>
<th>설명</th>
<th>예시</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>값</em></td>
<td>입력한 값과 동일</td>
<td>찾을 값을 입력합니다.</td>
<td><strong>스미스</strong>는 &quot;스미스&quot;를 찾습니다.</td>
</tr>
<tr>
<td>!<em>값</em>(느낌표)</td>
<td>입력한 값과 같지 않음</td>
<td>느낌표를 입력한 다음 제외할 값을 입력합니다.</td>
<td><strong>!Smith</strong>는 &quot;Smith&quot;를 제외한 모든 값을 찾습니다.</td>
</tr>
<tr>
<td><em>from-value</em>..<em>to-value</em>(마침표 이중)</td>
<td>이중 마침표로 구분된 두 값 사이</td>
<td>시작 값, 마침표 두 개, 종료 값을 차례로 입력합니다.</td>
<td><strong>1..10</strong>은 1에서 10까지의 모든 값을 찾습니다. 그러나 스트링 필드에서 <strong>A..C</strong>는 &quot;A&quot;와 &quot;B&quot;로 시작하는 모든 값과 &quot;C&quot;와 정확히 같은 값을 찾습니다. 예를 들어, 이 쿼리는 &quot;Ca&quot;를 찾지 않습니다. &quot;A<em>&quot;부터 &quot;C</em>&quot;까지의 모든 값을 찾으려면 <strong>A..D</strong>를 입력합니다.</td>
</tr>
<tr>
<td>..<em>값</em>(이중 마침표)</td>
<td>입력한 값보다 작거나 같음</td>
<td>마침표 두 개를 입력한 다음 값을 입력합니다.</td>
<td><strong>..1000</strong>은 &quot;100&quot;, &quot;999.95&quot;, &quot;1,000&quot;과 같이 1000보다 작거나 같은 숫자를 찾습니다.</td>
</tr>
<tr>
<td><em>값</em>.. (이중 마침표)</td>
<td>입력한 값보다 크거나 같음</td>
<td>값을 입력한 다음 마침표 두 개를 입력합니다.</td>
<td><strong>1000..</strong> &quot;1,000&quot;, &quot;1,000.01&quot; 및 &quot;1,000,000&quot;과 같이 1000보다 크거나 같은 숫자를 찾습니다.</td>
</tr>
<tr>
<td>&gt;<em>값</em>(보다 큼 기호)</td>
<td>입력한 값보다 큼</td>
<td>보다 큼 기호(<strong>&gt;</strong>)를 입력한 다음 값을 입력합니다.</td>
<td><strong>&gt;1000</strong>은 &quot;1000.01&quot;, &quot;20,000&quot; 및 &quot;1,000,000&quot;과 같이 1000보다 큰 숫자를 찾습니다.</td>
</tr>
<tr>
<td>&lt;<em>값</em>(미만 기호)</td>
<td>입력한 값보다 작음</td>
<td>보다 작음 기호(<strong>&lt;</strong>)를 입력한 다음 값을 입력합니다.</td>
<td><strong>&lt;1000</strong>은 &quot;999.99&quot;, &quot;1&quot; 및 &quot;-200&quot;과 같이 1000보다 작은 숫자를 찾습니다.</td>
</tr>
<tr>
<td><em>값</em>* (별표)</td>
<td>입력한 값부터 시작</td>
<td>시작 값을 입력한 다음 별표(<strong>*</strong>)를 입력합니다.</td>
<td><strong>S*</strong>는 &quot;스톡홀름&quot;, &quot;시드니&quot;, &quot;샌프란시스코&quot;와 같이 &quot;S&quot;로 시작하는 모든 스트링을 찾습니다.</td>
</tr>
<tr>
<td>*<em>값</em> (별표)</td>
<td>입력한 값으로 종료</td>
<td>별표를 입력한 다음 끝 값을 입력합니다.</td>
<td><strong>*east</strong>는 &quot;Northeast&quot; 및 &quot;South&quot;와 같이 &quot;동쪽&quot;으로 끝나는 스트링을 찾습니다.</td>
</tr>
<tr>
<td>*<em>값</em>*(별표)</td>
<td>입력된 값을 포함</td>
<td>별표를 입력한 다음 값을 입력한 다음 다른 별표를 입력합니다.</td>
<td><strong>*th*</strong>는 &quot;Northeast&quot; 및 &quot;Southeast&quot;와 같이 &quot;th&quot;가 포함된 모든 스트링을 찾습니다.</td>
</tr>
<tr>
<td>? (물음표)</td>
<td>알 수 없는 문자가 하나 이상 있는 경우</td>
<td>값에서 알 수 없는 문자의 위치에 물음표를 입력합니다.</td>
<td><strong>Sm?th</strong>는 &quot;Smith&quot;와 &quot;Smyth&quot;를 찾습니다.</td>
</tr>
<tr>
<td><em>value</em>,<em>value</em> (쉼표)</td>
<td>쉼표로 구분된 값 일치</td>
<td>모든 기준을 입력하고 쉼표를 사용하여 구분합니다.</td>
<td><strong>A, D, F, G</strong>는 정확히 &quot;A&quot;, &quot;D&quot;, &quot;F&quot;, &quot;G&quot;를 찾습니다. <strong>10, 20, 30, 100</strong>은 정확히 &quot;10, 20, 30, 100&quot;을 찾습니다.</td>
</tr>
<tr>
<td>(큰따옴표 두 개)</td>
<td>공백 값 일치</td>
<td>두 개의 연속적인 큰따옴표를 입력하여 해당 필드의 빈 값을 필터링합니다.</td>
<td>두 개의 연속된 큰따옴표(<strong>''</strong>)는 현재 열에 대한 값이 없는 행을 찾습니다.</td>
</tr>
<tr>
<td>(<span class="code">재무 및 운영 쿼리</span>) (괄호 사이에 재무 및 운영 쿼리)</td>
<td>정의된 쿼리 일치</td>
<td>재무 및 운영 쿼리 언어를 사용하여 괄호 안에 쿼리를 SQL 문으로 입력합니다.</td>
  <td><strong><span class="code">((AccountNum LIKE 'US *') && (DirPartyTable.Name LIKE 'Cont*'))</span></strong><br><br> 
       루트 데이터 소스의 필드와 다른 데이터 소스의 필드(모든 고객 페이지의 경우)에 대한 필터 조건 구문의 예</td>
</tr>
<tr>
<td>티</td>
<td>오늘 날짜</td>
<td><strong>T</strong>를 입력합니다.</td>
<td><strong>T</strong>는 오늘 날짜와 일치합니다.</td>
</tr>
<tr>
<td>(methodName(parameters)) (괄호 사이의 <strong>SysQueryRangeUtil</strong> 메서드)</td>
<td><strong>SysQueryRangeUtil</strong> 메서드의 매개 변수로 지정된 값 또는 값 범위 일치</td>
<td>값 또는 값 범위를 지정하는 매개 변수가 있는 <strong>SysQueryRangeUtil</strong> 메서드를 입력합니다.</td>
<td>
<ol>
<li><strong>미수금</strong> &gt; <strong>송장</strong> &gt; <strong>고객 송장 열기</strong>를 클릭합니다.</li>
<li>Ctrl+Shift+F3을 눌러 <strong>문의</strong> 페이지를 엽니다.</li>
<li><strong>범위</strong> 탭에서 <strong>추가</strong>를 클릭합니다.</li>
<li><strong>테이블</strong> 필드에서 <strong>고객 거래 열기</strong>를 선택합니다.</li>
<li><strong>필드</strong> 필드에서 <strong>기한</strong>을 선택합니다.</li>
<li><strong>기준</strong> 필드에 <strong>(yearRange(-2,0))</strong>을 입력합니다.</li>
<li><strong>확인</strong>을 클릭합니다. 목록 페이지가 업데이트되고 입력한 기준과 일치하는 송장이 나열됩니다. 이 예시에서는 지난 2년 동안 만기가 된 송장이 나열됩니다.</li>
</ol>
<strong>SysQueryRangeUtil</strong> 날짜 메서드 및 몇 가지 예에 대한 자세한 내용은 다음 섹션의 표를 참조하십시오.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>SysQueryRangeUtil 메서드를 사용하는 고급 날짜 쿼리

<table>
<thead>
<tr>
<th>메서드</th>
<th>설명</th>
<th>예시</th>
</tr>
</thead>
<tbody>
<tr>
<td>일(_relativeDays=0)</td>
<td>세션 날짜를 기준으로 날짜를 찾습니다. 양수 값은 미래 날짜를 나타내고 음수 값은 과거 날짜를 나타냅니다.</td>
<td>
<ul>
<li><strong>내일</strong> – <strong>(일(1))</strong>을 입력합니다.</li>
<li><strong>오늘</strong> – <strong>(일(0))</strong>을 입력합니다.</li>
<li><strong>어제</strong> – <strong>(일(-1))</strong>을 입력합니다.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange(_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>세션 날짜를 기준으로 날짜 범위를 찾습니다. 양수 값은 미래 날짜를 나타내고 음수 값은 과거 날짜를 나타냅니다.</td>
<td>
<ul>
<li><strong>지난 30일</strong> – <strong>(DayRange(-30,0))</strong>을 입력합니다.</li>
<li><strong>이전 30일 및 다음 30일</strong> – <strong>(DayRange(-30,30))</strong>을 입력합니다.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate(_relativeDays=0) GreaterThanUtcDate(_relativeDays=0)</td>
<td>지정된 상대 날짜 이후의 모든 날짜를 찾습니다.</td>
<td>
<ul>
<li><strong>지금부터 30일 이상</strong> – Enter <strong>(GreaterThanDate(30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow()</td>
<td>현재 시간 이후의 모든 날짜/시간 항목을 찾습니다.</td>
<td>
<ul>
<li><strong>미래의 모든 날짜/시간</strong> – <strong>(GreaterThanUtcNow())</strong>를 입력합니다.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate(_relativeDays=0) LessThanUtcDate(_relativeDays=0)</td>
<td>지정된 상대 날짜 이전의 모든 날짜를 찾습니다.</td>
<td>
<ul>
<li><strong>지금부터 7일 이내</strong> – Enter <strong>(LessThanDate(7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow()</td>
<td>현재 시간 이전의 모든 날짜/시간 항목을 찾습니다.</td>
<td>
<ul>
<li><strong>모든 과거 날짜/시간</strong> – Enter <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>월 범위(_relativeFrom=0, _relativeTo=0)</td>
<td>현재 월을 기준으로 하여 날짜 범위를 찾습니다.</td>
<td>
<ul>
<li><strong>이전 2개월</strong> – <strong>(MonthRange(-2,0))</strong>을 입력합니다.</li>
<li><strong>다음 3개월</strong> – <strong>(MonthRange(0,3))</strong>을 입력합니다.</li>
</ul>
</td>
</tr>
<tr>
<td>연도 범위(_relativeFrom=0, _relativeTo=0)</td>
<td>현재 연도를 기준으로 연도를 기준으로 날짜 범위를 찾습니다.</td>
<td>
<ul>
<li><strong>내년</strong> – <strong>(YearRange(0, 1))</strong>을 입력합니다.</li>
<li><strong>이전 연도</strong> – <strong>(YearRange(-1,0))</strong>를 입력합니다.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]