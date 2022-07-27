---
title: IoT 인텔리전스용 Azure 리소스 설정
description: 이 토픽에서는 IoT 인텔리전스에 필요한 Microsoft Azure 리소스를 만들고 구성하는 방법을 설명합니다.
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
ms.openlocfilehash: d50458be9196206978a8d146ecd5b8c2a0a1fa8c
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8449470"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>IoT 인텔리전스용 Azure 리소스 설정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 IoT 인텔리전스에 필요한 Microsoft Azure 리소스를 만들고 구성하는 방법을 설명합니다.

## <a name="create-azure-resources"></a>Azure 리소스 만들기

다음 단계에 따라 Microsoft Dynamics 365 Supply Chain Management에서 액세스할 수 있는 IoT Hub, Redis Cache 및 키 자격 증명 모음을 만드세요.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Microsoft Dynamics ERP Microservices 자사 앱 ID가 테넌트에 있는지 확인합니다.

Microsoft Dynamics ERP Microservices 자사 앱의 앱 ID가 테넌트에 있는지 확인하려면 다음 단계를 따르세요.

1. <https://portal.azure.com>에서 Azure Portal에 로그인합니다.
2. **Azure Active Directory** 로 이동합니다.
3. **엔터프라이즈 애플리케이션** 으로 이동합니다.
4. **애플리케이션 유형** 필드에서 **Microsoft 애플리케이션** 을 선택하세요.
5. 검색 필드에 **Microsoft Dynamics ERP 마이크로서비스** 를 입력합니다.
6. **Microsoft Dynamics ERP 마이크로서비스** 가 목록에 있는지 확인합니다. 다른 애플리케이션의 이름은 비슷합니다. 따라서 올바른 애플케이션인을 찾아야 합니다. 앱 아이디는 **0cdb527f-a8d1-4bf8-9436-b352c68682b2** 입니다.

    애플리케이션이 목록에 없으면 테넌트에 추가해야 합니다.

    1. Azure Portal의 도구 모음에서 단추를 선택하여 Azure Cloud Shell을 엽니다.
    2. **Install-Module AzureAD** 명령을 실행합니다. **Y** 를 입력하여 모듈을 설치합니다.
    3. **Get-InstalledModule -Name "AzureAD"** 명령을 실행하여 모듈이 설치되었는지 확인합니다.
    4. **Connect-AzureAD -Confirm** 명령을 실행하여 인증을 실행합니다.
    5. **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2** 명령을 실행합니다.

    이제 1~6단계를 반복하여 앱 ID가 테넌트에 있는지 확인할 수 있습니다.

### <a name="create-a-key-vault-resource"></a>키 자격 증명 모음 리소스 만들기

키 자격 증명 모음 리소스를 만들려면 다음 단계를 따르세요.

1. Azure Portal에서 리소스 그룹을 만들거나 이동합니다.
2. **추가** 를 선택합니다.
3. **새로 만들기** 페이지의 검색 필드에 **키 자격 증명 모음** 를 입력합니다. 그런 다음 **만들기** 를 선택합니다.
4. **키 자격 증명 모음 만들기** 페이지의 **키 자격 증명 모음 이름** 필드에 이름을 입력합니다.
5. 기본값을 검토한 다음 **검토 + 만들기** 를 선택합니다.
6. **만들기** 를 선택합니다.

키 자격 증명 모음은 백그라운드에서 만들어집니다.

### <a name="create-an-iot-hub-resource"></a>IoT 허브 리소스 만들기

IoT 허브 리소스를 만들려면 다음 단계를 따르세요.

1. 리소스 그룹을 만들거나 이동합니다.
2. **추가** 를 선택합니다.
3. **새로 만들기** 페이지의 검색 필드에 **IoT 허브** 를 입력합니다. 그런 다음 **만들기** 를 선택합니다.
4. **IoT 허브 이름** 필드에 이름을 입력합니다.
5. 기본값을 검토한 다음 **검토 + 만들기** 를 선택합니다.
6. **만들기** 를 선택합니다.

IoT 허브는 백그라운드에서 만들어집니다.

> [!NOTE]
> 환경당 하나의 IoT 허브 리소스만 만드는 것이 좋습니다.

### <a name="create-a-redis-cache-resource"></a>Redis Cache 리소스 생성

Redis Cache 리소스를 만들려면 다음 단계를 따르세요.

1. 리소스 그룹을 만들거나 이동합니다.
2. **추가** 를 선택합니다.
3. **새로 만들기** 페이지의 검색 필드에 **Azure Cache for Redis** 를 입력합니다. 그런 다음 **만들기** 를 선택합니다.
4. **DNS 이름** 필드에 이름을 입력합니다.
5. 기본값을 검토한 다음 **만들기** 를 선택합니다.

Redis Cache는 백그라운드에서 만들어집니다.

> [!NOTE]
> 환경당 하나의 Redis Cache 리소스만 만드는 것이 좋습니다.

이제 모든 리소스가 생성되었습니다.

## <a name="configure-the-azure-resources"></a>Azure 리소스 구성

### <a name="configure-the-iot-hub"></a>IoT 허브 구성

IoT 허브를 구성하는 순서는 다음과 같습니다.

1. 리소스에서 IoT 허브 리소스를 선택합니다.
2. 왼쪽 탐색 창에서 **기본 제공 엔드포인트** 를 선택합니다.
3. **소비자 그룹** 에서 다음 소비자 그룹을 붙여넣습니다. 이러한 소비자 그룹은 기본 시나리오에 해당합니다.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>키 자격 증명 모음 구성

키 자격 증명 모음을 구성하려면 다음 단계를 따르세요.

1. 리소스에서 키 자격 증명 모음을 선택합니다.
2. 왼쪽 탐색 창에서 **액세스 정책** 을 선택합니다.
3. **액세스 정책 추가** 를 선택합니다.
4. **액세스 정책 추가** 페이지의 **비밀 권한** 필드에서 **가져오기** 및 **나열** 을 선택합니다.
5. **주체 선택** 을 클릭합니다.
6. **주체** 대화 상자에서 **Microsoft Dynamics ERP Microservices** 를 검색하여 선택합니다. 그런 다음 **선택** 을 선택합니다.
7. **추가** 를 선택합니다.
8. **저장** 을 선택합니다.

이제 앱에서 키 자격 증명 모음의 비밀에 액세스할 수 있습니다.

### <a name="save-the-iot-hub-connection-string-secret"></a>IoT 허브 연결 문자열 비밀 저장

IoT 허브 연결 문자열에 대한 비밀을 저장하려면 다음 단계를 따르세요.

1. 리소스에서 IoT 허브 리소스를 선택합니다.
2. 왼쪽 탐색 창에서 **기본 제공 엔드포인트** 를 선택합니다.
3. **Event Hub 호환 엔드포인트** 필드의 값을 복사합니다.
4. 키 자격 증명 모음 리소스로 이동합니다.
5. 왼쪽 탐색 창에서 **비밀** 을 선택합니다.
6. **생성/가져오기** 를 선택합니다.
7. **이름** 필드에 이름을 입력합니다.
8. **값** 필드에 이전에 복사한 엔드포인트 값을 붙여넣습니다.
9. **만들기** 를 선택합니다.

### <a name="save-the-redis-cache-connection-string-secret"></a>Redis Cache에 대한 연결 문자열을 저장합니다.

IoT 허브 연결 문자열에 대한 비밀을 저장하려면 다음 단계를 따르세요.

1. 리소스에서 Redis Cache 리소스를 선택합니다.
2. **액세스 키** 를 선택합니다.
3. **기본 연결 문자열** 필드의 값을 복사합니다.
4. 키 자격 증명 모음 리소스로 이동합니다.
5. 왼쪽 탐색 창에서 **비밀** 을 선택합니다.
6. **생성/가져오기** 를 선택합니다.
7. **이름** 필드에 이름을 입력합니다.
8. **값** 필드에 이전에 복사한 연결 스트링을 붙여넣습니다.
9. **만들기** 를 선택합니다.

> [!NOTE]
> 연결 문자열 중 하나를 업데이트할 때마다 비밀 값도 업데이트해야 합니다.

이제 필요한 Azure 리소스 프로비저닝을 완료했습니다. 다음 단계는 [Microsoft Dynamics LCS(Lifecycle Services)에 IoT 인텔리전스 추가 기능을 설치](iot-lcs-setup.md)하는 것입니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
