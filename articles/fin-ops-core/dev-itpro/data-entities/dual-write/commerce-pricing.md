---
title: Dynamics 365 Sales와 함께 Dynamics 365 Commerce 가격 책정 엔진 사용
description: 이번에는 Microsoft Dynamics 365 Commerce 가격 책정 엔진을 사용하여 Dynamics 365 Sales에서 판매 견적을 만드는 방법에 대해 설명합니다.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c3f1527e5f37bebba57661ca86b1a3aae7e62da0
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2021
ms.locfileid: "8460998"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>Dynamics 365 Sales와 함께 Dynamics 365 Commerce 가격 책정 엔진 사용

[!include [banner](../../includes/banner.md)]

이번에는 Microsoft Dynamics 365 Commerce 가격 책정 엔진을 사용하여 Dynamics 365 Sales에서 판매 견적을 만드는 방법에 대해 설명합니다.

Dynamics 365 Commerce 가격 책정 엔진은 매장 수준 가격 책정, 제휴 기반 및 충성도 기반 가격 책정, 혼합 할인, 수량 할인 및 임계값 할인과 같은 대부분의 B2C(기업 대 소비자) 가격 책정 시나리오를 지원합니다. 가격 책정 엔진은 복잡한 규칙을 사용하여 주어진 견적이나 주문에 대한 최적의 가격을 결정합니다.

[이중 쓰기](./dual-write-overview.md)를 사용하는 경우 가격 책정 요구 사항에 대한 세 가지 옵션이 있습니다. Dynamics 365 Sales의 가격 목록, Dynamics 365 Supply Chain Management의 가격 책정 엔진 또는 Dynamics 365 Commerce의 가격 책정 엔진에서 가져온 정적 가격 책정을 사용할 수 있습니다. 이러한 옵션 중에서 Commerce 가격 책정 엔진은 B2C 시나리오에 가장 적합합니다.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>Sales에서 Commerce 가격 책정 엔진 사용

> [!NOTE]
> 현재 Commerce 가격 책정 엔진은 Sales에서 견적 생성에만 사용할 수 있습니다. Commerce 가격 책정 엔진과의 판매 주문 통합은 아직 사용할 수 없습니다.

사용자가 Sales에서 견적을 시작하면 이중 쓰기 프레임워크가 견적 세부 정보를 Commerce에 복사합니다. 기존 견적 라인의 변경 사항이나 Sales에 새로 추가된 견적 라인은 Commerce에 복사됩니다. 사용자가 상거래 가격 책정 엔진을 사용하여 견적 가격을 책정하려는 경우 **가격 견적** 을 선택하여 상거래 가격 책정 엔진을 기반으로 견적 가격을 업데이트할 수 있습니다. 이후 판매 및 상거래에서 가격이 자동으로 업데이트됩니다.

## <a name="prerequisites"></a>전제 조건

- Sales에서 Commerce 가격 책정 엔진을 사용하려면 [이중 쓰기에서 Prospect-to-cash](./dual-write-prospect-to-cash.md)의 단계를 따라야 합니다.
- 다음 단계에 따라 수동 입력에 대한 무역 계약 평가를 해제해야 합니다.

    1. 상거래 환경에서 **미수금 \> 설정 \> 미수금 매개 변수** 로 이동합니다.
    1. **가격** 탭의 **무역 계약 평가** FastTab에서 **수동 입력** 확인란의 선택을 취소합니다.

## <a name="additional-resources"></a>추가 리소스

[이중 쓰기의 잠재 현금화](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]