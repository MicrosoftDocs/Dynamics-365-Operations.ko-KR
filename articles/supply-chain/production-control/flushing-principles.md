---
title: 플러싱 원리
description: 이 토픽에서는 원자재 소비에 사용되는 4가지 세척 원칙에 대해 설명합니다.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7f644f26098bf7ac7d13292d6fbabb09a488d61e29fcd5fbd3cf0d261f0529bc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447193"
---
# <a name="flushing-principles"></a>플러싱 원리

[!include [banner](../includes/banner.md)]

플러싱 원리는 생산 공정에 사용되는 원자재에 대한 다양한 소비 전략을 반영합니다. 소비는 현재고에서 자재를 차감하고 소비된 자재의 값을 생산 오더 및 배치 오더에 대해 **재공품**(WIP)으로 설정하는 프로세스입니다. 원자재는 일반적으로 재료를 소비하는 프로세스에 대해 구성된 위치에서 소비됩니다. 이 위치를 생산 입력 위치라고 합니다.

재료 소모 전 재료는 입력 위치로 이동합니다. 다음 그림은 프로세스를 보여줍니다.

[![scenario4a.](./media/scenario4a.png)](./media/scenario4a.png)

1. 자재 창고
2. 원재료 피킹
3. 생산 입력 위치
4. 원자재 소비
5. 생산 가공

재료 소비는 다음 4가지 세척 원칙에 따라 제어됩니다.

- 수동
- 시작
- 마감
- 현장 사용 가능

플러싱 원칙은 기본값의 계층 구조로 구성됩니다. 계층 구조는 플러싱 원리가 **시작** 값을 갖는 릴리스된 제품에서 시작합니다. BOM(자재 명세서) 또는 수식 라인에서 제품의 플러싱 원칙을 무시할 수 있습니다. 생산 BOM 라인 또는 배치 주문 수식 라인의 기본 플러싱 원칙은 제품 또는 BOM 또는 수식의 대체된 값에서 가져옵니다.

## <a name="description-of-the-flushing-principles"></a>플러싱 원리 설명

### <a name="manual"></a>수동
수동 플러싱 원리는 재료 소비 등록이 수동 작업임을 나타냅니다. 이 원칙은 예를 들어 시간을 추적할 수 있기를 원하고 추적 목적으로 소비된 배치 번호 또는 일련 번호의 수량을 고려해야 하는 경우에 적합합니다. 수동 소비는 생산 피킹 목록 분개에 등록됩니다. 고급 창고 프로세스에 사용할 수 있는 항목의 경우 휴대용 흐름을 적용할 수 있습니다.

### <a name="start"></a>시작
플러싱 시작 원칙은 생산 주문이 시작될 때 자재가 자동으로 소모됨을 나타냅니다. 소모되는 재료의 양은 시작되는 양에 비례합니다. 세척 시작 원리를 제조 실행 시스템과 함께 사용하면 작업 또는 공정 작업이 시작될 때 재료를 세척하는 데에도 사용할 수 있습니다. 이 원칙은 예를 들어 소비 변동이 낮거나 자재가 가치가 낮은 자재이거나 추적 요구 사항이 없거나 운영 시간이 짧은 경우에 적합합니다. 

### <a name="finish"></a>마감
마감 플러싱 원칙은 생산 오더가 완료된 것으로 보고되거나 자재를 소비하도록 설정된 작업이 완료된 것으로 등록될 때 자재가 자동으로 소비됨을 나타냅니다. 소모되는 재료의 양은 완성된 것으로 보고되는 양에 비례합니다. 마무리 플러싱 원리가 제조 실행 시스템과 함께 사용되면 작업 또는 프로세스 작업이 완료될 때 재료를 세척하는 데 사용할 수도 있습니다. 이 원칙은 시작 원칙과 동일한 상황과 관련이 있습니다. 그러나 마감 원칙은 작업이 완료되기 전에 자재를 WIP로 설정하지 않아야 하는 더 긴 실행 시간이 있는 작업에 적용됩니다. 

### <a name="available-at-location"></a>현장 사용 가능
현장 사용 가능 플러싱 원칙은 자재가 생산을 위해 피킹된 것으로 등록될 때 자동으로 소모됨을 나타냅니다. 원자재 피킹 작업이 완료되거나 생산 입력 위치에서 자재가 사용 가능하고 자재 라인이 창고로 출고되면 자재가 피킹 위치로 등록됩니다. 프로세스 중에 생성된 피킹 목록은 배치 작업으로 전기됩니다. 이 원칙은 예를 들어 하나의 생산 주문에 대해 많은 피킹 활동이 있는 경우에 적합합니다. 이 경우 피킹 목록을 수동으로 업데이트할 필요가 없으며 WIP 잔액의 현재 보기를 얻을 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]