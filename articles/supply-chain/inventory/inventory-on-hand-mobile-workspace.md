---
title: 재고 보유 모바일 작업 영역
description: 이 토픽에서는 재고 보유 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 통해 언제 어디서나 예약 및 사용 가능한 재고에 대한 모바일 인사이트를 얻을 수 있습니다.
author: yufeihuang
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yufeihuang
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9e67e16acc8ed72d571e9010131723038c8586a9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448669"
---
# <a name="inventory-on-hand-mobile-workspace"></a>재고 보유 모바일 작업 영역

[!include [banner](../includes/banner.md)]

이 토픽에서는 **재고 보유** 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 통해 언제 어디서나 예약 및 사용 가능한 재고에 대한 인사이트를 얻을 수 있습니다.

이 모바일 작업 공간은 재무 및 운영 모바일 앱과 함께 사용하기 위한 것입니다.

## <a name="overview"></a>개요
일반적으로 회사는 매일 여러 번 선적하고 여러 번 재고를 받습니다. 이러한 이동은 현재고 상태를 지속적으로 변경합니다. **재고 보유** 모바일 작업 영역을 통해 회사 간 보유 재고 상태를 확인할 수 있으므로 선택한 모바일 디바이스의 재고 데이터에 대한 최신 인사이트를 얻을 수 있습니다. 창고, 구매, 판매, 제조, 관리 또는 기타 역할에 관계없이 언제 어디서나 보유 재고 데이터에 액세스할 수 있습니다. 

모바일 작업 영역은 시설 전체의 현재 상태를 즉시 볼 수 있도록 합니다. 이를 통해 시설 전체의 현재고, 현재 자재 예약 및 예약되지 않은 현재고를 볼 수 있습니다. 또한 품목 번호를 입력하여 현재고를 조회하고 현재고 제품 또는 변형에 대해 필터링된 검색을 수행할 수 있습니다. 

특히 모바일 작업 영역은 다음과 같은 기능을 제공합니다.

-   제품 번호 또는 제품 이름으로 검색하여 현재 재고 상태를 볼 제품을 찾을 수 있습니다.
-   선택한 제품에 대해 다음 정보를 볼 수 있습니다.

    -   사이트별 현재고
    -   창고별 현재고
    -   위치별 현재고
    -   배치당 현재고(배치 관리 제품의 경우)
    -   재고 상태별 현재고
    
-   제품 현재고는 다음과 같은 방식으로 표시됩니다.

    -   실제 재고별(이 보기는 총 수량을 나타냄.)
    -   실제 예약별(이 보기는 총 수량을 나타냄.)
    -   가용 실물별(이 보기는 예약이 없는 가용 금액을 나타냄)

## <a name="prerequisites"></a>전제 조건
전제 조건은 조직에 배포된 Supply Chain Management 버전에 따라 다릅니다.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Supply Chain Management를 사용하는 경우 전제 조건
Supply Chain Management가 조직에 배포된 경우 시스템 관리자는 **재고 보유** 모바일 작업 영역을 게시해야 합니다. 지침은 [모바일 작업 영역 게시](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)를 참조하세요.

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>플랫폼 업데이트 3 이상을 사용하는 경우 전제 조건 
플랫폼 업데이트 3 이상이 배포된 경우 시스템 관리자는 다음 전제 조건을 완료해야 합니다. 

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

<td>KB 4013633은 <strong>현재고</strong> 모바일 작업 영역이 포함된 X++ 업데이트 또는 메타데이터 핫픽스입니다. 이 KB 4013633을 구현하려면 시스템 관리자가 다음 단계를 따라야 합니다.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Microsoft Dynamics Lifecycle Services(LCS)에서 메타데이터 핫픽스를 다운로드합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">메타데이터 핫픽스를 설치합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package"><strong>SCMMobile</strong> 모델이 포함된 배포 가능한 패키지를</a> 만든 다음 배포 가능한 패키지를 LCS에 업로드합니다.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">배포 가능한 패키지를 적용합니다</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td><strong>재고 보유</strong> 모바일 작업 영역을 게시합니다.</td>
<td>시스템 관리자</td>
<td><a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">모바일 작업 공간 게시</a>를 참조하세요.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>모바일 앱 다운로드 및 설치

재무 및 운영 모바일 앱 다운로드 및 설치:

-   [Android 휴대폰용](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone의 경우](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>모바일 앱에 로그인

1.  모바일 디바이스에서 앱을 시작합니다.
2.  Dynamics 365 URL을 입력합니다.
3.  처음 로그인하면 사용자 이름과 암호를 묻는 메시지가 표시됩니다. 자격 증명을 입력합니다.
4.  로그인하면 회사에서 사용 가능한 작업 영역이 표시됩니다. 시스템 관리자가 나중에 새 작업 영역을 게시하는 경우 모바일 작업 영역 목록을 새로 고쳐야 합니다.

    [![당겨서 새로 고침합니다.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>현재고 모바일 작업 영역을 사용하여 제품의 현재고를 조회합니다.

1.  모바일 디바이스에서 **재고 보유** 작업 영역을 선택합니다.

2.  **항목에 대해 현재고 확인** 을 선택합니다. 오프라인 사용을 위해 앱에 로드된 제품 목록이 표시됩니다. 기본적으로 50개 항목이 로드되지만 개발자가 이 수를 변경할 수 있습니다. 자세한 내용은 개발자가 [모바일 플랫폼](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)을 참조해야 합니다.
3.  항목이 목록에 없으면 **추가 검색** 을 선택합니다. 제품 번호로 검색하거나 제품 이름으로 검색으로 전환하세요.

4.  제품을 선택합니다. 항목에 이미지가 있는 경우 이미지가 표시됩니다.
5.  다음 옵션 중 하나를 선택하여 현재고 상태를 조회합니다.

    -   사이트별 현재고 보기
    -   창고별 현재고 보기
    -   위치별 현재고 보기
    -   배치당 현재고 보기(배치 제어 제품의 경우)
    -   재고 상태별 현재고 보기

    제품 현재고는 다음과 같은 방식으로 표시됩니다.
    -   실제 재고별(이 보기는 총 수량을 나타냄.)
    -   실제 예약별(이 보기는 총 수량을 나타냄.)
    -   가용 실물별(이 보기는 예약이 없는 가용 금액을 나타냄)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]