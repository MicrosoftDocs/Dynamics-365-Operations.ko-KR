---
title: 자유 텍스트 송장에 대한 회계 분배 및 분개
description: 회계 분배는 수입, 세금 또는 요금이 자유 텍스트 송장에 대해 설명되는 방법과 같이 금액이 설명되는 방법을 정의하는 데 사용됩니다. 자유 텍스트 송장이 분개될 때 설명되어야 하는 모든 금액에는 하나 이상의 회계 분배가 있습니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da1d1b41c4da1fafcf20246022c4020b60152917f5df85f8e003e23aaef9433c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450298"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>자유 텍스트 송장에 대한 회계 분배 및 보조원장 입력

[!include [banner](../includes/banner.md)]

회계 분배는 수입, 세금 또는 요금이 자유 텍스트 송장에 대해 설명되는 방법과 같이 금액이 설명되는 방법을 정의하는 데 사용됩니다. 자유 텍스트 송장이 분개될 때 설명되어야 하는 모든 금액에는 하나 이상의 회계 분배가 있습니다.

## <a name="accounting-distributions"></a>회계 분배

자유 텍스트 송장 페이지에서 다음 버튼을 사용하여 자유 텍스트 송장의 각 금액에 대한 회계 분배를 보고 변경할 수 있습니다.

-   **금액 분배** - 세금 또는 비용과 같은 개별 라인 및 모든 하위 라인에 대한 회계 분배를 보고 변경합니다. 판매세 거래 페이지 또는 비용 거래 페이지에서 직접 하위 라인에 대한 회계 분배를 조회하고 변경할 수도 있습니다.
    -   요금 또는 통화 반올림 금액과 같은 자유 텍스트 송장 헤더 금액을 변경합니다.
    -   자유 텍스트 송장 라인 금액을 변경합니다.
-   **분배 보기** - 문서의 모든 라인에 대한 회계 분배를 봅니다. 이 보기에서는 회계 분배를 변경할 수 없습니다.
    -   헤더 및 라인 금액을 봅니다.

## <a name="distributing-amounts"></a>금액 분배
자유 텍스트 인보이스를 입력하면 각 금액이 다음과 같이 분배됩니다.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>금액 유형</th>
<th>기본 계정이 표시되는 위치</th>
<th>표시되는 기본 재무 차원을 결정하는 우선 순위</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>자유 텍스트 송장 라인</td>
<td>자유 텍스트 송장 라인의 원장 계정.</td>
<td><ol>
<li>기본 계정이 할당 계정인 경우 할당 계정 정의의 기본값을 사용합니다.</li>
<li>기본 계정이 할당 계정이 아닌 경우 자유 텍스트 송장 라인에서 재무 차원 기본 템플릿을 사용합니다.</li>
<li>자유 텍스트 송장 라인에 기본 재무 차원 값을 사용합니다.</li>
<li>계정 차트 페이지에서 원장 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>고정 자산 번호 및 가치 모델 조합에 대한 자유 텍스트 송장 라인
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>메모</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>자유 텍스트 송장 라인의 기본 계정은 고정 자산 처분 계정입니다.</td>
</tr>
</tbody>
</table>
</div></td>
<td>자유 텍스트 송장 라인의 원장 계정.</td>
<td><ol>
<li>자유 텍스트 송장 라인에 기본 재무 차원 값을 사용합니다.</li>
<li>계정 차트 페이지에서 원장 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>무료 문자 송장 할인 금액</td>
<td>현금 할인 페이지의 고객 할인에 대한 기본 계정 필드입니다.</td>
<td><ol>
<li>기본 계정이 할당 계정인 경우 할당 계정 정의의 기본값을 사용합니다.</li>
<li>기본 계정이 할당 계정이 아닌 경우 자유 텍스트 송장 라인에서 재무 차원 기본 템플릿을 사용합니다.</li>
<li>자유 텍스트 송장 라인에 기본 재무 차원 값을 사용합니다.</li>
<li>계정 차트 페이지에서 원장 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="even">
<td>자유 텍스트 송장 판매세 금액</td>
<td>원장 게시 그룹 페이지의 판매세 지불 필드입니다.</td>
<td><ol>
<li>자유 텍스트 송장 라인 금액 또는 비용 라인 금액에 대한 분배에 정의된 재무 차원을 사용합니다.</li>
<li>자유 텍스트 송장 라인에 기본 재무 차원 값을 사용합니다.</li>
<li>계정 차트 페이지에서 원장 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
<tr class="odd">
<td>자유 텍스트 송장 청구 라인 금액</td>
<td>요금 코드 페이지의 신용 계정 필드.</td>
<td><ol>
<li>기본 계정이 할당 계정인 경우 할당 계정 정의의 기본값을 사용합니다.</li>
<li>기본 계정이 할당 계정이 아닌 경우 자유 텍스트 송장 라인에서 재무 차원 기본 템플릿을 사용합니다.</li>
<li>자유 텍스트 송장 라인에 기본 재무 차원 값을 사용합니다.</li>
<li>계정 차트 페이지에서 원장 계정의 기본 재무 차원 값을 사용합니다.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>세금 분배
세금에 대한 회계 분배는 세금 계산이 끝나야 생성할 수 없습니다. 판매세를 계산하려면 자유 텍스트 송장 양식에서 다음 작업 중 하나를 완료해야 합니다.
-   판매세를 봅니다.
-   송장 합계를 봅니다.
-   현금 흐름을 봅니다.
-   전체 자유 텍스트 송장에 대한 회계 분배를 봅니다.
-   보조 원장 분개장을 봅니다.

## <a name="subledger-journals-for-free-text-invoices"></a>자유 텍스트 송장에 대한 보조원장 분개장
자유 텍스트 송장을 전기하기 전에 차변과 대변을 포함하는 송장의 전체 회계 항목을 보고 송장이 올바른 계정에 전기되고 있는지 확인할 수 있습니다. 전체 회계 입력의 이 보기를 보조원장 분개장이라고 합니다. 자유 텍스트 송장을 분개하기 전에 미리 볼 때 보조원장 분개 항목이 잘못된 경우 보조원장 분개 항목을 변경할 수 없습니다. 대신 회계 분배 또는 전기 프로필을 변경해야 합니다. 회계 분배는 회계 입력의 한 면인 차변 또는 대변을 정의하는 데 사용됩니다. 상계 보조원장 분개 계정 입력은 전기 프로필(예: 고객 계정 또는 세금)에서 생성됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]