---
title: 포장 및 보관을 위해 다른 치수 설정
description: 이 항목에서는 지정된 각 치수가 사용되는 프로세스(포장, 보관 또는 중첩 포장)를 지정하는 방법을 보여줍니다.
author: mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e8ce576f21f1f5ea5f3acb7d43bbe68826e6f39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449263"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>포장 및 보관을 위해 다른 치수 설정

[!include [banner](../../includes/banner.md)]

일부 품목은 여러 프로세스 각각에 대해 물리적 치수를 다르게 추적해야 할 수 있는 방식으로 포장되거나 저장됩니다. *포장 제품 치수* 기능을 사용하면 각 제품에 대해 하나 이상의 치수 유형을 설정할 수 있습니다. 각 치수 유형은 일련의 물리적 측정(무게, 너비, 깊이 및 높이)을 제공하고 이러한 물리적 측정 값이 적용되는 프로세스를 설정합니다. 이 기능이 활성화되면 시스템은 다음 유형의 치수를 지원합니다.

- *보관* - 재고 규모는 위치 용적 측정과 함께 사용되어 다양한 창고 위치에 저장할 수 있는 각 품목의 수를 결정합니다.
- *포장* - 포장 치수는 다양한 용기 유형에 맞는 각 품목의 수를 결정하기 위해 컨테이너화 및 수동 포장 프로세스 중에 사용됩니다.
- *중첩 포장* - 중첩 포장 치수는 포장 프로세스에 여러 수준이 포함될 때 사용됩니다.

*보관* 치수는 *포장 제품 치수* 기능이 활성화되어 있지 않은 경우에도 지원됩니다. Supply Chain Management의 **물리적 치수** 페이지를 사용하여 설정합니다. 이러한 치수는 포장 및 중첩 포장 치수가 지정되지 않은 모든 프로세스에서 사용됩니다.

*포장* 및 *중첩 포장* 치수는 치수는 *포장 제품 치수* 기능을 활성화할 때 추가되는 **실제 제품 치수** 페이지를 사용하여 설정됩니다.
이 항목에서는 이 기능을 사용하는 방법을 설명하는 시나리오를 제공합니다.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>포장 제품 치수 기능 켜기

이 기능을 사용하려면 먼저 시스템에서 켜져 있어야 합니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역을 사용하여 기능의 상태를 확인하고 필요한 경우 켤 수 있습니다. 거기에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈:** *창고 관리*
- **기능 이름:** *포장 제품 치수*

## <a name="example-scenario"></a>예시 시나리오

### <a name="set-up-the-scenario"></a>시나리오 설정

예제 시나리오를 실행하기 전에 이 섹션에 설명된 대로 시스템을 준비해야 합니다.

#### <a name="enable-demo-data"></a>데모 데이터 활성화

여기에 지정된 데모 레코드 및 값을 사용하여 이 시나리오를 진행하려면 표준 [데모 데이터](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)가 설치된 시스템에 있어야 합니다. 또한 시작하기 전에 *USMF* 법인을 선택해야 합니다.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>제품에 새로운 물리적 차원 추가

다음을 수행하여 제품에 대한 새 물리적 치수를 추가합니다.

1. **제품 정보 관리 \> 제품 \> 릴리스된 제품** 으로 이동합니다.
1. **품목 번호** *A0001* 로 제품을 선택합니다.
1. 작업 창에서 **재고 관리** 탭을 열고 **창고** 그룹에서 **물리적 제품 크기** 를 선택합니다.
1. **물리적 제품 크기** 페이지가 열립니다. 작업 창에서 **새로 만들기** 를 선택하여 다음 설정으로 그리드에 새 차원을 추가합니다.
    - **물리적 치수 유형** - *포장*
    - **물리적 단위** - *개*
    - **중량** - *4*
    - **중량 단위** - *kg*
    - **깊이** - *3*
    - **높이** - *4*
    - **너비** - *3*
    - **길이** - *cm*
    - **볼륨 단위** - *cm3*

**용량** 필드는 **깊이**, **높이**, **너비** 설정을 기반으로 자동 계산됩니다.

#### <a name="create-a-new-container-type"></a>새 컨테이너 유형 만들기

**창고 관리 \> 설정 \> 컨테이너 \> 컨테이너 유형** 으로 이동하고 다음 설정으로 새 레코드를 만듭니다.

- **컨테이너 유형 코드** - *짧은 상자*
- **설명** - *짧은 상자*
- **최대 순중량** - *50*
- **볼륨** - *144*
- **길이** - *6*
- **너비** - *6*
- **높이** - *4*

#### <a name="create-a-container-group"></a>컨테이너 그룹 생성

**창고 관리 \> 설정 \> 컨테이너 \> 컨테이너 그룹** 으로 이동하고 다음 설정으로 새 레코드를 만듭니다.

- **컨테이너 그룹 ID** - *짧은 상자*
- **설명** - *짧은 상자*

**세부 정보** 섹션에 새 라인을 추가합니다. **컨테이너 유형** 을 *짧은 상자* 로 설정합니다.

#### <a name="set-up-a-container-build-template"></a>컨테이너 제작 템플릿 설정

**창고 관리 \> 설정 \> 컨테이너 \> 컨테이너 제작 템플릿** 으로 이동하고 **상자** 를 선택합니다. **컨테이너 그룹 ID** 를 *짧은 상자* 로 변경합니다.

### <a name="run-the-scenario"></a>시나리오 실행

이전 섹션에서 설명한 대로 시스템을 준비했으면 다음 섹션에서 설명한 대로 시나리오를 실행할 준비가 된 것입니다.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>판매 주문 생성 및 배송 생성

이 프로세스에서 높이가 3보다 작은 치수의 경우 품목 *포장* 치수를 기반으로 배송을 생성합니다.

1. **영업 및 마케팅 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **판매 주문 만들기** 대화 상자에서 다음 값을 설정합니다.

    - **고객 계정** *US-001*
    - **창고:** *63*

1. **확인** 을 선택하여 판매 주문을 생성하고 대화 상자를 닫습니다.
1. 새 판매 주문이 열립니다. **판매 주문 라인** 빠른 탭의 그리드에 새로운 빈 라인을 포함해야 합니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *A0001*
    - **수량:** *5*

1. **판매 주문 라인** 빠른 탭에서 **재고 \> 예약** 을 선택합니다.
1. **예약** 페이지의 작업 창에서 **로트 예약** 을 선택하고 재고를 예약합니다.
1. 페이지를 닫습니다.
1. 작업 창에서 **창고** 탭을 열고 **창고로 출고** 를 선택하여 창고에 대한 작업을 생성합니다.
1. **판매 주문 라인** 빠른 탭에서 **창고 \> 배송 세부 정보** 를 선택합니다.
1. 작업 창에서 **운송** 탭을 열고 **컨테이너 보기** 를 선택합니다. 품목이 두 *짧은 상자* 컨테이너로 컨테이너화되었는지 확인합니다.

#### <a name="place-an-item-into-storage"></a>품목을 창고에 배치

1. 모바일 디바이스를 열고 창고 63에 로그인하고 **재고 \> 조정** 으로 이동합니다.
1. **Loc** = *SHORT-01* 을 입력합니다. **품목** = *A0001* 및 **수량** = *1개* 로 새 번호판을 만듭니다.
1. **확인** 을 선택합니다. "품목 A0001이 위치의 지정된 치수에 맞지 않기 때문에 위치 SHORT-01가 실패했습니다."라는 오류가 표시됩니다. 그 이유는 제품의 *보관* 유형 치수가 위치 프로필에 지정된 치수보다 큽니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]