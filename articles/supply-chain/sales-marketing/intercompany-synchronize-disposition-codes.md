---
title: 처리 코드 동기화
description: 이 토픽에서는 회사 간 상거래에 대한 처리 코드 동기화에 대해 설명합니다.
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
ms.openlocfilehash: 04a25324e79a1f9cb30a7da19d648bda995ba7b2
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447727"
---
# <a name="synchronize-intercompany-disposition-codes"></a>회사 간 처리 코드 동기화

[!include [banner](../../includes/banner.md)]

회사 간 반품을 지원하기 위해 Microsoft Dynamics 365 Supply Chain Management를 사용하면 외부에서 정의된 처분 코드를 해당 내부 처분 코드에 매핑할 수 있습니다. 회사 간 체인을 설정할 때 서로 매핑되는 두 회사의 처리 작업이 동일해야 합니다. 서로 다르면 동기화 프로세스가 실패합니다.

## <a name="about-disposition-codes-for-three-legged-direct-returns"></a>3-legged 직접 반품에 대한 처분 코드 정보

처리 코드는 회사 간 판매 주문 라인에서 원래 판매 주문 라인으로 동기화됩니다. 그러나 동기화는 원래 판매 주문 라인에 단 하나의 즉각적인 영향을 미칩니다. 이 효과는 A사에서 설정한 처분 코드와 잡비를 기준으로 잡회선 비용이 삭제된다는 것입니다. A사는 반품 주문을 생성하는 회사입니다.

3-레그 직접 납품 체인에서 모든 처분 작업은 회사 간 판매 주문 라인에서 지원됩니다. 그러나 제품이 고객에게 반품되는 경우 반품 주문의 배송 주소가 원래 주문에 지정된 고객 배송 주소와 일치하는지 확인해야 합니다.

> [!NOTE]
> 구매 주문에 대한 처분 코드가 없습니다. 따라서 회사 간 판매 주문에서 원래 반품 주문으로 처리 코드 동기화는 판매 주문에서 판매 주문로 수행되어야 합니다.

## <a name="replacing-returned-items"></a>반품된 품목 교체

반품된 품목을 교체하는 중이고 교체 주문이 이미 회사 B에서 생성된 경우 처분 코드를 선택할 수 없으며 회사 A에서 추가 교체 주문이 생성되지 않습니다.

## <a name="rules-for-intercompany-direct-deliveries"></a>회사 간 직접 납품 규칙

다음 일반 규칙은 회사 간 직접 배송과 관련된 시나리오의 원래 반품 주문에 적용됩니다.

- 최초 판매 주문 라인의 기본 처분 조치가 대변 및 폐기, 대변 또는 고객에게 반품인 경우 대변 처분 조치가 적용됩니다. 그러나 고객에게 반환 작업 코드는 회사 간 판매 주문의 기존 라인과 새로 동기화된 라인에서 순 금액을 0으로 설정합니다. 또한 스크랩 라인은 동기화되지 않습니다. 라인이 회사 간 판매 주문에 추가되면 양수 및 폐기 처리 조치(예: 대변 및 폐기 또는 대체 및 폐기)가 있는 판매 주문에 대해 동기화되지 않습니다.
- 신용 및 교체 또는 폐기 및 교체의 기본 처분 조치는 무효화되지 않습니다. 이는 신용 및 교체 또는 신용 및 교체의 처분 조치로 취급됩니다 이 규칙은 회사 A에서 생성된 스크랩 라인이 없고 회사 B(반품 품목을 수령한 회사)에서 대체 주문이 생성되지 않은 경우에도 적용됩니다. 포장 전표 업데이트가 수행된 경우에만 회사 A에서 교체 주문이 생성됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
