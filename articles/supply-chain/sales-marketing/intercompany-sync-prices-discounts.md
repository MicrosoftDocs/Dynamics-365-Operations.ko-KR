---
title: 회사 간 가격 및 할인 동기화
description: 이 토픽에서는 회사 간 판매 주문 및 구매 주문에 대한 가격 및 할인 동기화에 대해 설명합니다.
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
ms.openlocfilehash: a9467e8d06a44cfaab9e3c8ea3944675c3eb8fb5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447718"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>회사 간 가격 및 할인 동기화

[!include [banner](../../includes/banner.md)]

할인 및 가격은 회사 간 판매 주문과 회사 간 구매 주문 간에 항상 동기화됩니다. 또한 모든 주문의 가격과 할인이 동일하도록 원래 판매 주문과 가격 및 할인을 동기화할 수 있습니다. **영업 및 마케팅** 또는 **조달 및 소싱** 에서 **모든 고객** 목록 페이지의 **일반** 탭에 액세스하는 **회사 간** 페이지에서 이 작업을 수행합니다.

**가격 및 할인** 필드는 회사 간 판매 주문 라인과 동기화됩니다. 즉, **가격 편집 허용** 필드와 **할인 편집 허용** 필드를 선택하여 회사 간 판매 주문과 회사 간 구매 주문 간의 변경을 허용했습니다. 회사 간 판매 주문의 단가, 가격 단위 또는 판매 비용 변경에 따라 회사 간 구매 주문 라인의 가격이 결정됩니다.

**가격 편집 허용** 및 **할인 편집 허용** 필드가 회사 간 판매 주문 또는 회사 간 구매 주문에서 활성화된 경우 두 주문 중 하나에서 가격 또는 할인을 수동으로 변경할 수 있습니다. 그렇지 않으면 할 수 없습니다.

**가격 편집 허용** 및 **할인 편집 허용** 필드가 회사 간 판매 주문에서 활성화되지 않은 경우 회사 간 판매 주문에 대한 가격(또는 비용) 또는 할인을 수동으로 변경할 수 없습니다.

**가격 편집 허용** 및 **할인 편집 허용** 필드가 회사 간 구매 주문에서 활성화되지 않은 경우 회사 간 구매 주문에서 가격(또는 요금) 또는 할인을 수동으로 변경할 수 없습니다.

**가격 편집 허용** 및 **할인 편집 허용** 필드가 회사 간 구매 주문과 회사 간 판매 주문 모두에서 활성화된 경우 두 주문을 모두 수동으로 변경할 수 있습니다. 그러나 이로 인해 한 사람이 만든 업데이트가 같은 주문에 대해 다른 회사의 다른 사람이 만든 업데이트가 무시되는 상황이 발생할 수 있습니다.

> [!NOTE]
> 회사 간 구매 주문과 회사 간 판매 주문 모두에서 **가격 및 할인** 필드를 활성화한 경우 가격을 제어할 수 없습니다.

이러한 유형의 충돌을 방지하려면 회사 간 판매 주문 또는 회사 간 구매 주문에 대해서만 가격 및 할인을 변경할 수 있도록 하는 것이 가장 좋습니다. 이는 이러한 주문 중 하나에서 **가격 편집 허용** 및 **할인 편집 허용** 필드를 활성화하여 수행됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
