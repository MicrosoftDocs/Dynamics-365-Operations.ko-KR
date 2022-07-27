---
title: 회사 간 통화 변환
description: 이 토픽에서는 회사 간 거래에 대한 통화 변환에 대해 설명합니다.
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
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447769"
---
# <a name="intercompany-currency-conversions"></a>회사 간 통화 변환

[!include [banner](../../includes/banner.md)]

최초 판매 주문과 회사 간 구매 주문의 통화 코드가 다른 경우 동기화가 활성화된 경우 다음 필드가 통화로 변환됩니다.

- **단가**
- **판매 수수료** 또는 **구매에 대한 요금**
- **할인**
- **다중 라인 할인**

그런 다음 이러한 필드는 회사 간 판매 주문 라인과 동기화됩니다.

그러나 회사 간 구매 주문 및 회사 간 판매 주문의 통화는 항상 동기화되므로 다음 필드는 통화 변환을 사용하지 않고 동기화됩니다.

- **단가**
- **판매 수수료** 또는 **구매에 대한 요금**
- **할인**
- **할인율**
- **다중 라인 할인**
- **다중 라인 할인율**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
