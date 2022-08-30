---
title: 반품 주문에 대한 교환 구성 및 처리
description: 이 문서에서는 Dynamics 365 Commerce에서 반품 시 교환을 구성하는 방법에 대해 설명합니다.
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845796"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>반품 주문에 대한 교환 구성 및 처리

[!include [banner](includes/banner.md)]

Dynamics 365 Commerce의 이전 버전에서 고객 주문에 대한 반품은 본사의 반품 주문 문서를 사용하여 처리되었습니다. 그러나 반품 주문 문서는 반품이 진행 중인 제품만 처리하는 데 사용할 수 있습니다. 반품된 제품은 반품 주문 라인에서 음(–)의 수량으로 표시됩니다. 이에 반해 판매량은 양(+)의 수량으로 표시됩니다. 그러나 반품 주문 문서는 양(+)의 수량을 지원하지 않습니다. 이러한 제한이 있기 때문에 이전 버전의 앱에서는 반품 주문 문서를 사용하여 제품 교환을 수행하는 시나리오를 지원하지 않았습니다.

그러나 반품 주문 시 교환이 실행되는 시나리오를 지원하는 기능이 추가되었습니다. 이제 Commerce는 반품 주문 문서 대신에 판매 주문 문서를 사용하여 이러한 유형의 거래를 처리합니다.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>반품 주문 시 교환을 지원하도록 Commerce를 구성

> [!NOTE]
> Commerce 버전 10.0.20 및 이후 버전에서는 'POS의 통합 반품 처리 경험'이라는 새로운 기능을 사용할 수 있습니다. 이 기능을 활성화하면 아래의 설정 단계가 필요하지 않습니다. **반품을 판매 주문으로 처리** 는 영구적으로 구성된 설정이 되며 이 설정은 변경할 수 없습니다.

(**POS에서 통합 반품 처리 경험** 기능을 사용하지 않을 경우) 반품 주문 시 교환을 지원하도록 시스템을 구성하려면 다음 단계를 따르십시오.

1. **Retail 및 Commerce \> Headquarters 설정 \> 매개 변수 \> Commerce 매개 변수** 로 이동합니다. **고객 주문** 빠른 탭에서 **반품 주문을 판매 주문으로 처리** 옵션을 **예** 로 설정합니다.
2. **전역 구성 배포 일정** 작업(**1110**)을 실행합니다.

## <a name="make-an-exchange"></a>교환하기

이전 섹션에서 설명한 대로 시스템을 구성한 후에도 POS(Point of Sale) 사용자는 이전 버전의 앱에서와 같이 반품을 처리하기 위해 판매 주문 또는 판매 송장을 여전히 선택합니다. 다만 반품 항목이 장바구니에 추가되면 사용자는 장바구니에 새 판매 라인을 추가할 수 있습니다.

이러한 신규 판매 라인의 경우, 사용자는 고객 주문 라인을 처리하는 데 필요한 모든 특성을 정의해야 합니다. 이러한 특성에는 배달 방법 및 주문 이행 위치가 포함됩니다. 거래에 대해 지불해야 할 결제 대금은 반품 주문 라인과 판매 주문 라인을 공제한 금액이 됩니다. 거래에 대한 결제가 이루어지면 반품 주문은 본사에서 판매 주문 문서로 기장되며 시스템은 그 즉시 반품 라인에 송장을 보냅니다.

장바구니에 담은 여러 항목의 금액을 더 잘 파악할 수 있도록 3개의 새로운 금액 필드가 장바구니에 추가되었습니다. 화면 디자이너를 사용하면 POS 사용자 인터페이스(UI)에서 이러한 새 필드를 사용할 수 있습니다.

- **보증금 적용** – 사용자가 고객 주문 픽업을 할 때 거래에 적용되는 보증금입니다. 보증금 재정의가 없고 10% 보증금이 구성된 경우, 이 필드의 금액은 고객 주문 총액의 90%에 해당됩니다.
- **주문 이행 금액** – 고객 주문서가 생성 또는 편집되었을 때 또는 고객 주문 교환을 진행하는 중에 배달 모드가 **이행** 으로 설정된 라인의 총액. 이 필드의 금액에는 세금과 요금이 포함됩니다.
- **반환 금액** – 고객 주문 교환을 진행하는 중에 수량이 음수(–)로 표시되는 라인의 총액. 이 필드의 금액에는 세금과 요금이 포함됩니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
