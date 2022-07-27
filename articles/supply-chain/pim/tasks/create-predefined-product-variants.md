---
title: 미리 정의된 제품 변형 생성
description: 이 절차에서는 제품 치수 조합을 사용하여 제품 마스터에 대한 제품 변형을 만드는 과정을 안내합니다.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6d3a4ae8efd438e01c263af1c0a1746d9484e491
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449953"
---
# <a name="predefined-product-variants"></a>미리 정의된 제품 변형

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>예시 시나리오: 사전 정의된 제품 변형 생성

이 예시 시나리오에서는 제품 치수 조합을 사용하여 제품 마스터에 대한 제품 변형을 만드는 과정을 안내합니다.

### <a name="make-demo-data-available"></a>데모 데이터 사용 가능

여기에 제안된 값을 사용하여 이 시나리오를 따르려면 데모 데이터가 설치되어 있어야 하고 *USMF* 법인을 선택해야 합니다.

### <a name="step-1-create-a-product-master"></a>1단계: 제품 마스터 만들기

제품 마스터를 만들려면 다음을 따르세요.

1. **제품 정보 관리 > 제품 > 제품 마스터** 로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **제품 번호** 필드에 이미 숫자가 표시되지 않은 경우 값을 입력합니다. 이 단계는 이 필드에 대해 번호 시퀀스가 설정되지 않은 경우에만 필요합니다.
1. **제품 이름** 필드에 이름을 입력합니다.
1. **제품 차원 그룹** 필드에서 제품 차원 그룹 *SizeCol*(크기 및 색상)을 선택합니다.
1. **확인** 을 선택하여 새 제품 마스터를 만들고 엽니다.

### <a name="step-2-add-product-dimensions"></a>2단계: 제품 치수 추가

이 예는 제품 치수를 수동으로 입력하는 방법을 보여줍니다. 사용하려는 제품 치수 값이 포함된 크기, 색상 또는 스타일 그룹을 선택할 수도 있습니다.

제품 치수를 추가하려면 다음을 따르세요.

1. 새 제품 마스터가 열려 있는 상태에서 작업 창의 **제품 치수** 를 선택합니다.
1. **사이즈** 탭을 열고 도구 모음에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 새 행에 대해 다음을 설정합니다.
    - **크기:** 크기 값을 선택합니다.
    - **이름:** 크기의 이름을 입력합니다.
1. 도구 모음에서 **새로 만들기** 를 선택하고 새로운 **크기** 와 **이름** 으로 그리드에 두 번째 크기를 추가합니다.
1. **색상** 탭을 열고 도구 모음에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 새 행에 대해 다음을 설정합니다.
    - **색상:** 색상 값을 선택합니다.
    - **이름:** 색상의 이름을 입력합니다.
1. 도구 모음에서 **새로 만들기** 를 선택하고 새로운 **색상** 과 **이름** 으로 그리드에 두 번째 색상을 추가합니다.
1. **저장** 을 선택합니다.
1. 새 제품 마스터로 돌아가려면 페이지를 닫습니다.

### <a name="step-3-generate-product-variants"></a>3단계: 제품 변형 생성

> [!NOTE]
> 이 섹션에서는 *변형 제안 페이지 개선 사항* 기능이 활성화되어 있지 않을 때 제품 변형을 생성하는 방법을 설명합니다. 해당 기능을 사용할 수 있을 때 제품 변형을 생성하는 방법에 대한 자세한 내용은 다음 섹션을 참조하세요.

제품 변형을 생성하려면 다음을 따르세요.

1. 새 제품 마스터가 열려 있는 상태에서 작업 창의 **제품 변형** 을 선택합니다.
1. 그런 다음 작업 창에서 **변형 추천** 을 선택합니다.
1. 시스템은 제품에 대해 정의한 크기와 색상의 가능한 모든 조합으로 목록을 생성합니다. 도구 모음에서 **모두 선택** 을 선택합니다.
    - 이 예에서는 가능한 모든 변형을 선택합니다. 가능한 제품 차원 조합의 하위 집합만 사용하려는 경우 필요에 따라 필수 확인란만 선택합니다.  
1. **만들기** 를 선택합니다.
1. **저장** 을 선택합니다.

## <a name="improved-variant-suggestions"></a>개선된 변형 제안

*변형 제안 페이지 개선 사항* 기능은 많은 수의 제품 차원 조합이 있는 회사의 성능 및 사용성 문제를 해결하도록 **변형 추천** 페이지를 개선합니다. 변형 제안을 생성할 제품 차원 값을 선택하는 향상된 프로세스를 통해 관련 제품 변형 세트를 더 빠르고 쉽게 식별하고 출시할 수 있습니다.

이 기능으로 다음과 같은 개선 사항이 추가되었습니다.

- **지연된 변형 제안 생성:** **변형 제안** 페이지를 처음 열 때 더 이상 제안이 표시되지 않습니다. 대신 필요한 값을 명시적으로 선택한 다음 **제안** 버튼을 눌러 조합을 생성합니다. 이것은 프로세스를 보다 가시적이고 대화식으로 만듭니다.
- **치수 값 선택:** 차원 값이 많은 경우 일반적으로 몇 가지만 포함하는 변형 제안을 생성하는 데 관심이 있습니다(예: 새로운 색상 또는 스타일 세트 도입). 개선된 디자인으로 제품 변형 제안을 생성하려는 차원 값을 선택할 수 있습니다. 이렇게 하면 제안된 변형의 관련성이 크게 증가하고 시스템 성능과 사용자 생산성이 모두 향상됩니다.

### <a name="turn-the-variant-suggestions-page-improvements-feature-on-or-off"></a>변형 제안 페이지 개선 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다. 관리자는 [기능 관리](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *변형 제안 페이지 개선* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

### <a name="work-with-the-improved-variant-suggestions"></a>개선된 변형 제안 작업

*변형 제안 페이지 개선 사항* 기능이 활성화되어 있을 때 제품 변형 제안을 생성하려면 다음을 따르세요.

1. 이전 섹션에서 설명한 대로 제품 마스터를 열거나 생성하고 필요한 제품 치수를 추가합니다.
1. 제품 마스터가 열려 있는 상태에서 작업 창의 **제품 변형** 을 선택합니다.
1. 그런 다음 작업 창에서 **변형 추천** 을 선택합니다.
1. 각 차원에 사용할 값을 선택합니다.
1. 상단 도구 모음에서 **제안** 을 선택합니다.
1. 시스템은 선택한 크기와 색상의 가능한 모든 조합으로 목록을 생성합니다. **제안된 변형** 빠른 탭에서 사용하려는 각 제품 차원 조합의 확인란을 선택하거나 도구 모음에서 **모두 선택** 을 선택하여 모두 선택합니다.  
1. **만들기** 를 선택하여 현재 제품 마스터에 변형을 추가합니다.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
