---
title: 회사 간 요금 동기화
description: 이 토픽에서는 회사 간 요금 동기화에 대해 설명합니다.
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
ms.openlocfilehash: c4854b698c8046fc603454c4d9d7059c938c70b3
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447751"
---
# <a name="synchronize-intercompany-charges"></a>회사 간 요금 동기화

[!include [banner](../../includes/banner.md)]

요금은 회사 간 판매 주문과 회사 간 구매 주문 간에만 동기화되며 항상 동기화됩니다.

회사 간 구매 주문 또는 회사 간 판매 주문에서 **가격 편집 허용** 필드가 선택된 경우 회사 간 판매 주문 또는 회사 간 구매 주문에 비용을 수동으로 추가할 수 있습니다. 그렇지 않으면 할 수 없습니다.

회사 간 판매 주문에서 **가격 편집 허용** 필드가 선택되지 않은 경우 회사 간 판매 주문에 수동으로 비용을 추가할 수 없습니다.

회사 간 구매 주문에서 **가격 편집 허용** 필드가 선택되지 않은 경우 회사 간 구매 주문에 수동으로 비용을 추가할 수 없습니다.

회사 간 구매 주문과 회사 간 판매 주문 모두에서 **가격 편집 허용** 필드가 활성화된 경우 두 주문에 수동으로 비용을 추가할 수 있습니다. 그러나 이로 인해 많은 요금이 잘못 추가될 수 있습니다.

이러한 유형의 충돌을 방지하려면 회사 간 판매 주문이나 회사 간 구매 주문 중 하나에 요금을 추가할 수 있지만 둘 다에 추가할 수 없도록 하는 것이 가장 좋습니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
