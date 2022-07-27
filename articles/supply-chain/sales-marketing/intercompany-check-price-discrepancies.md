---
title: 회사 간 주문 가격 불일치 확인
description: 이 토픽에서는 회사 간 주문 가격 불일치를 확인하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: f9a0ba4980f8acf56d84dc865094b405b7402ad5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447721"
---
# <a name="check-intercompany-order-price-discrepancies"></a>회사 간 주문 가격 불일치 확인

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 회사 간 주문의 가격 불일치를 확인할 수 있습니다.

1. **조달 및 소싱** \> 정기 \> 정리 \>회사 간 주문 가격 불일치 확인.
1. 필요한 경우 일괄 작업을 설정한 다음 **확인** 을 선택하여 회사 간 판매 주문 및 구매 주문에 대한 가격 및 할인을 확인합니다. 그렇지 않으면 확인을 수행하지 않고 페이지를 닫으려면 **취소** 를 선택하세요.

    > [!TIP]
    > 동기화 문제 또는 가격 문제가 있는 경우 표시되는 정보 메시지에 나열됩니다. 참고용으로 정보 메시지를 인쇄할 수 있습니다.

1. 정보 메시지에서 관련 라인을 선택하여 현재 법인에서 주문을 엽니다. **회사 간 거래** 를 선택한 다음 **회사 간 구매 주문** 또는 **회사 간 판매 주문** 을 선택하여 관련 법인에서 주문을 엽니다.

    > [!NOTE]
    > 회사 간 주문 업데이트를 허용하려면:
    >
    > 1. **수취 계정 \> 고객 \> 모든 고객** 으로 이동합니다.
    > 1. 작업 창에서 **일반** 탭을 선택한 다음 **회사 간 거래** 를 선택합니다.
    > 1. **회사 간 거래** 페이지에서 **구매 주문 정책** 또는 **판매 주문 정책** 을 선택합니다.
    > 1. 두 영역에서 **가격 편집 허용** 및 **할인 편집 허용** 을 선택합니다.

1. 가격을 유지하려는 관련 회사 간 주문을 엽니다.
1. 각 주문 라인에 대해 라인의 **단가 필드** 를 변경한 다음 다시 원래 값으로 변경합니다. 라인에 대한 **할인** 필드를 앞뒤로 변경하고 관련 **구매 비용** 또는 **판매 비용** 필드를 앞뒤로 변경합니다. 값을 앞뒤로 변경하면 이 회사 간 주문 라인에서 참조된 회사 간 주문 라인으로 가격, 할인 및 요금이 동기화되어 자동으로 정렬됩니다.

    > [!NOTE]
    > 이 동기화는 회사 간 판매 주문이 송장이 발행되지 않은 경우에만 유효합니다. 회사 간 판매 주문이 송장 전기되고 고객 송장 분개가 생성된 경우 가격, 할인 및 비용을 회사 간 고객 송장 분개와 동일하게 설정하여 회사 간 구매 주문 라인에서 직접 변경을 수행해야 합니다. 이 작업을 수행하지 않으면 주문 총액이 일치하지 않기 때문에 회사 간 구매 주문을 송장 전기할 수 없습니다.

1. 모든 회사 간 구매 및 판매 주문이 동기화될 때까지 절차를 반복합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
