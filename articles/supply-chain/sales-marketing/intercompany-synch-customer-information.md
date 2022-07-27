---
title: 회사 간 고객 정보 동기화
description: 이 토픽에서는 회사 간 주문에 대한 고객 정보 동기화에 대해 설명합니다.
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
ms.openlocfilehash: c82216c8391f6c447bec74f25cd16b9db18d468d
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447754"
---
# <a name="synchronize-intercompany-customer-information"></a>회사 간 고객 정보 동기화

[!include [banner](../../includes/banner.md)]

판매 주문이 생성되거나 고객, 공급업체 참조 또는 고객 요청 번호가 변경될 때 **고객 정보** 필드가 활성화된 경우 고객 정보가 동기화됩니다.

이러한 동기화 필드의 값은 언제든지 변경할 수 있습니다. 그러나 이 매개 변수를 선택하여 이 값이 다른 회사 간 주문에 복사되는지 여부만 결정할 수 있습니다. 회사 간 판매 주문에서 **고객 정보** 필드를 활성화한 경우 회사 간 판매 주문에 대한 변경 사항이 회사 간 구매 주문과 동기화됩니다. 회사 간 구매 주문에서 **고객 정보** 필드를 활성화한 경우 원래 판매 주문과 다시 동기화됩니다.

> [!NOTE]
> 회사 간 구매 주문과 회사 간 판매 주문 모두에서 **고객 정보** 필드를 활성화한 경우 한 회사의 한 사람이 수행한 업데이트는 동일한 주문에 대해 다른 회사의 다른 사람이 수행한 업데이트보다 우선합니다.

회사 간 구매 주문서에서 **고객 정보** 필드를 활성화하는 것이 가장 좋습니다. 이렇게 하면 원래 판매 주문과 회사 간 구매 주문 간, 회사 간 구매 주문에서 회사 간 판매 주문로 동기화할 수 있습니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
