---
title: 비용 관리 모바일 작업 영역
description: 이 토픽에서는 비용 관리 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 통해 비용 센터 관리자는 언제 어디서나 비용 센터 실적에 대한 정보를 볼 수 있습니다.
author: AndersGirke
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cd86fdf640e59885e5e8aea841dc1c1c9604825b0f18d3b741c5a2777f8e9ff8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450289"
---
# <a name="cost-controlling-mobile-workspace"></a>비용 관리 모바일 작업 영역

[!include [banner](../includes/banner.md)]

이 토픽에서는 **비용 관리** 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 통해 비용 센터 관리자는 언제 어디서나 비용 센터 실적에 대한 정보를 볼 수 있습니다.

이 모바일 작업 영역은 재무 및 운영 모바일 앱과 함께 사용하기 위한 것입니다.

## <a name="overview"></a>개요
**비용 관리** 모바일 작업 영역은 실제 비용과 예산 비용을 비교하여 비용 센터의 현재 성과를 즉시 볼 수 있도록 합니다. 개별 비용 요소의 상태로 드릴다운할 수 있습니다.

예를 들어 직원이 국제 회의 초대장을 받았지만 조직에서 모든 여행 경비를 부담해야 합니다. 직원이 관리자에게 회의에 참석할 수 있는지 묻습니다. 관리자는 모바일 장치에서 **비용 관리** 모바일 작업 영역을 열어 직원이 회의에 참석할 수 있는 예산이 있는지 확인합니다.

### <a name="data-security"></a>데이터 보안
**비용 관리** 모바일 작업 영역의 데이터는 사용자 자격 증명을 통해 보호됩니다. 비용 센터 관리자는 자신의 비용 센터에 대한 데이터만 볼 수 있습니다. 액세스 수준 보안은 **원가 회계** 모듈에서 관리됩니다.

원가 회계사는 **원가 회계** 모듈에서 **비용 관리** 모바일 작업 영역의 구성을 정의합니다. 작업 영역이 모바일 앱에 게시되면 앱에서 사용할 수 있습니다. 따라서 조직의 모든 비용 센터 관리자는 동일한 형식으로 데이터를 볼 수 있습니다.

### <a name="actions-views-and-links"></a>작업, 보기 및 링크
**비용 관리** 모바일 작업 영역은 다음 작업, 보기 및 링크를 제공합니다.

-   **작업:**

    -   **구성 선택** 을 사용하여 레이아웃을 선택합니다.
    -   **비용 개체 선택** 을 사용하여 데이터를 필터링할 비용 센터를 선택합니다.
    
        > [!NOTE]
        > 목록에 표시되는 비용 센터는 **원가 회계** 모듈에서 부여된 액세스 권한에 따라 다릅니다.

-   **보기:** **원가 회계** 모듈에서 선택한 작업과 구성을 기반으로 카드에서 다음 정보를 볼 수 있습니다.

    -   실제 대 예산 비교(현재 기간)
    -   실제 대 수정 예산 비교(현재 기간)
    -   실제 대 예산 비교(이전 기간)
    -   실제 대 수정 예산 비교(이전 기간)
    -   실제 대 예산 비교(연초부터 현재까지)
    -   실제 대 수정 예산 비교(연초부터 현재까지)

    실제, 예산, 편차 및 편차 %와 같은 금액이 모든 카드에 표시됩니다.

-   **링크:**

    -   현재 기간 세부 정보
    -   이전 기간 세부 정보
    -   연초부터 현재까지 세부정보

    링크를 선택하면 각 비용 요소에 대한 카드가 표시됩니다. 실제, 예산, 예산 편차, 예산 편차 %, 수정 예산, 수정 예산 편차 및 수정 예산 편차 %와 같은 금액이 모든 카드에 표시됩니다.
    
    [![비용 요소에 대한 카드입니다.](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>전제 조건
전제 조건은 조직에 배포된 Microsoft Dynamics 365 버전에 따라 다릅니다.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a>Microsoft Dynamics 365 Finance를 사용하는 경우 필수 구성 요소
Finance가 조직에 배포된 경우 시스템 관리자는 **비용 관리** 모바일 작업 영역을 게시해야 합니다. 지침은 [모바일 작업 영역 게시](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)를 참조하십시오.

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a>플랫폼 업데이트 3 이상이 포함된 버전 1611을 사용하는 경우 전제 조건
플랫폼 업데이트 3 이상이 포함된 버전 1611이 조직에 배포된 경우 시스템 관리자는 다음 전제 조건을 완료해야 합니다.

<table>
<thead>
<tr class="header">
<th>전제 조건</th>
<th>역할</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>KB 4013633을 구현합니다.</td>
<td>시스템 관리자</td>

<td>KB 4013633은 <strong>비용 관리</strong> 모바일 작업 영역이 포함된 X++ 업데이트 또는 메타데이터 핫픽스입니다. 이 KB 4013633을 구현하려면 시스템 관리자가 다음 단계를 따라야 합니다.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Microsoft Dynamics Lifecycle Services(LCS)에서 메타데이터 핫픽스를 다운로드합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">메타데이터 핫픽스를 설치합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package"><strong>SCMMobile</strong> 모델이 포함된 배포 가능한 패키지를</a> 만든 다음 배포 가능한 패키지를 LCS에 업로드합니다.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">배포 가능한 패키지를 적용합니다</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td><strong>비용 관리</strong>모바일 작업 영역을 게시합니다.</td>
<td>시스템 관리자</td>
<td><a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">모바일 작업 공간 게시</a>를 참조하십시오.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>모바일 앱 다운로드 및 설치
재무 및 운영 모바일 앱 다운로드 및 설치:

-   [Android 휴대폰용](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhones용](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>모바일 앱에 로그인

1.  모바일 디바이스에서 앱을 시작합니다.
2.  Dynamics 365 URL을 입력합니다.
3.  처음 로그인하면 사용자 이름과 암호를 묻는 메시지가 표시됩니다. 자격 증명을 입력합니다.
4.  로그인하면 회사에서 사용 가능한 작업 영역이 표시됩니다. 시스템 관리자가 나중에 새 작업 영역을 게시하는 경우 모바일 작업 영역 목록을 새로 고쳐야 합니다.

[![당겨서 새로 고침합니다.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>비용 관리 모바일 작업 공간을 사용하여 비용 센터의 성과 보기

1.  모바일 디바이스에서 **비용 관리** 작업 영역을 선택합니다.
2.  **비용 개체 관리** 를 선택합니다.
3.  **작업** 을 선택합니다.
4.  **구성 선택** 을 선택하여 비용 관리 레이아웃을 선택합니다.
5.  **완료** 를 선택합니다.
6.  **작업** 을 선택합니다.
7.  **비용 개체 선택** 을 선택하여 액세스 권한이 부여된 비용 센터를 선택합니다.
8.  **완료** 를 선택합니다.
9.  비용 센터의 전체 성능을 봅니다.
10. **현재 기간에 대한 세부 정보** 링크를 선택합니다.
11. 개별 비용 요소의 성과를 봅니다.
12. 특정 비용 요소를 검색할 수도 있습니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]