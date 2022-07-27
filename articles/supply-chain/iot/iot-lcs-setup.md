---
title: LCS에 IoT 인텔리전스 추가 기능 설치
description: 이 토픽에서는 Microsoft Dynamics LCS(Lifecycle Services)에 IoT 인텔리전스 추가 기능을 설치하는 방법에 대해 설명합니다.
author: tonyafehr
ms.date: 07/07/2020
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
ms.openlocfilehash: ebf11b55f1034b9a84dda9ada77c2f1b7f587a58
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449458"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>LCS에 IoT 인텔리전스 추가 기능 설치

[!include [banner](../../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics LCS(Lifecycle Services)에 IoT 인텔리전스 추가 기능을 설치하는 방법에 대해 설명합니다. 추가 기능은 데모/평가판 환경에 설치할 수 없습니다. 추가 기능을 설치하려면 먼저 [Azure 리소스를 만들어야 합니다](iot-azure-setup.md).

## <a name="set-up-the-lcs-environment"></a>LCS 환경 설정

1. LCS를 열고 Microsoft Dynamics 365 Supply Chain Management 환경으로 이동합니다.
2. **환경 추가 기능** 섹션으로 스크롤합니다.
3. 환경에 대해 활성화된 추가 기능 목록을 표시하려면 **새 추가 기능 설치** 를 선택합니다.
4. **설치할 추가 기능 선택** 대화 상자에서 **IoT 인텔리전스** 를 선택합니다.
5. **추가 기능 설정** 대화 상자에서 IoT Hub 및 Redis 캐시에 대한 세부 정보를 제공합니다. [Azure 리소스 만들기](iot-azure-setup.md)에서 만든 키 자격 증명 모음에서 필요한 값을 찾을 수 있습니다.

    + **테넌트 ID** – Azure Portal에서 키 자격 증명 모음으로 이동한 다음, 왼쪽 탐색 창에서 **개요** 를 선택하고 **디렉터리 ID** 값을 복사합니다. **설치 추가 기능** 대화 상자에 해당 값을 붙여넣습니다.
    + **IoT 이벤트 허브 호환 엔드포인트 키 자격 증명 모음 URI** – 키 자격 증명 모음으로 이동한 다음, 왼쪽 탐색 창에서 **개요** 를 선택하고 **DNS 이름** 값을 복사합니다. **설치 추가 기능** 대화 상자에 해당 값을 붙여넣습니다.
    + **IoT 이벤트 허브 호환 엔드포인트 비밀 이름** – 키 자격 증명 모음으로 이동한 다음, 왼쪽 탐색 창에서 **비밀** 을 선택하고 IoT 허브에 대한 이벤트 허브 연결 문자열이 저장된 비밀의 이름을 복사합니다. **설치 추가 기능** 대화 상자에 해당 값을 붙여넣습니다.
    + **Redis 캐시 키 자격 증명 모음 URI** – 키 자격 증명 모음으로 이동한 다음, 왼쪽 탐색 창에서 **개요** 를 선택하고 **DNS 이름** 값을 복사합니다. **설치 추가 기능** 대화 상자에 해당 값을 붙여넣습니다.
    + **Redis 캐시 엔드포인트 비밀 이름** – 키 자격 증명 모음으로 이동한 다음 왼쪽 탐색 창에서 **비밀** 을 선택하고 Redis 캐시에 대한 연결 문자열이 저장된 비밀 이름을 복사합니다. **설치 추가 기능** 대화 상자에 해당 값을 붙여넣습니다.

6. 이용 약관에 동의하려면 확인란을 선택합니다.
7. **설치** 를 선택합니다.
8. "추가 기능이 설치를 위해 성공적으로 트리거되었습니다."라는 메시지 상자가 나타납니다. **확인** 을 선택합니다.

이제 LCS 설정이 완료되었습니다. 다음 단계는 [시나리오를 설정](iot-scenario-setup.md)하는 것입니다.

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>추가 기능 제거

1. Supply Chain Management에서 [시나리오를 사용하지 않습니다](iot-scenario-setup.md#disable-a-scenario).
2. LCS에서 Supply Chain Management 환경 세부 정보로 이동합니다.
3. **환경 추가 기능** 섹션으로 스크롤합니다.
4. IoT 인텔리전스 추가 기능에 대해 **제거** 를 선택합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]