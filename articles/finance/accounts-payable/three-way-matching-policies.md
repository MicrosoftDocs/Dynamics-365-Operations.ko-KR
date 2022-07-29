---
title: 3방향 매칭 정책
description: 이 항목에서는 3방향 매칭의 예를 제공합니다.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: twheeloc
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cffdc06216ce8ab1bfb79265f265bec1aee334c5
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451564"
---
# <a name="three-way-matching-policies"></a>3방향 매칭 정책

[!include [banner](../includes/banner.md)]

이 항목에서는 3방향 매칭의 예를 제공합니다.

## <a name="example-three-way-matching-for-items"></a>예: 품목에 대한 3방향 매칭

**요약:** Ken은 Fabrikam이라는 법인의 본사 관리자입니다. Ken은 구매 주문을 기반으로 하는 모든 공급업체 송장이 구매 주문 라인과 일치(양방향 매칭)해야 한다고 결정합니다. 고정 자산으로 사용할 품목 구매의 경우 송장은 구매 발주 라인 및 제품 입고 라인 모두와 일치(3방향 매칭)해야 합니다.

Fabrikam은 전 세계의 여러 법인 및 직원과 함께 운영합니다. 거래량이 증가함에 따라 영수증과 송장의 불일치도 증가하고 있습니다. 이로 인해 자산이 상각됩니다. 공급업체의 송장을 지불했지만 주문보다 적은 수의 품목을 수령하거나 전혀 수령하지 않은 경우 프로세스에서 불일치 식별이 포함되지 않습니다. 직원들이 작업을 수행하는 데 여전히 도구와 기타 재료가 필요하므로 지출도 증가합니다. Ken은 주문한 제품을 공급업체가 배송하고 Fabrikam 직원이 해당 항목을 수령하는지 확인하려고 합니다. 따라서 Ken은 조직의 모든 법인에 대해 양방향 및 3방향 매칭이 필요합니다. 송장 매칭을 통해 사라지거나 받지 못한 품목의 문제를 추적하고 해결할 수 있습니다. 

이 예의 송장 매칭 정책은 다음 역할의 사람들이 이러한 목표를 달성하는 데 도움이 됩니다.

-   Ken은 Fabrikam 엔터프라이즈의 관리자입니다. Ken은 조직의 사람들이 공급업체로부터 품목(상품 및 서비스)을 주문, 수령 및 지불할 때 문제를 식별하고 수정하도록 도울 수 있습니다.
-   Phyllis와 April은 Fabrikam의 미국 사업부 지급 계정 부서의 회계 관리자입니다. 그들은 기업 정책을 시행하고 해당하는 경우 송장이 구매 주문과 상품 및 서비스 수령과 일치한 후에만 송장이 지불되도록 할 수 있습니다.
-   Tony는 Fabrikam 미국 사업부의 생산 관리자입니다. Tony와 다른 생산 직원은 공급업체에 주문한 품목이 주문대로 수령되었는지 확인할 수 있으며 직원이 업무를 수행하는 데 필요한 물품을 받을 수 있도록 합니다.

### <a name="prerequisites"></a>전제 조건

-   Ken은 법인 수준에서 **매칭 정책** 을 **3방향 매칭** 으로 설정합니다.
-   Ken은 법인의 **헤더 매칭 상태 자동 업데이트** 토글을 **예** 로 설정합니다.
-   Ken은 법인의 **가격 합계 일치** 필드를 **백분율** 로 설정하고 **허용 오차 백분율** 에 15%를 입력합니다.
-   Ken은 품목 1500 – CNC Milicron Machine에 대한 항목 수준에서 매칭 정책을 **3방향 매칭** 으로 설정합니다. 이 품목은 Fabrikam에서 생산에 사용되는 자산 품목입니다. 이 품목에 대한 송장은 가격에 대한 구매 주문 라인 및 수량에 대한 제품 입고와 대응됩니다.
-   Tony는 5대의 CNC Milicron Machine에 대한 요청을 입력합니다. Fabrikam의 구매 주문 직원인 Alicia는 품목을 공급하기 위해 Contoso라는 법인에 구매 주문을 발행합니다.

    | 품목 번호                 | 수량 | 단가 | 순액 | 요금 코드        | 요금 값 |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 – CNC Milicron Machine | 5        | 8,000.00   | 40,000.00  | 배송 및 취급 | 3,000.00      |

-   Contoso의 미수금 담당 직원인 Arnie는 일주일 동안의 배송을 검토합니다. Arnie는 CNC Milicron Machine 배달에 대해 Fabrikam에 송장을 보낼 배송 거래를 선택합니다. Arnie는 배송 및 취급 비용을 포함시킵니다. Fabrikam은 비용을 자산 비용의 일부로 간주합니다.

### <a name="scenario"></a>시나리오

1.  Fabrikam의 입고 부서 직원인 Sammy는 Contoso에서 배송된 총 기계 수량을 받습니다. Sammy는 제품 영수증에 수량 5를 입력합니다. 구매 주문을 완전히 수령했으므로 구매 주문 상태가 수령함으로 변경됩니다.
2.  Fabrikam의 AP 코디네이터인 April은 Contoso에서 제출한 송장을 입력하고 확인합니다. 그녀는 다음 정보를 확인합니다.
    -   3방향 매칭이 필요한 품목의 경우 송장 라인의 수량이 입고된 수량과 일치합니다. 입고 수량은 송장과 일치하는 제품 영수증에 표시됩니다.
    -   양방향 또는 3방향 매칭이 필요한 품목의 경우 송장 라인의 가격이 Microsoft Dynamics 365 Finance에 정의된 허용 오차 내에 있습니다. 여기에는 다음 유형의 가격 매칭이 포함됩니다.
        -   순 단가 매칭 – 송장 라인의 순 단가가 허용 오차 백분율 내에서 구매 발주 라인의 순 단가와 일치합니다. 이 예에서 순 단가 허용 오차는 +8%입니다.
        -   가격 합계 매칭 – 송장 라인의 순 금액이 허용 오차 백분율, 금액 또는 백분율 및 금액 내에서 구매 발주 라인의 순액과 일치합니다. 이 예에서 가격 합계 매칭 허용 오차는 +15%입니다.

Contoso의 종이 송장에는 다음 정보가 포함되어 있습니다.

| 항목                        | 수량 | 단가 | 순액 |
|-----------------------------|----------|------------|------------|
| 1500 – CNC Milicron Machine | 5        | 8,100.00   | 40,500.00  |
| 배송 및 취급       |          |            | 4,000.00   |
| 세금                         |          |            | 0.00       |
| 합계                       |          |            | 44,500.00  |

송장 라인에는 다음 정보가 포함됩니다.

| 품목 번호                 | 수량 | 단가 | 라인 순액 | 매칭 정책    | 제품 수령 수량 일치 | 가격 일치 | 가격 합계 일치 |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 – CNC Milicron Machine | 5        | 8,100.00   | 40,500.00       | 3방향 매칭 | 통과                         | 통과      | 통과            |

이 라인은 송장 매칭 프로세스를 통과하므로 송장을 게시할 수 있습니다.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a>예: 품목 및 공급업체 조합에 대한 3방향 매칭
요약: Ken은 Fabrikam이라는 법인의 본사 관리자입니다. Ken은 구매 주문을 기반으로 하는 모든 송장이 구매 주문 라인과 일치(양방향 매칭)해야 한다고 결정합니다. Cassie는 Fabrikam의 말레이시아 사업부의 장부 담당자입니다. 그녀는 말레이시아의 특정 공급업체에서 주문한 선택한 품목이 구매 주문 라인 및 제품 입고 라인 모두와 일치(3방향 일치)해야 한다고 지정합니다. 그녀는 또한 특정 구매 주문에 대해 더 높은 수준의 매칭으로 매칭 정책을 재정의할 수 있습니다. 

물량과 금액이 적어 말레이시아 일부 업체의 배송에 문제가 있습니다. 이러한 이유로 Cassie는 말레이시아에서 조달되는 특정 품목 및 공급업체 조합에 대한 통제 수준을 3방향 매칭으로 설정합니다. 

이 예의 송장 매칭 정책은 다음 역할의 사람들이 이러한 목표를 달성하는 데 도움이 됩니다.
-   Ken은 Fabrikam 엔터프라이즈의 관리자입니다. Ken은 조직의 사람들이 공급업체로부터 품목(상품 및 서비스)을 주문, 수령 및 지불할 때 문제를 식별하고 수정하도록 도울 수 있습니다.
-   Cassie는 Fabrikam의 말레이시아 사업부의 장부 담당자입니다. 그녀는 기업 정책을 시행하고 상품 및 서비스의 수령을 나타내는 구매 주문 라인 및 제품 수령과 일치한 후에만 송장이 지불되도록 할 수 있습니다. 그녀는 또한 운영 비용을 통제하기 위해 특정 품목에 대한 3방향 매칭으로 통제 수준을 높일 수 있습니다.

### <a name="prerequisites"></a>전제 조건

-   Ken은 법인 수준에서 **매칭 정책** 을 **양방향 매칭** 으로 설정합니다.
-   Ken은 법인의 **가격 합계 일치** 필드를 **백분율** 로 설정하고 **허용 오차 백분율** 에 **10%** 를 입력합니다.
-   Ken은 모든 품목의 단가 허용 오차를 2%로 설정합니다.
-   Cassie는 품목 PH2500 – 컴퓨터 및 공급업체 Contoso에 대한 품목 및 공급업체 조합 수준에서 **매칭 정책** 을 **3방향 매칭** 으로 설정합니다.
-   Fabrikam의 말레이시아 사업부 구매 주문 직원인 Alicia는 다음 표와 같이 Contoso에 구매 주문을 발행하여 세 가지 품목을 공급합니다. 그녀는 구매 주문을 작성할 때 무선 마우스에 대한 **매칭 정책** 이 양방향 매칭 대신 3방향 매칭이 되도록 재정의합니다.

    | 품목 번호           | 수량 | 단가 | 순액 | 매칭 정책(기본 항목) | 매칭 정책(구매 주문 라인) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 – 컴퓨터     | 2        | 2,500.00   | 5,000.00   | 3방향 매칭              | 3방향 매칭                           |
    | MM01 – 무선 마우스 | 2        | 40.00      | 80.00      | 양방향 매칭                | 3방향 매칭                           |
    | USB 드라이브             | 200      | 10.00      | 2,000.00   | 양방향 매칭                | 양방향 매칭                             |

### <a name="scenario"></a>시나리오

1.  품목이 도착합니다. Fabrikam 말레이시아 사업부의 입고 부서 직원인 Sammy는 작업이 중단되어 제품 수령을 즉시 게시하지 않습니다.
2.  Fabrikam의 AP 코디네이터인 April은 Contoso에서 제출한 송장을 입력하고 확인합니다. 그녀는 다음 정보를 확인합니다.
    -   3방향 매칭이 필요한 품목의 경우 송장 라인의 수량이 입고된 수량과 일치합니다. 입고 수량은 송장과 일치하는 제품 영수증에 표시됩니다.
    -   양방향 또는 3방향 매칭이 필요한 품목의 경우 송장 라인의 가격이 애플리케이션에 정의된 허용 오차 내에 있습니다. 여기에는 다음 유형의 가격 매칭이 포함됩니다.
        -   순 단가 매칭 – 송장 라인의 순 단가가 허용 오차 백분율 내에서 구매 발주 라인의 순 단가와 일치합니다. 이 예에서 순 단가 허용 오차는 +2%입니다.
        -   가격 합계 매칭 – 송장 라인의 순 금액이 허용 오차 백분율, 금액 또는 백분율 및 금액 내에서 구매 발주 라인의 순액과 일치합니다. 이 예에서 가격 합계 매칭 허용 오차는 +10%입니다.

Contoso의 종이 송장에는 다음 정보가 포함되어 있습니다.

| 항목                  | 수량 | 단가 | 순액 |
|-----------------------|----------|------------|------------|
| PH2500 – 컴퓨터     | 2        | 2,500.00   | 5,000.00   |
| MM01 – 무선 마우스 | 2        | 41.00      | 82.00      |
| USB 드라이브             | 200      | 10.05      | 2,010.00   |
| 합계 송장         |          |            | 7,092.00   |

송장 라인에는 다음 정보가 포함됩니다.

| 품목 번호           | 수량 | 단가 | 라인 순액 | 매칭 정책    | 제품 수령 수량 일치 | 가격 일치 | 가격 합계 일치 |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 – 컴퓨터     | 2        | 2,500.00   | 5,000.00        | 3방향 매칭 | 실패                         | 통과      | 통과            |
| MM01 – 무선 마우스 | 2        | 41.00      | 82.00           | 3방향 매칭 | 실패                         | 실패      | 통과            |
| USB 드라이브             | 200      | 10.05      | 2010.00         | 양방향 매칭   |                                | 통과      | 통과            |

다음 품목을 확인하세요.
-   PH2500 – 컴퓨터 라인의 경우 송장 라인이 제품 입고와 일치하지 않기 때문에 제품 입고 수량 매칭 열에 경고 아이콘이 있습니다.
-   MM01 – 무선 마우스 라인의 경우 송장 라인이 제품 입고와 일치하지 않기 때문에 제품 입고 수량 매칭 열에 경고 아이콘이 있습니다. 단가 일치 열에는 2% 순 단가 허용 오차를 초과했기 때문에 경고 아이콘이 있습니다.
-   USB 드라이브 라인의 경우 양방향 일치가 송장 라인 및 제품 입고 라인 수량과 일치하지 않기 때문에 제품 입고 수량 매칭 열이 비어 있습니다.

송장 매칭 불일치가 있는 송장에 대한 승인이 필요한 경우 가격 매칭 오류 및 수량 매칭 오류가 있는 송장을 게시하려면 **송장 매칭 세부 정보** 페이지에서 **매칭 불일치가 있는 게시 승인** 토글을 선택해야 합니다. 승인이 필요하지 않은 경우 다른 게시 오류가 없으면 송장 처리를 계속할 수 있습니다.


자세한 내용은 [지급 계정 송장 매칭 개요](accounts-payable-invoice-matching.md)를 참조하세요.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]