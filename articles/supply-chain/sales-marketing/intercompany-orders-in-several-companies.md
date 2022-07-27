---
title: 여러 회사에서 회사 간 구매 및 판매 주문 생성
description: 이 토픽에서는 여러 회사에서 회사 간 구매 주문 또는 판매 주문을 생성하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 5d756a82abb7e7b19080128353d863f29837fc5b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447730"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>여러 회사에서 회사 간 구매 및 판매 주문 생성

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management는 하나의 생산 회사와 여러 판매 회사를 취급하는 데 국한되지 않습니다. 회사 간 거래를 위해 설정된 모든 회사는 무역 회사와 생산 회사가 될 수 있습니다.

같은 상품을 더 많은 업체에서 배송할 수 있다면 누구에게 구매할지 자유롭게 선택할 수 있으며, 하나의 판매 주문이 여러 구매 주문이 되어도 업데이트가 진행됩니다.

하나의 회사 간 구매 주문을 자동으로 생성하는 것과 같은 방식으로 회사에서 원래 판매 주문을 생성한 다음 둘 이상의 내부 구매 주문을 생성하여 여러 내부 공급업체 회사에서 주문을 이행하도록 할 수 있습니다. Microsoft Dynamics 365 Supply Chain Management는 공급업체 회사에서 회사 간 판매 주문을 자동으로 생성합니다.

이를 위해서는 모든 회사가 거래 관계로 설정되어야 합니다. 공급업체 회사는 Microsoft Dynamics 365 Supply Chain Management에서 내부 공급업체로 설정되어야 하며 관련 항목의 기본 공급업체여야 합니다. 판매 주문의 **헤더 보기** 에서 **회사 간 설정** 빠른 탭에서 **회사 간 주문 자동 생성** 필드 및 **직접 배송** 필드를 선택해야 합니다. 이는 기본 설정입니다.

일반적인 방법으로 판매 라인을 생성합니다. 기록에서 나가면 회사 간 구매 주문 및 회사 간 판매 주문이 생성되었음을 알리는 메시지가 나타납니다. 메시지에는 새 주문에 대한 링크가 포함되어 있습니다. 공급업체 회사에서 생성된 회사 간 판매 주문을 보려면 원래 판매 주문을 열고 **일반** 탭의 **관련 정보** 그룹에서 **참조** 를 선택합니다.

공급업체에 대한 회사 간 구매 주문을 열면 Microsoft Dynamics 365 Supply Chain Management가 각 공급업체에 대한 원래 판매 주문 번호와 내부 판매 주문 번호를 자동으로 채우는 것을 볼 수 있습니다.

마찬가지로 공급업체에 대한 회사 간 판매 주문을 열면 Microsoft Dynamics 365 Supply Chain Management가 각 공급업체에 대한 원래 판매 주문 번호와 내부 구매 주문 번호를 자동으로 채우는 것을 볼 수 있습니다.

> [!NOTE]
> 주문 항목이 회사 간 공급업체 회사 중 하나에는 있지만 다른 공급업체 회사에는 없는 경우 Microsoft Dynamics 365 Supply Chain Management은 항목이 있는 공급업체 회사에 대해 회사 간 주문을 생성하지만 다른 회사에 대한 주문 생성은 중지합니다. 이 경우 알림 메시지가 표시됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
