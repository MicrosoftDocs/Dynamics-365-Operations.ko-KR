---
title: 생산 자재에 대한 기본 예약 원칙 무시
description: 이 항목에서는 각 항목 모델 그룹에 대한 기본 예약 원칙을 설정하여 생산 BOM(자재 명세서) 또는 배치 주문 공식의 일부인 각 항목에 대해 서로 다른 예약 원칙을 자동으로 적용할 수 있도록 하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b12740e58b2bf8667bee8a2c51917d69771779f2
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449986"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>생산 자재에 대한 기본 예약 원칙 무시

[!include [banner](../includes/banner.md)]

*기본 생산 예약 재정의* 기능을 사용하면 각 항목 모델 그룹에 대한 기본 예약 원칙을 설정할 수 있습니다. 따라서 생산 BOM(자재 명세서) 또는 배치 주문 공식의 일부인 각 항목에 대해 서로 다른 예약 원칙이 자동으로 적용될 수 있습니다. 각 품목 모델 그룹이 주문에 대해 설정된 기본 예약 원칙을 재정의할지 여부와 대신 사용할 예약 원칙을 선택할 수 있습니다(*수동*, *견적*, *예약*, *릴리스* 또는 *시작*).

신규 생산 주문 또는 배치 주문을 생성할 때 해당 주문과 모든 BOM 라인 또는 공식 라인에 적용해야 하는 예약 원칙을 선택하라는 메시지가 표시됩니다. *기본 생산 예약 재정의* 기능이 사용되는 경우 BOM 또는 공식 라인의 일부 또는 전체가 해당 예약 원칙을 무시하고 대신 관련 품목 모델 그룹에 대해 설정된 예약 원칙을 사용할 수 있습니다.

예를 들어, 피킹 작업이 필요한 원자재 또는 재료가 있는 경우 해당 제품에 대해 생성된 BOM 또는 공식 라인에는 물리적 예약이 필요합니다. 물리적 예약은 창고 작업 생성을 위한 전제 조건이기 때문입니다. 일반적으로 예약이 자동으로 발생하도록 하려면 *견적*, *예약*, *릴리스* 또는 *시작* 예약 원칙 중 하나를 선택합니다. 반면에 피킹 작업이 필요하지 않은 재료나 성분이 있는 경우 해당 위치에서 직접 소비되기 때문에 일반적으로 *수동* 물리적 예약을 하거나 피킹 작업을 생성하지 않는 예약 원칙입니다.

## <a name="turn-the-override-default-production-reservation-feature-on-or-off"></a>기본 생산 예약 재정의 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *기본 생산 예약 재정의* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>품목 모델 그룹에 생산 예약 정책 할당

1. **Cost management \> 재고 회계 정책 설정 \> 품목 모델 그룹** 으로 이동합니다.
1. 품목 모델 그룹을 생성하거나 선택합니다.
1. **재고 정책** 빠른 탭에서 **품목 생산 예약 재정의** 확인란을 선택합니다.
1. **예약** 필드에서 선택한 모델 그룹에 속하는 품목에 대한 예약 원칙을 선택합니다. (이러한 품목에는 BOM 또는 공식 라인에 있는 품목이 포함됩니다.)

    - **수동** – 모델 그룹의 품목은 생산을 위해 물리적으로 자동으로 예약되지 않습니다. 그러나 필요에 따라 수동으로 예약할 수 있습니다.
    - **예측** – 모델 그룹의 품목은 생산 주문을 예측하는 동안 물리적으로 예약됩니다.
    - **예약** – 모델 그룹의 품목은 생산 주문을 예약하는 동안 물리적으로 예약됩니다.
    - **릴리스** – 모델 그룹의 품목은 생산 주문을 릴리스할 때 물리적으로 예약됩니다.
    - **시작** – 모델 그룹의 품목은 생산 주문을 시작할 때 물리적으로 예약됩니다.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>예: 대량/포장 시나리오에서 예약 원칙 사용

벌크 윤활제 재료는 1,000리터 믹서에서 생산됩니다. 벌크 재료가 준비되면 여러 주유소로 펌핑되어 다양한 크기의 병이 채워집니다. 채우기가 완료되면 병을 상자에 포장합니다. 그런 다음 해당 상자는 팔레트에 포장됩니다.

이 시나리오에서는 1,000리터의 벌크 자재를 만들기 위한 배치 주문이 생성됩니다. (지 주문은 일괄 처리 주문입니다.) 이 배치 주문이 완료되면 주유소의 자재 투입 위치에 완료로 보고됩니다. 그런 다음 각 병 크기를 채우고 포장하는 배치 주문이 생성됩니다. (이러한 주문은 포장 주문입니다.) 포장 주문은 벌크 재료, 빈 병, 라벨 및 기타 포장 재료로 구성된 공식이 있습니다. 벌크 재료는 믹서 탱크에서 충전 스테이션으로 직접 흐르기 때문에 이 재료를 선택하기 위해 창고 작업이 필요하지 않으며 벌크 재료는 투입 위치에서 직접 소비됩니다. 따라서 예약 원칙은 *수동* 으로 설정됩니다. 다른 재료는 피킹 작업을 통해 주유소로 스테이징됩니다. 따라서 이러한 라인에 대한 예약 원칙은 *릴리스* 로 설정됩니다. 예를 들어 포장 주문이 릴리스되면 예약이 자동으로 발생합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]