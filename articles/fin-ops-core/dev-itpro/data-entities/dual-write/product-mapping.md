---
title: 통합 제품 경험
description: 이 항목에서는 재무 및 운영 앱과 Dataverse 간의 제품 데이터 통합에 대해 설명합니다.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1b3dc1d16fc34992df0c9478b8b4d163c310b67b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460704"
---
# <a name="unified-product-experience"></a>통합 제품 경험

[!include [banner](../../includes/banner.md)]



비즈니스 에코시스템이 재무, Supply Chain Management 및 영업과 같은 Dynamics 365 응용 프로그램으로 구성된 경우 기업은 종종 이러한 응용 프로그램을 사용하여 제품 데이터를 소싱합니다. 이는 이러한 앱이 정교한 가격 개념과 정확한 재고 데이터로 보완된 강력한 제품 인프라를 제공하기 때문입니다. 제품 데이터를 소싱하기 위해 외부 PLM(제품 수명 주기 관리) 시스템을 사용하는 기업은 재무 및 운영 앱에서 다른 Dynamics 365 앱으로 제품을 채널화할 수 있습니다. 통합 제품 경험은 통합 제품 데이터 모델을 Dataverse로 가져오므로, Power Platform 사용자를 포함한 모든 애플리케이션 사용자가 재무 및 운영 앱에서 제공되는 풍부한 제품 데이터를 활용할 수 있습니다.

다음은 Sales의 제품 데이터 모델입니다.

![CE의 제품에 대한 데이터 모델입니다.](media/dual-write-product-4.jpg)

다음은 재무 및 운영 앱의 제품 데이터 모델입니다.

![재무 및 운영 제품의 데이터 모델입니다.](media/dual-write-products-5.jpg)

이 두 제품 데이터 모델은 아래 그림과 같이 Dataverse에 통합되었습니다.

![Dynamics 365 앱의 제품에 대한 데이터 모델입니다.](media/dual-write-products-6.jpg)

제품에 대한 이중 쓰기 테이블 맵은 재무 및 운영 앱에서 Dataverse로 거의 실시간으로 데이터를 단방향으로만 흐르도록 설계되었습니다. 그러나 필요한 경우 양방향으로 제품 인프라를 개방했습니다. 사용자 지정할 수 있지만 Microsoft는 이 접근 방식을 권장하지 않으므로 위험은 사용자가 감수해야 합니다.

## <a name="templates"></a>템플릿

제품 정보에는 제품 치수 또는 추적 및 보관 치수와 같은 제품 및 해당 정의와 관련된 모든 정보가 포함됩니다. 다음 표에서 볼 수 있듯이 제품 및 관련 정보를 동기화하기 위해 테이블 맵 모음이 생성됩니다.

금융 및 운영 앱 | 기타 Dynamics 365 앱 | 설명
-----------------------|--------------------------------|---
[모든 제품](mapping-reference.md#138) | msdyn_globalproducts | 모든 제품 테이블에는 출시된 제품과 출시되지 않은 제품 모두 재무 및 운영 앱에서 사용할 수 있는 모든 제품이 포함되어 있습니다.
[CDS 릴리스 고유 제품](mapping-reference.md#213) | 제품 | **제품** 테이블에는 제품을 정의하는 열이 포함됩니다. 여기에는 개별 제품(하위 유형 제품이 있는 제품) 및 제품 변형이 포함됩니다. 다음 표는 매핑을 보여줍니다.
[색상](mapping-reference.md#170) | msdyn\_productcolors
[구성](mapping-reference.md#171) | msdyn\_productconfigurations
[기본 주문 설정](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[제품 범주](mapping-reference.md#166) | msdyn_productcategories | 각 제품 범주와 해당 구조 및 특성에 대한 정보는 제품 범주 테이블에 포함되어 있습니다.
[제품 범주 할당](mapping-reference.md#167) | msdyn_productcategoryassignments | 제품을 범주에 할당하려면 제품 범주 할당 테이블을 사용할 수 있습니다.
[제품 범주 계층](mapping-reference.md#168) | msdyn_productcategoryhierarchies | 제품 계층을 사용하여 제품을 분류하거나 그룹화합니다. 범주 계층은 제품 카테고리 계층 구조 테이블을 사용하여 Dataverse에서 사용할 수 있습니다.
[제품 범주 계층 역할](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | 제품 계층은 D365 재무 및 운영의 다양한 역할에 사용할 수 있습니다. 제품 범주 역할 테이블이 사용되는 각 역할에서 사용되는 범주를 지정합니다.
[제품 기본 주문 설정 V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[제품 크기 그룹](mapping-reference.md#173) | msdyn\_productdimensiongroups | 제품 차원 그룹은 제품을 정의하는 제품 차원을 정의했습니다.
[제품 마스터 색상](mapping-reference.md#187) | msdyn_sharedproductcolors | **공유 제품 색상** 표는 특정 제품 마스터가 가질 수 있는 색상을 나타냅니다. 이 개념은 Dataverse로 마이그레이션되어 데이터를 일관성 있게 유지합니다.
[제품 마스터 구성](mapping-reference.md#188) | msdyn_sharedproductconfigurations | **공유 제품 구성** 표는 특정 제품 마스터가 가질 수 있는 구성을 나타냅니다. 이 개념은 Dataverse로 마이그레이션되어 데이터를 일관성 있게 유지합니다.
[제품 마스터 크기](mapping-reference.md#190) | msdyn_sharedproductsizes | **공유 제품 크기** 표는 특정 제품 마스터가 가질 수 있는 크기를 나타냅니다. 이 개념은 Dataverse로 마이그레이션되어 데이터를 일관성 있게 유지합니다.
[제품 마스터 스타일](mapping-reference.md#191) | msdyn_sharedproductstyles | **공유 제품 스타일** 표는 특정 제품 마스터가 가질 수 있는 스타일을 나타냅니다. 이 개념은 Dataverse로 마이그레이션되어 데이터를 일관성 있게 유지합니다.
[제품 번호 식별 바코드](mapping-reference.md#164) | msdyn\_productbarcodes | 제품 바코드는 제품을 고유하게 식별하는 데 사용됩니다.
[제품별 단위 변환](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[출시된 제품 V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | **msdyn\_sharedproductdetails** 표에는 제품을 정의하고 제품의 재무 및 관리 정보가 포함된 재무 및 운영 앱의 열이 포함되어 있습니다.
[사이즈](mapping-reference.md#174) | msdyn\_productsizes
[재고 규모 그룹](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | 제품 스토리지 차원 그룹은 창고에서 제품 배치를 정의하는 데 사용되는 방법을 나타냅니다.
[스타일](mapping-reference.md#178) | msdyn\_productsytles
[추적 규모 그룹](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | 제품 추적 차원 그룹은 인벤토리에서 제품을 추적하는 데 사용되는 방법을 나타냅니다.
[단위](mapping-reference.md#219) | uoms
[단위 변환](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>제품 통합

이 모델에서 제품은 Dataverse의 두 테이블 조합으로 표현됩니다. **제품** 및 **msdyn\_sharedproductdetails**. 첫 번째 테이블에는 제품에 대한 정의(제품의 고유 식별자, 제품 이름 및 설명)가 포함되어 있는 반면, 두 번째 테이블에는 제품 수준에 저장된 열이 포함되어 있습니다. 이 두 테이블의 조합은 SKU(stockkeeping unit)의 개념에 따라 제품을 정의하는 데 사용됩니다. 출시된 각 제품의 정보는 언급된 표(제품 및 공유 제품 세부 정보)에 있습니다. 모든 제품(출시 및 미출시)을 추적하려면 **글로벌 제품** 테이블이 사용됩니다.

제품이 SKU로 표시되기 때문에 고유한 제품, 제품 마스터 및 제품 변형의 개념을 다음과 같은 방법으로 Dataverse에 캡처할 수 있습니다.

- **하위 유형 제품이 있는 제품** 은 자체적으로 정의된 제품입니다. 치수를 정의할 필요가 없습니다. 예를 들어 특정 책이 있습니다. 이러한 제품의 경우 **제품** 테이블에 하나의 행이 생성되고 **msdyn\_sharedproductdetails** 테이블에 하나의 행이 생성됩니다. 제품군 행이 생성되지 않습니다.
- **제품 마스터** 는 비즈니스 프로세스의 동작을 결정하는 정의와 규칙을 보유하는 일반 제품으로 사용됩니다. 이러한 정의를 기반으로 제품 변형으로 알려진 고유한 제품을 생성할 수 있습니다. 예를 들어, T-셔츠는 제품 마스터이고 색상 및 크기를 치수로 가질 수 있습니다. 작은 파란색 티셔츠 또는 중간 크기의 녹색 티셔츠와 같이 이러한 치수의 다양한 조합을 가진 변형이 출시될 수 있습니다. 통합에서 제품 테이블에 변형당 하나의 행이 생성됩니다. 이 행에는 다양한 측정기준과 같은 변형별 정보가 포함되어 있습니다. 제품에 대한 일반 정보는 **msdyn\_sharedproductdetails** 테이블에 저장됩니다. (이 일반 정보는 제품 마스터에 보관됩니다.) 제품 마스터 정보는 릴리스된 제품 마스터가 생성되는 즉시(그러나 변형이 릴리스되기 전) Dataverse에 동기화됩니다.
- **고유 제품** 은 모든 제품 하위 유형 제품 및 모든 제품 변형을 나타냅니다.

![제품에 대한 데이터 모델입니다.](media/dual-write-product.png)

이중 쓰기 기능을 활성화하면 Finance 및 Operations의 제품이 **초안** 상태의 다른 Dynamics 365 제품과 동기화됩니다. Customer Engagement 앱에서 사용된 것과 동일한 통화로 첫 번째 가격 목록에 추가되고 가격 목록 이름에 알파벳순 정렬을 사용합니다. 즉, 재무 및 운영 앱에서 제품이 출시되는 법적 테이블의 통화와 일치하는 Dynamics 365 앱의 첫 번째 가격 목록에 추가됩니다. 지정된 통화에 대한 가격 목록이 없는 경우 가격 목록이 자동으로 생성되고 제품이 여기에 할당됩니다.

기본 가격 목록을 단위에 연결하는 이중 쓰기 플러그인의 현재 구현은 금융 및 운영 앱과 연결된 통화를 조회하고 가격 목록 이름에서 알파벳순 정렬을 사용하여 고객 참여 앱에서 첫 번째 가격 목록을 찾습니다. 해당 통화에 대한 가격 목록이 여러 개 있는 경우 특정 통화에 대한 기본 가격 목록을 설정하려면 가격 목록 이름을 동일한 통화에 대한 다른 가격 목록보다 사전순으로 더 빠른 이름으로 업데이트해야 합니다. 지정된 통화에 대한 가격 목록이 없으면 새 가격 목록이 생성됩니다.

기본적으로 금융 및 운영 앱의 제품은 **초단** 상태의 다른 Dynamics 365 앱과 동기화됩니다. 판매 주문 견적에서 직접 사용할 수 있도록 **활성** 상태인 제품을 동기화하려면 다음 설정을 선택해야 합니다. **시스템 > 관리 > 시스템 관리 > 시스템 설정 > 판매** 탭으로 이동하고 **활성 상태의 제품 생성 = 예** 를 선택합니다.

제품이 동기화되면 금융 및 운영 앱에서 **판매 단위** 필드가 Sales의 필수 필드이므로 값을 입력해야 합니다.

Dynamics 365 Sales에서 제품군 생성은 제품의 이중 쓰기 동기화에서 지원되지 않습니다.

제품 동기화는 재무 및 운영 앱에서 Dataverse로 발생합니다. 이것은 제품 테이블 열의 값이 Dataverse에서 변경될 수 있음을 의미하지만 동기화가 트리거되면(재무 및 운영 앱에서 제품 열이 수정되는 경우) Dataverse에서 이 값을 덮어씁니다.

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[CDS 릴리스 고유 제품](mapping-reference.md#213) | 제품 |
[출시된 제품 V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[모든 제품](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>제품 크기

제품 치수는 제품 변형을 식별하는 특성입니다. 4가지 제품 차원(색상, 크기, 스타일 및 구성)도 Dataverse에 매핑되어 제품 변형을 정의합니다. 다음 그림은 제품 크기 색상의 데이터 모델을 보여줍니다. 크기, 스타일 및 구성에 동일한 모델이 적용됩니다.

![제품 크기의 데이터 모델.](media/dual-write-product-two.png)

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[색상](mapping-reference.md#170) | msdyn\_productcolors
[사이즈](mapping-reference.md#174) | msdyn\_productsizes
[스타일](mapping-reference.md#178) | msdyn\_productsytles
[구성](mapping-reference.md#171) | msdyn\_productconfigurations

제품에 다른 제품 치수가 있는 경우(예: 제품 마스터에 제품 치수로 사이즈 및 색상이 있는 경우) 각 고유 제품(즉, 각 제품 변형)은 해당 제품 치수의 조합으로 정의됩니다. 예를 들어 제품 번호 B0001은 초소형 검은색 티셔츠이고 제품 번호 B0002는 작은 검은색 티셔츠입니다. 이 경우 기존 제품 치수 조합이 정의됩니다. 예를 들어, 앞의 예에서 티셔츠는 초소형 및 검정, 소형 및 검정, 중형 및 검정, 또는 대형 및 검정일 수 있지만 특대 및 검정은 될 수 없습니다. 즉, 제품 마스터가 취할 수 있는 제품 차원이 지정되고 이 값을 기반으로 변형이 출시될 수 있습니다.

제품 마스터가 취할 수 있는 제품 차원을 추적하기 위해 다음 테이블이 생성되고 각 제품 차원에 대해 Dataverse에 매핑됩니다. 자세한 내용은 [제품 정보 개요](../../../../supply-chain/pim/product-information.md)를 참조하세요.

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[제품 마스터 색상](mapping-reference.md#187) | msdyn_sharedproductcolors |
[제품 마스터 구성](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[제품 마스터 크기](mapping-reference.md#190) | msdyn_sharedproductsizes |
[제품 마스터 스타일](mapping-reference.md#191) | msdyn_sharedproductstyles |
[제품 번호 식별 바코드](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>기본 주문 설정 및 제품별 기본 주문 설정

기본 주문 설정은 항목이 소싱되거나 저장될 사이트 및 창고, 거래 또는 재고 관리에 사용될 최소, 최대, 다중 및 표준 수량, 리드 타임, 중지 플래그 및 주문 약속 방법을 정의합니다. 이 정보는 기본 주문 설정 및 제품별 기본 주문 설정 엔터티를 사용하여 Dataverse에서 볼 수 있습니다. [기본 주문 설정 토픽](../../../../supply-chain/production-control/default-order-settings.md)에서 기능에 대한 자세한 내용을 볼 수 있습니다.

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[기본 주문 설정](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[제품 기본 주문 설정 V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>측정 단위 및 측정 단위 변환

측정 단위 및 해당 변환은 Dataverse에서 사용할 수 있으며 다이어그램에 표시된 데이터 모델을 따릅니다.

![측정 단위에 대한 데이터 모델입니다.](media/dual-write-product-three.png)

측정 단위 개념은 재무 및 운영 앱과 기타 Dynamics 365 앱 간에 통합됩니다. 재무 및 운영 앱의 각 단위 클래스에 대해 단위 클래스에 속한 단위가 포함된 Dynamics 365 앱에서 단위 그룹이 생성됩니다. 모든 장치 그룹에 대해 기본 기본 장치도 생성됩니다.

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[제품별 단위 변환](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[단위](mapping-reference.md#219) | uoms
[단위 변환](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>재무 및 운영과 Dataverse 간의 단위 데이터 일치의 초기 동기화

### <a name="initial-synchronization-of-units"></a>장치의 초기 동기화

이중 쓰기가 활성화되면 금융 및 운영 앱의 단위가 다른 Dynamics 365 앱과 동기화됩니다. Dataverse의 재무 및 운영 앱에서 동기화된 단위 그룹에는 "외부적으로 유지 관리됨"을 나타내는 플래그 세트가 있어야 합니다.

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>재무 및 운영 및 기타 Dynamics 365 앱의 단위 및 단위 클래스/그룹 데이터 일치

먼저 단위의 통합 키는 msdyn_symbol이라는 점에 유의해야 합니다. 따라서 이 값은 Dataverse 또는 기타 Dynamics 365 앱에서 고유해야 합니다. 다른 Dynamics 365 앱에서는 단위의 고유성을 정의하는 것이 "단위 그룹 ID" 및 "이름" 쌍이기 때문에 재무 및 운영 앱 및 Dataverse 간에 단위 데이터를 일치시키기 위한 다양한 시나리오를 고려해야 합니다.

금융 및 운영 앱과 기타 Dynamics 365 앱에서 일치하는 단위/중첩의 경우:

+ **단위는 재무 및 운영 앱의 연결된 단위 클래스에 해당하는 다른 Dynamics 365 앱의 단위 그룹에 속합니다**. 이 경우 다른 Dynamics 365 앱의 msdyn_symbol 열은 재무 및 운영 앱의 단위 기호로 채워야 합니다. 따라서 데이터가 일치할 때 단위 그룹은 다른 Dynamics 365 앱에서 "외부적으로 유지 관리됨"으로 설정됩니다.
+ **단위는 Finance 및 Operations 앱의 연결된 단위 클래스에 해당하지 않는 다른 Dynamics 365 앱의 단위 그룹에 속합니다(다른 Dynamics 365 앱의 단위 클래스에 대한 Finance 및 Operations 앱의 기존 단위 클래스 없음).** 이 경우 msdyn_symbol은 임의의 문자열로 채워져야 합니다. 이 값은 기타 Dynamics 365 앱에서 고유해야 합니다.

기타 Dynamics 365 앱에 존재하지 않는 금융 및 운영의 단위 및 단위 클래스의 경우:

재무 및 운영 앱의 이중 쓰기 단위 그룹의 일부로 해당 단위가 생성되고 다른 Dynamics 365 앱 및 Dataverse과 동기화되며 단위 그룹은 "외부적으로 유지 관리됨"으로 설정됩니다. 추가 부트스트랩 노력이 필요하지 않습니다.

금융 및 운영 앱에 존재하지 않는 기타 Dynamics 365 앱의 단위의 경우:

모든 단위에 대해 msdyn_symbol 열을 채워야 합니다. 단위는 해당 단위 클래스(있는 경우)의 재무 및 운영 앱에서 항상 생성할 수 있습니다. 단위 클래스가 존재하지 않는 경우 먼저 다른 Dynamics 365 앱 단위 그룹과 일치하는 단위 클래스를 만들어야 합니다(열거형을 확장하는 경우 확장을 통하지 않고 재무 및 운영 앱에서 단위 클래스를 생성할 수 없음). 그런 다음 단위를 만들 수 있습니다. 금융 및 운영 앱의 단위 기호는 해당 단위에 대해 다른 Dynamics 365 앱에 이전에 지정된 msdyn_symbol이어야 합니다.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>제품 정책: 차원, 추적 및 저장소 그룹

제품 정책은 인벤토리에서 제품 및 해당 특성을 정의하는 데 사용되는 정책 집합입니다. 제품 차원 그룹, 제품 추적 차원 그룹 및 스토리지 차원 그룹은 제품 정책으로 찾을 수 있습니다.

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[제품 크기 그룹](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[재고 규모 그룹](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[추적 규모 그룹](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>프로젝트 계층

금융 및 운영 앱 | Customer Engagement 앱 |
---|---
[제품 범주 할당](mapping-reference.md#167) | msdyn_productcategoryassignments |
[제품 범주 계층](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[제품 범주 계층 역할](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>제품 통합 키

Dynamics 365 for Finance and Operations 및 Dataverse의 제품 간에 제품을 고유하게 식별하기 위해 제품 통합 키가 사용됩니다.
제품의 경우 **(productnumber)** 가 Dataverse에서 제품을 식별하는 고유 키입니다. 다음을 연결하여 구성됩니다:**(company, msdyn_productnumber)**. **회사** 는 재무 및 운영의 법인을 나타내며 **msdyn_productnumber** 는 금융 및 운영의 특정 제품에 대한 제품 번호를 나타냅니다.

다른 Dynamics 365 앱 사용자의 경우 제품은 UI에서 **msdyn_productnumber** 로 식별됩니다(열의 레이블은 **제품 번호** 임). 제품 양식에는 회사와 msydn_productnumber가 모두 표시됩니다. 단, 상품의 고유 키인 (productnumber) 컬럼은 표시되지 않습니다.

Dataverse에서 앱을 빌드하는 경우 **productnumber**(고유 제품 ID)를 통합 키로 사용하는 데 주의해야 합니다. **msdyn_productnumber** 는 고유하지 않으므로 사용하지 마세요.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>제품의 초기 동기화 및 Dataverse에서 금융 및 운영으로 데이터 마이그레이션

### <a name="initial-synchronization-of-products"></a>제품의 초기 동기화

이중 쓰기가 활성화되면 금융 및 운영 앱의 제품이 Dataverse 및 Customer Engagement 앱과 동기화됩니다. 이중 쓰기가 출시되기 전에 Dataverse 및 다른 Dynamics 365 앱에서 만들어진 제품은 업데이트되지 않거나 재무 및 운영 앱의 제품 데이터와 일치하지 않습니다.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>재무 및 운영 및 기타 Dynamics 365 앱의 제품 데이터 일치

동일한 제품이 재무 및 운영 및 Dataverse와 다른 Dynamics 365 앱에서 유지(중복/매칭)되는 경우 이중 쓰기를 활성화하면 재무 및 운영의 제품 동기화가 수행되고 중복 행이 같은 제품에 대해 Dataverse에 표시됩니다.
이전 상황을 피하기 위해 다른 Dynamics 365 앱에 재무 및 운영과 겹치거나 일치하는 제품이 있는 경우 이중 쓰기를 활성화하는 관리자는 제품 동기화가 발생하기 전에 **회사**(예: "USMF") 및 **msdyn_productnumber**(예: "1234:Black:S")를 부스트트랩해야 합니다. 즉, Dataverse의 제품에서 이 두 열은 제품이 일치해야 하는 재무 및 운영의 해당 회사와 제품 번호로 입력되어야 합니다.

그런 다음 동기화가 활성화되고 수행되면 재무 및 운영의 제품이 Dataverse 및 다른 Dynamics 365 앱의 일치하는 제품과 동기화됩니다. 이는 개별 제품과 제품 변형 모두에 적용됩니다.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Dynamics 365 앱에서 재무 및 운영으로 제품 데이터 마이그레이션

다른 Dynamics 365 앱에 재무 및 운영에 없는 제품이 있는 경우 관리자는 먼저 **EcoReleasedProductCreationV2Entity** 를 재무 및 운영 부문에서 해당 제품을 가져오는 데 사용할 수 있습니다. 둘째, 위에서 설명한 대로 금융 및 운영 및 기타 Dynamics 365 앱의 제품 데이터를 일치시킵니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
