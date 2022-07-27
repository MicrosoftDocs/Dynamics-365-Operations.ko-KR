---
title: 감소일 예시
description: 감소일 예시입니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97fb032d02df1dbedaeccec14496cb1d63e8cf70
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448066"
---
# <a name="reduction-days-example"></a>감소일 예시

[!include [banner](../includes/banner.md)]

다음 표에 설명된 대로 고객의 유지 관리 구독에 대한 구독 트랜잭션을 생성했습니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>시작일</p></th>
<th><p>종료일</p></th>
<th><p>구독</p></th>
<th><p>구독 유형</p></th>
<th><p>프로젝트 </p></th>
<th><p>카테고리</p></th>
<th><p>판매 통화</p></th>
<th><p>판매 가격</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2011년 3월 01일</p></td>
<td><p>2011년 3월 31일</p></td>
<td><p>NR-2</p></td>
<td><p><strong>정기</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>200.00</p></td>
</tr>
</tbody>
</table>

고객이 이틀(3월 10일 및 3월 11일) 동안 서비스 적용 범위가 필요하지 않다고 보고합니다. 귀하는 이 2일까지 구독량을 줄이는 데 동의합니다.

다음 표에 설명된 대로 **감소 일** 유형의 새 트랜잭션을 생성합니다.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>시작일</p></th>
<th><p>종료일</p></th>
<th><p>구독</p></th>
<th><p>구독 유형</p></th>
<th><p>프로젝트 </p></th>
<th><p>카테고리</p></th>
<th><p>판매 통화</p></th>
<th><p>판매 가격</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2011년 3월 10일</p></td>
<td><p>2011년 3월 11일</p></td>
<td><p>NR-2</p></td>
<td><p><strong>감소일 수</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>-12.90</p></td>
</tr>
</tbody>
</table>

2011년 3월 거래에 대한 송장이 발행되면 200 EUR의 판매 가격이 12.90 EUR만큼 감소합니다. 따라서 구독 거래에 대해 청구 가능한 금액은 EUR 187.10이고 두 거래에 대해 총 EUR 187.10의 송장이 청구됩니다.

## <a name="see-also"></a>참고 항목

[구독료 일 수 감소](reduce-the-days-on-subscription-fees.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]