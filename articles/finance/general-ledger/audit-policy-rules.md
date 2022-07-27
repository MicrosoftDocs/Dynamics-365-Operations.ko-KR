---
title: 감사 정책 규칙
description: 감사 정책을 사용하여 경비 보고서, 공급업체 송장 및 구매 주문을 평가하여 생성한 정책 규칙을 준수하는지 확인할 수 있습니다. 감사 정책과 연결된 모든 규칙은 지정한 일정에 따라 일괄 처리 모드로 실행됩니다.  각 정책 규칙은 정책 규칙 유형의 인스턴스입니다. 각 정책 규칙 유형에 대해 한 번에 하나의 정책 규칙만 활성화할 수 있습니다.
author: panolte
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbf93f5b8b2f8d95102a52178b096d7e334894483c0ac0bacc62653aea845022
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450475"
---
# <a name="audit-policy-rules"></a>감사 정책 규칙

[!include [banner](../includes/banner.md)]

감사 정책을 사용하여 경비 보고서, 공급업체 송장 및 구매 주문을 평가하여 생성한 정책 규칙을 준수하는지 확인할 수 있습니다. 감사 정책과 연결된 모든 규칙은 지정한 일정에 따라 일괄 처리 모드로 실행됩니다.  각 정책 규칙은 정책 규칙 유형의 인스턴스입니다. 각 정책 규칙 유형에 대해 한 번에 하나의 정책 규칙만 활성화할 수 있습니다. 

## <a name="queries-and-query-types"></a>쿼리 및 쿼리 유형

감사 정책 규칙을 생성할 때 먼저 정책 규칙 유형을 선택합니다. 정책 규칙 유형은 정책 규칙을 생성하기 위한 시작점으로 사용할 애플리케이션 개체 트리(AOT) 쿼리를 지정합니다. 또한 정책 규칙에 사용할 쿼리 유형을 지정합니다. 쿼리는 정책 규칙이 평가하는 소스 문서를 결정합니다. 또한 감사를 위해 문서를 선택할 때 사용할 법인과 날짜를 식별하는 소스 문서의 필드를 지정합니다. 쿼리 유형은 쿼리 페이지 및 감사 정책 규칙 페이지의 기본 필드를 제어합니다. 다음 표에는 감사 정책 규칙에 사용할 수 있는 쿼리 유형이 나와 있습니다.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>쿼리 유형</th>
<th>목적</th>
<th>추가 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>조건부</td>
<td>지정된 값에 대해 소스 문서 특성을 평가합니다.</td>
<td></td>
</tr>
<tr class="even">
<td>집계</td>
<td>숫자 값을 집계하여 정책 규칙에 대해 여러 소스 문서 또는 소스 문서 라인을 평가합니다.</td>
<td></td>
</tr>
<tr class="odd">
<td>샘플링</td>
<td>정책 위반을 평가할 소스 문서의 지정된 비율을 무작위로 선택합니다.</td>
<td>이 옵션을 선택할 경우 감사 정책 규칙 페이지를 사용하여 감사를 위해 임의로 선택할 문서의 백분율을 지정합니다.</td>
</tr>
<tr class="even">
<td>복제</td>
<td>소스 문서를 평가하여 지정된 필드에 중복 항목이 포함되어 있는지 확인합니다.</td>
<td>이 옵션을 선택하면 감사 정책 규칙 페이지를 사용하여 문서가 중복 항목에 대해 평가될 때 문서 선택 날짜 범위의 시작 부분에 추가할 일 수를 지정합니다.</td>
</tr>
<tr class="odd">
<td>목록 검색</td>
<td>특정 엔터티에 대한 소스 문서를 평가합니다.</td>
<td>쿼리의 루트 문서는 감사 중인 문서를 정의합니다. 쿼리는 dirpartytable 테이블에 대한 참조를 포함하는 목록 쿼리여야 합니다. 이 옵션은 다음 AOT 쿼리에만 사용할 수 있습니다.
<ul>
<li><span class="ui">AuditPolicyExpenseList</span>(경비 보고서 모니터링 직원)</li>
<li><span class="ui">AuditPolicyPurchList</span>(구매 주문 모니터링 공급업체)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span>(공급업체 송장 모니터링 공급업체)</li>
</ul>
이 옵션을 선택하는 경우 감사 정책 규칙 페이지에서 모니터링되는 엔터티를 지정합니다.</td>
</tr>
<tr class="even">
<td>키워드 검색</td>
<td>소스 문서를 평가하여 특정 단어가 포함되어 있는지 확인합니다.</td>
<td>이 옵션을 선택하는 경우 감사 정책 규칙 페이지에서 찾을 단어를 입력합니다. 감사 정책 규칙 페이지에는 입력한 단어에 대해 평가할 테이블과 필드를 지정할 수 있는 옵션도 포함되어 있습니다.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>공통 매개 변수
특정 감사 정책에 대한 모든 정책 규칙은 동일한 일괄 처리 매개 변수와 동일한 문서 선택 날짜 범위를 공유합니다. 이러한 매개 변수는 추가 옵션 페이지에서 정책에 대해 지정됩니다.



## <a name="additional-resources"></a>추가 리소스

[정책 위반 및 사례 감사](audit-policy-violations-cases.md)
[소스 문서에 대한 감사 정책 정의](tasks/define-audit-policies-source-documents.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]