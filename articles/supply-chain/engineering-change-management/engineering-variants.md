---
title: 엔지니어링 제품에 대한 변형 생성
description: 이 토픽에서는 엔지니어링 제품의 변형을 생성하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7921983a965af5557f54f608418c8ec922256ba6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450010"
---
# <a name="generate-variants-for-engineering-products"></a>엔지니어링 제품에 대한 변형 생성

[!include [banner](../includes/banner.md)]

이 토픽에서는 엔지니어링 제품의 변형을 생성하는 방법에 대해 설명합니다.

## <a name="turn-variant-generation-for-engineering-products-on-or-off"></a>엔지니어링 제품에 대한 변형 생성 켜기 또는 끄기

이 토픽에 설명된 기능을 사용하려면 엔지니어링 제품 기능에 대한 *엔지니어링 변경 관리* 및 *변형 생성* 기능이 모두 시스템에 켜져 있어야 합니다. 이러한 기능을 켜거나 끄는 방법에 대한 자세한 내용은 [엔지니어링 변경 관리 개요](product-engineering-overview.md)를 참조하세요.

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>엔지니어링 제품의 하나 이상의 새 변형 생성

기존 제품에서 정보를 복사하지 않고 제품의 새로운 변형을 하나 이상 생성할 수 있습니다. 이는 동시에 여러 제품 변형을 생성해야 할 때 유용합니다.

다음 절차에서는 색상 치수를 포함하는 여러 변형을 생성하는 방법의 예를 제공합니다.

1. **출시된 제품** 페이지를 엽니다(예: **엔지니어링 변경 관리 \> 공통 \> 출시 제품** 으로 이동).
1. 작업 창에서 **제품** 탭을 열고 **새로 만들기** 그룹에서 **엔지니어링 제품** 을 선택합니다.
1. **새 제품** 대화 상자가 열립니다. **적절한 엔지니어링** 범주를 선택합니다.
1. 선택한 엔지니어링 범주에 변형 치수가 포함된 경우 지금 값을 설정할 수 있습니다. 이 예의 경우 범주에 **색상** 차원이 있는 경우 *파란색* 으로 설정할 수 있습니다.
1. 필요에 따라 다른 설정을 지정합니다. **확인** 을 선택하여 해당 제품을 생성합니다.
1. 제품 및 파란색 V-1 변형이 생성되고 이제 새 제품이 열립니다.
1. BOM(자재 명세서)을 추가하고 필요에 따라 변형으로 라우팅합니다.
1. 작업 창에서 **제품** 탭을 열고 **제품 마스터** 그룹에서 **제품 크기** 를 선택합니다.
1. **제품 크기** 페이지가 열립니다. 이 페이지에는 사용 가능한 각 차원에 대한 탭이 있습니다. 각 탭에서 각 관련 차원에 대해 지원할 각 값에 대한 행을 추가합니다. (이 예에서는 *흰색*, *노란색* 및 *녹색* 에 대해 **색상** 탭에 행을 추가할 수 있습니다.)
1. 페이지를 닫고 **출시된 제품 변형** 을 선택합니다. 생성한 첫 번째 변형(파란색 V-1)이 나타납니다.
1. 작업 창의 **제품 변형** 탭에서 **변형 제안** 을 선택합니다.
1. **변형 제안** 대화 상자에서 다음 단계 중 하나를 수행합니다.

    - 대화 상자 상단에는 사용 가능한 각 차원에 대한 섹션이 있습니다. 각 차원에 대해 변형 제안을 생성할 각 값의 확인란을 선택한 다음 도구 모음에서 **제안** 을 선택합니다. 관련 제안이 **제안된 변형** 섹션에 추가됩니다.
    - 도구 모음에서 **모두 제안** 을 선택하여 사용 가능한 모든 차원 값 조합에 대한 변형 제안을 생성합니다. 제안은 **제안된 변형** 섹션에 추가됩니다.

1. **제안된 변형** 섹션에서 생성하려는 각 변형에 대한 확인란을 선택합니다. 그런 다음 **만들기** 를 선택하여 선택한 변형을 생성하고 엔지니어링 회사에 릴리스합니다. 다음 조건이 적용됩니다.

    - 생성된 변형에는 BOM 또는 경로가 없습니다.
    - 이러한 변형의 특성은 기본적으로 엔지니어링 범주에서 설정되며 이전 변형에서 복사되지 않습니다.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>다른 제품 변형의 사본으로 변형 생성

다른 제품 변형을 기반으로 제품의 변형을 생성할 수 있습니다. BOM(자재 명세서) 및 소스 제품 변형의 경로가 새 변형으로 복사됩니다. 이는 시작 BOM을 기반으로 BOM을 생성하고 이전 변형의 변경 사항을 추적하는 데 도움이 될 수 있는 개별 제조 제품에 유용할 수 있습니다. 추적성을 유지하기 위해 시스템은 복사된 변형을 기록하여 새 복사본을 만듭니다.

다음 절차는 기존 변형의 복사본을 생성하여 색상 치수를 포함하는 새 변형을 생성하는 방법의 예를 제공합니다.

1. **출시된 제품** 페이지를 엽니다(예: **엔지니어링 변경 관리 \> 공통 \> 출시 제품** 으로 이동).
1. 작업 창에서 **제품** 탭을 열고 **새로 만들기** 그룹에서 **엔지니어링 제품** 을 선택합니다.
1. **새 제품** 대화 상자가 열립니다. **적절한 엔지니어링** 범주를 선택합니다.
1. 선택한 엔지니어링 범주에 변형 치수가 포함된 경우 지금 값을 설정할 수 있습니다. 이 예의 경우 범주에 **색상** 차원이 있는 경우 *파란색으* 로 설정할 수 있습니다.)
1. 필요에 따라 다른 설정을 지정합니다. **확인** 을 선택하여 해당 제품을 생성합니다.
1. 제품 및 파란색 V-1 변형이 생성되고 이제 새 제품이 열립니다.
1. BOM을 추가하고 필요에 따라 변형으로 라우팅합니다.
1. 필요에 따라 제품 변형에 속성을 추가합니다
1. 파란색 V-1 제품 변형을 엔지니어링 변경 주문에 추가합니다.
1. **영향** 을 *새 변형* 으로 설정합니다.
1. 새 색상 값(예: *흰색*)을 선택합니다 다음 조건이 적용됩니다. 
    - 새 변형에는 이전 변형에서 복사한 BOM 및 경로가 있습니다.
    - 새 변형에는 이전 변형에서 복사한 속성이 있습니다.
1. 변경 주문을 승인합니다.
1. 변경 주문을 진행합니다. 주문이 처리된 후 새로운 V-1 변형이 생성되어 엔지니어링 회사에 릴리스됩니다.
