---
title: Warehouse Management 모바일 앱 설치 및 연결
description: 이 토픽에서는 각 모바일 디바이스에 Warehouse Management 모바일 앱을 설치하고 Microsoft Dynamics 365 Supply Chain Management 환경에 연결하도록 구성하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 812dd30e0e444bc310fc81edd16958e0c0747885
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449989"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱 설치 및 연결

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 이 토픽에서는 새 Warehouse Management 모바일 앱을 구성하는 방법에 대해 설명합니다. 이전 웨어하우스 앱(현재 사용되지 않음)을 구성하는 방법에 대한 정보를 찾고 있다면 [웨어하우스 앱 설치 및 연결](../../supply-chain/warehousing/install-configure-warehousing-app.md)을 참조하세요.

이 토픽에서는 각 모바일 디바이스에 Warehouse Management 모바일 앱을 다운로드하고 설치하는 방법과 Supply Chain Management 환경에 연결하도록 앱을 구성하는 방법에 대해 설명합니다. 각 디바이스를 수동으로 구성하거나 파일을 통해 또는 QR 코드를 스캔하여 연결 설정을 가져올 수 있습니다.

## <a name="system-requirements"></a>시스템 요구 사항

Warehouse Management 모바일 앱은 Windows 및 Google Android 운영 체제 모두에서 사용할 수 있습니다. 앱을 사용하려면 모바일 디바이스에 다음 운영 체제 중 하나가 설치되어 있어야 합니다.

- Windows 10(유니버설 Windows 플랫폼 \[UWP\]) 2018년 10월 업데이트 1809(빌드 10.0.17763) 이상
- Android 4.4 이상

## <a name="turn-warehouse-management-mobile-app-features-or-or-off-in-supply-chain-management"></a>Supply Chain Management에서 Warehouse Management 모바일 앱 기능을 켜거나 끕니다.

Warehouse Management 모바일 앱을 사용하려면 *새 창고 앱 기능에 대한 사용자 설정, 아이콘 및 단계 제목* 이 시스템에서 켜져 있어야 합니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 공간에서 *새 창고 앱에 대한 사용자 설정, 아이콘 및 단계 제목* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="get-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱 다운로드

소규모 배포의 경우 일반적으로 관련 스토어에서 각 디바이스에 앱을 설치한 다음 사용 중인 환경에 대한 연결을 수동으로 구성할 수 있습니다.

대규모 배포의 경우 앱 배포 및/또는 구성을 자동화할 수 있으며, 이는 많은 디바이스를 관리하는 경우 더 편리할 수 있습니다. 예를 들어[ Microsoft Intune](/mem/intune/fundamentals/what-is-intune)과 같은 모바일 디바이스 관리 및 모바일 응용 프로그램 관리 솔루션을 사용할 수 있습니다. Intune을 사용하여 애플리케이션을 추가하는 방법에 대한 자세한 내용은 [Microsoft Intune에 앱 추가](/mem/intune/apps/apps-add)를 참조하세요.

### <a name="install-the-app-from-an-app-store"></a>앱 스토어에서 앱 설치

단일 디바이스에 앱을 설치하는 가장 쉬운 방법은 일반적으로 사용 가능한 최신 버전을 항상 제공하는 앱 스토어에서 설치하는 것입니다. Microsoft Intune은 앱 스토어에서 앱을 가져올 수도 있습니다. 다음 링크 중 하나를 사용하여 앱 스토어에서 앱을 설치합니다.

- **Windows(UWP):** [Microsoft Store의 Warehouse Management](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Google Play 스토어의 Warehouse Management](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Microsoft App Center에서 앱 다운로드

앱 스토어에서 설치하는 대신 Microsoft App Center에서 앱을 다운로드할 수 있습니다. App Center는 테스트용으로 로드할 수 있는 설치 가능한 패키지를 제공합니다. 현재 버전 외에도 App Center를 통해 이전 버전을 다운로드할 수 있으며 시험해 볼 수 있는 향후 기능이 포함된 프리뷰 버전을 제공할 수 있습니다. Microsoft App Center에서 Warehouse Management 모바일 앱의 현재, 이전 또는 프리뷰 버전을 다운로드하려면 다음 링크 중 하나를 사용하세요.

- **Windows(UWP):** [Warehouse Management(Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    Windows 디바이스에 다운로드한 패키지를 설치한 다음 필요한 인증서를 설정하는 방법에 대한 지침은[ App Center에서 빌드 설치](/appcenter/distribution/installation)를 참조하세요.

- **Android:** [Warehouse Management (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    프리뷰 버전을 다운로드하는 경우 설치하려면 몇 가지 추가 단계가 필요합니다. 자세한 내용은 [Android 앱 테스트](/appcenter/distribution/testers/testing-android)를 참조하세요.

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Azure Active Directory에서 웹 서비스 애플리케이션 만들기

Warehouse Management 모바일 앱이 특정 Supply Chain Management 서버와 상호 작용할 수 있도록 하려면 Azure AD(Azure Active Directory)에서 Supply Chain Management 테넌트에 대한 웹 서비스 애플리케이션을 등록해야 합니다. 다음 절차는 이 작업을 완료하는 한 가지 방법을 보여줍니다. 자세한 정보 및 대안은 절차 후 링크를 참조하세요.

1. 웹 브라우저에서 [https://portal.azure.com](https://portal.azure.com/)로 이동합니다.
1. Azure 구독에 대한 액세스 권한이 있는 사용자의 이름과 암호를 입력합니다.
1. Azure Portal의 왼쪽 탐색 창에서 **Azure Active Directory** 를 선택합니다.

    ![Azure Active Directory.](media/app-connect-azure-aad.png "Azure Active Directory")

1. Supply Chain Management에서 사용하는 Azure AD 인스턴스로 작업하고 있는지 확인합니다.
1. **관리** 목록에서 **앱 등록** 을 선택합니다.

    ![앱 등록](media/app-connect-azure-register.png "앱 등록")

1. 도구 모음에서 **새 등록** 을 선택하여 **애플리케이션 등록** 마법사를 엽니다.
1. 애플리케이션 이름을 입력하고 **이 조직 디렉터리에만 있는 계정** 옵션을 선택한 다음 **등록** 을 선택합니다.

    ![애플리케이션 마법사를 등록합니다.](media/app-connect-azure-register-wizard.png "애플리케이션 마법사 등록")

1. 새 앱 등록이 열립니다. 나중에 필요하므로 **애플리케이션 (클라이언트) ID** 값을 기록해 둡니다. 이 ID는 이 항목의 뒷부분에서 *클라이언트 ID* 라고 합니다.

    ![애플리케이션 (클라이언트) ID](media/app-connect-azure-app-id.png "애플리케이션 (클라이언트) ID")

1. **관리** 목록에서 **인증서 및 비밀** 을 선택합니다. 그런 다음 인증을 위해 앱을 구성하려는 방법에 따라 다음 버튼 중 하나를 선택합니다. (자세한 내용은 이 토픽 뒷부분의 [인증서 또는 클라이언트 암호를 사용하여 인증](#authenticate) 섹션을 참조하세요.)

    - **인증서 업로드** – 암호로 사용할 인증서를 업로드합니다. 이 방법이 더 안전하고 더 완벽하게 자동화될 수 있으므로 이 방법을 권장합니다. Windows 디바이스에서 Warehouse Management 모바일 앱을 실행하는 경우 인증서를 업로드한 후 표시되는 **지문** 값을 기록해 두세요. Windows 디바이스에서 인증서를 구성할 때 이 값이 필요합니다.
    - **새 클라이언트 암호** – **암호** 섹션에 키 설명과 기간을 입력하여 키를 만든 다음 **추가** 를 선택합니다. 키를 복사하여 안전하게 보관합니다.

    ![인증서 및 비밀.](media/app-connect-azure-authentication.png "인증서 및 비밀")

Azure AD에서 웹 서비스 애플리케이션을 설정하는 방법에 대한 자세한 내용은 다음 리소스를 참조하세요.

- Windows PowerShell을 사용하여 Azure AD에서 웹 서비스 애플리케이션을 설정하는 방법을 보여주는 지침은 [방법: Azure PowerShell을 사용하여 인증서로 서비스 주체 만들기](/azure/active-directory/develop/howto-authenticate-service-principal-powershell)를 참조하세요.
- Azure AD에서 웹 서비스 애플리케이션을 수동으로 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

    - [빠른 시작: Microsoft ID 플랫폼에 애플리케이션 등록](/azure/active-directory/develop/quickstart-register-app)
    - [방법: 포털을 사용하여 리소스에 액세스할 수 있는 Azure AD 애플리케이션 및 서비스 주체 만들기](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a><a name="user-azure-ad"></a>자세한 내용은 Supply Chain Management에서 사용자 계정 생성 및 구성을 참조하세요.

Supply Chain Management에서 Azure AD 애플리케이션을 사용하도록 설정하려면 다음 단계를 따르세요.

1. Warehouse Management 모바일 앱에 대한 사용자 자격 증명에 해당하는 사용자를 생성합니다.

    1. Supply Chain Management에서 **시스템 관리 \> 사용자 \> 사용자** 로 이동합니다.
    1. 사용자를 만듭니다.
    1. *창고 모바일 디바이스 사용자* 역할을 사용자에게 할당합니다.

    ![창고 모바일 디바이스 사용자 역할을 할당합니다.](media/app-connect-app-users.png "창고 모바일 디바이스 사용자 역할 할당")

1. Azure AD 애플리케이션을 Warehouse Management 모바일 앱 사용자와 연결합니다.

    1. **시스템 관리 \> 설정 \> Azure Active Directory 애플리케이션** 으로 이동합니다.
    1. 작업 창에서 **새로 만들기** 를 선택하여 라인을 만듭니다.
    1. **클라이언트 ID** 필드에 이전 섹션에서 기록해 둔 클라이언트 ID를 입력합니다.
    1. **이름** 필드에 이름을 입력합니다.
    1. **사용자 ID** 필드에서 방금 생성한 사용자 ID를 선택합니다.

    ![Azure Active Directory 애플리케이션.](media/app-connect-aad-apps.png "Azure Active Directory 애플리케이션")

> [!TIP]
> 이러한 설정을 사용하는 한 가지 방법은 각 물리적 디바이스에 대해 Azure에서 클라이언트 ID를 만든 다음 **Azure Active Directory 애플리케이션** 페이지에 각 클라이언트 ID를 추가하는 것입니다. 그런 다음 디바이스를 분실한 경우 해당 페이지에서 클라이언트 ID를 제거하여 Supply Chain Management에 대한 액세스를 쉽게 제거할 수 있습니다. (이 방법은 이 토픽의 뒷부분에서 설명하는 것처럼 각 디바이스에 저장된 연결 자격 증명도 클라이언트 ID를 지정하기 때문에 작동합니다.)
>
> 또한 각 클라이언트 ID에 대한 기본 언어, 숫자 형식 및 시간대 설정은 여기에 매핑된 **사용자 ID** 값에 대해 설정된 기본 설정에 의해 설정됩니다. 따라서 이러한 기본 설정을 사용하여 클라이언트 ID를 기반으로 각 디바이스 또는 디바이스 모음에 대한 기본 설정을 지정할 수 있습니다. 그러나 이러한 기본 설정은 작업자가 디바이스에 로그인하는 데 사용하는 *창고 앱 사용자 계정* 에도 정의된 경우 재정의됩니다. (자세한 내용은 [모바일 디바이스 사용자 계정](mobile-device-work-users.md)을 참조하세요.)

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>인증서 또는 클라이언트 암호를 사용하여 인증

Azure AD를 사용한 인증은 모바일 디바이스를 Supply Chain Management에 연결하는 안전한 방법을 제공합니다. 클라이언트 암호 또는 인증서를 사용하여 인증할 수 있습니다. 연결 설정을 가져올 경우 클라이언트 암호 대신 인증서를 사용하는 것이 좋습니다. 클라이언트 암호는 항상 안전하게 저장해야 하므로 이 항목의 뒷부분에서 설명하는 것처럼 연결 설정 파일이나 QR 코드에서 가져올 수 없습니다.

인증서는 토큰이 요청될 때 애플리케이션의 ID를 증명하기 위한 비밀로 사용될 수 있습니다. 인증서의 공개 부분은 Azure Portal의 앱 등록에 업로드되지만 전체 인증서는 Warehouse Management 모바일 앱이 설치된 각 디바이스에 배포되어야 합니다. 조직은 순환 등의 측면에서 인증서를 관리할 책임이 있습니다. 자체 서명된 인증서를 사용할 수 있지만 항상 내보낼 수 없는 인증서를 사용해야 합니다.

Warehouse Management 모바일 앱을 실행하는 각 디바이스에서 로컬로 인증서를 사용할 수 있도록 해야 합니다. Intune을 사용하는 경우 Intune 제어 디바이스의 인증서를 관리하는 방법에 대한 자세한 내용은 [Microsoft Intune에서 인증에 인증서 사용](/mem/intune/protect/certificates-configure)을 참조하세요.

## <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>클라우드 및 에지 스케일 장치용 Warehouse Management 모바일 앱 구성

클라우드 또는 에지 스케일 디바이스에 대해 Warehouse Management 모바일 앱을 실행하려는 경우 몇 가지 추가 단계가 필요합니다. 지침은 [클라우드 및 에지 스케일 단위에 대한 Warehouse Management 모바일 앱 구성](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)을 참조하세요.

## <a name="configure-the-application-by-importing-connection-settings"></a>연결 설정을 가져와서 애플리케이션 구성

많은 모바일 디바이스에서 애플리케이션을 더 쉽게 유지 관리하고 배포할 수 있도록 각 디바이스에 수동으로 입력하는 대신 연결 설정을 가져올 수 있습니다. 이 섹션에서는 설정을 만들고 가져오는 방법에 대해 설명합니다.

### <a name="create-a-connection-settings-file-or-qr-code"></a>연결 설정 파일 또는 QR 코드 생성

파일 또는 QR 코드에서 연결 설정을 가져올 수 있습니다. 두 접근 방식 모두에서 먼저 JSON(JavaScript Object Notation) 형식 및 구문을 사용하는 설정 파일을 생성해야 합니다. 파일에는 추가해야 하는 개별 연결이 포함된 연결 목록이 포함되어야 합니다. 다음 테이블에는 연결 설정 파일에서 지정해야 하는 매개 변수가 요약되어 있습니다.

| 매개 변수 | 설명 |
|---|---|
| ConnectionName | 연결 설정의 이름을 지정합니다. 최대 길이는 20자입니다. 이 값은 연결 설정에 대한 고유 식별자이므로 목록에서 고유한지 확인합니다. 동일한 이름을 가진 연결이 디바이스에 이미 존재하는 경우 가져온 파일의 설정이 무시됩니다. |
| ActiveDirectoryClientAppId | [Azure Active Directory에서 웹 서비스 애플리케이션 만들기](#create-service) 섹션에서 Azure AD를 설정하는 동안 기록해 둔 클라이언트 ID를 지정합니다. |
| ActiveDirectoryResource | Supply Chain Management의 루트 URL을 지정합니다. |
| ActiveDirectoryTenant | Supply Chain Management 서버와 함께 사용 중인 Azure AD 도메인 이름을 지정합니다. 이 값의 형식은 `https://login.windows.net/<your-Azure-AD-domain-name>`입니다. 다음은 예입니다. `https://login.windows.net/contosooperations.onmicrosoft.com` Azure AD 도메인 이름을 찾는 방법에 대한 자세한 내용은 [사용자의 중요한 ID 찾기](/partner-center/find-ids-and-domain-names)를 참조하세요. |
| 회사 | 애플리케이션을 연결할 Supply Chain Management의 법인을 지정합니다. |
| ConnectionType | (선택 사항) 연결 설정이 환경에 연결하기 위해 인증서 또는 클라이언트 암호를 사용해야 하는지 여부를 지정합니다. 유효한 값은 *"certificate"* 및 *"clientsecret"* 입니다. 기본값은 *"인증서"* 입니다.<p>**메모:** 클라이언트 암호는 가져올 수 없습니다.</p> |
| IsEditable | (선택 사항) 앱 사용자가 연결 설정을 편집할 수 있어야 하는지 여부를 지정합니다. 유효한 값은 *"true"* 및 *"false"* 입니다. 기본값은 *"true"* 입니다. |
| IsDefault | (선택 사항) 연결이 기본 연결인지 여부를 지정합니다. 기본 연결로 설정된 연결은 앱을 열 때 자동으로 미리 선택됩니다. 하나의 연결만 기본 연결로 설정할 수 있습니다. 유효한 값은 *"true"* 및 *"false"* 입니다. 기본값은 *"false"* 입니다. |
| CertificateThumbprint | (선택 사항) Windows 디바이스의 경우 연결에 대한 인증서 지문을 지정할 수 있습니다. Android 디바이스의 경우 앱 사용자는 처음 연결을 사용할 때 인증서를 선택해야 합니다. |

다음 예는 두 개의 연결이 포함된 유효한 연결 설정 파일을 보여줍니다. 보시다시피 연결 목록(파일에서 *"ConnectionList"* 로 명명됨)은 각 연결을 개체로 저장하는 배열이 있는 개체입니다. 각 개체는 중괄호({})로 묶어야 하고 쉼표로 구분해야 하며 배열은 대괄호(\[\])로 묶어야 합니다.

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

정보를 JSON 파일로 저장하거나 동일한 내용의 QR 코드를 생성할 수 있습니다. 정보를 파일로 저장하는 경우, 특히 각 모바일 디바이스의 기본 위치에 저장하는 경우 기본 이름인 *connections.json* 을 사용하여 저장하는 것이 좋습니다.

### <a name="save-the-connection-settings-file-on-each-device"></a>각 디바이스에 연결 설정 파일 저장

일반적으로 디바이스 관리 도구 또는 스크립트를 사용하여 관리 중인 각 디바이스에 연결 설정 파일을 배포합니다. 각 디바이스에 연결 설정 파일을 저장할 때 기본 이름과 위치를 사용하면, Warehouse Management 모바일 앱은 앱 설치 후 처음 실행하는 동안에도 자동으로 가져옵니다. 파일에 대한 사용자 지정 이름 또는 위치를 사용하는 경우 앱 사용자는 처음 실행하는 동안 값을 지정해야 합니다. 그러나 앱은 이후에 지정된 이름과 위치를 계속 사용합니다.

앱이 시작될 때마다 변경 사항이 있는지 확인하기 위해 이전 위치에서 연결 설정을 다시 가져옵니다. 앱은 연결 설정 파일의 연결과 이름이 같은 연결만 업데이트합니다. 다른 이름을 사용하는 사용자 생성 연결은 업데이트되지 않습니다.

연결 설정 파일을 사용하여 연결을 제거할 수 없습니다.

언급했듯이 기본 파일 이름은 *connections.json* 입니다. 기본 파일 위치는 Windows 디바이스를 사용하는지 Android 디바이스를 사용하는지에 따라 다릅니다.

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

일반적으로 경로는 앱을 처음 실행한 후 자동으로 생성됩니다. 그러나 설치하기 전에 연결 설정 파일을 디바이스로 전송해야 하는 경우 수동으로 생성할 수 있습니다.

> [!NOTE]
> 앱이 제거되면 기본 경로와 해당 콘텐츠가 제거됩니다.

### <a name="import-the-connection-settings"></a>연결 설정 가져오기

파일 또는 QR 코드에서 연결 설정을 가져오려면 다음 단계를 따르세요.

1. 모바일 디바이스에서 Warehouse Management 모바일 앱을 시작합니다. 앱을 처음 시작하면 환영 메시지가 표시됩니다. **연결 선택** 을 선택합니다.

    ![환영 메시지.](media/app-configure-welcome-screen.png "환영 메시지")

1. 파일에서 연결 설정을 가져오고 파일을 저장할 때 기본 이름과 위치가 사용된 경우 앱에서 이미 파일을 찾았을 수 있습니다. 이 경우 4단계로 건너뜁니다. 그렇지 않으면 **연결 설정** 을 선택한 다음 3단계를 계속합니다.

    ![연결 설정.](media/app-configure-set-up-connection.png "연결 설정")

1. **연결 설정** 대화 상자에서 설정을 가져올 방법에 따라 **파일에서 추가** 또는 **QR 코드에서 추가** 를 선택합니다.

    - 파일에서 연결 설정을 가져오는 경우 **파일에서 추가** 를 선택하고 로컬 디바이스에서 파일을 찾아 선택합니다. 사용자 지정 위치를 선택하면 앱이 해당 위치를 저장하고 다음에 자동으로 사용합니다.
    - QR 코드를 스캔하여 연결 설정을 가져오는 경우 **QR 코드에서 추가** 를 선택합니다. 앱에서 디바이스의 카메라 사용 권한을 묻는 메시지를 표시합니다. 권한을 부여하면 카메라가 시작되어 스캔에 사용할 수 있습니다. 디바이스의 카메라 품질 및 QR 코드의 복잡성에 따라 올바른 스캔을 얻기 어려울 수 있습니다. 이 경우 QR 코드당 하나의 연결만 생성하여 QR 코드의 복잡성을 줄이십시오. (현재는 디바이스의 카메라로만 QR코드를 스캔할 수 있습니다.)

    ![연결 설정 메뉴.](media/app-configure-connection-setup-flyout.png "연결 설정 메뉴")

1. 연결 설정이 성공적으로 로드되면 선택한 연결이 표시됩니다.

    ![연결 설정이 로드되었습니다.](media/app-configure-select-connection.png "연결 설정이 로드됨")

1. Android 디바이스를 사용 중이고 인증에 인증서를 사용하는 경우 디바이스에서 인증서를 선택하라는 메시지를 표시합니다.

    ![Android 디바이스에서 인증서 프롬프트를 선택합니다.](media/app-configure-select-certificate.png "Android 디바이스에서 인증서 프롬프트 선택")

1. 앱이 Supply Chain Management 서버에 연결되고 로그인 페이지가 표시됩니다.

    ![로그인 페이지입니다.](media/app-configure-sign-in-page.png "로그인 페이지")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>애플리케이션 수동 구성

파일 또는 QR 코드가 없는 경우 Azure AD 애플리케이션을 통해 Supply Chain Management 서버에 연결하도록 디바이스에서 앱을 수동으로 구성할 수 있습니다.

1. 모바일 디바이스에서 Warehouse Management 모바일 앱을 시작합니다.
1. 앱이 **데모 모드** 에서 시작된 경우 **연결 설정** 을 선택합니다. 앱 실행 시 **로그인** 페이지가 나타나면 **연결 변경** 을 선택하세요.
1. **연결 설정** 을 선택합니다.

    ![연결 설정.](media/app-configure-set-up-connection.png "연결 설정")

1. **수동으로 입력** 을 선택합니다.

    ![연결 설정 메뉴.](media/app-configure-connection-setup-flyout.png "연결 설정 메뉴")

    **새 연결** 페이지가 나타나고 연결 세부 정보를 수동으로 입력하는 데 필요한 설정이 표시됩니다.

    ![수동 연결 필드.](media/app-configure-input-manually.png "수동 연결 필드")

1. 다음 정보를 입력합니다.

    - **클라이언트 암호 사용** – 클라이언트 암호를 사용하여 Supply Chain Management에서 인증하려면 이 옵션을 _예_ 로 설정합니다. 인증에 인증서를 사용하려면 _아니오_ 로 설정합니다. (자세한 내용은 이 항목 앞부분의 섹션에서 [Azure Active Directory 웹 서비스 애플리케이션 만들기](#create-service)를 참조하세요.)
    - **연결 이름** – 새 연결의 이름을 입력합니다. 이 이름은 다음에 연결 설정을 열 때 **연결 선택** 필드에 나타납니다. 입력하는 이름은 고유해야 합니다. (즉, 다른 연결 이름이 디바이스에 저장되어 있는 경우 디바이스에 저장된 다른 모든 연결 이름과 달라야 합니다.)
    - **Active Directory 클라이언트 ID** – [Azure Active Directory에서 웹 서비스 애플리케이션 만들기](#create-service) 섹션에서 Azure AD를 설정하는 동안 기록해 둔 클라이언트 ID를 입력합니다.
    - **Active Directory 클라이언트 암호** - 이 필드는 **클라이언트 암호 사용** 옵션이 _예_ 로 설정된 경우에만 사용할 수 있습니다. [Azure Active Directory에서 웹 서비스 애플리케이션 만들기](#create-service) 섹션에서 Azure AD을 설정하는 동안 기록해 둔 클라이언트 암호를 입력합니다.
    - **Active Directory 인증서 지문** – 이 필드는 Windows 디바이스에서만 사용할 수 있으며 **클라이언트 암호 사용** 옵션이 _아니요_ 로 설정된 경우에만 사용할 수 있습니다. [Azure Active Directory에서 웹 서비스 애플리케이션 만들기](#create-service) 섹션에서 Azure AD를 설정하는 동안 기록한 인증서 지문을 입력합니다.
    - **Active Directory 리소스** – Supply Chain Management의 루트 URL을 지정합니다.

        > [!IMPORTANT]
        > 이 값을 슬래시(/)로 끝내지 마십시오.

    - **Active Directory 테넌트** – Supply Chain Management 서버와 함께 사용 중인 Azure AD 도메인 이름을 입력합니다. 이 값의 형식은 `https://login.windows.net/<your-Azure-AD-domain-name>`입니다. 다음은 예입니다. `https://login.windows.net/contosooperations.onmicrosoft.com` Azure AD 도메인 이름을 찾는 방법에 대한 자세한 내용은 [사용자의 중요한 ID 찾기](/partner-center/find-ids-and-domain-names)를 참조하세요.

        > [!IMPORTANT]
        > 이 값을 슬래시(/)로 끝내지 마십시오.

    - **회사** – 애플리케이션을 연결할 Supply Chain Management의 법인(회사)을 입력합니다.

1. 페이지의 오른쪽 상단 모서리에 있는 **저장** 버튼을 선택합니다.
1. Android 디바이스를 사용 중이고 인증에 인증서를 사용하는 경우 디바이스에서 인증서를 선택하라는 메시지를 표시합니다.
1. 앱이 Supply Chain Management 서버에 연결되고 로그인 페이지가 표시됩니다.

## <a name="remove-access-for-a-device"></a>디바이스에 대한 액세스 제거

디바이스를 분실하거나 손상된 경우 해당 디바이스에 대한 Supply Chain Management에 대한 액세스 권한을 제거해야 합니다. 다음 단계에서는 액세스 권한을 제거하는 데 권장되는 프로세스를 설명합니다.

1. **시스템 관리 \> 설정 \> Azure Active Directory 애플리케이션** 으로 이동합니다.
1. 액세스를 제거하려는 디바이스에 해당하는 라인을 삭제하세요. 나중에 필요하므로 디바이스에 사용되는 클라이언트 ID를 기록해 둡니다.

    클라이언트 ID를 하나만 등록했고 여러 디바이스에서 동일한 클라이언트 ID를 사용하는 경우 해당 디바이스에 새 연결 설정을 푸시해야 합니다. 그렇지 않으면 액세스 권한을 잃게 됩니다.

1. [https://portal.azure.com](https://portal.azure.com/)에서 Azure Portal에 로그인합니다.
1. 왼쪽 탐색 창에서 **Active Directory** 를 선택하고 올바른 디렉터리에 있는지 확인합니다.
1. **관리** 목록에서 **앱 등록** 을 선택한 다음 구성할 애플리케이션을 선택합니다. **설정** 페이지가 나타나고 구성 정보가 표시됩니다.
1. 애플리케이션의 클라이언트 ID가 2단계에서 기록해 둔 클라이언트 ID와 일치하는지 확인합니다.
1. 도구 모음에서 **삭제** 를 선택합니다.
1. 표시되는 확인 메시지에서 **예** 를 선택합니다.

## <a name="additional-resources"></a>추가 리소스

- [모바일 디바이스 사용자 설정](mobile-device-user-settings.md)
- [Warehouse Management 모바일 앱에 대한 단계 아이콘 및 제목 할당](step-icons-titles.md)
- [클라우드 및 에지 스케일 디바이스용 Warehouse Management 모바일 앱 구성](../cloud-edge/cloud-edge-workload-setup-warehouse-app.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
