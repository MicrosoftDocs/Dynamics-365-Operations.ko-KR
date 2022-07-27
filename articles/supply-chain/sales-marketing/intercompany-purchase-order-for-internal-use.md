---
title: 내부 사용을 위한 회사 간 구매 주문 생성 및 송장
description: 이 토픽에서는 내부 사용을 위해 회사 간 구매 주문을 생성하고 송장을 발행하는 방법에 대해 설명합니다.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 88a14ff962c5cf0cd1cff24b16cc7a62e9e1c8ce
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447742"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>내부 사용을 위한 회사 간 구매 주문 생성 및 송장

[!include [banner](../../includes/banner.md)]

회사 간 공급업체에 대한 회사 간 구매 주문을 생성할 수 있습니다. 그러면 회사 간 공급업체에서 회사 간 판매 주문이 자동으로 생성됩니다.

![회사 내부 구매 프로세스](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>회사 간 구매 주문 및 해당 회사 간 판매 주문 생성

그림과 같이 법인 AAA에서 이 단계를 수행합니다.

1. **지급 계정** \> **판매 주문** \> **모든 구매 주문** 을 선택합니다.
1. **모든 구매 주문** 목록 페이지에서 회사 간 공급업체에 대한 구매 주문을 생성합니다. 필드 값은 공급업체 계정에서 구매 주문으로 복사됩니다.

    회사 간 공급업체와 작업 중이므로 공급업체에 해당하는 법인에서 회사 간 판매 주문이 생성됩니다. 회사 간 판매 주문의 번호는 회사 간 구매 주문의 번호와 같을 수 있으며, 법인의 ID를 포함할 수 있습니다. 사용되는 번호 구조는 **회사 간** 페이지의 **판매 주문 번호 매기기** 필드에서 선택한 항목에 따라 다릅니다. 예를 들어 법인 AAA에서 구매 주문 00029\_064를 생성하는 경우 법인 BBB의 판매 주문 번호는 AAA00029\_64입니다.

    회사 간 구매 주문 및 회사 간 판매 주문이 생성되었음을 알리는 정보 메시지가 표시됩니다. 메시지에는 참고용으로 회사 간 판매 주문 번호가 포함되어 있습니다.

1. 구매 주문에 항목을 추가합니다. 해당 라인 항목은 회사 간 판매 주문에 자동으로 추가됩니다. 항목이 다른 법인에 존재하지 않는 경우 메시지가 표시되고 구매 주문에 항목을 추가할 수 없습니다. 이 문제를 해결하려면 다른 법인으로 전환하고 해당 법인에 제품을 출고하세요. 항목은 해당 법인의 판매 주문에 추가할 수 있습니다. 그런 다음 구매 주문의 법인으로 다시 전환하고 계속해서 품목을 추가합니다.
1. 구매 주문에 대한 정보 입력이 완료되면 확인합니다.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>회사 간 포장 전표 및 고객 송장 처리

그림과 같이 법인 BBB에서 이 단계를 수행합니다.

1. **수취 계정 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. **모든 판매 주문** 목록 페이지에서 회사 간 판매 주문을 선택합니다.
1. 작업 창에서 **선택 및 포장** 탭을 선택한 다음 **포장 전표** 를 선택합니다.
1. **전기** 확인란을 선택합니다.
1. **확인** 을 선택합니다. 포장 전표는 법인 BBB에 전기됩니다.
1. **모든 판매 주문** 목록 페이지에서 회사 간 판매 주문을 선택합니다.
1. 작업 창에서 **송장** 탭을 선택한 다음 **송장** 을 선택합니다.
1. **전기** 확인란을 선택합니다.
1. **확인** 을 선택합니다.

    회사 간 판매 주문에 대한 고객 송장은 법인 BBB에 전기됩니다.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>회사 간 제품 입고 및 공급업체 송장 처리

그림과 같이 법인 AAA에서 이 단계를 수행합니다.

1. **지급 계정 \> 구매 주문 \> 모든 구매 주문** 으로 이동합니다.
1. **모든 판매 주문** 목록 페이지에서 회사 간 판매 주문을 선택합니다.
1. 작업 창에서 **받기** 를 선택한 다음, **제품 수령** 을 선택합니다. 상품 영수증이 생성됩니다. 제품 수령 번호는 회사 간 포장 전표 번호와 동일합니다.
1. **전기** 확인란을 선택합니다.
1. **확인** 을 선택합니다.
1. **모든 판매 주문** 목록 페이지에서 회사 간 판매 주문을 선택합니다.
1. 작업 창에서 **송장** 을 선택한 다음 **송장** 을 선택합니다. 공급업체 송장이 생성됩니다. 공급업체 송장 번호는 회사 간 고객 송장 번호와 동일합니다.
1. 공급업체 송장 입력을 완료한 후 전기합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
