---
title: BOM 계산
description: 비용 롤업 및 판매 가격 계산을 BOM(자재 명세서) 계산이라고 하며 계산 페이지에서 시작합니다. 이 토픽에서는 BOM 계산에 대한 정보를 제공합니다.
author: AndersGirke
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, ProdSetupCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 2a3939d092bcba00aa9dc63c0fe7546beed2041d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448864"
---
# <a name="bom-calculations"></a>BOM 계산

[!include [banner](../includes/banner.md)]

비용 롤업 및 판매 가격 계산을 BOM(자재 명세서) 계산이라고 하며 계산 페이지에서 시작합니다. 이 토픽에서는 BOM 계산에 대한 정보를 제공합니다.

비용 롤업 및 판매 가격 계산을 BOM(자재 명세서) 계산이라고 하며 **계산** 페이지에서 시작합니다. **계산** 페이지를 사용하여 다음 작업을 수행할 수 있습니다.

-   제조 품목의 원가를 계산하고 원가 계산 버전 내에서 연관된 품목 원가 레코드를 생성합니다.
-   제조 품목의 판매 가격을 계산하고 원가 계산 버전 내에서 연관된 품목 판매 가격 레코드를 생성합니다.

**계산** 페이지를 사용하는 방법은 BOM 계산을 시작하는 방법에 따라 약간 다릅니다. 또한 **계산** 페이지를 사용하는 방법은 BOM 계산에 표준 원가 또는 계획 원가에 대한 원가 계산 버전이 포함되는지 여부와 BOM 계산에 사용되는 원가 계산 버전에 정의된 여러 정책에 따라 다릅니다. **참고:** **계산** 페이지의 변형은 판매 주문, 판매 견적 또는 서비스 주문 라인 항목의 컨텍스트에서 사용됩니다. 이러한 계산을 주문별 BOM 계산이라고 합니다. 주문별 BOM 계산은 원가계산 버전 내에서 품목 원가 레코드를 생성하지 않습니다. 대신에 **BOM 계산 세부정보** 페이지에 표시되는 계산 레코드를 생성합니다. 계산 레코드에는 계산된 비용과 계산된 판매 가격이 포함됩니다. **계산** 페이지는 단일 제조 품목 또는 원가계산 버전에 대해 열 수 있습니다.

-   단일 제조 품목의 비용을 계산하려면 **품목 가격** 페이지에서 BOM 계산을 시작합니다. **계산** 페이지는 항목 식별자를 상속합니다. 원가 계산 버전, BOM 버전, 경로 버전, 계산 수량, 계산 날짜 및 사이트를 지정해야 합니다.
    -   기본적으로 BOM 버전 및 경로 버전은 품목, 사이트, 날짜 및 계산 수량에 대한 활성 버전으로 설정됩니다. 그러나 승인된 버전으로 기본값을 재정의할 수 있습니다.
    -   기본적으로 계산 수량은 항목의 표준 주문 수량으로 설정됩니다. 그러나 기본값을 재정의할 수 있습니다.
    -   계산 날짜 또는 사이트는 비용 계산 버전에서 지정하거나 날짜 또는 사이트가 비용 계산 버전에서 지정되지 않은 경우 사용자 지정 값을 설정할 수 있습니다. 미래 계산 날짜에 따라 보류 비용 레코드가 사용되는 방식이 결정됩니다. BOM 계산은 가장 가까운 시작 날짜가 계산 날짜 또는 그 이전인 보류 비용 레코드를 사용합니다.
-   모든 제조 품목 또는 선택한 품목에 대한 원가를 계산하거나 사용처를 기준으로 품목을 업데이트하려면 **원가 계산 버전 설정** 페이지 또는 **원가 계산 버전 유지 관리** 페이지에서 BOM 계산을 시작합니다. **계산** 페이지는 원가 계산 버전을 상속합니다.
    -   계산을 위해 제조된 구성요소에 지정된 하위 BOM 또는 하위 경로가 없는 경우 활성 BOM 버전 및 경로 버전이 제조 품목(관련 사이트, 날짜 및 수량에 대해)에 사용된다고 가정합니다.
    -   계산에는 표준 주문 수량이 제조 품목에 사용되는 것으로 가정합니다. 표준 주문 수량은 구성품 수량 계산, 관련 BOM 버전 및 경로 버전 결정(수량에 민감한 BOM 및 경로 사용 시), 일정 비용 상각을 위한 기초를 제공합니다. 그러나 제조된 구성요소에 BOM 라인 유형이 **생산** 또는 **공급업체** 인 경우 또는 BOM 계산에 주문 제작 전개 모드를 사용하는 경우 수량은 지정된 계산 수량을 반영하므로 이 가정은 적용되지 않습니다.
    -   계산 날짜 또는 사이트는 비용 계산 버전에서 지정하거나 날짜 또는 사이트가 비용 계산 버전에서 지정되지 않은 경우 사용자 지정 값을 설정할 수 있습니다.

BOM 계산의 다른 변형은 원가 계산 유형 및 원가 계산 버전의 제한 사항을 반영합니다.

-   표준 원가를 사용하는 BOM 계산은 원가 계산 버전 정책에 의해 제한되어야 합니다. 그 제한은 표준 원가 계산 원칙이 사용되도록 보장하는 데 도움이 되기 때문입니다. 표준 원가계산 원칙은 구매 품목에 대한 표준 원가 사용, 단일 수준 폭발 모드 및 단위 원가에 기타 비용 포함에 대한 제한을 적용해야 합니다.
-   계획 원가를 사용하는 BOM 계산은 표준 원가 계산 원칙을 따를 필요가 없습니다. 이러한 BOM 계산은 다양한 전개 모드, 구매 품목에 대한 비용 데이터의 대체 소스 및 비용 계산 버전 내에서 선택적 제한 적용을 사용할 수 있습니다.

### <a name="bom-calculations-that-use-standard-costs"></a>표준 비용을 사용하는 BOM 계산

원가계산 버전 내의 정책(표준 원가용)은 5가지 BOM 계산 정책의 시행을 의무화할 수 있습니다. 비용 계산 버전의 **레코딩 제한** 옵션은 이러한 정책 중 하나를 의무화하며, 여기서 기타 비용은 단가에 포함되어야 합니다. 구매 품목에 대한 기타 비용은 수동으로 입력할 수 있는 반면 제조 품목에 대한 기타 비용은 일정 비용의 계산된 상각을 반영합니다. 원가 계산 버전의 **계산 제한** 옵션은 다른 네 가지 BOM 계산 정책을 요구합니다.

-   구매 품목에 대한 비용 기여 출처는 표준 비용을 기준으로 해야 합니다. 즉, BOM 계산은 지정된 원가계산 버전 내에서 또는 표준 원가를 포함하는 대체 내에서 품목 원가 레코드를 사용해야 합니다.
-   정확하고 일관된 표준 비용 계산을 보장하려면 폭발 모드가 단일 수준이어야 합니다.
-   품목의 판매 가격을 계산할 때 일관된 결과를 보장하려면 이익 설정을 의무화해야 합니다. 원가 계산 버전에서 판매 가격 콘텐츠를 허용하는 경우에만 이익 설정을 사용할 수 있고 품목 판매 가격 레코드를 생성할 수 있습니다.
-   대체 원칙은 의무화되어야 하며 **없음**, **활성**(활성 비용 레코드의 경우) 또는 **원가 계산 버전**(지정된 원가계산 버전의 경우)으로 설정할 수 있습니다.

### <a name="bom-calculations-that-use-planned-costs"></a>계획된 비용을 사용하는 BOM 계산

원가계산 버전 내의 정책(계획된 비용)은 선택적으로 5가지 BOM 계산 정책의 시행을 의무화할 수 있습니다. 또는 정책에서 기본값만 제공할 수 있습니다. 비용 계산 버전의 **레코딩 제한** 옵션은 기타 비용에 대한 BOM 계산 정책을 의무화할지 아니면 기본값으로 사용할지를 결정합니다. 기타 요금은 선택적으로 단가에 포함될 수 있습니다. 비용 계산 버전의 **계산 제한** 옵션은 다른 4개의 BOM 계산 정책을 의무화할지 아니면 기본값으로 사용할지를 결정합니다.

-   구매 품목에 대한 비용 기여의 출처는 원가계산 버전 내의 품목 비용 레코드일 수 있습니다. 또는 항목에 지정된 BOM 계산 그룹에서 소스를 정의할 수 있습니다. 예를 들어, BOM 계산 그룹은 구매 가격 거래 계약을 비용 기여 데이터의 소스로 정의할 수 있습니다.
-   전개 모드는 단일 레벨, 다중 레벨 또는 주문 제작일 수 있거나 BOM 라인 항목을 기반으로 할 수 있습니다. BOM 라인 유형에 대한 전개 모드는 생산 주문 견적을 위한 비용 계산 로직을 복제합니다.
-   이익 설정은 필수이거나 기본값일 수 있습니다. 원가 계산 버전에서 판매 가격 콘텐츠를 허용하는 경우에만 이익 설정을 사용할 수 있고 품목 판매 가격 레코드를 생성할 수 있습니다.
-   대체 원칙은 필수이거나 기본값일 수 있습니다. 대체 원칙은 **없음**, **활성**(활성 비용 레코드의 경우) 또는 **원가 계산 버전**(지정된 원가계산 버전의 경우)으로 설정할 수 있습니다.

BOM 계산은 경고 메시지 및 기타 유형의 메시지를 생성합니다. 여러 BOM 계산 정책에 따라 메시지 유형이 결정됩니다. 경고 조건은 항목에 지정된 BOM 계산 그룹에서 정의됩니다. 그러나 BOM 계산을 시작할 때 이러한 경고 조건을 무시할 수 있습니다. 대체 원칙이 사용되는 경우 대체가 정보 메시지로 표시되면 종종 도움이 됩니다. 비용 레코드가 누락된 항목에 대해 계산된 비용을 업데이트하려고 할 때 정보 메시지가 업데이트되지 않은 항목을 식별하는 경우에도 유용합니다.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>대체 원칙을 사용하는 BOM 계산
다음 상황은 대체 원칙의 두 가지 용도를 보여줍니다.

-   **표준 비용 업데이트에 대한 2가지 버전 접근 방식** - 원가 계산 버전에는 새 항목 또는 원가 변경을 나타내는 보류 원가 레코드와 같은 표준 원가에 대한 증분 변경이 포함될 수 있습니다. 이 상황에서 대체 원칙은 다른 원가 계산 버전에 포함된 활성 표준 원가의 사용을 식별할 수 있습니다.
-   **계획원가를 이용한 원가변동 효과 시뮬레이션** - 계획된 원가에 대한 원가계산 버전은 시뮬레이션을 위한 증분 변경을 포함할 수 있습니다. 이 원가 계산 버전에는 항목, 원가 범주 및 간접 원가 계산 공식에 대한 시뮬레이션 원가 변경을 나타내는 보류 원가 기록이 포함됩니다. 이 상황에서 대체 원칙은 다른 원가 계산 버전에 포함된 활성 표준 원가의 사용을 식별할 수 있습니다.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>제안 판매 가격의 BOM 계산
원가 가산 인상 접근 방식을 사용하는 경우 품목에 대해 계산된 판매 가격은 BOM 계산에 대해 지정된 이익 설정 퍼센트 세트와 품목의 구성품 품목, 공정순서 공정 및 적용 가능한 제조 간접비를 반영합니다. 마크업은 원가 그룹에 할당된 이익 설정 백분율, 품목에 할당된 원가 그룹, 공정순서 작업에 대한 원가 범주 및 제조 간접비에 대한 간접 원가 계산 공식을 반영합니다. 이익 설정 백분율 세트에는 **표준**, **이익 1**, **이익 2** 및 **이익 3** 레이블이 지정됩니다. 예를 들어 이익 1 세트 내에서 구매 자재에 할당된 비용 그룹에 대해 50%의 이익 설정 비율을 정의할 수 있고 할당된 비용 그룹에 대해 80%의 이익 설정 비율을 정의할 수 있습니다. 이는 라우팅 작업에 대한 비용 범주로 이동합니다. BOM 계산 컨텍스트에 따라 계산된 판매 가격의 결과가 처리되는 방식이 결정됩니다.

-   **품목 및 지정된 원가계산 버전에 대한 BOM 계산** - BOM 계산은 원가계산 버전 내에서 보류 중인 판매 가격 레코드를 생성합니다. 이 판매 가격 레코드는 계산 세부 정보를 보기 위한 시작점을 제공합니다(예: **품목 비용 계산** 페이지). 판매 가격 레코드는 주로 참조 정보 역할을 하며 판매 주문에 대한 판매 가격의 기준으로 사용되지 않습니다.
-   **주문별 BOM 계산:** **BOM 계산** 페이지의 변형은 판매 주문, 판매 견적 또는 서비스 주문 라인 항목의 컨텍스트에서 사용됩니다. 주문별 BOM 계산은 원가계산 버전 내에서 레코드를 생성하지 않습니다. 대신에 **BOM 계산 결과** 페이지에 표시되는 계산 레코드를 생성합니다. 이 계산 레코드는 계산 세부 정보를 보기 위한 시작점을 제공합니다(예: **품목 비용 계산** 페이지). 선택한 계산 레코드에 대한 정보를 원래 라인 항목으로 전송할 수 있습니다. 예를 들어 계산된 판매 가격을 판매 주문 항목으로 전송할 수 있습니다.

## <a name="order-specific-bom-calculations"></a>주문별 BOM 계산
주문별 BOM 계산은 제조 품목에 대한 BOM 계산의 변형을 나타냅니다. 주문별 BOM 계산은 판매 주문, 판매 견적 또는 서비스 주문 라인 항목의 컨텍스트에서 수행됩니다. 주문별 BOM 계산은 **BOM 계산 결과** 페이지에 나타나는 계산 레코드를 생성합니다. 계산 레코드에는 계산된 가중치, 활성 비용 레코드를 기반으로 하는 계산된 비용 및 계산된 판매 가격이 포함됩니다. **BOM 계산 결과** 페이지에서 항목에 대한 각 주문별 BOM 계산이 생성하는 계산 레코드는 계산 번호로 고유하게 식별됩니다. 계산 레코드의 결과는 선택적으로 원래 라인 항목으로 전송할 수 있습니다. 주문별 BOM 계산은 제조 품목에 대한 BOM 계산에 따라 두 가지로 나뉩니다.

-   주문별 BOM 계산은 원가계산 버전 내에서 품목 원가 레코드를 생성하지 않습니다. 따라서 품목 비용 레코드가 생성되거나 비용 레코드를 덮어쓸 때 BOM 계산 정책이 적용되지 않습니다.
-   주문별 BOM 계산은 항상 구성 요소, 비용 범주 및 간접 비용 계산 공식에 대한 활성 비용 레코드를 사용합니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]