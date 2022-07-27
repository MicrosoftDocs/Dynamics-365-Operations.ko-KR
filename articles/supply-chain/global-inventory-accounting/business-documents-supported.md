---
title: Global Inventory Accounting에서 지원하는 비즈니스 문서
description: 이 항목에서는 Global Inventory Accounting에서 지원하는 비즈니스 문서를 나열합니다. 또한 구매 주문 문서에 대한 자세한 예를 제공합니다.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 47251a7167a00346aed26b9e9535f1b12301e5a6
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2021
ms.locfileid: "8449497"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Global Inventory Accounting에서 지원하는 비즈니스 문서

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Global Inventory Accounting Add-in이 완전히 설정되면 Microsoft Dynamics 365 Supply Chain Management에 입력된 재고 관련 문서를 처리할 준비가 된 것입니다.

## <a name="supported-business-documents"></a>지원되는 비즈니스 문서

두 가지 유형의 비즈니스 문서가 있습니다.

- **저널이 있는 문서** – 이러한 문서에는 제품 영수증, 구매 송장, 포장 명세서 및 판매 송장 문서가 포함됩니다.
- **저널이 없는 문서** – 이러한 문서에는 집계, 이동 및 재고 조정 문서가 포함됩니다.

이 항목의 뒷부분에서 구매 주문이 프로세스를 설명하기 위한 예로 사용됩니다.

다음 표에는 현재 릴리스에서 지원하는 문서가 나열되어 있습니다.

| 문서 유형      | 문서        |
|--------------------|-----------------|
| 구매 주문     | 제품 영수증 |
| 구매 주문     | 송장         |
| 판매 주문        | 포장 전표    |
| 판매 주문        | 송장         |
| 재고 분개 | 이동        |
| 재고 분개 | 조정      |
| 재고 분개 | 원가 계산        |
| 재고 분개 | 이전        |
| 이전 주문     | 배송        |
| 이전 주문     | 수령         |

> [!IMPORTANT]
> Global Inventory Accounting은 Supply Chain Management에 입력된 문서를 비동기식으로 처리합니다. 문제가 있는 문서에는 오류 메시지가 표시되지 않습니다.

## <a name="example-purchase-order"></a>예: 구매 주문

### <a name="product-receipt"></a>제품 영수증

일반적인 방법으로 제품 영수증을 게시합니다. **모든 구매 주문** 페이지에서 구매 주문을 선택한 다음 작업 창의 **수령** 탭에서 **제품 영수증** 을 선택하여 **제품 수령 일지** 페이지를 엽니다. 라인별로 작업 이벤트와 Global Invntroy Accounting 이벤트가 생성됩니다. 따라서 **라인** 탭을 선택한 다음 **인벤토리 \> 이벤트 및 측정** 을 선택하여 **이벤트 및 측정** 페이지를 엽니다.

Global Inventory Accounting은 이벤트 및 측정을 기반으로 하는 회계 시스템입니다. **이벤트 및 측정** 페이지의 측정 라인 그리드는 측정 목록을 보여줍니다. 각 측정에는 차원 목록이 있습니다.

각 작업 이벤트에 대해 두 가지 유형의 측정이 있습니다.

- **작업 측정** – 이러한 측정은 비즈니스 문서를 일반적인 용어로 설명합니다. 하나의 측정은 문서에 사용된 측정 단위를 사용하는 제품 수량입니다. 확장 가격, 할인, 할인 퍼센트 및 라인 요금과 같이 재고 가치에 영향을 미치는 측정값도 있습니다.
- **자원 회계 측정** – 이러한 측정은 인벤토리 레지스터 관점에서 나온 것입니다. 재고 측정 단위의 재고에 대한 문서의 영향을 설명합니다. 여러 재고 등록이 있는 경우 여러 라인의 자원 회계 측정이 있습니다.

차원은 다음과 같은 방식으로 구성됩니다.

- **이중성** – 이중성은 경제 이벤트에 참여하는 대리인을 설명합니다. 외부 비즈니스 문서의 경우 기본 차원은 문서가 입력되는 법인을 설명하는 반면 이중 차원은 공급업체, 고객 등을 설명합니다. 내부 비즈니스 문서(예: 이전 주문)의 경우 이중 차원은 상대 창고를 설명합니다.
- **차원 유형** – 차원 유형은 차원을 분류합니다.
- **차원** – 차원의 이름입니다.
- **차원 값** – 차원의 값입니다.

### <a name="global-inventory-accounting-event"></a>Global Inventory Accounting 이벤트

Global Inventory Accounting은 운영 이벤트 및 측정값을 입력으로 사용합니다. 그런 다음 첨부된 통화 및 규칙에 따라 각 관련 원장에 대해 적절한 회계를 수행합니다. **Global Inventory Accounting 이벤트 및 측정** 을 선택하여 Global Inventory Accounting 이벤트를 볼 수 있습니다. Global Inventory Accounting 이벤트는 작업 이벤트와 동일한 방법론을 따르지만 다른 측정값을 사용합니다. 제품 원가 수량, 제품 원가 및 분산의 세 가지 주요 측정 유형이 있습니다.

보조원장 계정은 측정을 추가로 분류하는 데 사용됩니다. 여러 장부가 있을 수 있습니다. 이 원장은 문서가 입력되는 법인에 연결됩니다. **원장** 필드의 값을 변경하여 각 원장에 대한 이벤트 및 측정을 볼 수 있습니다.

### <a name="cost-element"></a>비용 요소

원장에 첨부된 비용 요소 정책에 따라 시스템은 재고 비용에 영향을 미치는 각 회계 작업 이벤트 측정에 비용 요소를 할당합니다. 이러한 측정에는 확장 가격, 할인, 할인 퍼센트 및 회선 요금이 포함됩니다.

### <a name="measurement-line-details"></a>측정 라인 세부 정보

**개요** 탭에는 연결된 정책의 세부 정보가 표시됩니다. 비용 개체 차원은 비용 개체 정책에 따라 비용 개체를 표시합니다. 특정 식별 차원은 비용 흐름 가정이 *특정 - 일괄* 인 경우 배치 번호를 표시합니다.

### <a name="purchase-invoice"></a>구매 청구서

일반적인 방법으로 청구서를 게시합니다. 그런 다음 작업 창의 **송장** 탭에서 **분개장** 그룹의 **송장** 을 선택하여 송장 저널을 엽니다. 라인별로 작업 이벤트와 Global Invntroy Accounting 이벤트가 생성됩니다. 따라서 **라인** 탭을 선택한 다음 **인벤토리 \> 이벤트 및 측정** 을 선택하여 **이벤트 및 측정** 페이지를 엽니다. **이벤트 및 측정** 페이지에는 동일한 측정 유형이 표시됩니다. 그러나 페이지에 다른 측정 역할과 측정 수정자가 표시되므로 에이전트(법인)에 미치는 영향이 다릅니다.

**Global Inventory Accounting 이벤트 및 측정** 을 선택하여 Global Inventory Accounting 이벤트를 봅니다. 이제 재고 수량과 비용이 *송장이 발행되지 않은 입고된 상품* 보조 원장 계정에서 *구매한 상품의 비용* 보조 원장 계정으로 이동합니다.
