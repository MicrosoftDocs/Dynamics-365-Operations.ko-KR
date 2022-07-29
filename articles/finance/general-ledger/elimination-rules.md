---
title: 소거 규칙
description: 이 항목에서는 제거 규칙 및 제거에 대한 보고를 위한 다양한 옵션에 대한 정보를 제공합니다.
author: aprilolson
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c31df2526f3b852bbc2b5086ce2154310118352d43c9f8803b72d49df4a450b5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450580"
---
# <a name="elimination-rules"></a>소거 규칙

[!include [banner](../includes/banner.md)]

이 항목에서는 제거 규칙 및 제거에 대한 보고를 위한 다양한 옵션에 대한 정보를 제공합니다.

모 법인이 하나 이상의 자회사 법인과 사업을 하고 연결 재무 보고를 사용하는 경우 제거 거래가 필요합니다. 연결 재무제표에는 연결 조직과 해당 조직 외부의 다른 기업 간에 발생하는 거래만 포함되어야 합니다. 따라서 동일한 조직에 속한 법인 간의 거래는 재무 보고서에 나타나지 않도록 총계정원장에서 제거하거나 제거해야 합니다. 제거에 대해 보고하는 방법에는 여러 가지가 있습니다.

-   제거 규칙은 연결 또는 제거 회사에서 만들고 처리할 수 있습니다.
-   재무 보고를 사용하여 특정 행 또는 열에 제거 계정 및 차원을 표시할 수 있습니다.
-   별도의 법인을 사용하여 수동 거래 입력을 게시하여 제거를 추적할 수 있습니다.

이 항목은 통합 또는 제거 회사에서 처리되는 제거 규칙에 중점을 둡니다. 제거 규칙을 설정하여 제거 대상 법인으로 지정된 법인에서 제거 트랜잭션을 생성할 수 있습니다. 이 대상 법인을 제거 법인이라고 합니다. 제거 분개는 통합 프로세스 동안 또는 제거 분개 제안을 사용하여 생성할 수 있습니다. 제거 규칙을 설정하기 전에 다음 용어에 익숙해져야 합니다.

-   **출처 법인** – 제거되는 금액이 전기된 법인.
-   **목적지 법인** – 제거 규칙이 게시된 법인.
-   **제거 법인** – 제거 대상 법인으로 지정된 법인.
-   **연결 법인** – 법인 그룹에 대한 재무 결과를 보고하기 위해 생성된 법인입니다. 법인의 재무 데이터는 이 법인에 통합되고 결합된 데이터를 사용하여 재무 보고서가 생성됩니다.

다음 표는 제거해야 할 수 있는 트랜잭션 유형을 보여줍니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>트랜잭션 유형</th>
<th>예:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>매도 주문 입력 및 인보이스 발행(중앙 집중식 처리)</td>
<td>조직의 다른 법인을 대신하여 고객에게 제품을 판매합니다.</td>
</tr>
<tr class="even">
<td>판매 주문서 입력(회사 간/회사 내) 및 송장 작성</td>
<td>조직의 법인 간에 제품을 판매합니다.</td>
</tr>
<tr class="odd">
<td>구매 주문(중앙 집중식 처리)</td>
<td>조직의 다른 법인을 대신하여 공급업체로부터 재고, 소모품, 서비스, 고정 자산 및 기타 제품을 구매합니다.</td>
</tr>
<tr class="even">
<td>재고 관리(본사/사내)</td>
<td><ul>
<li>한 법인의 재고를 조직 내 다른 법인의 고정 자산으로 이전합니다.</li>
<li>한 법인의 재고를 조직 내 다른 법인의 재고로 이전합니다.</li>
</ul></td>
</tr>
<tr class="odd">
<td>운송 중 재고 추적</td>
<td>동일한 법인의 창고 간에 품목을 이전하지만 지리적 위치는 다릅니다.</td>
</tr>
<tr class="even">
<td>미지급금 중앙 집중식 송장 처리</td>
<td>조직의 다른 법인을 대신하여 송장을 기록합니다.</td>
</tr>
<tr class="odd">
<td>미지급 계정 중앙 결제 처리</td>
<td>조직의 다른 법인을 대신하여 송장을 지불합니다.</td>
</tr>
<tr class="even">
<td>현금 관리 및 재무(중앙 집중식 처리)</td>
<td><ul>
<li>세금 납부, 세금 환급, 이자 비용, 대출, 선지급, 배당금 지급, 선지급 로열티 또는 수수료를 처리합니다.</li>
<li>조직의 다른 법인을 대신하여 송장을 지출합니다. 송장은 목적지 법인의 장부에 입력되며 법인 간에 교차 결제해야 합니다. 예를 들어, 한 법인이 다른 법인 직원의 경비 보고서를 지불합니다. 이 경우 직원의 경비 보고서에는 다른 법인과 관련된 비용이 있습니다.</li>
<li>조직의 한 법인에서 다른 법인으로 현금을 이체합니다.</li>
</ul></td>
</tr>
<tr class="odd">
<td>외상매출금(중앙 집중 처리)</td>
<td>다른 법인의 고객 송장에 대해 현금을 받고 해당 법인의 은행 계좌에 수표를 입금합니다.</td>
</tr>
<tr class="even">
<td>급여(중앙 집중식 처리, 회사 간/회사 내)</td>
<td><ul>
<li>다른 법인의 급여를 지불합니다. 예를 들어 법인은 직원에 대해 자체 급여를 지불하지만 해당 급여 실행 동안 직원이 다른 법인을 위해 수행한 작업에 대해 청구합니다. 또는 직원이 법인 A에서 하프 타임으로, 법인 B에서 하프 타임으로 일했으며 급여가 모든 급여에 적용됩니다. 이 경우 직원의 급여에는 두 법인의 급여가 모두 포함됩니다. 급여뿐만 아니라 세금, 복리후생, 공제 및 급여에 대한 발생액도 전기됩니다.</li>
<li>한 부서나 부서에서 다른 부서로 인력을 이전합니다.</li>
</ul></td>
</tr>
<tr class="odd">
<td>고정 자산(회사 간/회사 내)</td>
<td>고정 자산을 다른 법인의 고정 자산 또는 재고로 이전합니다.</td>
</tr>
<tr class="even">
<td>할당(회사 간/회사 내)</td>
<td>기업 할당을 처리합니다. 할당은 원래 모듈에 관계없이 할당된 모든 계정에 대한 활동입니다.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>예:
법인 A 법인은 조직의 다른 법인 B 법인에게 위젯을 판매합니다. 다음 예는 두 법인 간에 발생하는 거래를 제거해야 하는 방법을 보여줍니다.

-   법인 A는 10.00인 위젯을 법인 B에게 10.00에 판매합니다.
-   법인 A는 실제 운송비로 2.00을 더한 10.00에 법인 B에 10.00의 위젯을 판매합니다.
-   법인 A는 10.00인 위젯을 법인 B에게 15.00에 판매하고 판매 마진을 인식합니다.
-   법인 A는 10.00인 위젯을 법인 B에게 15.00에 판매하고 판매 마진 절반을 인식합니다. 법인 B는 판매 마진의 나머지 절반을 인식합니다. 따라서 수익이 분할됩니다. 분할 수익은 외부 조직이 아닌 조직의 다른 법인에서 주문할 인센티브를 제공합니다.

이러한 모든 트랜잭션은 만기 및 만기 계정에 전기되는 내부 거래 트랜잭션을 생성합니다. 또한 이러한 거래에는 회사 간 판매 금액이 판매된 상품의 비용과 같지 않은 경우 인상 및 인상 금액이 포함될 수 있습니다.

## <a name="set-up-elimination-rules"></a>소거 규칙 설정
제거 규칙을 설정할 때 특히 제거를 위해 재무 차원을 생성하는 것이 좋습니다. 대부분의 고객은 이를 거래 파트너 또는 비슷한 이름으로 부릅니다. 재무 차원을 사용하지 않기로 결정한 경우 회사 간 거래에만 적합한 기본 계정을 만드십시오. 

제거 설정은 통합 모듈의 설정 영역에 있습니다. 규칙에 대한 설명을 입력한 후 소거 분개장이 게시될 회사를 선택해야 합니다. 법인 설정에서 **재무 소거 프로세스에 사용** 을 선택한 회사여야 합니다. 

제거 규칙이 적용되는 날짜와 필요한 경우 만료되는 날짜를 설정할 수 있습니다. 삭제 제안 프로세스에서 사용 가능하려면 **활성** 항목을 **예** 로 설정해야 합니다. **제거** 유형이 있는 저널 이름을 선택합니다.

기본을 정의한 후 **라인** 을 눌러 실제 처리 규칙을 정의할 수 있습니다. 소거에는 순변동액을 제거하거나 고정금액을 정의하는 두 가지 옵션이 있습니다. 

원본 계정을 선택하십시오. 별표(\*)를 와일드카드 문자로 사용할 수 있습니다. 예를 들어, 1\*은 1로 시작하는 모든 계정을 할당에 대한 데이터 소스로 선택합니다. 

원본 계정을 선택한 후 **계정 사양** 에 따라 사용되는 대상 회사의 계정이 결정됩니다. **소스** 계정에 정의된 것과 동일한 기본 계정을 사용하려면 **소스** 를 선택합니다. **사용자 정의** 를 선택하는 경우 대상 계정을 지정해야 합니다. 

치수 지정은 동일한 방식으로 작동합니다. **소스** 를 선택하면 대상 회사에서 소스 회사와 동일한 차원을 사용합니다. **사용자 정의** 를 선택한 경우 **대상 치수** 메뉴 항목을 클릭하여 대상 회사의 치수를 지정해야 합니다. 

소스 차원과 소거 소스로 사용되는 재무 차원 및 값을 선택합니다.

## <a name="process-elimination-transactions"></a>소거 트랜잭션 처리
제거 트랜잭션을 처리하는 방법은 통합 온라인 프로세스 중에 또는 제거 저널을 만들고 제거 제안 프로세스를 실행하는 두 가지 방법이 있습니다. 이 섹션에서는 저널 생성 및 제거 프로세스 실행에 중점을 둡니다. 

제거 회사로 정의된 회사에서 통합 모듈에서 **제거 저널** 을 선택합니다. 저널 이름을 선택한 후 **라인** 을 클릭합니다. **제안** 메뉴를 선택한 다음 **삭제 제안** 을 선택하여 제안을 실행할 수 있습니다.

통합 데이터의 원본인 회사를 선택한 다음 처리할 규칙을 선택하십시오. 제거 금액 검색을 시작하려면 시작 일자를 입력하고 제거 금액 검색을 종료하려면 종료 일자를 입력합니다. **GL 게시 날짜** 필드는 일반 대장에 저널을 게시하는 데 사용되는 날짜입니다. **확인** 을 누른 후 금액을 검토하고 분개장을 게시할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]