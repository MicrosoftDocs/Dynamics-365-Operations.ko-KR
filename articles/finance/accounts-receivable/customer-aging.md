---
title: 고객 에이징 보고서
description: 고객 에이징 보고서에는 날짜 간격 또는 에이징 기간별로 정렬된 고객의 잔액이 표시됩니다.
author: JodiChristiansen
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33bee60a3807c92cc97f0f5e6d660a67cdd7f297
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451015"
---
# <a name="customer-aging-report"></a>고객 에이징 보고서 

**고객 에이징** 보고서에는 날짜 간격 또는 에이징 기간별로 정렬된 고객의 잔액이 표시됩니다.

이 보고서를 생성하면 다음 기본 매개 변수가 표시됩니다. 이 매개 변수를 사용하여 보고서에 표시될 데이터를 필터링할 수 있습니다. 자세한 내용은 [수금 설정](set-up-collections.md)을 참조하십시오.

<table>
<colgroup>
<col>
<col>
</colgroup>
<thead>
<tr class="header">
<th><p>필드</p></th>
<th><p>설명</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>청구 분류</strong></p></td>
<td><p>보고서에 포함할 하나 이상의 청구 분류를 선택합니다.</p>
<div class="alert">

**참고:** 이 컨트롤은 <STRONG>공공 부문</STRONG> 구성 키가 선택된 경우에만 사용할 수 있습니다.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>청구 분류가 없는 거래 포함</strong></p></td>
<td><p>이 확인란을 선택하면 청구 분류가 할당되지 않은 모든 거래가 보고서에 표시됩니다.</p>
<div class="alert">

**참고:** 이 컨트롤은 <STRONG>공공 부문</STRONG> 구성 키가 선택된 경우에만 사용할 수 있습니다.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>에이징 기준 시점</strong></p></td>
<td><p>현재 에이징 버킷에 사용된 날짜를 입력합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>잔액 기준 시점</strong></p></td>
<td><p>고객 잔액을 조회할 날짜를 입력합니다. 거래 마감일이라고도 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>시작 날짜</strong></p></td>
<td><p>보고서에 포함할 첫 번째 기간 간격 또는 에이징 기간에 있는 날짜를 입력합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>기준</strong></p></td>
<td><p>보고서의 기준이 될 날짜 유형을 선택합니다.</p>
<ul>
<li><p><strong>거래 날짜</strong> – 거래의 전기 날짜. 예를 들어 만기일 계산의 기준이 되는 송장 날짜일 수 있습니다.</p></li>
<li><p><strong>만기일</strong> – 지불 조건에 따른 거래 기한.</p></li>
<li><p><strong>문서 날짜</strong> – 만기일 계산의 기준이 되는 사용자 정의 문서 날짜입니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>에이징 기간 정의</strong></p></td>
<td><p>에이징 기간 정의를 선택합니다. 에이징 기간 정의를 선택한 경우 <strong>간격</strong> 필드는 사용되지 않습니다.</p>
<p>6개 이상의 에이징 기간이 있는 에이징 기간 정의는 인쇄된 보고서에 사용할 수 없습니다.</p>
<div class="alert">

**참고:** <STRONG>에이징 기간 정의</STRONG> 페이지에서 에이징 기간을 설정할 수 있습니다.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>에이징 기간 설명 인쇄</strong></p></td>
<td><p><strong>예</strong>를 선택하여 보고서의 각 에이징 기간 열 상단에 에이징 기간 설명을 포함합니다. <strong>아니요</strong>를 선택하여 열 헤더 없이 보고서를 인쇄합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>간격</strong></p></td>
<td><p>각 기간의 일 또는 월 단위 수를 입력하여 사용할 기간을 정의합니다. 예를 들어, 주별 에이징 정보를 보려면 이 필드에 7을 입력하고 <strong>일/월</strong> 필드에서 <strong>일</strong>을 선택합니다.</p>
<div class="alert">

**참고:** 이 필드에 입력하는 정보는 에이징 기간 정의를 선택하지 않은 경우에만 사용됩니다. 그렇지 않으면 에이징 기간 정의에 인쇄 방향이 정의됩니다.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>일/월</strong></p></td>
<td><p><strong>간격</strong> 필드에서 기간을 정의하는 데 사용되는 단위로 <strong>일</strong> 또는 <strong>월</strong>를 선택합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인쇄 방향</strong></p></td>
<td><p>잔액을 계산하고 과거 또는 미래 기간에 대한 에이징 보고서를 인쇄할지 여부를 선택합니다. 날짜는 <strong>잔액 기준 날짜</strong> 필드에 선택된 날짜를 기준으로 평가됩니다. <strong>뒤로</strong>를 선택하여 과거 기간에 대한 정보를 표시합니다. <strong>앞으로</strong>를 선택하여 미래 기간에 대한 정보를 표시합니다.</p>
<div class="alert">
  
<STRONG>참고:</STRONG> 이 필드에 입력하는 정보는 에이징 기간 정의를 선택하지 않은 경우에만 사용됩니다.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>세부 정보</strong></p></td>
<td><p>보고서에 표시되는 잔액에 포함된 거래를 나열하려면 선택합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>거래 통화의 금액 포함</strong></p></td>
<td><p>회계 통화의 금액 외에 거래 통화의 금액을 포함하려면 선택합니다. 이 확인란을 선택하지 않으면 보고서의 금액이 회계 통화로만 표시됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>마이너스 잔액</strong></p></td>
<td><p>마이너스 잔액이 있는 고객 계정을 포함하려면 선택합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>잔액 없는 계정 제외</strong></p></td>
<td><p>잔액이 0인 고객 계정을 제외하려면 선택합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>지불 위치</strong></p></td>
<td><p>정산되지 않은 지불을 표시하려면 선택합니다. 보고서의 첫 번째 열에 표시됩니다.</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]