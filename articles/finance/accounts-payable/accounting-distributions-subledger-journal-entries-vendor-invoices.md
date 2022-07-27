---
title: 공급업체 송장에 대한 회계 분배 및 분개
description: 회계 분배는 비용, 세금 또는 요금이 공급업체 송장에 대해 설명되는 방법과 같이 금액이 설명되는 방법을 정의하는 데 사용됩니다. 공급업체 송장이 분개될 때 설명되어야 하는 모든 금액에는 하나 이상의 회계 분배가 있습니다.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451645"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>공급업체 송장에 대한 회계 분배 및 분개

[!include [banner](../includes/banner.md)]

회계 분배는 비용, 세금 또는 요금이 공급업체 송장에 대해 설명되는 방법과 같이 금액이 설명되는 방법을 정의하는 데 사용됩니다. 공급업체 송장이 분개될 때 설명되어야 하는 모든 금액에는 하나 이상의 회계 분배가 있습니다. 

## <a name="accounting-distributions"></a>회계 분배 

공급업체 송장 페이지에서 다음 버튼을 사용하여 공급업체 송장의 각 금액에 대한 회계 분배를 보고 수정할 수 있습니다.
-   **금액 분배** - 세금 또는 비용과 같은 개별 라인 및 모든 하위 라인에 대한 회계 분배를 보고 수정합니다. **판매세 거래** 페이지 또는 **비용 거래** 페이지에서 직접 하위 라인에 대한 회계 분배를 조회하고 수정할 수도 있습니다.
    -   요금 또는 통화 반올림 금액과 같은 공급업체 송장 헤더 금액을 수정합니다.
    -   공급업체 송장 라인 금액을 수정합니다.
-   **분포 보기** - 문서의 모든 라인에 대한 회계 분배를 봅니다. 이 보기에서는 회계 분배를 수정할 수 없습니다.
    -   헤더 및 라인 금액을 봅니다.

공급업체 송장이 구매 발주를 참조하는 경우 재고가 없는 품목이 포함된 라인에 대한 회계 분배를 분할하고 수정할 수 있습니다. 공급업체 송장 라인이 구매 발주 라인을 참조하지 않는 경우 회계 분배를 삭제할 수도 있습니다. 요금, 세금 및 라인 할인에 대한 라인을 분할하거나 삭제할 수 없습니다. 원장 계정은 수정할 수 있지만 금액이나 백분율은 변경할 수 없습니다.
> [!NOTE]                                                                                                                                 
> 상위 라인에 재고가 없는 품목이 포함되어 있고 회계 분배가 분할되면 상위 라인의 재무 차원과 일치하도록 하위 라인이 자동으로 분할됩니다. 하위 라인에 대한 회계 분배는 추가로 분할하거나 삭제할 수 없지만 하위 라인의 설정에 따라 하위 라인의 회계 분배에 대한 원장 계정을 수정할 수 있습니다.

## <a name="distributing-amounts"></a>금액 분배
공급업체 인보이스를 입력하면 각 금액이 다음과 같이 분배됩니다.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>공급업체 송장 라인 입력</th>
<th>기본 계정이 표시되는 위치를 결정하는 우선 순위</th>
<th>표시되는 기본 재무 차원을 결정하는 우선 순위</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>보관된 제품</td>
<td><ol>
<li>구매 발주 라인에 대한 회계 분배.</li>
<li><strong>게시</strong> 페이지에서 상품 구매비 선택 시 <strong>메인 계정</strong> 필드입니다.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장에 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>조달 카테고리 또는 재고가 없는 제품</td>
<td><ol>
<li>공급업체 송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배.</li>
<li><strong>게시</strong> 페이지에서 경비 구매비 선택 시 <strong>메인 계정</strong> 필드입니다.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>기본 계정이 할당 계정인 경우 할당 계정 정의의 기본값을 사용합니다.</li>
<li>공급업체 송장에 기본 재무 차원 값을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>고정 자산</td>
<td><ol>
<li>공급업체 송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배.</li>
<li><strong>공급업체 송장</strong> 페이지의 <strong>거래 유형</strong> 필드에서 <strong>취득</strong>을 선택한 경우 <strong>고정 자산 게시 프로필</strong> 페이지에서 <strong>취득</strong>을 선택한 경우 <strong>기본 계정</strong> 필드입니다.</li>
<li><strong>거래 유형</strong> 필드에서 <strong>취득 조정</strong>을 선택한 경우 <strong>고정 자산 게시 프로필</strong> 페이지에서 <strong>취득 조정</strong>을 선택한 경우 <strong>기본 계정</strong> 필드입니다.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>공급업체 송장 라인에 정의된 프로젝트</td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배입니다.</li>
<li><strong>프로젝트 그룹</strong> 페이지의 <strong>전기 비용 - 항목</strong> 필드에서 <strong>잔액</strong>을 선택한 경우 <strong>원장 전기 설정</strong> 페이지에서 <strong>비용</strong>을 선택한 경우 <strong>기본 계정</strong> 필드입니다.</li>
<li><strong>프로젝트 그룹</strong> 페이지의 <strong>전기 비용 - 항목</strong> 필드에서 <strong>수익 및 손실</strong>을 선택한 경우 <strong>원장 전기 설정</strong> 페이지에서 <strong>비용 - 항목</strong>을 선택한 경우 <strong>기본 계정</strong> 필드입니다.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>라인 할인</td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배입니다.</li>
<li><strong>게시</strong> 페이지에서 <strong>할인</strong>을 선택한 경우 <strong>기본 계정</strong> 필드입니다.</li>
<li>할인에 대한 기본 계정이 전기 프로필에 정의되지 않은 경우 구매 발주 라인의 확장 가격 회계 분배입니다.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 확장 가격에 대한 회계 분배의 재무 차원을 사용합니다.</li>
<li>공급업체 송장 라인에 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>구매 주문 라인의 <strong>가격 및 할인</strong> 탭에 입력된 구매 비용</td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배입니다.</li>
<li>구매 발주 라인의 확장 가격 회계 분배.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 확장 가격에 대한 회계 분배의 재무 차원을 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>라인 요금</td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배입니다.</li>
<li><strong>비용 코드</strong> 페이지의 <strong>차변 유형</strong> 필드에서 <strong>원장 계정</strong>을 선택한 경우 <strong>비용 코드</strong> 페이지의 <strong>차변 계정</strong> 필드.</li>
<li><strong>비용 코드</strong> 페이지의 <strong>차변 유형</strong> 필드에서 <strong>품목</strong>을 선택한 경우 구매 발주 라인의 확장 가격에 대한 회계 분배.</li>
<li><strong>비용 코드</strong> 페이지의 <strong>차변 유형</strong> 필드에서 <strong>고객/공급업체</strong>를 선택한 경우 <strong>비용 코드</strong> 페이지의 <strong>대변 계정</strong> 필드.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 확장 가격에 대한 회계 분배의 재무 차원을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>다음 조건이 적용된 세금:
<ul>
<li><strong>미국 과세 규칙 적용</strong> 옵션은 <strong>총계정원장 매개 변수</strong> 페이지에서 선택됩니다.</li>
</ul></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 회계 분배입니다.</li>
<li>총 금액 또는 요금의 회계 분배.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 확장 가격에 대한 회계 분배의 재무 차원을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>다음 조건이 적용된 세금:
<ul>
<li><strong>미국 과세 규칙 적용</strong> 옵션은 <strong>총계정원장 매개 변수</strong> 페이지에서 삭제됩니다.</li>
<li><strong>판매세 그룹</strong>에 대한 <strong>사용세</strong> 필드는 판매세 그룹 페이지에서 지워집니다.</li>
</ul></td>
<td><ol>
<li>세액이 공제 가능한 경우 <strong>원장 전기 그룹</strong> 페이지의 <strong>받을 판매세</strong> 필드입니다.</li>
<li>세액을 회수할 수 없는 경우 요금에 대한 확장 가격 또는 회계 분배.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 비용에 대해 확장 가격 또는 회계 분배의 재무 차원을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>다음 조건이 적용된 세금:
<ul>
<li>미국 과세 규칙 적용 옵션은 <strong>총계정원장 매개 변수</strong> 페이지에서 삭제됩니다.</li>
<li><strong>판매세 그룹</strong>에 대한 <strong>사용세</strong> 필드는 판매세 그룹 페이지에서 선택됩니다.</li>
</ul></td>
<td><ol>
<li>세액이 공제 가능한 경우 <strong>원장 전기 그룹</strong> 페이지의 <strong>받을 판매세</strong> 필드입니다.</li>
<li>세액을 회수할 수 없는 경우 <strong>원장 전기 그룹</strong> 페이지의 <strong>세금 사용</strong> 필드.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 비용에 대해 확장 가격 또는 회계 분배의 재무 차원을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>머리글 요금</td>
<td><ol>
<li><strong>비용 코드</strong> 페이지의 <strong>차변 유형</strong> 필드에서 <strong>원장 계정</strong>을 선택한 경우 <strong>비용 코드</strong> 페이지의 <strong>차변 계정</strong> 필드.</li>
<li><strong>비용 코드</strong> 페이지의 <strong>차변 유형</strong> 필드에서 <strong>고객/공급업체</strong>를 선택한 경우 <strong>비용 코드</strong> 페이지의 <strong>대변 계정</strong> 필드.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>기본 계정이 할당 계정인 경우 할당 계정 정의의 기본값을 사용합니다.</li>
<li>공급업체 송장 헤더의 재무 차원 기본 템플릿 값을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>헤더 할인</td>
<td><ol>
<li><strong>자동 거래를 위한 계정</strong> 페이지의 <strong>공급업체 송장 할인 전기 유형</strong>에 대한 <strong>기본 계정</strong> 필드입니다.</li>
</ol></td>
<td><ol>
<li>송장 라인이 구매 발주 라인을 참조하는 경우 구매 발주 라인에 대한 계정 분배를 사용합니다.</li>
<li>공급업체 송장 라인의 확장 가격에 대한 회계 분배의 재무 차원을 사용합니다.</li>
<li>공급업체 송장 라인의 재무 차원 값을 사용합니다.</li>
<li><strong>계정 차트</strong> 페이지에서 기본 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>세금 분배

세금에 대한 회계 분배는 세금 계산이 끝나야 생성할 수 없습니다. 판매세를 계산하려면 **공급업체 송장** 페이지에서 다음 작업 중 하나를 완료해야 합니다.
-   송장 합계를 봅니다.
-   판매세를 봅니다.
-   보조 원장 분개장을 봅니다.
-   전체 공급업체 송장에 대한 회계 분배를 봅니다.
-   공급업체 송장을 보류합니다.
-   공급업체 송장을 기장합니다.

## <a name="subledger-journals-for-vendor-invoices"></a>공급업체 송장에 대한 보조원장 분개장
공급업체 송장을 전기하기 전에 차변과 대변을 포함하는 송장의 전체 회계 항목을 보고 송장이 올바른 계정에 전기되고 있는지 확인할 수 있습니다. 전체 회계 입력의 이 보기를 보조원장 분개장이라고 합니다. 

공급업체 송장을 분개하기 전에 미리 볼 때 보조 원장 분개장 항목이 잘못된 경우 보조 원장 분개장 항목을 수정할 수 없습니다. 대신 회계 분배 또는 전기 프로필을 수정해야 합니다. 회계 분배는 회계 입력의 한 면인 차변 또는 대변을 정의하는 데 사용됩니다. 상계 보조원장 분개 계정 입력은 공급업체 계정 또는 세금과 같은 전기 프로필을 사용하여 생성됩니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
