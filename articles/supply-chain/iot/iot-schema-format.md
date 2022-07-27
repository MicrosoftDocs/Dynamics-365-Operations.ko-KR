---
title: IoT 허브 메시지의 스키마 형식
description: 이 토픽에서는 IoT 인텔리전스에서 사용할 수 있는 메시지 스키마를 디자인하는 방법에 대해 설명합니다.
author: tonyafehr
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b24a6e14182baa91299abad0da2987b2dca92601
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449455"
---
# <a name="schema-formats-for-iot-hub-messages"></a>IoT 허브 메시지의 스키마 형식

[!include [banner](../../includes/banner.md)]

이 토픽에서는 IoT 인텔리전스에서 사용할 수 있는 메시지 스키마를 디자인하는 방법에 대해 설명합니다.

## <a name="message-requirements"></a>메시지 요구 사항

IoT 인텔리전스의 메시지 모니터링에는 다음 규칙이 적용됩니다.

+ 메시지 스키마는 JSON(JavaScript Object Notation) 형식이어야 합니다.
+ 값이 밀리초(ms)로 표시되는 UNIX **timestamp** 속성은 Microsoft Azure IoT 허브 메시지에 있어야 합니다.
+ 시나리오 설정에 정의된 모든 속성이 메시지에 포함된 경우에만 메시지가 추적됩니다. 예를 들어 **id**, **timestamp**, **value** 속성을 정의하면 다음과 같은 메시지가 모니터링 된다.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    **value** 속성이 없기 때문에 이 메시지는 모니터링되지 않습니다.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ IoT 인텔리전스는 시나리오 구성에 정의되지 않은 메시지의 속성을 무시합니다. 예를 들어 **id**, **timestamp** 및 **value** 속성을 정의하면 IoT 인텔리전스는 다음 메시지를 모두 모니터링합니다.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ IoT 인텔리전스는 시나리오 구성 기준과 일치하지 않는 메시지를 자동으로 무시합니다.
+ 여러 유형의 메시지 스키마를 정의하고 사용할 수 있습니다.
+ 모든 유형의 메시지 스키마를 정의해야 하는 것은 아닙니다. IoT 인텔리전스 시나리오에 사용할 스키마만 정의해야 합니다.

## <a name="id-value-pair-schema"></a>ID-값 쌍 스키마

ID-값 쌍은 IoT 인텔리전스 메시지 스키마의 일반적인 패턴입니다. ID-값 쌍을 사용하여 모든 시나리오에서 메시지 스키마가 동일한지 확인합니다. 예를 들어 다음은 **장비 가동 중지 시간** 또는 **생산 지연** 시나리오에 대한 메시지입니다.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

다음은 **제품 품질** 시나리오에 대한 메시지입니다.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

앞의 두 메시지 모두 **id** 및 **value** 속성을 포함합니다. **id** 값은 시나리오 설정 중에 **신호 데이터 값** 테이블에서 매핑할 수 있습니다. **장비 가동 중지 시간** 시나리오의 경우 **IoTInt.Machine1225.PartOut** 값을 매핑합니다. **제품 품질** 시나리오의 경우 **IoTInt.Machine1225.Temperature** 값을 매핑합니다.

자세한 내용은 [Azure IoT Hub 설명서](/azure/iot-hub/)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]