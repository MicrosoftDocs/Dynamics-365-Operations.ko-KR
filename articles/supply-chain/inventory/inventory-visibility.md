---
title: 인벤토리 가시성 추가 기능 개요
description: 이 토픽에서는 인벤토리 가시성이 무엇인지 설명하고 기능에 대해 설명합니다.
author: yufeihuang
ms.date: 10/26/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8871d10dac9103f17780989bc547b6c20ba79b76
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449749"
---
# <a name="inventory-visibility-add-in-overview"></a>인벤토리 가시성 추가 기능 개요

[!include [banner](../includes/banner.md)]

인벤토리 가시성 추가 기능(*인벤토리 가시성* 이라고도 함)은 실시간 재고 추적을 가능하게 하는 확장성이 뛰어난 독립적인 마이크로서비스입니다. 따라서 인벤토리에 대한 전역 보기를 제공합니다.

외부 시스템은 RESTful API를 통해 서비스에 액세스합니다. 그런 식으로 그들은 주어진 차원 집합에 대한 현재 정보를 쿼리하거나 다른 사용자 지정 데이터 원본에서 재고를 변경할 수 있습니다.

Microsoft Dataverse를 기반으로 하는 마이크로서비스인 인벤토리 가시성은 확장성을 제공합니다. Power Apps를 사용하여 앱을 빌드할 수 있습니다. 또한 Power BI을 적용하여 비즈니스 요구 사항을 충족하는 사용자 지정 기능을 제공할 수 있습니다.

표준화된 재고 차원에 대한 구성 옵션을 설정하고 트랜잭션 유형을 설정하여 인벤토리 가시성을 여러 타사 시스템과 통합할 수 있습니다. 인벤토리 가시성은 구성 가능한 계산 수량을 통해 맞춤형 확장성을 지원합니다.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management와의 인벤토리 가시성 통합

통합 솔루션은 Dynamics 365 Supply Chain Management에서 재고 데이터를 가져오고 재고 변경 사항을 지속적으로 추적합니다. 자세한 내용은 [인벤토리 가시성 설치 및 설정](inventory-visibility-setup.md) 및 [인벤토리 가시성 구성](inventory-visibility-configuration.md)을 참조하세요.

## <a name="get-a-global-view-of-inventory"></a>인벤토리의 전역 보기 가져오기

통합 솔루션을 통해 고유한 데이터 소스를 정의하고 인벤토리 데이터를 중앙 집중화할 수 있습니다. 자세한 내용은 [인벤토리 가시성 구성](inventory-visibility-configuration.md)을 참조하세요.

인벤토리를 보는 방법에는 다음 두 가지가 있습니다.

- 고성능 API를 통해 쿼리를 제출합니다. 이 API는 캐시된 인스턴스에서 직접 거의 실시간 인벤토리 데이터를 반환할 수 있습니다. [인벤토리 가시성 공개 API](inventory-visibility-api.md)에서 계약과 샘플을 찾을 수 있습니다.
- 원시 재고 목록을 봅니다. 이 목록은 캐시된 인스턴스에서 주기적으로 동기화되며 Dataverse에서 볼 수 있습니다. 자세한 내용은 [인벤토리 가시성 앱](inventory-visibility-power-platform.md)을 참조하세요.

## <a name="soft-reservations"></a>소프트 예약

소프트 예약은 초과 판매를 방지하는 판매 주문 이행과 같이 기업이 지원하기 위해 특정 수량의 제품을 예약해야 하는 경우에 적용됩니다. Supply Chain Management 또는 기타 주문 관리 시스템에서 판매 주문이 생성되고 확인되면 수량 예약 요청이 인벤토리 가시성으로 전송됩니다. 인벤토리 가시성을 사용하면 차원 세부 정보 및 특정 인벤토리 트랜잭션 유형이 있는 제품을 예약할 수 있습니다. (자세한 내용은 [인벤토리 가시성 앱](inventory-visibility-power-platform.md)을 참조하세요.) 수량 예약이 성공적으로 완료되면 예약 ID가 반환됩니다. 이 예약 ID를 사용하여 Supply Chain Management 또는 기타 주문 관리 시스템의 원래 주문에 다시 연결할 수 있습니다.

이 기능은 인벤토리 가시성의 예약이 총 수량을 변경하지 않도록 설계되었습니다. 대신 예약된 수량만 표시합니다. (따라서 *소프트 예약* 이라고 합니다.) 소프트 예약 수량은 제품이 Supply Chain Management 또는 타사 시스템에서 소비될 때 API를 다시 호출하여 수량 공제를 수행하고 인벤토리 가시성의 총 수량을 업데이트하여 상쇄할 수 있습니다. 자세한 내용은 [인벤토리 가시성 예약](inventory-visibility-reservations.md)을 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
