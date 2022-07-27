---
title: IoT 인텔리전스를 위한 시나리오 설정
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management에서 IoT 인텔리전스에 대한 시나리오를 구성하는 방법에 대해 설명합니다.
author: tonyafehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b8e8c65cebe64f86dcf158668e8a4f5600c158a1
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449461"
---
# <a name="scenario-setup-for-iot-intelligence"></a>IoT 인텔리전스를 위한 시나리오 설정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management에서 IoT 인텔리전스에 대한 시나리오를 구성하는 방법에 대해 설명합니다. 시나리오를 설정하려면 먼저 [Microsoft Microsoft Dynamics LCS(Lifecycle Services)를 설정](iot-lcs-setup.md)해야 합니다.

이 토픽에서는 장비가 중지될 때 Supply Chain Management에서 알림이 생성되도록 **장비 가동 중지 시간** 시나리오를 구성합니다. 항목의 속성이 지정된 범위를 벗어날 경우 알림이 생성되도록 **제품 품질** 시나리오를 구성하는 방법과 생산 처리량이 임계값 아래로 떨어지는 경우 알림이 생성되도록 **생산 지연** 시나리오를 구성하는 방법도 보여줍니다.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Supply Chain Management에서 장비 가동 중지 시간 시나리오 구성

**장비 가동 중지 시간** 시나리오는 **PartOut** 신호를 기계 경고 임계값에 매핑합니다. 시스템은 시나리오에 대해 선택되고 Supply Chain Management에서 **실행** 으로 설정된 경우에만 모니터링됩니다. **PartOut** 신호가 기계에서 마지막으로 수신된 이후의 시간이 경고 임계값을 초과하면 **기계 다운** 알림이 트리거됩니다. 기계가 여전히 실행 중이면 다음 **PartOut** 신호가 수신될 때 **기계 가동** 알림이 트리거됩니다. 머신이 30분 동안 다운된 상태로 있으면 새로운 **기계 다운** 알림이 트리거됩니다.

**장비 가동 중지 시간** 시나리오에는 다음과 같은 종속성이 있습니다.

+ 매핑된 시스템에서 생산 주문이 실행 중인 경우에만 경고가 트리거될 수 있습니다.
+ 매핑된 머신의 **PartOut** 신호를 나타내는 신호는 IoT 허브로 전송되어야 하며 고유한 속성 이름이 포함되어야 합니다.
+ 값이 밀리초(ms)로 표시되는 UNIX **타임스탬프** 속성은 Azure IoT Hub 메시지에 있어야 합니다.

시나리오를 구성하려면 다음 단계를 따르세요.

1. Supply Chain Management에 로그인합니다.
2. IoT 인텔리전스 기능 플래그를 활성화합니다. 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.
3. 메트릭을 구성합니다. 자세한 내용은 [메트릭을 구성하는 방법](iot-metrics-setup.md#configure-metrics)을 참조하세요.
4. **생산 관리 \> 설정 \> IoT 인텔리전스 \> 시나리오 관리** 로 이동합니다.
6. **장비 가동 중지 시간** 타일에서 **구성** 을 선택하여 구성 마법사를 엽니다.

   마법사의 첫 번째 페이지는 **장비 센서 스키마 정의** 페이지입니다. 이 페이지에서 목표는 IoT 허브 메시지의 JSON(JavaScript Object Notation) 형식과 일치하도록 Supply Chain Management에서 스키마를 설정하는 것입니다. 여러 메시지 스키마를 정의할 수 있습니다. 자세한 내용은 [IoT Hub 메시지의 스키마 형식](iot-schema-format.md)을 참조하세요. 이 예에서 메시지 페이로드에는 다음 형식의 메시지 일괄 처리가 포함되어 있습니다.

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. 테이블에 행을 추가하고 다음 값을 설정합니다.

    1. **스키마 이름** 필드를 **ID** 로 설정합니다.
    2. **스키마 경로** 필드를 **/payload\[\*\]/id** 로 설정합니다.
    3. **설명** 필드를 **메시지 ID** 로 설정합니다.

8. 테이블에 다른 행을 추가하고 다음 값을 설정합니다.

    1. **스키마 이름** 필드를 **타임스탬프** 로 설정합니다.
    2. **스키마 경로** 필드를 **/payload\[\*\]/timestamp** 로 설정합니다.
    3. **설명** 필드를 **메시지 타임스탬프** 로 설정합니다.

9. 테이블에 다른 행을 추가하고 다음 값을 설정합니다.

    1. **스키마 이름** 필드를 **값** 으로 설정합니다.
    2. **스키마 경로** 필드를 **/payload\[\*\]/value** 로 설정합니다.
    3. **설명** 필드를 **메시지 값** 으로 설정합니다.

    > [!NOTE]
    > 메시지의 모든 속성을 정의할 필요는 없습니다. 필요한 속성만 정의하세요. 이전 단계에서는 **루트 타임스탬프** 에 대한 행을 생성하지 않았습니다. **루트 타임스탬프** 의 경로는 **/timestamp** 입니다.

10. **다음** 을 선택하여 **장비 센서 스키마 맵** 페이지로 이동합니다.
11. **장비 리소스 ID** 행의 **스키마 이름** 필드에서 **ID** 를 선택합니다.
12. **UTC 시간** 행의 **스키마 이름** 필드에서 **타임스탬프** 를 선택합니다.
13. **부품 생성 신호** 행의 **스키마 이름** 필드에서 **값** 을 선택합니다.
14. **다음** 을 선택하여 **장비 리소스 ID 구성** 페이지로 이동합니다.
15. 다음 단계에 따라 IoT 허브 메시지의 값을 Supply Chain Management 리소스에 매핑합니다.

    1. **신호 데이터 값** 테이블에서 새 행을 추가합니다. **값** 필드에 **IoTInt.Machine1225.PartOut** 을 입력합니다. 이 값은 IoT 허브 메시지의 JSON **id** 속성에서 가져옵니다.
    2. **저장** 을 선택합니다.
    3. **비즈니스 레코드 매핑** 테이블에서 **새로 만들기** 를 선택합니다. **비즈니스 레코드 유형** 필드의 기본값은 자동으로 채워지며 변경할 필요가 없습니다.
    4. **비즈니스 레코드** 필드에서 신호 값이 전송되는 Supply Chain Management 시스템 리소스를 선택합니다.
    5. **저장** 을 선택합니다.
    6. 이 단계를 반복하여 **Machine1226** 에 대한 새 비즈니스 레코드 매핑을 추가합니다. 여러 신호 데이터 값을 Supply Chain Management의 단일 레코드에 매핑할 수 있습니다.

16. **선택됨** 열을 사용하여 처리할 시스템을 선택합니다. 모든 신호 값을 정의할 필요가 없으며 모든 기계를 선택할 필요도 없습니다.
17. **다음** 을 선택하여 **부품 생산 신호 구성** 페이지로 이동합니다.
18. **신호 데이터 값** 테이블에서 행을 추가하고 **값** 필드를 **True** 로 설정합니다. 이 값은 IoT Hub 메시지의 JSON **value** 속성에서 가져옵니다. 시나리오에 필요한 만큼 값을 추가할 수 있습니다.
19. **저장** 을 선택합니다.
20. **다음** 을 선택하여 **장비 가동 중단 시간 임계값** 페이지로 이동합니다. 나열된 기계는 이전에 신호 값에 매핑된 기계입니다. 이 페이지에서는 시스템이 다운되었는지 여부를 결정하기 위한 임계값을 정의합니다. 예를 들어 임계값을 **10** 으로 설정하면 10분 동안 기계에서 **PartOut** 신호가 수신되지 않으면 Supply Chain Management에서 알림을 생성합니다.
21. **다음** 을 선택하여 **시나리오 사용** 페이지로 이동합니다. 시나리오를 활성화하는 옵션을 설정합니다.
22. **완료** 를 선택합니다.

이제 시나리오 설정이 완료되었습니다. IoT 인텔리전스는 IoT 허브 메시지 처리를 자동으로 시작합니다.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Supply Chain Management에서 제품 품질 시나리오 구성

**제품 품질** 시나리오는 항목의 속성이 지정된 범위를 벗어나는 경우 알림을 생성합니다. 예를 들어 센서는 각 항목의 무게를 IoT 허브로 보냅니다. 항목이 너무 무겁거나 너무 가벼운 경우 Supply Chain Management에서 알림이 생성됩니다.

**제품 품질** 시나리오에는 다음과 같은 종속성이 있습니다.

+ 생산 주문이 매핑된 시스템에서 실행 중이고 매핑된 배치 속성이 있는 제품을 생산하는 경우에만 경고가 트리거될 수 있습니다.
+ 배치 특성을 나타내는 신호를 IoT Hub로 보내야 하며 고유한 속성 이름을 포함해야 합니다.
+ 값이 밀리초(ms)로 표시되는 UNIX **timestamp** 속성은  IoT 허브 메시지에 있어야 합니다.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Supply Chain Management에서 생산 지연 시나리오 구성

**생산 지연** 시나리오는 생산 처리량이 임계값 아래로 떨어지면 알림을 생성합니다. 이 시나리오에서는 생산되는 각 항목에 대해 **PartOut** 신호가 IoT 허브로 전송됩니다. Supply Chain Management에서 주문 지연은 생산 주문이 실행되도록 예약된 시간, 생산해야 하는 항목 수, 작업이 실행된 시간 및 수신한 **PartOut** 신호 수를 기반으로 계산됩니다. 작업에 대한 **PartOut** 신호 수가 임계값 아래로 떨어지면 지연 알림이 생성됩니다.

**생산 지연** 시나리오에는 다음과 같은 종속성이 있습니다.

+ 매핑된 시스템에서 생산 주문이 실행 중인 경우에만 경고가 트리거될 수 있습니다.
+ 매핑된 머신의 **PartOut** 신호를 나타내는 신호는 Azure IoT Hub로 전송되어야 하며 고유한 속성 이름이 포함되어야 합니다.
+ 값이 밀리초(ms)로 표시되는 UNIX **timestamp** 속성은  IoT 허브 메시지에 있어야 합니다.

## <a name="disable-a-scenario"></a>시나리오 사용 안 함

각 시나리오를 사용하지 않으려면 다음 단계를 따르세요.

1. Supply Chain Management에서 **생산 관리 \> 설정 \> IoT 인텔리전스 \> 시나리오 관리** 로 이동합니다.
2. 시나리오의 타일에서 **구성** 을 선택합니다.
3. **다음** 을 선택하여 마지막 마법사 페이지로 이동합니다.
4. 시나리오를 사용하지 않는 옵션을 설정합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]