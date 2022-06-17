---
title: 개선된 일괄 추적 항목 처리
description: 이 항목에서는 Microsoft Dynamics 365 Commerce에서의 명세서 전기 프로세스 중에 실행되는 일괄 추적 항목의 개선된 처리에 대해 설명합니다.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 513b6ca84fa71e851a5a3e4275e0b6572789e1eb
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2021
ms.locfileid: "8452890"
---
# <a name="improved-handling-of-batch-tracked-items"></a>개선된 일괄 추적 항목 처리

[!include [banner](includes/banner.md)]

이 항목에서는 Microsoft Dynamics 365 Commerce에서의 명세서 전기 프로세스 중에 실행되는 일괄 추적 항목의 개선된 처리에 대해 설명합니다.

Dynamics 365 Commerce POS(Point of Sale)의 경우에는 판매 시점에 일괄 추적 항목의 배치 번호를 캡처할 수 없습니다. 그러나 고객 주문 또는 명세서 전기를 통해 Commerce Headquarters에 판매가 전기되는 구성의 경우, Commerce에서는 일괄 추적 항목에 대한 유효한 배치 번호가 존재하고 송장 발행 프로세스 중에 사용된다고 예상합니다.

제품에 대해 유효한 배치 번호를 사용할 수 있다면, 고객 주문 송장 발행 프로세스와 명세서 전기의 판매 주문 송장 발행 프로세스에서 모두 이 번호를 사용합니다. 제품에 유효한 배치 번호를 사용할 수 없다면, 고객 주문 송장 발행 프로세스를 전기할 수 없고 POS 사용자는 오류 메시지를 받게 됩니다. 이 경우 제품의 마이너스 재고를 활성화해도 명세서 전기가 오류 상태가 됩니다.

Commerce에 적용된 개선 사항은 일괄 추적 항목의 마이너스 재고를 설정했을 때, 재고가 0(영)이거나 배치 번호를 사용할 수 없다면 명세서 게시를 통한 고객 주문 송장 발행 및 판매 주문 송장 발행이 이러한 해당 항목에 대해 차단되지 않게 합니다. 개선된 기능은 배치 번호를 사용할 수 없는 경우 판매 라인의 기본 배치 ID를 사용합니다.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>고객 주문에 사용하는 기본 배치 ID 정의

고객 주문에 사용하는 기본 배치 ID를 정의하려면 다음 단계를 따르세요.

1. Commerce Headquarters에서 **Retail 및 Commerce \> Headquarters 설정 \> 매개 변수 \> Commerce 매개 변수** 로 이동합니다.
1. **고객 주문** 탭의 **주문** 빠른 탭에서 **기본 배치 ID** 필드에 값을 입력합니다.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>명세서 전기를 통해 판매 주문 송장 발행에 사용하는 기본 배치 ID 정의

명세서 전기를 통한 판매 주문 송장 발행에 사용하는 기본 배치 ID를 정의하려면 다음 단계를 따르세요.

1. Commerce Headquarters에서 **Retail 및 Commerce \> Headquarters 설정 \> 매개 변수 \> Commerce 매개 변수** 로 이동합니다.
1. **전기** 탭의 **재고 업데이트** 빠른 탭에서 **기본 배치 ID** 필드에 값을 입력합니다.

> [!NOTE]
> - 기본 배치 ID 기능은 특정 매장 창고 및 품목의 고급 입고가 활성화된 경우에만 사용할 수 있습니다. 향후 릴리스에서는 고급 입고 관리가 활성화되지 않은 상황에서도 기본 배치 ID 기능이 지원될 예정입니다.
> - 고급 입고 관리를 사용하지 않는 상황에서의 명세서 전기 중 일괄 추적 항목의 개선 처리는 Commerce 버전 10.0.5 릴리스에서 도입되었습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
