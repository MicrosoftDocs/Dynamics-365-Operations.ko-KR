---
title: 제품 크기
description: 색상, 구성, 크기, 스타일 및 버전의 5가지 제품 치수가 있습니다. 크기 그룹의 제품 치수를 결합하고 크기 그룹을 제품 마스터에 할당합니다. 제품 치수의 조합에 따라 제품 변형이 정의되는 방식이 결정됩니다.
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 46079daafc744421abcbdf0a3539428f2a39f13c
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449596"
---
# <a name="product-dimensions"></a>제품 크기

[!include [banner](../includes/banner.md)]

색상, 구성, 크기, 스타일 및 버전의 5가지 제품 치수가 있습니다. 크기 그룹의 제품 치수를 결합하고 크기 그룹을 제품 마스터에 할당합니다. 제품 치수의 조합에 따라 제품 변형이 정의되는 방식이 결정됩니다.

제품 치수는 제품 변형을 식별하는 데 사용되는 특성입니다. 제품 치수의 조합을 사용하여 제품 변형을 정의할 수 있습니다. 제품 변형을 생성하려면 제품 마스터에 대해 하나 이상의 제품 치수를 정의해야 합니다.

## <a name="product-variants"></a>제품 변형

제품 변형은 항목이라고도 합니다. 항목은 서비스와 동일하지 않은 유형 제품입니다. 서비스 유형으로 제품 마스터를 정의하는 것도 가능합니다. 서비스 유형을 사용하여 서비스를 포함하는 제품 변형을 지정할 수 있습니다. 예를 들어 컨설팅 작업에는 제품 마스터를 지정하고 선임 컨설턴트와 주니어 컨설턴트가 수행하는 작업에는 제품 변형을 지정할 수 있습니다.

## <a name="product-dimensions"></a>제품 크기

제품 치수 값을 기반으로 제품 변형을 생성할 수 있습니다.

크기, 색상 및 스타일 치수에 대한 제품 치수 값은 다음 위치에서 생성할 수 있습니다.

- **크기** 페이지(**제품 정보 관리 \> 설정 \> 치수 및 변형 그룹 \> 크기**)
- **색깔** 페이지(**제품 정보 관리 \> 설정 \> 치수 및 변형 그룹 \> 색깔**)
- **스타일** 페이지(**제품 정보 관리 \> 설정 \> 치수 및 변형 그룹 \> 스타일**)

구성 차원에 대한 제품 치수 값은 일반적으로 제품 구성자 또는 차원 기반 구성자를 사용하여 생성됩니다. 

제품 버전은 일반적으로 제품 수명 주기 동안 제품이 발전함에 따라 특정 버전용으로 생성됩니다. 제품 버전은 이 항목의 뒷부분에서 자세히 다룹니다.

제품 치수는 다음 위치에서 액세스할 수 있는 **제품 치수** 페이지에서도 생성 및 유지 관리할 수 있습니다.

- **제품 정보 관리 \> 제품 \> 제품 마스터** 로 이동합니다. 작업 창에서 **제품 치수** 를 선택합니다.
- **제품 정보 관리 \> 제품 \> 모든 제품 및 제품 마스터** 로 이동합니다. 제품 마스터 선택 작업 창에서 **제품 치수** 를 선택합니다.
- **제품 정보 관리 \> 출시 제품** 으로 이동합니다. 제품 마스터 선택 작업 창의 **제품** 탭에 있는 **제품 마스터** 그룹에서 **제품 크기** 를 선택합니다.

항목에 대해 생성할 수 있는 변형 수는 가능한 제품 치수 조합의 수로 제한됩니다.

> [!TIP]
> 예를 들어 주문 라인에서 제품을 사용할 때 제품 치수를 선택하여 작업하려는 제품 변형을 식별합니다.

## <a name="example"></a>예:

데님 청바지를 판매하는 회사가 있습니다. *청바지* 항목은 색상 및 크기 제품 치수를 사용합니다. 청바지는 3가지 색상 및 6가지 크기로 판매됩니다. 색상은 블루, 블랙 및 브라운이 있습니다. 사이즈는 XS, S, M, L, XL 및 XXL입니다. 세 가지 색상 모두에서 모든 크기를 사용할 수 있는 것은 아닙니다. 모든 조합을 사용할 수 있는 경우 18가지 유형의 청바지가 있습니다. 그러나 이 예에서는 다음 9개의 제품 변형 조합만 생성됩니다.

| 색 | 크기 |
|-------|------|
| 파랑  | XS   |
| 파랑  | S    |
| 파랑  | M    |
| 검정 | M    |
| 검정 | L    |
| 검정 | XL   |
| 밤색 | L    |
| 밤색 | XL   |
| 밤색 | XXL  |

## <a name="the-version-product-dimension"></a>버전 제품 크기

버전은 공급망 전체에서 제품의 여러 버전을 유지 관리하고 추적하는 데 도움이 되는 제품 크기입니다. 버전 추적은 제품 수명 주기가 지속적으로 단축되고 품질 및 신뢰성 요구 사항이 증가하며 제품 안전에 대한 관심이 증가하는 세상에서 운영되는 제조업체의 성공에 필수적입니다.

표준 제품 크기로서 버전은 기존 제품 크기(크기, 스타일, 색상 및 구성)와 유사하게 작동합니다. 따라서 제품 버전 추적 외에 다른 용도로 사용할 수 있습니다.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>버전 차원 켜기

#### <a name="before-you-turn-on-the-version-dimension"></a>버전 차원을 켜기 전에

버전 차원을 켤 때 인벤토리 차원에 사용자 지정을 추가하는 다른 솔루션을 설치한 경우 일부 기능이 손상되거나 예상대로 작동하지 않을 수 있습니다. 버전 차원이 완전히 작동하려면 인벤토리 차원에 대한 참조에 버전 차원을 포함하도록 솔루션을 업데이트해야 할 수 있습니다.

버전 차원과의 호환성에 대해 솔루션을 테스트할 때 다음 요소를 찾으십시오.

1. **기능:** 가장 중요한 것은 인벤토리 차원과 관련된 모든 사용자 정의가 버전 차원과 함께 작동할 수 있도록 평가되어야 한다는 것입니다.
1. **인벤토리 차원에 대한 참조:** 인벤토리 차원에 대한 참조(즉, 차원이 명시적으로 참조되는 위치)를 찾으십시오. `InventDimId`에 대한 참조는 기본적으로 작동해야 하지만 스타일이나 색상에 대한 참조를 찾으십시오. 예를 들어 다음 요소를 확인하세요.

    - 확장 클래스의 API 호출
    - 확장 코드의 특정 인벤토리 차원에 대한 모든 참조(이 코드는 스타일, 색상 및 크기 차원과 함께 버전 차원을 부동해야 합니다.)

1. **사용되지 않는 API 호출에 대한 참조:** 버전 차원을 도입하면서 Microsoft는 가능한 한 적은 수의 API를 구식으로 만들려고 노력했습니다. 더 이상 사용되지 않는 몇 가지 API는 **제품 크기 - 버전** 구성 키를 켤 때 경고를 발행합니다. 프로덕션 시스템에서 버전 차원을 켜기 전에 확장 솔루션에서 해당 API에 대한 호출을 수정해야 합니다. 다음은 버전별 사용되지 않는 API입니다.

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **맵:** 인벤토리 차원을 사용하는 맵이 있는 경우 버전 차원을 포함하도록 이러한 맵에 대한 해당 관계 매핑을 업데이트해야 합니다. 확장 모델 또는 테이블 확장에서 필드에 인벤토리 차원이 포함된 테이블을 찾으십시오.
1. **Microsoft Dynamics 365 Commerce기능:** 켜져 있으면 버전 차원이 Dynamics 365 Supply Chain Management의 Commerce 특정 코드 전체에 나타납니다. 그러나 버전 차원은 아직 Commerce 채널 데이터베이스나 POS(Point of Sale) 또는 전자 상거래 애플리케이션에서 지원되지 않습니다. 이러한 Commerce 전용 애플리케이션은 버전 차원별로 인벤토리를 판매/배송 또는 반품/수신하는 사용자를 지원하지 않습니다. 인벤토리 가용성 조회 기능은 Commerce 앱의 버전 차원으로 재고를 식별하지 않습니다. 이 동작은 Commerce 전체에서 구성 차원의 현재 동작과 유사합니다.

#### <a name="turn-on-the-version-dimension"></a>버전 차원 켜기

이 버전 차원을 사용하려면 먼저 시스템에서 켜져 있어야 합니다. 이 작업에는 관리자 권한이 필요합니다.

1. **시스템 관리 \> 작업 영역 \> 기능 관리** 로 이동합니다.
1. *제품 크기 버전* 이라는 기능을 켭니다. (자세한 내용은 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.)
1. 시스템을 [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)로 전환합니다.
1. **시스템 관리 \> 설정 \> 라이선스 구성** 으로 이동합니다.
1. **구성 키** 탭에서 **무역** 을 확장하고 **제품 크기 - 버전** 확인란을 선택합니다.
1. [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)를 끕니다.

### <a name="areas-where-the-version-dimension-isnt-supported"></a>버전 차원이 지원되지 않는 영역

다음 영역은 버전 차원을 지원하지 않습니다(이 영역을 계속 사용할 수 있지만 버전이 지정된 제품(버전 차원이 사용되는 제품)을 추가할 수 없음). 예를 들어 공급업체 카탈로그에 버전이 지정된 항목을 추가할 수 없습니다. 버전 차원이 있는 제품을 이러한 영역에 추가하면 주요 변경 사항이 발생하기 때문입니다.

- 비용 개체 월별 명세서
- 비용 개체 월별 캐시
- 항목별 MCR 판매 통계
- 공급업체 카탈로그
- EcoResProductDimensionGroupEntity

또한 Commerce의 주문 생성 및 주문 처리 기능(예: POS, 콜 센터 및 전자 상거래 주문)은 버전 차원을 지원하지 않습니다. Commerce 주문이 이를 지원하도록 향상될 시기에 대해서는 확인된 일정이 없습니다.

### <a name="functional-characteristics-of-the-version-dimension"></a>버전 차원의 기능적 특성

버전 차원은 다른 제품 크기처럼 작동합니다. 그러나 고유한 특성과 제품의 여러 버전을 유지 관리하고 추적하기 위한 것이기 때문에 약간 다르게 작동합니다. 다음은 몇 가지 차이점과 유사점입니다.

- **버전 그룹이 없습니다.**

    사이즈, 색상 및 스타일(색상 그룹, 사이즈 그룹 및 스타일 그룹)에 대한 그룹 개념은 존재하지만 버전 그룹 개념은 존재하지 않는다. 그룹을 사용하면 적용 가능한 값을 미리 정의할 수 있으므로 예를 들어 제품에 색상 그룹을 할당할 때 제품이 해당 색상 그룹의 모든 색상을 사용할 수 있습니다. 제품이 사용하는 버전은 제품이 생성될 때 미리 정의되지 않기 때문에 이 개념은 버전 차원에 적용되지 않습니다. 대신 제품의 수명 주기 동안 필요에 따라 버전이 생성됩니다. 일반적으로 제품의 양식, 핏, 기능이 동일하면 새 제품 대신 새 버전을 만듭니다.

- **제품 변형 제안은 현재와 같이 작동합니다.**

    제품 변형 제안은 다른 차원과 마찬가지로 모든 버전 차원 값에 대한 제안을 생성합니다. 버전이 지정된 제품을 만들고 출시하는 프로세스는 다른 차원을 사용하는 제품의 경우와 동일합니다. 버전이 지정된 제품을 생성하면 첫 번째 버전(V1)이 제품 크기로 생성되고 변형이 출시됩니다. 제품이 변경되고 새 버전이 필요하게 되면 새 버전 값(V2)이 추가되고 필요한 변형이 출시됩니다. 제품에 대해 모든 버전(V1, V2 및 V3)이 미리 생성될 것이라는 기대는 없습니다.

> [!IMPORTANT]
> 버전 차원을 켜고 사용하는 경우 인벤토리 차원을 참조하는 일부 솔루션이 예상대로 작동하지 않을 수 있습니다. 이러한 문제를 확인하고 수정하려면 영향을 받는 솔루션에 대해 ISV(독립 소프트웨어 공급업체)에 문의하세요. 자세한 내용은 [버전 차원 활성화](#enable-version-dim)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]