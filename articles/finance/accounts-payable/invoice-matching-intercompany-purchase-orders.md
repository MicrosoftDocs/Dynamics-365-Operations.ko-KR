---
title: 송장 매칭 및 회사 간 구매 주문
description: 회사 간 무역 거래와 연관된 구매 법인은 지급 계정 송장 매칭을 사용하도록 설정할 수 있습니다. 이 경우 회사 간 공급업체 송장이 게시되기 전에 회사 간 거래 및 지급 계정 송장 매칭에 대한 게시 요구 사항이 모두 충족되어야 합니다.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: twheeloc
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e884e96e1275f9162b642bbe48c2d891c6434002
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451561"
---
# <a name="invoice-matching-and-intercompany-purchase-orders"></a>송장 매칭 및 회사 간 구매 주문

[!include [banner](../includes/banner.md)]

회사 간 무역 거래와 연관된 구매 법인은 지급 계정 송장 매칭을 사용하도록 설정할 수 있습니다. **지급 계정 매개 변수** 페이지의 **불일치하는 송장 게시** 필드가 **승인 필요** 로 설정되면 송장 매칭 유효성 검사가 수행됩니다. 이 경우 회사 간 공급업체 송장이 게시되기 전에 회사 간 거래 및 지급 계정 송장 매칭에 대한 게시 요구 사항이 모두 충족되어야 합니다.

이 항목의 예에서는 회사 간 거래에 대해 다음 설정을 사용합니다.
-   Fabrikam Purchase는 구매 법인입니다.
-   Fabrikam Sales는 판매 법인입니다.
-   고객 4020은 Fabrikam Sales에 있습니다.
-   공급업체 3024는 Fabrikam Purchase에 있습니다.
-   Fabrikam Purchase에서 공급업체 3024에 대한 회사 간 정보가 지정됩니다. Fabrikam Sales는 고객 회사로 지정되고 고객 4020은 Fabrikam Purchase 법인에 해당하는 고객 계정으로 지정됩니다.
-   Fabrikam Sales에서는 고객 4020에 대해 회사 간 정보가 지정됩니다. Fabrikam Purchase는 공급업체 회사로 지정되고 공급업체 3024는 Fabrikam Sales 법인에 해당하는 공급업체 계정으로 지정됩니다.

예에서는 Fabrikam Purchase에 대한 지급 계정 송장 매칭에 대해 다음 설정을 사용합니다.
-   **지급 계정 매개 변수** 페이지에서 **송장 매칭 유효성 검사 활성화** 옵션이 선택됩니다.
-   **지급 계정 매개 변수** 페이지에서 **불일치하는 송장 게시** 필드가 **승인 필요** 로 설정됩니다.
-   법인의 가격 허용 오차 백분율은 2%입니다.

## <a name="example-price-matching-and-intercompany-trade"></a>예: 가격 매칭 및 회사 간 거래
회사 간 공급업체 송장과 회사 간 고객 송장의 순 금액은 같아야 합니다. 이 요구 사항은 적용되는 승인 또는 가격 허용 오차 한도 백분율과 일치하는 모든 송장을 재정의합니다. 예를 들어 다음 단계를 따릅니다.
1.  Fabrikam Purchase에서 고객 4020에 대한 판매 주문 SO888을 만듭니다. Fabrikam Purchase에서 공급업체 3024에 대해 회사 간 구매 주문 ICPO222가 자동으로 생성되고 Fabrikam Sales에서 판매 주문 ICSO888이 자동으로 생성됩니다.
2.  Fabrikam Sales에서 항목 수령을 등록하고 포장 전표를 게시합니다. ICSO888의 상태가 배송됨으로 변경됩니다. ICPO222의 상태가 수령함으로 변경됩니다.
3.  Fabrikam Sales에서 ICSO888의 송장을 업데이트합니다. 단가는 0.45이며, 100개 품목이 업데이트됩니다.
4.  Fabrikam Purchase에서 ICPO222의 송장을 업데이트합니다. 실수로 순 가격을 45.00에서 54.00으로 변경했습니다. 가격이 허용 가능 가격 허용 오차 2%를 초과했음을 나타내는 아이콘이 표시됩니다.
5.  **송장 매칭 세부 정보** 페이지에서 매칭 불일치가 있는 게시를 승인하는 옵션을 선택합니다. **공급업체 송장** 페이지에서 **확인** 을 클릭합니다. 공급업체 송장이 회사 간 공급업체 송장이 아닌 경우 게시가 성공합니다. 그러나 회사 간 공급업체 송장으로 작업하고 있기 때문에 게시에 실패합니다. 회사 간 거래의 경우 회사 간 판매 주문의 송장 합계는 해당 회사 간 구매 주문의 송장 합계와 같아야 합니다. 이 문제를 해결하려면 순 가격을 기본 금액인 45.00으로 다시 변경하여 송장의 순 가격을 수정해야 합니다.

## <a name="example-quantity-matching-with-intercompany-trade"></a>예: 회사 간 거래와 수량 매칭
회사 간 구매 주문과 회사 간 판매 주문의 수량은 같아야 합니다. 이 요구 사항은 적용되는 모든 송장 매칭 승인보다 우선합니다. 이 예에서는 회사 간 거래에 대해 다음 추가 설정을 사용합니다.
-   Fabrikam Purchase에서 공급업체 3024에 대한 구매 주문 작업 정책은 원본 고객 송장과 회사 간 공급업체 송장을 모두 자동으로 게시하도록 설정됩니다.

이 예에서는 Fabrikam Purchase에 대한 지급 계정 송장 매칭에 대해 다음 추가 설정을 사용합니다.
-   품목 B-R14에서 사용하는 모델 그룹의 **품목 모델 그룹** 페이지에서 **수령 요구 사항** 옵션이 선택됩니다.
-   품목 B-R14의 현재고 수량은 0(영)입니다.

예를 들어 다음 단계를 따릅니다.
1.  Fabrikam Purchase에서 고객 4020에 대한 판매 주문 SO999를 만듭니다. 주문에는 각각 1.00의 단가에 100개의 배터리(품목 B-R14)라는 한 품목이 포함되어 있습니다. Fabrikam Purchase에서 공급업체 3024에 대해 회사 간 구매 주문 ICPO333이 자동으로 생성되고 Fabrikam Sales에서 판매 주문 ICSO999가 자동으로 생성됩니다.
2.  Fabrikam Sales에서 ICSO999의 송장 업데이트를 수행합니다. 상품이 품절되어 아직 입고되지 않아 게시에 실패했습니다. 따라서 재무 정보를 업데이트할 수 없습니다.
3.  Fabrikam Sales에서 항목을 받았다고 등록하고 ICSO999의 포장 전표를 게시합니다. ICPO333의 제품 영수증이 Fabrikam Purchase에 자동으로 게시됩니다. Fabrikam Purchase에서 품목 B-R14의 입고 수량이 100으로 변경됩니다.
4.  Fabrikam Sales에서 ICSO999의 송장 업데이트를 수행합니다. 두 법인 모두에서 게시에 성공합니다. Fabrikam Purchase에서 품목 B-R14의 구매 수량이 100으로 변경됩니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
