---
title: 재고 개체 값
description: 이 문서에서는 재고 개체의 값을 계산하는 방법에 대한 정보를 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6564df5bd9c768f647138714875c60ddd6df3c85
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448159"
---
# <a name="inventory-object-values"></a>재고 개체 값

[!include [banner](../includes/banner.md)]

이 문서에서는 재고 개체의 값을 계산하는 방법에 대한 정보를 제공합니다. 

**물리적 수량** 이라는 새로운 기능을 사용하면 특정 재고 개체의 값을 볼 수 있습니다. 

비용 개체는 재고 회계가 수행되는 엔터티 수준을 나타냅니다. 비용 개체에 대한 자세한 내용은 [비용 개체](cost-object.md)를 참조하세요. 

특정 재고 개체의 값을 보려면 **비용 개체** 페이지에서 **물리적 수량** 을 클릭합니다. 재고 개체의 값이 계산되는 방법은 다음과 같습니다. 

재고 object.Value = 비용 object.Average 단가 × 재고 object.Quantity 

다음 예는 재고 개체 및 비용 개체의 값이 계산되는 방법을 보여줍니다. 품목 A에 두 개의 제품 영수증 이벤트가 등록되었습니다.

-   제품 입고 1: 수량 = 100개, 금액 = $1,000.00, 사이트 = 1, 창고 =11, 배치 번호 = B1
-   제품 입고 2: 수량 = 50개, 금액 = $800.00, 사이트 = 1, 창고 =11, 배치 번호 = B2

다음 표는 원가 개체에 대한 계산 결과를 보여줍니다. **비용 개체** 페이지에서 결과를 볼 수 있습니다.

<table>
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>개체 유형</th>
<th>품목 번호</th>
<th>사이트</th>
<th>수량</th>
<th>재고 단위</th>
<th>값</th>
<th>평균 단가</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>원가 개체</td>
<td>A</td>
<td>1</td>
<td>150</td>
<td>개</td>
<td><p>$1800.00</p></td>
<td><p>$12.00</p></td>
</tr>
</tbody>
</table>

다음 표는 재고 개체에 대한 계산 결과를 보여줍니다. **비용 개체** 페이지에서 **물리적 수량** 을 클릭하여 결과를 볼 수 있습니다.

<table>
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>개체 유형</th>
<th>품목 번호</th>
<th>사이트</th>
<th>창고</th>
<th>배치 번호</th>
<th>수량</th>
<th>재고 단위</th>
<th>값</th>
<th>평균 단가</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>인벤토리 개체</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>개</td>
<td><p>$1200.00</p></td>
<td><p>$12.00</p></td>
</tr>
<tr class="even">
<td>인벤토리 개체</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>개</td>
<td><p>$600.00</p></td>
<td><p>$12.00</p></td>
</tr>
</tbody>
</table>



## <a name="additional-resources"></a>추가 리소스

[원가 개체](cost-object.md)

[비용 항목](cost-entries.md)

[새로운 기능 및 변경된 기능](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]