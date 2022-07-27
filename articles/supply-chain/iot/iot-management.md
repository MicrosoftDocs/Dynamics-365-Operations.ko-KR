---
title: IoT 인텔리전스 모니터링 및 관리
description: 이 토픽에서는 IoT 인텔리전스를 모니터링하고 관리하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 8fbd750aa4a316f5e04f3c8622d0847ad9318360
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449464"
---
# <a name="monitor-and-manage-iot-intelligence"></a>IoT 인텔리전스 모니터링 및 관리

[!include [banner](../../includes/banner.md)]

이 토픽에서는 IoT 인텔리전스를 모니터링하고 관리하는 방법에 대해 설명합니다.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Microsoft에서 시나리오 모니터링Dynamics 365 Supply Chain Management

여러 위치에서 IoT 인텔리전스 처리를 모니터링할 수 있습니다.

+ **모듈 \> 생산 관리 \> 문의 및 신고 \> IoT 인텔리전스 \> 알림** - 해결되지 않은 알림 목록을 봅니다.
+ **모듈 \> 생산 관리 \> 문의 및 신고 \> IoT 인텔리전스 \> 닫힌 알림** - 해결되거나 해제된 알림 목록을 봅니다.
+ **모듈 \> 생산 관리 \> 문의 및 신고 \> IoT 인텔리전스 \> 메트릭 키** – **리소스 상태** 시계열 차트에 대한 메트릭 키를 봅니다.
+ **모듈 \> 생산 관리 \> 제조 실행 \> 리소스 상태** – **구성** 대화 상자를 사용하여 특정 메트릭을 추적합니다. 시나리오에서 예외를 감지하면 알림에 예외 세부 정보가 표시됩니다.
+ **작업 영역 \> 생산 현장 관리 \> 알림** – 해결되지 않은 알림 목록을 봅니다.

## <a name="modify-a-running-iot-intelligence-scenario"></a>실행 중인 IoT 인텔리전스 시나리오 수정

시나리오가 실행 중일 때 다음과 같이 변경할 수 있습니다.

+ 새 센서 스키마 정의를 추가합니다.
+ 새 신호 데이터 값을 선택합니다.
+ 기존 신호 데이터 값의 선택을 취소합니다.
+ 새 신호 데이터 값을 추가하고 매핑합니다.
+ 임계값을 업데이트합니다.

시나리오가 실행 중일 때는 다음과 같은 변경이 금지됩니다.

+ 활성화된 시나리오에서 현재 사용 중인 스키마 정의를 삭제하거나 수정합니다.
+ 활성화된 시나리오에서 선택한 스키마 경로를 변경합니다.

## <a name="simulation-options"></a>시뮬레이션 옵션

공장 기계 신호를 시뮬레이션할 수 있습니다. 자세한 내용은 다음 토픽을 참조하세요.

+ [IoT DevKit AZ3166을 Azure IoT Hub에 연결](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Raspberry Pi 온라인 시뮬레이터를 Azure IoT Hub(Node.js)에 연결](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [디바이스 시뮬레이션 솔루션 가속기 개요](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]