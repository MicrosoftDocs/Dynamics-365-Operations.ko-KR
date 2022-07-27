---
title: IoT 인텔리전스 홈 페이지
description: 이 토픽에서는 IoT 인텔리전스에 대한 정보에 대한 링크를 제공합니다.
author: tonyafehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b6c179052cdb9d1ca808d9cba089163bde0d5d5
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449467"
---
# <a name="iot-intelligence-home-page"></a>IoT 인텔리전스 홈 페이지

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> 이 기능은 현재 다음 국가/지역에서만 사용할 수 있습니다.
>
> - US(미국)
> - EU(유럽 연합)
> - AU(오스트레일리아)
> - CA(캐나다)
> - UK(영국)

IoT 인텔리전스는 Microsoft Dynamics 365 Supply Chain Management용 추가 기능입니다. IoT(사물 인터넷) 신호를 Supply Chain Management의 데이터와 통합하여 실행 가능한 인사이트를 생성합니다.

IoT 인텔리전스는 다음 시나리오를 지원합니다.

+ **생산 지연** – 이 시나리오는 실제 주기 시간을 계획된 주기 시간과 비교합니다. Supply Chain Management는 생산이 예정대로 이루어지지 않을 때 알려 주므로 개입하여 운영 효율성을 극대화하고 주문 지연을 방지할 수 있습니다.
+ **장비 가동 중지 시간** – 이 시나리오는 측정된 가동 시간을 사용자 정의 매개 변수와 비교합니다. Supply Chain Management는 중단 임계값이 초과되면 사용자에게 알려서 생산 작업 주문 일정 변경 또는 유지 관리 작업 주문 생성과 같은 조치를 취할 수 있습니다.
+ **제품 품질** – 이 시나리오는 수분 및 온도와 같은 센서 판독값을 사용자 정의 품질 메트릭과 비교합니다. Supply Chain Management는 편차가 발생하면 사용자에게 알려서 품질 표준을 유지하고 낭비를 최소화하기 위해 개입할 수 있습니다.

다음 그림은 Azure IoT Hub, IoT 인텔리전스 및 Supply Chain Management의 상호 작용을 보여줍니다.

![IoT 허브, IoT 인텔리전스 및 Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>설정

코드를 작성하지 않고도 IoT 인텔리전스를 설정하고 구성할 수 있습니다. 다음은 기본 단계입니다.

1. [Azure 리소스 설정](iot-azure-setup.md) – Supply Chain Management에서 액세스할 수 있는 IoT Hub, Redis 캐시 및 키 자격 증명 모음을 만듭니다.
2. [IoT 허브의 메시지 스키마 형식](iot-schema-format.md) – IoT 허브에 메시지를 보내도록 디바이스를 구성하고 JSON(JavaScript Object Notation) 메시지 형식을 정의합니다.
3. 기능 관리에서 IoT 인텔리전스 기능 플래그를 활성화합니다. 
4. [Microsoft Dynamics LCS(Lifecycle Services)에 IoT 인텔리전스 추가 기능 설치](iot-lcs-setup.md) – LCS에 추가 기능을 설치하고 Azure 비밀을 구성합니다.
5. [메트릭 설정](iot-metrics-setup.md) – Supply Chain Management에서 메트릭을 설정합니다.
6. [시나리오 설정](iot-scenario-setup.md) – Supply Chain Management에서 시나리오를 설정합니다.

## <a name="tracking-and-maintenance"></a>추적 및 유지 관리

+ [Dynamics 365 Supply Chain Management에서 시나리오 모니터링](iot-management.md#monitor-scenarios)
+ [시나리오 사용 안 함](iot-scenario-setup.md#disable-a-scenario)
+ [추가 기능 제거](iot-lcs-setup.md#uninstall-addin)
+ [실행 중인 IoT 인텔리전스 시나리오 수정](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [시뮬레이션 옵션](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]