---
title: 재고 가시성 구성
description: 이 토픽에서는 재고 가시성을 구성하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8ba478fef424a6c4688191ed4e5375bbce52de0c
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449812"
---
# <a name="configure-inventory-visibility"></a>재고 가시성 구성

[!include [banner](../includes/banner.md)]


이 토픽에서는 Power Apps의 재고 가시성 앱을 사용하여 재고 가시성을 구성하는 방법을 설명합니다.

## <a name="introduction"></a><a name="introduction"></a>소개

재고 가시성 작업을 시작하기 전에 이 항목에 설명된 대로 다음 구성을 완료해야 합니다.

- [데이터 원본 구성](#data-source-configuration)
- [파티션 구성](#partition-configuration)
- [제품 인덱스 계층 구성](#index-configuration)
- [예약 구성(선택 사항)](#reservation-configuration)
- [기본 구성 샘플](#default-configuration-sample)

## <a name="prerequisites"></a>전제 조건

시작하기 전에 [재고 가시성 설치 및 설정](inventory-visibility-setup.md)에 설명된 대로 재고 가시성 추가 기능을 설치 및 설정합니다.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Power Apps 기능 관리에서 재고 가시성 기능 사용

재고 가시성 추가 기능은 Power Apps 설치에 몇 가지 새로운 기능을 추가합니다. 기본적으로 이러한 기능은 꺼져 있습니다. 이를 사용하려면 Power Apps에서 **구성** 페이지를 연 후 **기능 관리** 탭에서 다음 기능을 켜십시오.

- *OnHandReservation*
- *OnHandMostSpecificBackgroundService*

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>서비스 엔드포인트 찾기

올바른 재고 가시성 서비스 엔드포인트를 모르는 경우 Power Apps에서 **구성** 페이지를 연 다음 오른쪽 위 모서리에서 **서비스 엔드포인트 표시** 를 선택합니다. 페이지에 올바른 서비스 엔드포인트가 표시됩니다.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>재고 가시성 앱의 구성 페이지

Power Apps에서 [재고 가시성 앱](inventory-visibility-power-platform.md)의 **구성** 페이지는 현재 구성 및 소프트 예약 구성을 설정하는 데 도움이 됩니다. 추가 기능이 설치된 후 기본 구성에는 Microsoft Dynamics 365 Supply Chain Management(`fno` 데이터 원본)의 값이 포함됩니다. 기본 설정을 검토할 수 있습니다. 게다가 비즈니스 요구 사항 및 외부 시스템의 재고 게시 요구 사항을 기반으로 구성을 수정하여 여러 시스템에서 재고 변경 사항을 게시, 구성 및 쿼리할 수 있는 방법을 표준화할 수 있습니다. 이 토픽의 나머지 섹션에서는 **구성** 페이지의 각 부분을 사용하는 방법에 대해 설명합니다.

구성이 완료되면 앱에서 **구성 업데이트** 를 선택해야 합니다.

## <a name="data-source-configuration"></a>데이터 원본 구성

각 데이터 원본은 데이터의 출처 시스템을 나타냅니다. 데이터 원본 이름의 예에는 `fno`(Dynamics 365 금융 및 운영 앱"을 나타냄) 및 `pos`("POS(Point of Sale)"를 나타냄)이 포함됩니다. 기본적으로 Supply Chain Management는 재고 가시성에서 기본 데이터 원본(`fno`)로 설정되어 있습니다.

> [!NOTE]
> `fno` 데이터 원본은 Supply Chain Management를 위해 예약되어 있습니다. 재고 가시성 추가 기능이 Supply Chain Management 환경과 통합된 경우 데이터 원본에서 `fno`와 관련된 구성을 삭제하지 않는 것이 좋습니다.

데이터 원본을 추가하려면 다음 단계를 따르세요.

1. Power Apps 환경에 로그인하고 **재고 가시성** 을 엽니다.
1. **구성** 페이지를 엽니다.
1. **데이터 원본** 탭에서 **새 데이터 원본** 를 선택하여 데이터 원본을 추가합니다.

> [!NOTE]
> 데이터 원본을 추가할 때 재고 가시성 서비스에 대한 구성을 업데이트하기 전에 데이터 원본 이름, 물리적 측정값 및 차원 매핑을 확인합니다. **구성 업데이트** 를 선택한 후에는 이러한 설정을 수정할 수 없습니다.

데이터 원본 구성에는 다음 부분이 포함됩니다.

- 차원(차원 매핑)
- 물리적 측정값
- 계산된 측정값

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>차원(차원 매핑)

차원 구성의 목적은 차원 조합을 기반으로 이벤트 및 쿼리 게시를 위한 다중 시스템 통합을 표준화하는 것입니다. 재고 가시성은 데이터 원본의 차원에서 매핑할 수 있는 기본 차원 목록을 제공합니다. 33개의 차원을 매핑에 사용할 수 있습니다.

- 기본적으로 Supply Chain Management를 데이터 원본 중 하나로 사용하는 경우 13개의 차원이 Supply Chain Management 표준 차원에 매핑됩니다. 12개의 다른 차원(`inventDimension1` ~ `inventDimension12`)은 Supply Chain Management의 사용자 지정 차원에 매핑됩니다. 나머지 8개 차원은 외부 데이터 원본에 매핑할 수 있는 확장 차원입니다.
- Supply Chain Management를 데이터 원본 중 하나로 사용하지 않는 경우 차원을 자유롭게 매핑할 수 있습니다. 다음 테이블은 사용 가능한 차원의 전체 목록을 보여줍니다.

> [!NOTE]
> 차원이 기본 차원 목록에 없고 외부 데이터 원본을 사용하는 경우 매핑을 수행하기 위해 `ExtendedDimension1`~`ExtendedDimension8`를 사용하는 것이 좋습니다.

| 차원 유형 | 기본 차원 |
|---|---|
| 제품 | `ColorId` |
| 제품 | `SizeId` |
| 제품 | `StyleId` |
| 제품 | `ConfigId` |
| 추적 | `BatchId` |
| 추적 | `SerialId` |
| 위치 | `LocationId` |
| 위치 | `SiteId` |
| 재고 상태 | `StatusId` |
| 창고별 | `WMSLocationId` |
| 창고별 | `WMSPalletId` |
| 창고별 | `LicensePlateId` |
| 기타 | `VersionId` |
| 재고(사용자 지정) | `InventDimension1` ~ `InventDimension12` |
| 내선 번호 | `ExtendedDimension1` ~ `ExtendedDimension8` |
| 시스템 | `Empty` |

> [!NOTE]
> 앞의 테이블에 나열된 차원 유형은 참조용일 뿐입니다. 재고 가시성에서 정의할 필요가 없습니다.
>
> 재고(사용자 지정) 차원은 Supply Chain Management용으로 예약되어 있을 수 있습니다. 이 경우 확장된 치수를 대신 사용할 수 있습니다.

외부 시스템은 RESTful API를 통해 재고 가시성에 액세스할 수 있습니다. 통합의 경우 재고 가시성을 통해 _외부 데이터 원본_ 와 _외부 차원_ 에서 _기본 차원_ 으로의 매핑을 구성할 수 있습니다. 다음은 차원 매핑 테이블의 예입니다.

| 외부 치수 | 기본 차원 |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

차원 매핑을 구성하여 외부 차원을 재고 가시성으로 직접 보낼 수 있습니다. 그러면 재고 가시성이 자동으로 외부 치수를 기본 치수로 변환합니다.

차원 매핑을 추가하려면 다음 단계를 따르세요.

1. Power Apps 환경에 로그인하고 **재고 가시성** 을 엽니다.
1. **구성** 페이지를 엽니다.
1. **데이터 원본** 탭의 **차원 매핑** 섹션에서 **추가** 를 선택하여 차원 매핑을 추가합니다.
    ![차원 매핑 추가](media/inventory-visibility-dimension-mapping.png "차원 매핑 추가")

1. **차원 이름** 필드에서 소스 차원을 지정합니다.
1. **기본 치수로 변환** 필드에서 매핑하려는 재고 가시성의 차원을 선택합니다.
1. **저장** 을 선택합니다.

예를 들어 데이터 원본에 제품 색상 측정기준이 포함된 경우 이를 `ColorId` 기본 측정기준에 매핑하여 `exterchannel` 데이터 원본에 `ProductColor` 맞춤 측정기준을 추가할 수 있습니다. 그런 다음 `ColorId` 기본 차원에 매핑됩니다.

### <a name="physical-measures"></a>물리적 측정값

데이터 원본이 재고 가시성에 재고 변경 사항을 게시하면 *물리적 측정* 을 사용하여 해당 변경 사항을 게시합니다. 물리적 측정은 수량을 수정하고 재고 상태를 반영합니다. 요구 사항에 따라 고유한 물리적 측정을 정의할 수 있습니다. 쿼리는 물리적 측정을 기반으로 할 수 있습니다.

재고 가시성은 Supply Chain Management(`fno` 데이터 원본)에 연결된 기본 물리적 측정값 목록을 제공합니다. 이러한 기본 물리적 측정은 Supply Chain Management(**재고 관리 \> 조회 및 보고 \> 현재고 목록**)의 **현재고 목록** 페이지에 있는 재고 트랜잭션 상태에서 가져옵니다. 다음 테이블은 물리적 조치의 예를 제공합니다.

| 물리적 측정값 이름 | 설명 |
|---|---|
| `NotSpecified` | 지정하지 않음 |
| `Arrived` | 입고 |
| `AvailOrdered` | 주문 가능 |
| `AvailPhysical` | 사용 가능한 실제 |
| `Deducted` | 공제 |
| `OnOrder` | OnOrder |
| `Ordered` | 주문함 |
| `PhysicalInvent` | 실제 재고 |
| `Picked` | 피킹됨 |
| `PostedQty` | 기장된 수량 |
| `QuotationIssue` | 견적 발행 |
| `QuotationReceipt` | 견적 수령 |
| `Received` | 수령함 |
| `Registered` | 등록됨 |
| `ReservOrdered` | 예약 주문됨 |
| `ReservPhysical` | 실제 예약됨 |

데이터 원본이 Supply Chain Management인 경우 기본 물리적 측정을 다시 만들 필요가 없습니다. 그러나 외부 데이터 원본의 경우 다음 단계에 따라 새 물리적 측정값을 생성할 수 있습니다.

1. Power Apps 환경에 로그인하고 **재고 가시성** 을 엽니다.
1. **구성** 페이지를 엽니다.
1. **데이터 원본** 탭의 **물리적 측정값** 섹션에서 **추가** 를 선택하고 소스 측정값 이름을 지정한 다음 변경 사항을 저장합니다.

### <a name="calculated-measures"></a>계산된 측정값

재고 가시성을 사용하여 재고 물리적 측정과 *사용자 지정 계산 측정* 모두에 대해 쿼리할 수 있습니다. 계산된 측정값은 물리적 측정값의 조합으로 구성된 사용자 지정 계산 공식을 제공합니다. 이 기능을 사용하면 사용자 정의된 측정에서 추가할 물리적 측정 세트 및/또는 뺄 물리적 측정 세트를 정의할 수 있습니다.

구성을 통해 총 집계된 출력 수량을 얻기 위해 더하거나 빼는 수정자 세트를 정의할 수 있습니다.

사용자 지정 계산된 측정값을 설정하려면 다음 단계를 따르세요.

1. Power Apps 환경에 로그인하고 **재고 가시성** 을 엽니다.
1. **구성** 페이지를 엽니다.
1. **계산된 측정값** 탭에서 **새 계산된 측정값** 을 선택하여 계산된 측정값을 추가합니다. 이후 다음 테이블에 설명된 대로 필드를 설정합니다.

    | 필드 | 값 |
    |---|---|
    | 새롭게 계산된 측정값 이름 | 계산된 측정값의 이름을 입력합니다. |
    | 데이터 원본 | 쿼리 시스템은 데이터 원본입니다. |
    | 수정자 데이터 원본 | 수정자의 데이터 원본을 입력합니다. |
    | 한정자 | 수정자 이름을 입력합니다. |
    | 수정자 유형 | 수정자 유형(*더하기* 또는 *빼기*)을 선택합니다. |

예를 들어 다음과 같은 쿼리 결과가 있을 수 있습니다.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

그런 다음 다음 테이블과 같이 `MyCustomAvailableforReservation`이라는 계산된 측정값을 구성합니다. 이 계산된 측정값은 소비 시스템에서 소비됩니다.

| 소비 시스템 | 계산된 측정값 | 데이터 원본 | 물리적 측정값 | 계산 유형 |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

이 계산 공식을 사용하면 새 쿼리 결과에 사용자 지정 측정이 포함됩니다.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

사용자 지정 측정의 계산 설정을 기반으로 하는 `MyCustomAvailableforReservation` 출력은 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220입니다.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>파티션 구성

현재 파티션 구성은 데이터 배포 방식을 나타내는 두 가지 기본 차원(`SiteId` 및 `LocationId`)으로 구성됩니다. 동일한 파티션에서 작업하면 더 낮은 비용으로 더 높은 성능을 제공할 수 있습니다. 다음 테이블은 재고 가시성 추가 기능이 제공하는 기본 파티션 구성을 보여줍니다.

| 기본 차원 | 계층 구조 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

솔루션에는 기본적으로 이 파티션 구성이 포함됩니다. 따라서 *직접 정의할 필요가 없습니다.*

> [!IMPORTANT]
> 기본 파티션 구성을 사용자 지정하지 마세요. 삭제하거나 변경하면 예상치 못한 오류가 발생할 수 있습니다.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>제품 인덱스 계층 구성

대부분의 경우 현재 재고 쿼리는 가장 높은 "전체" 수준에만 있는 것은 아닙니다. 대신 재고 차원을 기반으로 집계된 결과를 볼 수도 있습니다.

재고 가시성은 _인덱스_ 를 설정할 수 있도록 하여 유연성을 제공합니다. 이러한 인덱스는 차원 또는 차원 조합을 기반으로 합니다. 인덱스는 다음 테이블에 정의된 대로 *집합 번호*, *차원* 및 *계층 구조* 로 구성됩니다.

| 이름 | 설명 |
|---|---|
| 집합 번호 | 동일한 집합(색인)에 속한 차원은 함께 그룹화되고 동일한 집합 번호가 할당됩니다. |
| 차원 | 쿼리 결과가 집계되는 기본 차원입니다. |
| 계층 구조 | 계층은 쿼리할 수 있는 지원되는 차원 조합을 정의하는 데 사용됩니다. 예를 들어 계층 시퀀스가 `(ColorId, SizeId, StyleId)`인 차원 집합을 설정합니다. 이 경우 시스템은 4차원 조합에 대한 쿼리를 지원합니다. 첫 번째 조합은 비어 있고 두 번째는 `(ColorId)`, 세 번째는 `(ColorId, SizeId)`, 네 번째는 `(ColorId, SizeId, StyleId)`입니다. 다른 조합은 지원되지 않습니다. 자세한 내용은 다음 예를 참조하세요. |

제품 계층 인덱스를 설정하려면 다음 단계를 따르세요.

1. Power Apps 환경에 로그인하고 **재고 가시성** 을 엽니다.
1. **구성** 페이지를 엽니다.
1. **제품 계층 인덱스** 탭의 **차원 매핑** 섹션에서 **추가** 를 선택하여 차원 매핑을 추가합니다.
1. 기본적으로 인덱스 목록이 제공됩니다. 기존 인덱스를 수정하려면 해당 인덱스 섹션에서 **편집** 또는 **추가** 를 선택합니다. 새 인덱스 집합을 만들려면 **새 인덱스 집합** 을 선택합니다. 모든 인덱스 집합의 각 행에 대해 **차원** 필드의 기본 차원 목록에서 선택합니다. 다음 필드의 값이 자동으로 생성됩니다.

    - **세트 번호** – 동일한 그룹(인덱스)에 속한 차원을 함께 그룹화하여 동일한 세트 번호를 할당합니다.
    - **계층** – 계층은 차원 그룹(색인)에서 쿼리할 수 있는 지원되는 차원 조합을 정의하는 데 사용됩니다. 예를 들어 *스타일*, *색상* 및 *크기* 의 계층 순서가 있는 차원 그룹을 설정하는 경우 시스템은 세 가지 쿼리 그룹의 결과를 지원합니다. 첫 번째 그룹은 스타일 전용입니다. 두 번째 그룹은 스타일과 색상의 조합입니다. 그리고 세 번째 그룹은 스타일, 색상 및 크기의 조합입니다. 다른 조합은 지원되지 않습니다.

### <a name="example"></a>예

이 섹션에서는 계층 구조가 작동하는 방식을 보여주는 예를 제공합니다.

다음 테이블은 이 예에 사용 가능한 재고 목록을 제공합니다.

| 항목 | ColorId | SizeId | StyleId | 수량 |
|---|---|---|---|---|
| 티셔츠 | 검정 | 스몰 | 와이드 | 1 |
| 티셔츠 | 검정 | 스몰 | 일반 | 2 |
| 티셔츠 | 검정 | 라지 | 와이드 | 3 |
| 티셔츠 | 검정 | 라지 | 일반 | 4 |
| 티셔츠 | 빨강 | 스몰 | 와이드 | 5 |
| 티셔츠 | 빨강 | 스몰 | 일반 | 6 |
| 티셔츠 | 빨강 | 라지 | 일반 | 7 |

다음 테이블은 인덱스 계층이 설정되는 방법을 보여줍니다.

| 집합 번호 | 차원 | 계층 구조 |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

인덱스를 사용하면 다음과 같은 방법으로 현재고를 조회할 수 있습니다.

- `()`– 모두 그룹화

    - 티셔츠, 28

- `(ColorId)` – `ColorId`로 그룹화

    - 티셔츠, 검정, 10
    - 티셔츠, 빨강, 18

- `(ColorId, SizeId)`– `ColorId` 및 `SizeId`의 조합으로 그룹화

    - 티셔츠, 검정, 스몰, 3
    - 티셔츠, 검정, 라지, 7
    - 티셔츠, 빨강, 스몰, 11
    - 티셔츠, 빨강, 라지, 7

- `(ColorId, SizeId, StyleId)`– `ColorId`, `SizeId` 및 `StyleId`의 조합으로 그룹화

    - 티셔츠, 검정, 스몰, 와이드, 1
    - 티셔츠, 검정, 스몰, 와이드, 일반, 2
    - 티셔츠, 검정, 라지, 와이드, 3
    - 티셔츠, 검정, 라지, 일반, 4
    - 티셔츠, 빨강, 스몰, 와이드, 5
    - 티셔츠, 빨강, 스몰, 일반, 6
    - 티셔츠, 빨강, 라지, 일반, 7

> [!NOTE]
> 파티션 구성에 정의된 기본 차원은 인덱스 구성에 정의하면 안 됩니다.
> 
> 모든 차원 조합으로 집계된 재고만 쿼리해야 하는 경우 기본 차원 `Empty`이 포함된 단일 인덱스를 설정할 수 있습니다.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>예약 구성(선택 사항)

소프트 예약 기능을 사용하려면 예약 설정이 필요합니다. 구성은 두 가지 기본 부분으로 구성됩니다.

- 소프트 예약 매핑
- 소프트 예약 계층

### <a name="soft-reservation-mapping"></a>소프트 예약 매핑

예약할 때 현재 보유 재고가 예약 가능한지 여부를 알고 싶을 수 있습니다. 유효성 검사는 물리적 측정값 조합의 계산 공식을 나타내는 계산된 측정값에 연결됩니다.

물리적 측정값에서 계산된 측정값으로의 매핑을 설정하면 재고 가시성 서비스가 물리적 측정값을 기반으로 예약 가용성을 자동으로 검증할 수 있습니다.

이 매핑을 설정하기 전에 물리적 측정값, 계산된 측정값 및 해당 데이터 원본을 Power Apps **구성** 페이지의 **데이터 원본** 및 **계산된 측정값** 탭에서 정의해야 합니다(이 항목의 앞부분에서 설명한 대로).

소프트 예약 매핑을 정의하려면 다음 단계를 따르십시오.

1. 소프트 예약 측정의 역할을 하는 물리적 측정을 정의합니다(예:`SoftReservOrdered`).
1. **구성** 페이지의 **계산된 측정값** 탭에서 실제 측정값에 매핑하려는 AFR 계산 공식이 포함된 *예약 가능*(AFR) 계산된 측정값을 정의합니다. 예를 들어 `AvailableToReserve`(예약 가능)을 설정하여 이전에 정의된 `SoftReservOrdered` 물리적 측정값에 매핑되도록 할 수 있습니다. 이런 식으로 `SoftReservOrdered` 재고 상태를 가진 수량을 예약할 수 있는지 확인할 수 있습니다. 다음 테이블은 AFR 계산 공식을 보여줍니다.

    | 계산 유형 | 데이터 원본 | 물리적 측정값 |
    |---|---|---|
    | 더하기 | `fno` | `AvailPhysical` |
    | 더하기 | `pos` | `Inbound` |
    | 빼기 | `pos` | `Outbound` |
    | 빼기 | `iv` | `SoftReservOrdered` |

    예약 측정의 기반이 되는 물리적 측정이 포함되도록 계산된 측정을 설정하는 것이 좋습니다. 이러한 방식으로 계산된 측정 수량은 예약 측정 수량의 영향을 받습니다. 따라서 이 예에서 `iv` 데이터 원본의 `AvailableToReserve` 계산된 측정값은 구성요소로 `iv`의 `SoftReservOrdered` 물리적 측정값을 포함해야 합니다.

1. **구성** 페이지를 엽니다.
1. **소프트 예약 매핑** 탭에서 실제 측정값에서 계산된 측정값으로의 매핑을 설정합니다. 이전 예의 경우 다음 설정을 사용하여 `AvailableToReserve`을 이전에 정의된 `SoftReservOrdered` 물리적 측정에 매핑할 수 있습니다.

    | 계산된 측정값 데이터 원본 | 물리적 측정값 | 예약 데이터 원본에 사용 가능 | 예약 측정값 이름에 사용 가능 |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > **소프트 예약 매핑** 탭을 편집할 수 없는 경우 **기능 관리** 탭에서 *OnHandReservation* 기능을 켜야 할 수 있습니다.

이제 `SoftReservOrdered`에서 예약을 수행하면 재고 가시성이 자동으로 `AvailableToReserve` 및 관련 계산 공식을 찾아 예약 검증을 수행합니다.

예를 들어 재고 가시성에 다음과 같은 현재고가 있습니다.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

이 경우 다음 계산이 적용됩니다.

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

따라서 `iv.SoftReservOrdered`에서 예약을 하려고 하고 수량이 `AvailableToReserve`(10) 이하이면 예약이 가능합니다.

> [!NOTE]
> 예약 API를 호출할 때 요청 본문에 부울 `ifCheckAvailForReserv` 매개 변수를 지정하여 예약 유효성 검사를 제어할 수 있습니다. 값 `True`는 유효성 검사가 필요함을 의미하고 `False` 값은 유효성 검사가 필요하지 않음을 의미합니다. 기본값은 `True`입니다.

### <a name="soft-reservation-hierarchy"></a>소프트 예약 계층

예약 계층은 예약 시 지정해야 하는 차원의 순서를 설명합니다. 제품 인덱스 계층 구조가 현재 쿼리에 대해 작동하는 것과 동일한 방식으로 작동합니다.

예약 계층은 제품 인덱스 계층과 독립적입니다. 이러한 독립성을 통해 사용자가 차원을 세부적으로 분류하여 보다 정확한 예약을 위한 요구 사항을 지정할 수 있는 범주 관리를 구현할 수 있습니다. 소프트 예약 계층 구조는 파티션 구성을 구성하기 때문에 `SiteId` 및 `LocationId`를 구성 요소로 포함해야 합니다. 예약 시 제품에 대한 파티션을 지정해야 합니다.

다음은 소프트 예약 계층의 예입니다.

| 기본 차원 | 계층 구조 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

이 예에서는 다음 차원 시퀀스에서 예약을 수행할 수 있습니다. 예약 시 상품에 대한 파티션을 지정해야 합니다. 따라서 사용할 수 있는 기본 계층은 `(SiteId, LocationId)`입니다.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

유효한 차원 시퀀스는 차원별로 예약 계층 구조를 엄격하게 따라야 합니다. 예를 들어 계층 시퀀스 `(SiteId, LocationId, SizeId)`은 `ColorId`가 없기 때문에 유효하지 않습니다.

## <a name="complete-and-update-the-configuration"></a>구성 완료 및 업데이트

구성을 완료한 후 재고 가시성에 대한 모든 변경 사항을 커밋해야 합니다. 변경 사항을 커밋하려면 Power Apps의 **구성** 페이지 오른쪽 상단에서 **구성 업데이트** 를 선택합니다.

**구성 업데이트** 를 처음 선택하면 시스템에서 자격 증명을 요청합니다.

- **클라이언트 ID** – 재고 가시성을 위해 만든 Azure 애플리케이션 ID입니다.
- **테넌트 ID** – Azure 테넌트 ID입니다.
- **클라이언트 암호** – 재고 가시성을 위해 만든 Azure 애플리케이션 암호입니다.

로그인하면 재고 가시성 서비스에서 구성이 업데이트됩니다.

> [!NOTE]
> 재고 가시성 서비스에 대한 구성을 업데이트하기 전에 데이터 원본 이름, 물리적 측정값 및 차원 매핑을 확인합니다. **구성 업데이트** 를 선택한 후에는 이러한 설정을 수정할 수 없습니다.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>기본 구성 샘플

초기화 단계에서 재고 가시성은 기본 구성을 설정하며 여기에 자세히 설명되어 있습니다. 필요에 따라 이 빈도를 변경할 수 있습니다.

### <a name="data-source-configuration"></a>데이터 원본 구성

#### <a name="configuration-of-the-iv-data-source"></a>iv 데이터 원본 구성

이 섹션에서는 `iv` 데이터 원본을 구성하는 방법을 설명합니다.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>iv 데이터 원본에 대해 구성된 물리적 측정

`iv` 데이터 원본에 대해 다음과 같은 물리적 측정이 구성됩니다.

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>계산된 측정값 OrderedTotal

계산된 `OrderedTotal` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `Ordered` |
| 더하기 | `fno` | `Arrived` |
| 더하기 | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>OnHand 계산된 측정값

계산된 `OnHand` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `PhysicalInvent` |
| 더하기 | `iom` | `OnHand` |
| 더하기 | `erp` | `Unrestricted` |
| 더하기 | `erp` | `QualityInspection` |
| 더하기 | `pos` | `PosInbound` |
| 빼기 | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>ReservedTotal 계산된 측정값

계산된 `ReservedTotal` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `ReservPhysical` |
| 더하기 | `fno` | `ReservOrdered` |
| 더하기 | `iv` | `SoftReservPhysical` |
| 더하기 | `iv` | `SoftReservOrdered` |
| 더하기 | `iv` | `ReservPhysical` |
| 더하기 | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>SoftReserved 계산된 측정값

계산된 `SoftReserved` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `iv` | `SoftReservPhysical` |
| 더하기 | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>HardReserved 계산된 측정값

계산된 `HardReserved` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `ReservPhysical` |
| 더하기 | `fno` | `ReservOrdered` |
| 더하기 | `iv` | `ReservPhysical` |
| 더하기 | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>OpenOrder 계산된 측정값

계산된 `OpenOrder` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `OnOrder` |
| 더하기 | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>OnHandAvailable 계산된 측정값

계산된 `OnHandAvailable` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `PhysicalInvent` |
| 더하기 | `iom` | `OnHand` |
| 더하기 | `erp` | `Unrestricted` |
| 더하기 | `erp` | `QualityInspection` |
| 더하기 | `pos` | `PosInbound` |
| 빼기 | `fno` | `ReservPhysical` |
| 빼기 | `iv` | `SoftReservPhysical` |
| 빼기 | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>AvailableToReserve 계산된 측정값

계산된 `AvailableToReserve` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `PhysicalInvent` |
| 더하기 | `iom` | `OnHand` |
| 더하기 | `erp` | `Unrestricted` |
| 더하기 | `erp` | `QualityInspection` |
| 더하기 | `pos` | `PosInbound` |
| 더하기 | `fno` | `Ordered` |
| 더하기 | `fno` | `Arrived` |
| 더하기 | `iv` | `Ordered` |
| 빼기 | `fno` | `ReservPhysical` |
| 빼기 | `fno` | `ReservOrdered` |
| 빼기 | `iv` | `SoftReservPhysical` |
| 빼기 | `iv` | `SoftReservOrdered` |
| 빼기 | `iv` | `ReservPhysical` |
| 빼기 | `iv` | `ReservOrdered` |
| 빼기 | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>InventorySupply 계산된 측정값

계산된 `InventorySupply` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `Ordered` |
| 더하기 | `fno` | `Arrived` |
| 더하기 | `iv` | `Ordered` |
| 더하기 | `fno` | `PhysicalInvent` |
| 더하기 | `iom` | `OnHand` |
| 더하기 | `erp` | `Unrestricted` |
| 더하기 | `erp` | `QualityInspection` |
| 더하기 | `pos` | `PosInbound` |
| 빼기 | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>InventoryDemand 계산된 측정값

계산된 `InventoryDemand` 측정값은 다음 테이블과 같이 `iv` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `OnOrder` |
| 더하기 | `iom` | `OnOrder` |
| 더하기 | `iv` | `SoftReservPhysical` |
| 더하기 | `iv` | `SoftReservOrdered` |
| 더하기 | `fno` | `ReservPhysical` |
| 더하기 | `fno` | `ReservOrdered` |
| 더하기 | `iv` | `ReservPhysical` |
| 더하기 | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>fno 데이터 원본 구성

이 섹션에서는 `fno` 데이터 원본을 구성하는 방법을 설명합니다.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>fno 데이터 원본에 대한 차원 매핑

다음 테이블에 나열된 차원 매핑은 `fno` 데이터 원본에 대해 구성됩니다.

| 외부 치수 | 기본 차원 |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>fno 데이터 원본에 대해 구성된 물리적 측정

`fno` 데이터 원본에 대해 다음과 같은 물리적 측정이 구성됩니다.

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>pos 데이터 원본 구성

이 섹션에서는 `pos` 데이터 원본을 구성하는 방법을 설명합니다.

##### <a name="physical-measures-for-the-pos-data-source"></a>pos 데이터 원본에 대해 구성된 물리적 측정

`pos` 데이터 원본에 대해 다음과 같은 물리적 측정이 구성됩니다.

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>AvailQuantity 계산된 측정값

계산된 `AvailQuantity` 측정값은 다음 테이블과 같이 `pos` 데이터 원본에 대해 구성됩니다.

| 계산 유형 | 데이터 원본 | 물리적 측정값 |
|---|---|---|
| 더하기 | `fno` | `AvailPhysical` |
| 더하기 | `pos` | `PosInbound` |
| 빼기 | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>iom 데이터 원본 구성

`iom`(지능형 주문 관리) 데이터 원본에 대해 다음과 같은 물리적 측정이 구성됩니다.

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>erp 데이터 원본 구성

`erp`(엔터프라이즈 리소스 계획) 데이터 원본에 대해 다음과 같은 물리적 측정이 구성됩니다.

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>파티션 구성

다음 테이블은 기본 파티션 구성을 보여줍니다.

| 기본 차원 | 계층 구조 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>인덱스 구성

다음 테이블은 기본 인덱스 구성을 보여줍니다.

| 집합 번호 | 차원 | 계층 구조 |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>예약 구성

이 섹션에서는 기본 예약 구성에 대해 설명합니다.

#### <a name="reservation-mapping"></a>예약 매핑

다음 테이블은 기본 예약 매핑을 보여줍니다.

| 계산된 측정값 데이터 원본 | 물리적 측정값 | 예약 데이터 원본에 사용 가능 | 예약 측정값 이름에 사용 가능 |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>예약 계층

다음 테이블은 기본 예약 계층을 보여줍니다.

| 기본 차원 | 계층 구조 |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
