---
title: 자산 관리 모바일 작업 영역 설정
description: 이 항목에서는 작업자가 자산 관리 작업을 수행하는 데 사용할 수 있는 자산 관리 모바일 작업 영역을 실행하기 위해 Microsoft Dynamics 365 Supply Chain Management 및 재무 및 운영(Dynamics 365) 모바일 앱을 설정하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5d628f99d4fc6788ddb38590c65decb871d49f93
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448495"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>자산 관리 모바일 작업 영역 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 작업자가 자산 관리 작업을 수행하는 데 사용할 수 있는 **자산 관리** 모바일 작업 영역을 실행하기 위해 Microsoft Dynamics 365 Supply Chain Management 및 재무 및 운영(Dynamics 365) 모바일 앱을 설정하는 방법에 대해 설명합니다.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Supply Chain Management에서 유지 관리 작업자 사용자 설정

**자산 관리** 모바일 작업 영역에 액세스해야 하는 각 사용자에 대해 다음 단계를 따르세요.

1. Supply Chain Management에서 **인적 자원 \> 작업자** 로 이동하고 설정하려는 사용자에 대한 작업자 레코드가 있는지 확인하세요. 필요에 따라 새 작업자 레코드를 만듭니다.
1. **자산 관리 \> 설정 \> 작업자 \> 작업자** 로 이동하고 이전 단계에서 식별(또는 생성)한 작업자 레코드가 유지 관리 작업자 레코드에 매핑되었는지 확인합니다. 필요에 따라 새 유지 관리 작업자 레코드를 생성하고 **작업자** 필드를 이전 단계의 작업자 레코드에 추가합니다.
1. **자산 관리 \> 설정 \> 작업자 \> 유지 관리 작업자 그룹** 로 이동하고 이전 단계에서 식별(또는 생성)한 유지 관리 작업자 레코드가 유지 관리 작업자 그룹에 속하는지 확인합니다.
1. **시스템 관리 \> 사용자** 로 이동합니다.
1. 그리드에서 관련 사용자를 선택합니다.
1. **사용자 세부 정보** 빠른 탭에서 **사람** 필드를 현재 사용자 계정과 연결하려는 작업자 계정으로 설정합니다. 이 작업자 계정은 1단계에서 식별(또는 생성)하고 2단계에서 유지 관리 작업자 레코드에 매핑한 작업자 레코드여야 합니다.

> [!NOTE]
> 사용자 권한 및 보안 역할은 Supply Chain Management 사용자 인터페이스의 기능에 적용되는 것처럼 **자산 관리** 모바일 작업 영역의 기능에 적용됩니다. 따라서 **자산 관리** 모바일 작업 영역에 액세스하도록 설정한 모든 사용자는 Supply Chain Management에서 직접 유사한 작업을 수행하는 데 필요한 보안 역할을 가지고 있어야 합니다.

## <a name="publish-the-asset-management-mobile-workspace"></a>자산 관리 모바일 작업 영역 게시

Finance and Operations(Dynamics 365) 모바일 앱에서 자산 관리 기능을 사용할 수 있도록 하려면 **자산 관리** 모바일 작업 영역을 게시해야 합니다.

1. Supply Chain Management에서 **설정** 단추(오른쪽 상단의 톱니바퀴 기호)를 선택한 다음 메뉴에서 **모바일 앱** 을 선택합니다.
1. **모바일 앱 관리** 대화 상자에서 **자산 관리** 타일을 찾습니다. "메타데이터에 있음 - 게시되지 않음"이라는 텍스트가 포함되어 있으면 작업 영역이 아직 게시되지 않은 것입니다. "메타데이터에서 - 게시됨"이라는 텍스트가 포함되어 있으면 작업 영역이 이미 게시된 것이므로 이 절차의 나머지 부분을 건너뛸 수 있습니다.

    ![모바일 앱 관리 대화 상자.](media/mobile-workspaces.png "모바일 앱 관리 대화 상자")

1. **자산 관리** 타일을 선택한 다음 도구 모음에서 **게시** 를 선택합니다. 몇 초 후에 작업 영역이 성공적으로 게시되었다는 알림을 받아야 합니다. 또한 타일의 텍스트가 "메타데이터에서 - 게시됨"으로 변경되어야 합니다.

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Finance and Operations(Dynamics 365) 모바일 앱 설치 및 설정

1. 다음 앱 스토어 중 하나로 이동하여 모바일 디바이스에 **Microsoft Finance and Operations(Dynamics 365)** 앱을 설치합니다.

    - [Google Android 디바이스용](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Apple iOS 디바이스용](https://go.microsoft.com/fwlink/?linkid=850663)

1. Finance and Operations(Dynamics 365) 앱을 엽니다. 로그인 페이지가 나타나야 합니다. **로그인** 필드에 Supply Chain Management URL을 입력하거나 **최근 환경** 목록에서 최근 URL을 선택한 다음 **연결** 을 탭합니다.

    ![로그인 페이지입니다.](media/mobile-app-sign-in.png "로그인 페이지")

1. 연결을 확인하라는 메시지가 표시되면 **이해함** 확인란을 선택한 다음 **연결** 을 탭합니다.
1. **계정 선택** 페이지에서 Microsoft 계정을 사용하여 모바일 애플리케이션에 로그인합니다.

    **작업 영역** 페이지가 나타납니다. 여기에는 Supply Chain Management 인스턴스에서 게시한 모든 모바일 작업 영역이 나열됩니다.

    ![작업 영역 목록입니다.](media/mobile-app-workspaces.png "작업 영역 목록")

1. 법인(회사)을 변경해야 하는 경우 왼쪽 상단의 메뉴 단추(햄버거 또는 햄버거 단추라고도 함)를 누른 후 **회사 변경** 을 누릅니다.

    ![법인 변경.](media/mobile-app-change-comp.png "법인 변경")

1. **작업 영역** 페이지에서 작업할 작업 영역을 선택하여 엽니다.

    ![자산 관리 모바일 작업 영역.](media/mobile-app-asset-workspace.png "자산 관리 모바일 작업 영역")

## <a name="work-with-the-asset-management-mobile-workspace"></a>자산 관리 모바일 작업 영역으로 작업

**자산 관리** 모바일 작업 영역으로 작업하는 방법에 대한 자세한 내용은 [자산 관리 모바일 작업 영역 사용](asset-management-mobile-workspace.md)을 참조하세요.

Finance and Operations(Dynamics 365) 모바일 앱에 대한 자세한 내용은 [모바일 앱 홈 페이지](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]