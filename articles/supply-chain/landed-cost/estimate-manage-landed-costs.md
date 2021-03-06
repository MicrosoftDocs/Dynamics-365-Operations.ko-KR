---
title: 상륙 비용 추정 및 관리
description: 시스템은 자동 비용 설정을 사용하여 상륙 비용에 대한 추정치를 결정합니다. 이 토픽에서는 보다 정확한 추정치를 제공하기 위해 다양한 시나리오를 정의하는 방법에 대해 설명합니다.
author: sherry-zheng
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5a8df57eaa779fe7b1f709a59372d9c634447c4a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447859"
---
# <a name="estimate-and-manage-landed-costs"></a>상륙 비용 추정 및 관리

[!include [banner](../../includes/banner.md)]

시스템은 [자동 비용 설정](auto-cost-setup.md)을 사용하여 상륙 비용에 대한 추정치를 결정합니다. 또한 다양한 시나리오를 정의하여 보다 정확한 추정치를 제공할 수 있습니다. 이러한 시나리오가 저장됩니다. 따라서 나중에 검토하고 보고서의 실제와 비교할 수 있습니다. 항목 가격을 업데이트할 수도 있습니다.

## <a name="set-up-cost-estimates"></a>비용 추정치 설정

### <a name="set-up-cost-templates"></a>비용 템플릿 설정

비용 템플릿은 견적을 받는 사용자가 반드시 알지 못하는 기본 설정을 지정합니다. 템플릿은 정확한 추정치를 얻기 위해 사용자가 지정해야 하는 선택을 최소화하여 추정 프로세스의 복잡성을 줄이는 데 도움이 될 수 있습니다. 표준 비용 모델을 사용하는 경우 상품 비용을 설정하는 동안 비용 템플릿을 사용할 수 있습니다.

비용 템플릿을 설정하려면 **상륙 비용 \> 원가 계산 설정 \> 비용 템플릿** 으로 이동합니다. **비용 템플릿** 페이지에서 왼쪽의 목록 창에 현재 비용 템플릿이 모두 표시됩니다. 작업 창의 버튼을 사용하여 템플릿을 생성, 삭제 및 편집할 수 있습니다.

다음 테이블에서는 각 템플릿에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 비용 템플릿 | 비용 템플릿의 고유한 이름을 입력합니다. 이름은 일반적으로 템플릿의 요소 또는 비용 승수를 설명합니다. |
| 설명 | 비용 템플릿에 대한 설명을 입력합니다. |
| 배송 회사 | 템플릿을 사용할 때 적용해야 하는 배송 회사를 선택합니다. |
| 배송 모드 | 템플릿을 사용할 때 적용해야 하는 해상 또는 항공과 같은 배송 방식을 선택합니다. 이 필드는 예상 비용에서 상품과 관련된 자동차 비용을 결정하는 데 도움이 됩니다. |
| 배송 컨테이너 유형 | 템플릿을 사용할 때 적용해야 하는 배송 컨테이너 유형을 선택합니다. 이 필드는 예상 비용에서 상품과 관련된 자동차 비용을 결정하는 데 도움이 됩니다. |
| 관세사 | 템플릿을 사용할 때 적용해야 하는 통관 중개업체(벤더)입니다. 이 필드는 예상 비용과 관련된 자동차 비용을 결정하는 데 도움이 됩니다. |
| 계수 | 템플릿을 사용할 때 비용 견적에 자동으로 적용되어야 하는 승수(백분율)를 입력합니다. 예를 들어, 계산된 예상 비용에 10%를 더하려면 *1.10* 을 입력합니다. |

### <a name="create-a-cost-estimate"></a>비용 견적 생성

**비용 견적** 대화 상자를 사용하여 선택한 비용 템플릿, 선택한 항목 집합 및 여정의 기타 세부 정보를 기반으로 하는 새 비용 견적을 생성합니다. 그런 다음 이러한 설정을 사용하여 예상 물품 수입 비용을 결정합니다. 이러한 비용 견적은 주로 표준 비용 항목으로 작업하는 데 사용됩니다. 예상 상륙 비용을 재고의 표준 상품 원가에 추가하면 상품이 항해에 추가될 때 변동 트랜잭션이 더 작아질 것입니다. 표준 비용은 상륙 비용의 추정치를 반영하기 때문입니다.

**비용 견적** 대화 상자를 열려면 **상륙 비용 \> 정기 작업 \> 비용 견적** 으로 이동합니다. 이후 다음 하위 섹션에 설명된 대로 필드를 설정합니다. 마지막으로 **확인** 을 선택하여 추정치를 생성합니다. **비용 견적** 페이지(**상륙 비용 \> 문의 \> 비용 견적**)가 나타나고 이 토픽의 뒷부분에 설명된 대로 새 견적이 표시됩니다.

### <a name="settings-on-the-parameters-tab"></a>매개 변수 탭의 설정

다음 테이블에서는 **비용 견적** 대화 상자의 **매개 변수** 탭에서 사용할 수 있는 필드에 대해 설명합니다.


| 필드 | 설명 |
|---|---|
| 비용 템플릿 | 비용 템플릿을 선택합니다. 선택한 템플릿과 연결된 설정은 적용되는 자동 비용을 결정하는 데 사용됩니다. |
| 예상 날짜 | 기본적으로 이 필드는 오늘 날짜로 설정되지만 값을 변경할 수 있습니다. 지정된 날짜는 적절한 판매 가격, 구매 가격, 자동차 비용 및 배송료를 사용하는 경우 환율을 선택하는 데 사용됩니다. |
| 측정 | 비용은 측정에 따라 다를 수 있습니다. 예를 들어 항공 화물이 사용되는 경우 부피 가격 책정이 적용될 수 있습니다. 비용이 측정에 따라 달라지는 경우 해당 측정 값을 입력합니다. 그렇지 않으면 측정을 사용하여 할당이 발생하지 않는 것이 확실하지 않은 경우 이 필드를 *1* 로 설정하는 것이 좋습니다. 소수점 값을 입력합니다. 단위는 해당 자동 비용 레코드에 정의된 단위입니다. |
| 여정 템플릿 | [경험 템플릿](multi-leg-journey-setup.md)을 선택합니다. 이 필드는 적용해야 하는 올바른 자동 비용을 결정하는 데 사용됩니다. |
| 출발 항구 | 항목이 출발할 항구입니다. 이 필드는 선택한 경험 템플릿을 기반으로 설정됩니다. |
| 도착 항구 | 항목이 배송될 항구입니다. 이 필드는 선택한 경험 템플릿을 기반으로 설정됩니다. |
| 통화 | 항목을 구매할 통화를 선택합니다. |
| 컨테이너 | 일반적으로 여러 컨테이너를 사용하는 경우 컨테이너 수를 지정합니다. 그런 다음 시스템은 비용을 추정할 때 여러 컨테이너에 대한 비용을 사용합니다. |
| 폴리오 | 일반적으로 여러 폴리오가 사용되는 경우 수량을 지정합니다. (수량은 보통 *1* 입니다.) |
| 사이트 | 상품이 배송될 사이트를 지정합니다. |

### <a name="settings-on-the-items-tab"></a>항목 탭의 설정

**항목** 탭에서 필요한 만큼 항목을 견적에 추가할 수 있습니다. 도구 모음을 사용하여 그리드에 항목을 추가하거나 항목을 제거합니다. 도구 모음에서 **재고 \> 표시 차원** 을 선택하여 그리드에 차원 열을 추가하거나 열을 제거할 수 있는 대화 상자를 엽니다.

다음 테이블에서는 각 항목에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 품목 번호 | 가격을 결정할 항목을 선택합니다. (항목이 시스템에 아직 존재하지 않는 경우 더미 항목을 생성하고 선택적으로 항해 항목 비용 그룹에 첨부한 다음 가격을 공백으로 두거나 가격을 생성 또는 변경합니다.) |
| 공급업체 계정 | 이 항목의 견적에 사용할 공급업체를 선택합니다. 항목에 기본 공급업체가 할당된 경우 이 필드가 자동으로 설정됩니다. |
| 수량 | 구매하실 수량을 선택합니다. |
| 원가 | 시스템은 초기 가격을 찾기 위해 가격 책정 규칙을 사용하지만 필요한 경우 해당 가격을 무시할 수 있습니다. |
| 판매 가격 | 상품의 예상 판매 가격을 입력합니다. |
| 측정 | 상품 측정을 위한 소수점 값을 입력합니다. 단위는 해당 출시 제품에 대해 설정된 단위입니다. |
| 항목 무게/부피 업데이트 | 출시된 제품의 중량 또는 부피 측정이 이 행에 대해 입력된 **측정** 값과 일치하도록 업데이트하려면 이 확인란을 선택합니다. |
| (기타 치수) | 표시하도록 선택한 차원에 따라 각 항목에 대한 추가 정보 열이 표시될 수 있습니다. |

항목의 부피 및/또는 무게 세부 정보를 보거나 조정하려면 그리드에서 항목을 선택한 다음 페이지 하단의 필드를 사용합니다.

## <a name="manage-estimated-costs"></a>예상 비용 관리

생성한 비용 견적을 보고 편집하려면 **상륙 비용 \> 문의 \> 비용 견적** 으로 이동합니다. **비용 견적** 페이지에서 왼쪽의 목록 창에 현재 비용 견적이 모두 표시됩니다. 작업 창의 단추를 사용하여 선택한 추정값으로 작업할 수 있습니다. **비용 견적** 페이지에서는 새 비용 견적을 생성할 수 없습니다. 대신 이 토픽의 앞부분에서 설명한 대로 **비용 견적** 대화 상자(**상륙 비용 \> 정기 작업 \> 비용 견적**)를 사용합니다.

**비용 견적** 페이지는 각 예상 비용이 어떻게 도출되었는지 보여줍니다. 또한 각 항목에 대한 예상 상륙 비용을 보여줍니다. 다양한 상품과 관련된 비용 가격 및/또는 통화를 변경하여 비용 견적을 수정할 수 있습니다. 항해 수준과 컨테이너 수준 모두에서 연결된 항해 비용을 수정할 수도 있습니다. 이 페이지를 사용하여 비용을 수정하면 비용 견적 항목에 대한 예상 비용을 다시 계산하라는 메시지가 표시됩니다. 준비가 되면 견적을 사용하여 비용 템플릿에 있는 항목의 비용 가격을 업데이트할 수 있습니다.

### <a name="information-on-the-header"></a>헤더에 대한 정보

**비용 견적** 페이지 상단에는 이전 섹션에서 설명한 대로 선택한 비용 견적을 생성하는 데 사용된 설정이 표시됩니다. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>라인 빠른 탭의 설정 및 단추

**라인** 빠른 탭은 현재 견적에 포함된 각 항목을 나열합니다. 다음 테이블에서는 각 행에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 공급업체 계정 | 항목과 연결된 공급업체 계정입니다. |
| 품목 번호 | 품목 번호입니다. |
| 수량 | 비용을 결정하는 데 사용되는 항목 수입니다. |
| 원가 | 무역 협정에 따른 비용 가격. 이 값은 현지 통화로 표시됩니다. |
| 측정 | 개별 측정. 단위는 해당 출시 제품에 대해 정의된 단위입니다. |
| 예상 상륙 비용 | 총 수량에 대한 예상 입고 비용입니다. |
| 단위당 | 예상 입고 비용을 수량으로 나눈 값입니다. |
| (기타 치수) | 표시하도록 선택한 차원에 따라 각 항목에 대한 추가 정보 열이 표시될 수 있습니다. |

다음 테이블에서는 **라인** 빠른 탭의 도구 모음에서 사용할 수 있는 단추에 대해 설명합니다.

| 단추 | 설명 |
|---|---|
| 추가 | 비용 견적에 항목을 추가합니다. 항목을 추가한 후 작업 창에서 **다시 계산** 을 선택해야 합니다. |
| 제거 | 비용 견적에서 항목을 제거합니다. 항목을 제거한 후 작업 창에서 **다시 계산** 을 선택해야 합니다. |
| 항해 비용 | 항목에 대한 다양한 유형의 항해 비용을 보고 편집할 수 있는 페이지를 엽니다. |
| 재고 \> 차원 표시 | 그리드에 차원 열을 추가하거나 열을 제거할 수 있는 대화 상자를 엽니다. |

### <a name="settings-on-the-general-fasttab"></a>일반 빠른 탭의 설정

**일반** 빠른 탭은 현재 **라인** 빠른 탭에서 선택된 항목에 대한 세부 정보를 보여줍니다. 이 정보의 대부분은 **라인** 빠른 탭에서 반복되며 어느 곳에서나 편집할 수 있습니다. 그러나 추가 세부 정보도 여기에서 확인할 수 있습니다. 추가 필드의 값은 해당 출시 제품의 설정을 기반으로 합니다.

### <a name="settings-on-the-dimension-fasttab"></a>차원 빠른 탭의 설정

**차원** 빠른 탭에는 표시하도록 선택한 차원에 관계없이 **라인** 빠른 탭에서 선택한 항목에 대해 사용 가능한 모든 재고 차원 값이 표시됩니다. 여기에 표시된 모든 값은 해당 비용 견적 템플릿에서 가져옵니다. 비용 견적 템플릿에서 선택 사항입니다.

### <a name="buttons-on-the-action-pane"></a>작업 창의 단추

**비용 견적** 페이지의 작업 창에 있는 단추를 사용하여 선택한 비용 견적으로 작업할 수 있습니다. 다음 테이블에서는 사용 가능한 단추에 대해 설명합니다.

| 작업 | 설명 |
|---|---|
| 비용 문의 | 항해에 대한 모든 비용을 봅니다. 필요에 따라 개별 항목 수준에서 비용을 볼 수 있습니다. |
| 표준 비용 업데이트 | <p>**상륙 비용 매개 변수** 페이지에 정의된 기본 원가 계산 버전을 사용하여 표준 원가를 업데이트합니다. 이 버전을 재정의할 수 있습니다.</p><p>**메모:** 항목에 여러 항목 치수(예: 다양한 크기, 색상 및 구성)가 있지만 추정치를 위해 이러한 치수가 선택되지 않은 경우 시스템은 각 조합에 대해 보류 가격을 생성합니다.</p><p>**중요:** 가격 분석이 생성되고 수입 부대 비용당 표준 비용 차이를 결정하는 데 사용됩니다.</p> |
| 항해 비용 | 발송물의 모든 상품에 대한 항해 비용을 보고 편집합니다. |
| 다시 계산 | 항해 비용이 업데이트, 추가 또는 제거된 후 예상 상륙 비용을 업데이트합니다. |
| 잠금 | 더 이상 변경할 수 없도록 비용 견적 레코드를 잠급니다. |

## <a name="item-cost-price-update"></a>항목 원가 업데이트

**항목 비용 가격 업데이트** 정기 작업은 작업을 실행할 때 설정한 필터와 일치하는 모든 비용 견적을 업데이트합니다. 효과는 단일 견적에 대해 작업 창에서 **표준 비용 업데이트** 를 선택한 효과와 유사합니다. 그러나 이 경우 업데이트는 일치하는 모든 견적에 적용됩니다.

정기 작업을 실행하려면 다음 단계를 따르세요.

1. **상륙 비용 \> 정기 작업 \> 항목 원가 업데이트** 로 이동합니다.
1. **견적에서 비용 업데이트** 대화 상자에서 업데이트 범위를 제한하는 데 필요한 다음 필드를 설정합니다.

    - **버전** – 지정된 원가 계산 버전을 사용하는 추정만 업데이트합니다.
    - **사이트** – 지정된 사이트를 사용하는 추정만 업데이트합니다.
    - **비용 템플릿** – 지정된 템플릿을 사용하는 추정만 업데이트합니다.
    - **도착 항구** – 지정된 "도착" 항구를 사용하는 추정만 업데이트합니다.
    - **예상 날짜** – 지정된 날짜가 있는 추정값만 업데이트합니다.

1. **포함할 레코드** 및 **백그라운드에서 실행** 빠른 탭의 옵션을 정기적인 작업에 대해 평소와 같이 설정합니다.
1. **확인** 을 선택하여 작업을 실행합니다.

> [!NOTE]
> 이 정기 작업은 다음 정보를 사용할 수 있는 경우에만 성공적으로 실행됩니다.
>
> - 각 관련 제품에는 **총 깊이**, **총 너비** 및 **총 높이** 가 정의되어 있어야 합니다.
> - 각 관련 공급업체에는 **출발 항구** 가 정의되어 있어야 합니다.
