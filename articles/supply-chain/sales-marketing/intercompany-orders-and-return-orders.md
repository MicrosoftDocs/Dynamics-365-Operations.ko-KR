---
title: 회사 간 주문 및 반품 주문
description: 이 토픽에서는 회사 간 주문 및 반품 주문에 대해 설명합니다.
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
ms.openlocfilehash: 103225595e82bdedec6d97e5ebe5b61498377065
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447766"
---
# <a name="intercompany-orders-and-return-orders"></a>회사 간 주문 및 반품 주문

[!include [banner](../../includes/banner.md)]

이 토픽에서는 회사 간 구매 주문, 판매 주문, 반품 주문, 구매 계약 및 판매 계약이 생성되고 업데이트되는 방법에 대해 설명합니다.

## <a name="about-intercompany-orders"></a>회사 간 주문 정보

회사 간 판매 주문을 생성하면 Microsoft Dynamics 365 Supply Chain Management가 해당 구매 주문을 자동으로 생성합니다. 마찬가지로, 회사 간 구매 주문을 생성하면 해당 회사 간 판매 주문이 자동으로 생성됩니다.

이는 two-legged 주문(두 관련 회사 간의 트랜잭션) 및 대부분의 three-legged 회사(회사 간 트랜잭션이 외부 고객에 대한 판매 주문에서 시작된 경우)에 해당됩니다.

## <a name="intercompany-order-example"></a>회사 간 주문 예

두 개의 관련 회사가 있습니다. 회사 A는 판매 자회사이고 회사 B는 유통 단위입니다. 회사 간 판매 주문 및 구매 주문은 다음 시나리오에서 자동으로 생성됩니다.

- 회사 A가 구매 주문을 생성하고 공급업체가 회사 B인 경우 회사 B에서 회사 간 판매 주문이 자동으로 생성됩니다. 투 레그드(Two-legged) 주문 체인은 회사 A의 구매 주문과 회사 B의 회사 간 판매 주문으로 구성됩니다.
- 회사 B가 판매 주문을 생성하고 고객이 회사 A인 경우 회사 A에서 회사 간 구매 주문이 자동으로 생성됩니다. 투-레그드 주문 체인은 회사 B의 판매 주문과 회사 A의 회사 간 구매 주문으로 구성됩니다.
- 회사 A가 외부 고객에 대한 판매 주문을 처음 생성할 때 회사 A에서 구매 주문이 자동으로 생성될 수 있습니다. 그러면 회사 B에서 회사 간 판매 주문이 자동 생성됩니다. 회사 A의 판매 주문 및 구매 주문 및 회사 B의 회사 간 판매 주문.

## <a name="about-intercompany-return-orders"></a>회사 간 반품 주문 정보

일반 반품과 마찬가지로 회사 간 항목을 반품할 수 있습니다. 그러나 회사 간 항목의 경우 외부 고객의 반품 주문은 회사 간 구매 주문을 생성합니다. 그러면 회사 간 판매 반품 주문이 자동으로 생성됩니다. 외부 고객 반품 주문 없이 회사 간 품목을 반품할 수도 있습니다.

일반 반품 주문과 유사한 회사 간 반품 주문은 **반품 주문 생성** 페이지에서 시작됩니다.

Microsoft Dynamics 365 Supply Chain Management에서 회사 간 판매 및 구매 계약은 반환된 항목을 반영하도록 자동으로 업데이트됩니다. 해당 항목에 대한 판매 또는 구매 계약 약정은 품목이 반품될 때 수량 또는 금액의 변경을 반영하도록 자동으로 조정됩니다.

## <a name="intercompany-return-order-example"></a>회사 간 반품 주문 예

회사 A는 회사 간 품목에 대한 구매 계약에 연결된 구매 주문을 생성합니다. 회사 간 판매 주문은 해당 판매 계약에 연결된 회사 B에서 자동으로 생성됩니다. 구매 계약과 판매 계약은 회사 간 계약으로 관련되어 있습니다.

회사 A는 회사 간 품목을 회사 B로 반품합니다. 회사 B는 품목에 대한 반품 주문을 생성하고 구매 반품 주문은 회사 A에서 자동으로 생성됩니다. 원래 주문에 연결된 구매 계약 및 판매 계약 모두에 대한 약정 수량이나 금액의 변화를 반영하도록 자동으로 조정됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
