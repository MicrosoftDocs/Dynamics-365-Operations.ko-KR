---
title: 내부 사용을 위한 회사 간 판매 주문 생성 및 송장
description: 이 토픽에서는 내부 사용을 위해 회사 간 판매 주문을 생성하는 방법에 대해 설명합니다.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0718a1560ec42df2a0a12e8b81484aa3be46d2d8
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447733"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>내부 사용을 위한 회사 간 판매 주문 생성 및 송장

[!include [banner](../../includes/banner.md)]

일반적으로 회사 간 판매 주문은 회사 간 구매 주문에 따라 자동으로 생성됩니다. 회사 간 판매 주문을 수동으로 생성한 다음 회사 간 고객의 법인에서 회사 간 구매 주문을 생성할 수도 있습니다.

![회사 간 내부 판매 프로세스](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>회사 간 판매 주문 직접 만들기

그림과 같이 법인 B에서 이 단계를 수행합니다.

1. **수취 계정 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. 작업 창에서 **판매 주문** 을 선택하여 판매 주문을 생성합니다.
1. **판매 주문 생성** 페이지에서 고객 계정을 선택합니다. **일반** 빠른 탭에서 **회사 간** 확인란이 선택되어 있는지 확인합니다. 이는 선택한 고객이 회사 간 고객임을 나타냅니다.
1. 정보를 입력하거나 수정하고 **확인** 을 선택한 다음 평소와 같이 주문 라인을 완료합니다.

    **배송 주소** 필드 값이 회사 간 판매 주문 헤더에서 회사 간 구매 주문 헤더로 복사됩니다. 제품 차원을 포함한 **품목 번호** 필드 값, **배달 날짜** 및 **통화 코드** 필드 값이 회사 간 판매 주문 라인에서 내부 구매 주문 라인으로 복사됩니다.

1. 주문 헤더에서 **회사 간** 를 선택하여 관련 회사 간 구매 주문을 봅니다.
1. 주문 라인에서 회사 간를 선택하여 **회사 간 거래** 를 위한 현재고에 대한 정보를 조회합니다.

> [!TIP]
> **회사 간 주문** 페이지에서 회사 간 판매 주문을 볼 수 있습니다.

> [!NOTE]
> 회사 간와 작업하는 경우 **수취 계정 매개 변수** 페이지에서 **송장 발행 후 주문 삭제** 확인란의 선택을 취소하는 것이 좋습니다. 그렇지 않으면 관련 구매 주문이 삭제됩니다. 또한 **지급 계정 매개 변수** 페이지에서 **송장 발행 후 구매 주문 삭제** 확인란의 선택을 취소하는 것이 좋습니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
