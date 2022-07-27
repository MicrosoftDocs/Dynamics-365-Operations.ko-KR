---
title: IoT 인텔리전스에 대한 메트릭 설정
description: 이 토픽에서는 IoT 인텔리전스에 대한 메트릭을 설정하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 85db0211c32ad4e27c3a9a65d2c74c5a39687f9c
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449473"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>IoT 인텔리전스에 대한 메트릭 설정

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>메트릭 구성

Microsoft Dynamics 365 Supply Chain Management에서 메시지의 시계열 차트를 보려면 다음 단계에 따라 메트릭을 설정해야 합니다.

1. Redis 캐시에 대한 연결 문자열을 복사합니다.

    1. Azure Portal에서 Redis Cache로 이동합니다.
    2. **설정** \> **액세스 키** 로 이동합니다.
    3. **기본 연결 문자열** 필드의 값을 복사합니다.

2. Supply Chain Management에서 **생산 관리 \> 설정 \> IoT 인텔리전스 \> 시나리오 매개 변수** 로 이동합니다.
3. **시나리오 매개 변수** 페이지에서 **시계열** 탭의 **Redis 메트릭 저장소 연결 문자열** 필드에 이전에 복사한 연결 문자열을 붙여넣습니다. 이 단계에서는 Azure IoT Hub의 메트릭을 Supply Chain Management에서 시각화할 수 있습니다. 값을 필드에 붙여넣으면 **\*\*\*\*\*\*** 로 표시됩니다.

    > [!NOTE]
    > Redis Cache 연결 문자열을 업데이트할 때마다 이 필드도 업데이트해야 합니다.

4. **생산 관리 \> 문의 및 신고 \> IoT 인텔리전스 \> 메트릭 키** 로 이동합니다.
5. **메트릭 키** 페이지에서 **업데이트** 를 선택합니다.
6. **메트릭 키 업데이트** 대화 상자의 필드에서 **백그라운드에서 실행** 이 선택되어 있는지 확인합니다. **확인** 을 선택합니다.

Redis Cache의 모든 메트릭 키가 검색되어 **메트릭 키** 목록에 추가됩니다. [시나리오를 활성화](iot-scenario-setup.md)할 때까지 메트릭 값이 표시되지 않습니다.

## <a name="configure-the-resource-status-time-series"></a>리소스 상태 시계열 구성

**리소스 상태** 시계열을 구성하려면 다음 단계를 따르세요.

1. Supply Chain Management에서 **생산 관리 \> 제조 실행 \> 리소스 상태** 로 이동합니다.
2. **리소스 상태** 페이지에서 **구성** 을 선택합니다.
2. **구성** 대화 상자의 **리소스** 목록에서 모니터링할 항목을 선택합니다.
3. **시계열 1** 에 대해 **편집** 버튼을 선택합니다.
4. **시계열 선택** 대화 상자의 그리드에서 메트릭을 선택합니다. (**메트릭 키 업데이트** 링크를 사용하여 이 대화 상자에서 메트릭 키를 업데이트할 수도 있습니다.)
5. **확인** 을 선택하여 **구성** 대화 상자로 돌아갑니다.
6. 표시 이름을 입력합니다.
7. **데이터 표시 시작** 필드에서 시간 프레임을 선택합니다.
8. **확인** 을 선택합니다.

차트가 표시됩니다.

## <a name="delete-a-metric-key"></a>메트릭 키 삭제

1. Supply Chain Management에서 **생산 관리 \> 문의 및 신고 \> IoT 인텔리전스 \> 메트릭 키** 로 이동합니다.
2. **메트릭 키** 페이지에서 삭제할 메트릭 키를 선택합니다.
3. **삭제** 를 선택합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]