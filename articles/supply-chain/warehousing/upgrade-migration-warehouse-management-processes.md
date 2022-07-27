---
title: Microsoft Dynamics AX 2012에서 창고 관리를 Supply Chain Management로 업그레이드
description: 이 토픽에서는 제품 및 창고 관리 마이그레이션 옵션에 대한 개요를 제공합니다.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ac8c0d8781e5146186fbf71ce619f90ca3556ccefefe7e974efded7e0eb86dd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447259"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Microsoft Dynamics AX 2012에서 창고 관리를 Supply Chain Management로 업그레이드 


[!include [banner](../includes/banner.md)]

이 토픽에서는 WMSII 모듈을 실행하는 Microsoft Dynamics AX 2012 R3에서 Supply Chain Management로 업그레이드하는 프로세스의 개요를 제공합니다.

Supply Chain Management는 Microsoft Dynamics AX 2012부터 레거시 **WMSII** 모듈을 더 이상 지원하지 않습니다. 대신 **창고 관리** 모듈을 사용할 수 있습니다. WMSII 모듈에서 재무 인벤토리에 대해 위치 및 팔레트 ID 인벤토리 차원을 선택할 수 있지만 팔레트 ID 인벤토리 차원은 Supply Chain Management의 재무 인벤토리에 사용할 수 없습니다.

업그레이드하는 동안 팔레트 ID 인벤토리 차원을 사용하는 재고 규모 그룹과 연결된 모든 제품이 식별되고 차단된 것으로 표시되며 업그레이드를 위해 처리되지 않습니다.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>AX 2012 R3 WMSII 사용 시 Supply Chain Management로 업그레이드
업그레이드 후 **항목에 대한 저장소 차원 그룹 변경** 양식의 옵션 집합을 사용하여 업그레이드 중에 차단된 제품의 차단을 해제한 다음 해당 제품에 대한 트랜잭션을 처리할 수 있습니다.

### <a name="enabling-items-in-supply-chain-management"></a>Supply Chain Management에서 항목 활성화 
Supply Chain Management에서 품목 추적이 창고 관리 프로세스의 일부이기 때문에 이 변경이 필요합니다. 이러한 프로세스의 경우 모든 창고 및 해당 위치는 위치 프로필과 연관되어야 합니다. 창고 관리 프로세스를 사용하려면 다음을 구성해야 합니다.
-   창고 관리 프로세스를 사용하려면 기존 창고를 활성화해야 합니다. 
-   기존 출시 제품은 창고 관리 프로세스를 사용하는 재고 규모 그룹과 연결되어야 합니다. 

소스 스토리지 차원 그룹이 팔레트 ID 재고 차원을 사용하는 경우 팔레트 ID 재고 차원을 사용한 기존 보유 재고의 위치는 **번호판 추적 사용** 매개 변수가 선택된 위치 프로필과 연관되어야 합니다. 기존 창고에서 창고 관리 프로세스를 사용할 수 없는 경우 기존 현재고의 재고 차원 그룹을 사이트, 창고 및 위치 재고 차원만 처리하는 그룹으로 변경할 수 있습니다. 

> [!NOTE] 
>  미결 재고 트랜잭션이 있는 경우에도 항목에 대한 재고 차원 그룹을 변경할 수 있습니다.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>팔레트 ID로 인해 차단된 제품 찾기
업그레이드 중에 차단되어 처리할 수 없는 출시된 제품 목록을 보려면 **인벤토리 관리** &gt; **설정** &gt; **인벤토리** &gt; **인벤토리 업데이트를 위해 차단된 항목** 을 클릭합니다.

## <a name="change-storage-dimension-group-for-blocked-products"></a>차단된 제품에 대한 재고 차원 그룹 변경 
 
창고 관리 프로세스의 일부로 사용하려면 항목이 위치 재고 차원이 활성 상태이고 **창고 관리 프로세스 사용** 매개 변수가 선택되어 있는 재고 차원 그룹과 연관되어야 합니다. 이 설정을 선택하면 사이트, 창고, 재고 상태, 위치 및 번호판 재고 차원이 활성화됩니다.

업그레이드 중에 차단된 제품의 차단을 해제하려면 제품에 대한 새 재고 규모 그룹을 선택해야 합니다. 열려 있는 인벤토리 트랜잭션이 있는 경우에도 재고 규모 그룹을 변경할 수 있습니다. 업그레이드 중에 차단된 항목을 사용하려면 두 가지 옵션이 있습니다.

-   항목의 재고 규모 그룹을 사이트, 창고 및 위치 인벤토리 차원만 사용하는 재고 규모 그룹으로 변경합니다. 이 변경으로 인해 팔레트 ID 인벤토리 차원은 더 이상 사용되지 않습니다.
-   항목의 저장소 차원 그룹을 창고 관리 프로세스를 사용하는 저장소 차원 그룹으로 변경합니다. 이 변경으로 인해 번호판 인벤토리 차원이 사용됩니다.

## <a name="configure-warehouse-management-processes"></a>창고 관리 프로세스 구성
**창고 관리** 모듈에서 릴리스된 제품을 사용하기 전에 제품은 **창고 관리 프로세스 사용** 매개 변수가 선택된 스토리지 차원 그룹을 사용해야 합니다.

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>창고에서 창고 관리 프로세스를 사용할 수 있도록 합니다.

1.  하나 이상의 새 위치 프로필을 만듭니다.
2.  **창고 관리** &gt; **설정** &gt; **창고 관리 프로세스 활성화** &gt; **창고 설정 활성화** 를 클릭합니다.
3.  **창고 설정 활성화** 페이지에서 활성화해야 하는 창고를 추가합니다. 페이지에서 직접 또는 Microsoft Office 통합을 사용하여 이 단계를 완료할 수 있습니다.
4.  모든 위치에 위치 프로필을 할당합니다. 이 단계는 페이지에서 직접 Microsoft Office 통합을 사용하여 쉽게 완료할 수 있습니다. 데이터를 내보내고 가져오거나 [데이터 관리](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)에서 데이터 엔터티 처리를 사용할 수 있습니다.
5.  변경 사항을 확인합니다. 유효성 검사 프로세스의 일부로 데이터 무결성에 대한 다양한 유효성 검사가 발생합니다. 대규모 업그레이드 프로세스의 일부로 발생하는 문제는 소스 구현에서 조정해야 할 수 있습니다. 이 경우 추가 데이터 업그레이드가 필요합니다.
6.  변경을 처리합니다.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>창고 관리 프로세스를 사용하도록 항목에 대한 저장소 차원 그룹 변경

1.  새 **재고 상태** 값을 작성하고 **창고 관리 매개 변수** 설정에서 **기본 재고 상태 ID** 값으로 지정합니다.
2.  **창고 관리 프로세스 사용** 매개 변수가 선택된 새 스토리지 차원 그룹을 작성합니다.
3.  **예약 계층** 페이지에서 항목의 스토리지 및 추적 차원 그룹에 따라 새 예약 계층을 정의합니다.
4.  항목의 인벤토리 단위에 사용되는 것과 동일한 단위를 적어도 포함하는 단위 시퀀스 그룹을 하나 이상 만듭니다.
5.  **창고 관리** &gt; **설정** &gt; **창고 관리 프로세스 사용** &gt; **항목에 대한 스토리지 차원 그룹 변경** 을 클릭합니다.
6.  **항목에 대한 저장소 차원 그룹 변경** 페이지에서 품목 번호, 저장소 차원 그룹 및 단위 시퀀스 그룹을 추가합니다. 이 단계는 Microsoft Office 통합을 사용하거나 [데이터 관리](../../fin-ops-core/dev-itpro/data-entities/data-entities.md)의 데이터 엔터티 프로세스를 사용하여 페이지에서 직접 완료할 수 있습니다.
7.  변경 사항을 확인합니다. 유효성 검사 프로세스의 일부로 데이터 무결성에 대한 다양한 유효성 검사가 발생합니다. 대규모 업그레이드 프로세스의 일부로 발생하는 문제는 소스 구현에서 조정해야 할 수 있습니다. 이 경우 추가 데이터 업그레이드가 필요합니다.
8.  변경을 처리합니다. 모든 인벤토리 차원을 업데이트하는 데 시간이 걸릴 수 있습니다. 배치 작업 태스크를 사용하여 진행 상황을 모니터링할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]