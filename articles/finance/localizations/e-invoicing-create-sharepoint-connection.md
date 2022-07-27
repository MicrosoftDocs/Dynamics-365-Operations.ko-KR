---
title: SharePoint 연결 구성
description: 이 항목에서는 전자 송장 발행이 Microsoft SharePoint 사이트에 액세스할 수 있도록 연결을 구성하는 방법을 설명합니다.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6b9fffc1f3525e69792517dd1c6ebdcfbe5a74d2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451669"
---
# <a name="configure-a-sharepoint-connection"></a>SharePoint 연결 구성

[!include [banner](../includes/banner.md)]

전자 송장 발행 서비스는 Microsoft SharePoint 폴더에서 파일을 읽고 SharePoint에 파일을 업로드할 수 있습니다. 전자 송장 발행이 특정 SharePoint 사이트에 액세스할 수 있도록 하려면 전자 송장 발행 서비스에 사이트 자격 증명을 제공해야 합니다. 또한 자격 증명이 안전하게 저장되도록 하려면 이를 직접 제공하지 마십시오. 대신 Azure Key Vault에 저장하고 Azure Key Vault 비밀을 제공하십시오.

## <a name="grant-access-to-a-sharepoint-folder"></a>SharePoint 폴더에 권한 부여

1. RCS(Regulatory Configuration Service)가 설치된 테넌트에서 앱 등록을 만듭니다.

    1. [Azure Portal](https://portal.azure.com/)에 로그인합니다.
    2. **앱 등록** 으로 이동합니다.
    3. **신규 등록** 을 선택합니다.
    4. **전자 송장 발행용 SharePoint 앱** 과 같은 이름을 입력하고 등록 완료
    5. 새 앱 등록을 선택합니다.
    6. **인증** 탭에서 **공용 클라이언트 흐름 허용** 옵션을 활성화합니다.
    4. **인증서 및 비밀** 탭에서 **새 클라이언트 비밀** 을 선택하여 클라이언트 암호를 만듭니다.
    5. 생성된 비밀 값을 복사합니다.

    다음 지침을 따르십시오.

    - 다른 서비스에 같은 앱 등록을 사용하지 않습니다.
    - [암호 정책 권장 사항](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide)을 따릅니다.
    - 암호 순환을 설정합니다. 순환하는 동안 앱 등록을 위한 새 클라이언트 암호를 만들고 Key Vault를 업데이트한 다음 이전 암호를 삭제합니다.

2. **앱 등록 비밀** 및 **애플리케이션(클라이언트) ID** 값을 전자 송장 발행 환경 설정의 키 자격 증명 모음에 두 개의 새 비밀로 저장합니다.
3. 만든 비밀을 RCS의 전자 송장 발행 환경 설정에서 Key Vault 매개 변수에 추가합니다.
4. Azure Portal에서 SharePoint에 대한 액세스 권한을 부여합니다. 이 단계는 테넌트 관리자가 완료해야 합니다.

    1. 만든 앱 등록을 선택합니다.
    2. **API 사용 권한** 탭에서 **사용 권한 추가** 를 선택합니다.
    3. **Microsoft Graph(애플리케이션 사용 권한)** \> **Sites.Selected** 를 선택합니다.
    4. **\<user&nbsp;name\>에 관리자 동의 부여** 를 선택합니다.
    5. **상태** 필드를 검토하여 사용 권한이 부여되었는지 확인합니다.

        ![API 사용 권한 탭에 부여된 권한.](media/configured-permissions.jpg)

    6. [Graph 탐색기 - Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer)를 열고 로그인합니다.
    7. 왼쪽 창에 있는 **샘플 쿼리** 탭의 **SharePoint 사이트** 에서 **사이트의 상대 경로를 기반으로 SharePoint 사이트 가져오기** 를 선택합니다.
    8. **\{호스트 이름\}** 및 **\{서버 상대 경로\}** 매개 변수를 입력합니다. 예를 들어 **\{호스트 이름\}** 에 `<domain>.sharepoint.com`을 입력하고 **\{서버 상대 경로\}** 에 `sites/<siteName>`을 입력합니다.

        > [!NOTE]
        > 기본 웹 사이트의 경우 **\{서버 상대 경로\}** 매개 변수를 비워 둡니다.

    9. **쿼리 실행** 을 선택하고 결과를 저장합니다.
    10. 다음 쿼리를 구성합니다.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        이 쿼리에서 **\{사이트 ID\}** 는 이전 쿼리 응답의 **ID** 노드 값입니다.

        다음은 요청 본문입니다.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        이 요청 본문에서 **\{앱 ID\}** 는 **애플리케이션(클라이언트) ID** 값이고 **\{앱 이름\}** 은 **애플리케이션 이름** 값입니다.

        ![POST 쿼리.](media/app-id-query.jpg)

    11. **권한 수정** 탭에서 **사용 권한 패널 열기** 를 선택한 다음 **사이트** \> **Sites.FullControl.All** \> **동의** 를 선택합니다.
    12. **쿼리 실행** 을 선택합니다.

이제 전자 송장 발행 서비스가 SharePoint 사이트에 액세스할 수 있습니다.
