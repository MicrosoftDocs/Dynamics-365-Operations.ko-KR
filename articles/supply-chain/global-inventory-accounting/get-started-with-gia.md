---
title: Global Inventory Accounting 시작하기
description: 이 토픽에서는 Global Inventory Accounting을 시작하는 방법에 대해 설명합니다.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88f1e9ef8c8b2aa494c44ea3b33713adc470eb96
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450103"
---
# <a name="get-started-with-global-inventory-accounting"></a>Global Inventory Accounting 시작하기

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Global Inventory Accounting를 사용하면 설정한 Global Inventory Accounting 원장에서 여러 재고 회계를 수행할 수 있습니다. 각 Global Inventory Accounting 원장을 *규칙* 과 연결해야 합니다. 규칙은 다음 유형의 회계 정책 모음입니다.

- 원가 개체
- 입력 측정 기준
- 비용 흐름 가정
- 비용 요소

> [!NOTE]
> Global Inventory Accounting을 설정한 후에도 일반적인 방식으로 Microsoft Dynamics 365 Supply Chain Management에서 재고 회계를 수행할 수 있습니다.

Global Inventory Accounting은 추가 기능입니다. 해당 기능을 사용하려면 Microsoft Dynamics LCS(Lifecycle Services)에서 설치해야 합니다. 프로덕션 환경에서 켜기 전에 테스트 환경에서 평가하도록 선택할 수 있습니다.

Global Inventory Accounting은 현재 Supply Chain Management에 내장된 모든 비용 관리 기능을 지원하지 않습니다. 따라서 현재 사용 가능한 기능 집합이 요구 사항을 충족하는지 평가하는 것이 중요합니다.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>Global Inventory Accounting 공개 프리뷰를 얻는 방법

> [!IMPORTANT]
> Global Inventory Accounting을 사용하려면 LCS 지원 고가용성 환경(OneBox 환경 아님)이 있어야 합니다. 또한 Supply Chain Management 버전 10.0.19 이상을 실행하고 있어야 합니다.

Global Inventory Accounting 공개 프리뷰에 등록하려면 [Global Inventory Accounting 팀](mailto:GlobalInvAccount@microsoft.com)에 이메일로 LCS 환경 ID를 보내세요. 프로그램에 대한 승인을 받으면 팀에서 Global Inventory Accounting 베타 키와 서비스 엔드포인트가 포함된 후속 이메일을 보내드립니다. 베타 키를 받은 후 [추가 기능을 설치](#install)할 수 있습니다.

## <a name="licensing"></a>라이선싱

Global Inventory Accounting은 Supply Chain Management에 사용할 수 있는 재고 회계의 표준 기능과 함께 사용이 허가됩니다. Global Inventory Accounting을 사용하기 위해 추가 라이선스를 구매할 필요가 없습니다.

## <a name="prerequisites"></a>전제 조건

### <a name="set-up-microsoft-power-platform-integration"></a>Microsoft Power Platform 통합 설정

추가 기능을 활성화하려면 먼저 다음 단계에 따라 Microsoft Power Platform과 통합해야 합니다.

1. 서비스를 추가할 LCS 환경을 엽니다.
1. **전체 세부 정보** 로 이동합니다.
1. **Power Platform 통합** 섹션에서 **설정** 을 선택합니다.
1. **Power Platform 환경 설정** 대화 상자에서 확인란을 선택한 후 **설정** 을 선택합니다. 일반적으로 설정에는 60~90분이 소요됩니다.
1. Microsoft Power Platform 환경 설정이 완료되면 페이지에 환경 이름이 표시됩니다. 또한 **Power Platform 통합** 섹션에는 "Power Platform 환경 설정이 완료되었습니다."라는 문구가 표시됩니다. Global Inventory Accounting에는 이중 쓰기 애플리케이션이 필요하지 않습니다.

자세한 내용은 [환경 배포 후 활성화](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy)를 참조하세요.

### <a name="set-up-dataverse"></a>Dataverse 설정

Dataverse를 설정하기 전에 다음 단계에 따라 Global Inventory Accounting 서비스 원칙을 테넌트에 추가하세요.

1. [Graph용 Azure Active Directory PowerShell 설치](/powershell/azure/active-directory/install-adv2)에 설명된 대로 Windows PowerShell v2용 Azure AD 모듈을 설치합니다.
1. 다음 PowerShell 명령을 실행합니다.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

다음으로 다음 단계에 따라 Dataverse에서 Global Inventory Accounting에 대한 애플리케이션 사용자를 생성합니다.

1. Dataverse 환경의 URL을 엽니다.
1. **고급 설정 \> 시스템 \> 보안 \> 사용자** 로 이동한 후 애플리케이션 사용자를 생성합니다. **보기** 필드를 사용하여 페이지 보기를 *애플리케이션 사용자* 로 변경합니다.
1. **새로 만들기** 를 선택합니다.
1. **애플리케이션 ID** 필드를 *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9* 로 설정합니다.
1. **역할 할당** 을 선택한 다음 *시스템 관리자* 를 선택합니다. *Common Data Service 사용자* 라는 역할이 있는 경우 해당 역할도 선택합니다.
1. 이전 단계를 반복하되 **애플리케이션 ID** 필드를 *5f58fc56-0202-49a8-ac9e-0946b049718b* 로 설정합니다.

자세한 내용은 [애플리케이션 사용자 생성](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user)을 참조하세요.

Dataverse 설치의 기본 언어가 영어가 아닌 경우 다음 단계를 따르세요.

1. **고급 설정 \> 관리 \> 언어** 로 이동합니다.
1. *영어*(*LanguageCode=1033*)를 선택한 다음 **적용** 을 선택합니다.

## <a name="install-the-add-in"></a><a name="install"></a>추가 기능 설치

Global Inventory Accounting를 사용할 수 있도록 추가 기능을 설치하려면 다음 단계를 따르세요.

1. Global Inventory Accounting 공개 프리뷰에 [등록](#sign-up)하세요.
1. [LCS](https://lcs.dynamics.com/Logon/Index)에 로그인합니다.
1. **프리뷰 기능 관리** 로 이동합니다.
1. 더하기 기호(**+**)를 선택합니다.
1. **코드** 필드에 Global Inventory Accounting에 대한 추가 기능 베타 키를 입력합니다. (가입할 때 이메일로 베타 키를 받았어야 합니다.)
1. **차단 해제** 를 선택합니다.
1. 서비스를 추가할 LCS 환경을 엽니다.
1. **전체 세부 정보** 로 이동합니다.
1. **Power Platform 통합** 으로 이동하고 **설정** 을 선택합니다.
1. **Power Platform 환경 설정** 대화 상자에서 확인란을 선택한 후 **설정** 을 선택합니다. 일반적으로 설정에는 60~90분이 소요됩니다.
1. Microsoft Power Platform 환경 설정이 완료된 후 **환경 추가 기능** 빠른 탭에서 **새 추가 기능 설치** 를 선택합니다.
1. **Global inventory accounting** 을 선택합니다.
1. 설치 가이드를 따르고 이용 약관에 동의합니다.
1. **설치** 를 선택합니다.
1. **환경 추가 기능** 빠른 탭에서 Global Inventory Accounting이 설치되고 있음을 확인해야 합니다. 몇 분 후 상태가 *설치 중* 에서 *설치됨* 으로 변경됩니다. (이 변경 사항을 확인하려면 페이지를 새로 고쳐야 할 수도 있습니다.) 이 시점에서 Global Inventory Accounting을 사용할 준비가 된 것입니다.

## <a name="set-up-the-integration"></a>통합 설정

Global Inventory Accounting과 Supply Chain Management 간의 통합을 설정하려면 다음 단계를 따르세요.

1. Supply Chain Management에 로그인합니다.
1. **시스템 관리 \> 기능 관리** 로 이동합니다.
1. **업데이트 확인** 을 선택합니다.
1. **모두** 탭에서 *(프리뷰) Global inventory accounting* 라는 기능을 검색합니다.
1. **지금 활성화** 를 선택합니다.
1. **Global inventory accounting \> 설정 \> Global inventory accounting 매개 변수 \> 통합 매개 변수** 로 이동합니다.
1. **Data Service 엔드포인트** 및 **Global inventory accounting 엔드포인트** 필드에 프리뷰에 등록할 때 Global Inventory Accounting 팀이 보낸 이메일의 URL을 입력합니다.

이제 Global Inventory Accounting를 사용할 준비가 되었습니다.
