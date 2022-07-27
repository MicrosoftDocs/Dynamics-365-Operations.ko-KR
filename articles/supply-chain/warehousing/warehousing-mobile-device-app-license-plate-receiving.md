---
title: Warehouse Management 모바일 앱을 통해 번호판 받기
description: 이 토픽에서는 차량 번호판 수신 프로세스를 사용하여 총실사를 수신하도록 지원하도록 Warehouse Management 모바일 앱을 설정하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6663188334c70035906f924c7850a0dc5002f306
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449950"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱을 통해 번호판 받기

[!include [banner](../includes/banner.md)]

이 토픽에서는 차량 번호판 수령 프로세스를 사용하여 총실사를 받을 수 있도록 Warehouse Management 모바일 앱을 설정하는 방법에 대해 설명합니다.

이 기능을 사용하여 사전 배송 안내(ASN)와 관련된 인바운드 재고 입고를 빠르게 기록할 수 있습니다. 시스템은 창고 관리 프로세스를 사용하여 이전 주문을 배송할 때 자동으로 ASN을 생성합니다. 구매 주문 프로세스의 경우 ASN을 수동으로 기록하거나 인바운드 ASN 데이터 엔터티 프로세스를 사용하여 자동으로 가져올 수 있습니다.

ASN 데이터는 팔레트(상위 번호판)에 케이스(중첩 번호판)가 포함될 수 있는 *포장 구조* 를 통해 화물 및 배송에 연결됩니다.

> [!NOTE]
> 중첩된 번호판이 있는 포장 구조를 사용할 때 재고 트랜잭션 수를 줄이기 위해 시스템은 상위 번호판에 실제 재고를 기록합니다. 포장 구조 데이터를 기반으로 상위 번호판에서 중첩된 번호판으로 실제 보유 재고의 이동을 트리거하려면 모바일 디바이스에서 *중첩된 번호판으로 포장* 작업 생성 프로세스를 기반으로 하는 메뉴 항목을 제공해야 합니다. .

## <a name="warehousing-mobile-device-app-processing"></a>보관 모바일 디바이스 앱 처리

작업자가 들어오는 번호판 ID를 스캔하면 시스템에서 번호판 수신 프로세스를 초기화합니다. 이 정보를 기반으로 번호판의 내용(ASN에서 오는 데이터)은 인바운드 도크 위치에 물리적으로 등록됩니다. 이어지는 흐름은 비즈니스 프로세스 요구 사항에 따라 달라집니다.

## <a name="work-policies"></a>작업 정책

예를 들어 *완료로 보고* 모바일 디바이스 메뉴 항목 프로세스와 마찬가지로 번호판 수신 프로세스는 정의된 설정을 기반으로 하는 여러 워크플로를 지원합니다.

### <a name="work-policies-with-work-creation"></a>작업 생성을 통한 작업 정책

작업을 생성하는 작업 정책을 사용하여 들어오는 항목을 등록할 때 시스템은 각 등록에 대해 치워진 작업 기록을 생성하고 저장합니다. *번호판 수신 및 보관* 작업을 이용하면 모바일 디바이스 메뉴 항목 하나로 등록 및 보관 작업이 한 번에 처리됩니다. *번호판 수령* 프로세스를 사용하는 경우 수령 및 보관 프로세스는 각각 고유한 모바일 디바이스 메뉴 항목이 있는 두 개의 서로 다른 창고 작업으로 처리됩니다.

### <a name="work-policies-without-work-creation"></a>작업 생성 없는 작업 정책

작업을 만들지 않고도 번호판 수신 프로세스를 이용할 수 있습니다. 작업 주문 유형이 *영수증 전송* 및/또는 *구매 주문* 인 작업 정책을 정의하고 *번호판 수령(및 보관)* 프로세스를 사용하는 경우 다음 두 가지 창고 모바일 앱 프로세스는 작업을 생성하지 않습니다. 대신, 인바운드 입고 도크의 번호판에 인바운드 재고 목록을 등록하기만 하면 됩니다.

- *번호판 수신*
- *번호판 수신 및 처리*

> [!NOTE]
> - **인벤토리 위치** 섹션에서 작업 정책에 대해 하나 이상의 위치를 정의해야 합니다. 여러 작업 정책에 대해 동일한 위치를 지정할 수 없습니다.
> - 창고 모바일 디바이스 메뉴 항목에 대한 **레이블 인쇄** 옵션은 작업 생성 없이 번호판 레이블을 인쇄하지 않습니다.

시스템에서 이 기능을 사용할 수 있게 하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 *번호판 수신 향상* 기능을 켜야 합니다.

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>번호판을 추적하지 않는 위치에서 재고 받기

**번호판 추적 사용** 이 켜져 있지 않은 경우에도 위치 프로필에 할당된 창고 위치를 사용할 수 있습니다. 따라서 재고 입고 시 작업 생성 없이 해당 위치에 직접 현재고를 등록할 수 있습니다.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>창고의 각 입고 위치에 대한 모바일 디바이스 메뉴 항목 추가

*번호판 수령 개선* 기능을 사용하면 창고 모바일 앱에 위치별 번호판 수령(및 보관) 메뉴 항목을 추가하여 창고의 어느 위치에서나 수령할 수 있습니다. 이전에는 시스템이 각 창고에 대해 정의된 기본 위치에서만 입고를 지원했습니다. 그러나 이 기능이 켜져 있으면 번호판 수신(및 보관)을 위한 모바일 디바이스 메뉴 항목이 이제 **기본 데이터 사용** 옵션을 제공하여 각 메뉴 항목에 대한 사용자 지정 "대상" 위치를 선택할 수 있습니다. (이 옵션은 일부 다른 유형의 메뉴 항목에 대해 이미 사용 가능했습니다.)

시스템에서 이 기능을 사용할 수 있게 하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 *번호판 수신 향상* 기능을 켜야 합니다.

## <a name="show-or-skip-the-receiving-summary-page"></a>수신 요약 페이지 표시 또는 건너뛰기

*모바일 디바이스에 수신 요약 페이지를 표시할지 여부 제어* 기능을 사용하여 번호판 수신 프로세스의 일부로 추가적인 상세한 Warehouse Management 모바일 앱 흐름을 활용할 수 있습니다.

이 기능이 켜져 있으면 번호판 수령 또는 번호판 수령 및 보관을 위한 모바일 디바이스 메뉴 항목이 **디스플레이 수신 요약 페이지** 설정을 제공합니다. 이 설정에는 다음과 같은 옵션이 있습니다.

- **자세한 요약 표시** – 번호판을 받는 동안 작업자는 전체 ASN 정보를 보여주는 추가 페이지를 보게 됩니다.
- **요약 건너뛰기** – 작업자는 전체 ASN 정보를 볼 수 없습니다. 창고 작업자도 처리 코드를 설정하거나 수신 프로세스 중에 예외를 추가할 수 없습니다.

이 기능을 사용하려면 *모바일 디바이스에 수신 요약 페이지 표시 여부 제어* 기능이 시스템에 켜져 있어야 합니다. Supply Chain Management 버전 10.0.21부터 이 기능은 기본적으로 켜져 있습니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *모바일 디바이스에 수신 요약 페이지 표시 여부 제어* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>운송장으로 배송된 번호판을 목적지 창고 이외의 창고에서 사용하는 것을 방지

ASN에 이미 존재하는 번호판 ID가 포함되어 있고 번호판 등록이 발생하는 창고 위치가 아닌 창고 위치에 실제 보유 데이터가 있는 경우 번호판 수신 프로세스를 사용할 수 없습니다.

운송 창고가 번호판을 추적하지 않는(따라서 번호판당 실제 현재고도 추적하지 않는) 이전 주문 시나리오의 경우 운송 주문에서 *배송된 번호판을 대상 창고가 아닌 다른 창고에서 사용하지 못하도록 방지* 기능을 사용하여 운송 중인 번호판의 실제 현재 업데이트를 방지할 수 있습니다. 이 기능을 사용 가능하게 하려면 시스템에 대해 *운송 주문 배송 번호판을 대상 창고 이외의 다른 창고에서 사용하지 못하도록 방지* 기능을 켜야 합니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 검색하여 이 기능을 켜거나 끌 수 있습니다.

이 기능을 사용할 수 있을 때 기능을 관리하려면 다음 단계를 따르세요.

1. **Warehouse Management \> 설정 \> Warehouse Management 매개 변수** 로 이동합니다.
1. **일반** 탭의 **번호판** 빠른 탭에서 **운송 창고 번호판 정책** 필드를 다음 값 중 하나로 설정합니다.

    - **추적되지 않은 번호판 재사용 허용** - 시스템은 *이전 주문 배송된 번호판을 대상 창고 이외의 다른 창고에서 사용하지 못하도록 방지* 기능을 사용할 수 없는 경우 작동하는 것과 동일한 방식으로 작동합니다. 이 값은 기능을 처음 활성화할 때의 기본 설정입니다.
    - **추적되지 않은 번호판 재사용 방지** – 운송 주문이 접수될 때까지 배송된 번호판과 관련된 현재고 업데이트만 목적지 창고에서 허용됩니다.

## <a name="more-information"></a>추가 정보

모바일 디바이스 메뉴 항목에 대한 자세한 내용은 [창고 작업을 위한 모바일 디바이스 설정](configure-mobile-devices-warehouse.md)을 참조하세요.

*완료로 보고* 생산 시나리오에 대한 자세한 내용은 [창고 작업 정책 개요](warehouse-work-policies.md)를 참조하세요.

인바운드 로드 관리에 대한 자세한 내용은 [구매 주문에 대한 인바운드 로드의 창고 처리](inbound-load-handling.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]