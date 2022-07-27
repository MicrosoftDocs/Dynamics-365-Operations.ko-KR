---
title: 공급업체 송장 및 송장 승인 분개장에 대한 기본 상쇄 계정
description: 이 항목은 송장 분개장의 기본 계정을 할당해야 하는 위치를 결정하는 방법을 설명합니다.
author: abruer
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1b0184850602191da5448df25779437f70e5c3182e1b7b70d92d4c406e08599
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450520"
---
# <a name="default-offset-accounts-for-vendor-invoice-and-invoice-approval-journals"></a>공급업체 송장 및 송장 승인 분개장에 대한 기본 상쇄 계정

[!include [banner](../includes/banner.md)]

기본 상쇄 계정은 다음 공급업체 송장 분개장 페이지에서 사용됩니다.

-   송장 분개장
-   송장 승인 분개장

다음 표를 참조하여 청구서 분개장의 기본 계정을 할당해야 하는 위치를 결정하십시오.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>여기서 기본 계정 설정</th>
<th>기본 계정이 제공되는 위치</th>
<th>이 옵션이 처리에 미치는 영향</th>
<th>이 옵션을 사용해야 하는 경우</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>공급업체 그룹</strong> – <strong>기본 계정 설정</strong> 페이지에서 공급업체 그룹의 기본 상쇄 계정을 설정합니다. 이 페이지는 <strong>공급업체 그룹</strong> 페이지에서 열 수 있습니다.</td>
<td><ul>
<li>공급업체 계정</li>
<li>공급업체 계정에 기본 계정이 지정되지 않은 경우 공급업체 그룹의 공급업체 계정에 대한 분개장 항목</li>
</ul></td>
<td>공급업체 그룹의 기본 상쇄 계정은 <strong>기본 계정 설정</strong> 페이지에 공급업체의 기본 상쇄 계정으로 표시됩니다. 이 페이지는 <strong>모든 공급업체</strong> 목록 페이지에서 열 수 있습니다.</td>
<td>일반적으로 동일한 공급업체 그룹의 동일한 유형의 제품에 대해 장기간에 걸쳐 비용을 지불하는 경우 이 옵션을 사용합니다.</td>
</tr>
<tr class="even">
<td><strong>공급업체 계정</strong> – <strong>기본 계정 설정</strong> 페이지에서 공급업체 계정의 기본 계정을 설정합니다. 이 페이지는 <strong>공급업체</strong> 페이지에서 열 수 있습니다.</td>
<td>공급업체 계정에 대한 분개장 항목</td>
<td>공급업체 계정의 기본 상쇄 계정은 공급업체 계정의 분개장 항목에 대한 기본 상쇄 계정으로 표시됩니다.</td>
<td>일반적으로 동일한 공급업체의 동일한 유형의 제품에 대해 장기간에 걸쳐 비용을 지불하는 경우 이 옵션을 사용합니다.</td>
</tr>
<tr class="odd">
<td><strong>분개장 이름</strong> – <strong>분개장 이름</strong> 페이지에서 분개장의 기본 상쇄 계정을 설정합니다. <strong>고정 상쇄 계정</strong> 옵션을 선택합니다. 분개장 이름의 분개장 유형이 <strong>송장 등록</strong> 또는 <strong>승인</strong>인 경우 분개장 이름에 기본 상쇄 계정을 지정할 수 없습니다.</td>
<td><ul>
<li>분개장 이름을 사용하는 분개장 헤더</li>
<li>분개장 이름을 사용하는 분개장의 분개장 항목</li>
</ul></td>
<td><strong>분개장 이름</strong> 페이지에서 <strong>고정 상쇄 계정</strong> 옵션을 선택하면 분개장 이름의 상쇄 계정이 공급업체 또는 공급업체 그룹의 기본 상쇄 계정을 덮어씁니다.</td>
<td>공급업체 또는 공급업체 그룹에 관계없이 특정 계정에 청구되는 특정 비용 및 지출에 대한 분개장을 설정하려면 이 옵션을 사용합니다.</td>
</tr>
<tr class="even">
<td><strong>분개장 이름</strong> – <strong>분개장 이름</strong> 페이지에서 분개장의 기본 상쇄 계정을 설정합니다. <strong>고정 상쇄 계정</strong> 옵션을 선택 취소합니다. 분개장 이름의 분개장 유형이 <strong>송장 등록</strong> 또는 <strong>승인</strong>인 경우 분개장 이름에 기본 상쇄 계정을 지정할 수 없습니다.</td>
<td><ul>
<li>분개장 헤더</li>
<li>분개장 이름을 사용하는 분개장의 분개장 항목</li>
</ul></td>
<td>이러한 기본 항목은 분개장 헤더 페이지에서 사용되며 분개장 헤더 페이지의 상쇄 계정은 분개장 바우처 페이지의 기본 항목으로 사용됩니다. <strong>분개장 이름</strong> 페이지의 기본 계정은 공급업체 계정에 기본 계정이 설정되어 있지 않은 경우에만 사용됩니다.</td>
<td>이 옵션을 사용하여 기본 공급업체 상쇄 계정이 할당되지 않았을 때 사용되는 기본 계정을 설정할 수 있습니다.</td>
</tr>
<tr class="odd">
<td><strong>분개장 헤더</strong> – 분개장 바우처 페이지에서 분개장의 기본 상쇄 계정을 기본 항목으로 설정합니다. 분개장 헤더의 분개장 유형이 <strong>송장 등록</strong> 또는 <strong>승인</strong>인 경우 분개장 이름에 기본 상쇄 계정을 지정할 수 없습니다.</td>
<td>분개장의 분개장 항목</td>
<td>분개장의 기본 상쇄 계정은 분개장 바우처 페이지의 기본 항목으로 사용됩니다.</td>
<td>분개장의 대부분의 항목에 동일한 상쇄 계정이 있는 경우 이 옵션을 사용하여 데이터 입력 속도를 높일 수 있습니다.</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]