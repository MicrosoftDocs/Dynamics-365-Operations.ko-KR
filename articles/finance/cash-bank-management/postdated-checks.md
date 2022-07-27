---
title: 기한이 지난 수표
description: 이 문서에서는 Microsoft Dynamics 365 Finance의 기한이 지난 수표 지원에 대한 정보를 제공합니다. 기한이 지난 수표는 미래의 날짜에 지불을 하고 받기 위해 발행되는 수표입니다. 따라서 지정된 날짜까지 수표를 현금으로 바꿀 수 없습니다.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f5c4d641a3d3ccc326ee56ce7bd05c891b3fa8a
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451036"
---
# <a name="postdated-checks"></a>기한이 지난 수표

[!include [banner](../includes/banner.md)]

이 문서에서는 기한이 지난 수표 지원에 대한 정보를 제공합니다. 기한이 지난 수표는 미래의 날짜에 지불을 하고 받기 위해 발행되는 수표입니다. 따라서 지정된 날짜까지 수표를 현금으로 바꿀 수 없습니다.

Dynamics 365 Finance는 다음 표와 같이 수취 계정과 지급 계정 모두에서 기한이 지난 수표에 대한 전체 관리 주기를 지원합니다.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>시나리오</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>후일 수표 설정</td>
<td>새 결제 방법을 설정하고 발행된 수표, 받은 수표 및 원천징수세에 대한 계좌를 정리하기 위한 결제 절차를 지정해야 합니다.</td>
</tr>
<tr class="even">
<td>공급업체에 대한 소급 수표 등록 및 게시</td>
<td>공급업체에 발급한 기한이 지난 수표의 세부 정보를 등록합니다. 결제가 게시되면 공급업체의 책임은 인정되지만 은행 계좌에는 아직 지급되지 않습니다. 대신 이를 위해 가계정이 사용됩니다. </td>
</tr>
<tr class="odd">
<td>고객에 대한 소급 수표 등록 및 게시</td>
<td>고객으로부터 받은 기한이 지난 수표의 세부 정보를 등록합니다. 결제가 게시되면 고객의 미수금은 신용이지만, 은행 계좌에는 아직 차변되지 않습니다. 대신 이를 위해 가계정이 사용됩니다.</td>
</tr>
<tr class="even">
<td>고객 또는 공급업체에 대한 기한이 지난 교체 수표 등록 및 게시</td>
<td>
공급업체 또는 고객의 원래 수표가 분실되거나 손상된 경우, 기한이 지난 대체 수표를 발행할 수 있습니다. 수표 세부 정보를 등록할 때 원본 수표에 대한 참조를 제공하고 새 수표가 원본 수표의 대체임을 나타냅니다. 교체 수표를 게시할 수도 있습니다.</td>
</tr>
<tr class="odd">
<td>공급업체로 고객의 기한이 지난 교체 수표 전송</td>
<td>고객으로부터 기한이 지난 교체 수표를 받으면 해당 수표를 지급으로 공급업체에 양도할 수 있습니다.</td>
</tr>
<tr class="even">
<td>고객 또는 공급업체를 위해 기한이 지난 교체 수표 결제</td>
<td>수표가 최종적으로 만료될 때 고객 또는 공급업체의 브리징 계정에 게시된 기한이 지난 교체 수표를 정산합니다. 수표가 결제되면, 은행은 이전에 사용되었던 결제 계좌에 입금하거나 신용을 부여합니다.</td>
</tr>
<tr class="odd">
<td>공급업체에 대한 기한이 지난 교체 수표 취소</td>
<td>다음 상황에서 게시된 기한이 지난 교체 수표를 취소할 수 있습니다. - 수표는 은행에서 반환됩니다.
- 잘못된 송장에 수표가 적용되었습니다.
- 수표에 대해 현금으로 지불합니다.
  </td>
  </tr>
  <tr class="even">
  <td>기한이 지난 수표에 대한 지불 중지</td>
  <td>자금 부족, 공급업체와의 계약 조건 변경, 공급업체의 불량품 공급 또는 공급업체에 대한 반품 등의 이유로 공급업체에 발행된 기한이 지난 수표에 대한 지급을 중지할 수 있습니다. 지불이 끝나지 않은 수표에 대해서만 지불을 중지할 수 있습니다.</td>
  </tr>
  </tbody>
  </table>



자세한 내용은 다음 항목을 참조하세요.

[기한이 지난 수표 설정](tasks/set-up-postdated-checks.md)

[고객에 대한 기한이 지난 수표 등록 및 게시](tasks/register-post-postdated-check-customer.md)

[고객의 기한이 지난 교체 수표 결제](tasks/settle-postdated-check-customer.md)

[공급업체에 대한 기한이 지난 수표 등록 및 게시](tasks/register-post-postdated-check-vendor.md) 

[공급업체에 대한 기한이 지난 교체 수표 결제](tasks/settle-postdated-check-vendor.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
