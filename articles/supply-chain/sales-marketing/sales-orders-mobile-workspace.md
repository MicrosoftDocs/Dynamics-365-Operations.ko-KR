---
title: 판매 주문 모바일 작업 영역
description: 이 토픽에서는 판매 주문 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 사용하면 언제 어디서나 판매 주문에 대한 최신 정보를 얻을 수 있습니다.
author: Mirzaab
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 712b45cf1fd35de9f823af1bf89db9c4a572d61ebf7aa3e1fded16902c09557a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447181"
---
# <a name="sales-orders-mobile-workspace"></a>판매 주문 모바일 작업 영역

[!include [banner](../includes/banner.md)]

이 토픽에서는 **판매 주문** 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 사용하면 언제 어디서나 판매 주문에 대한 최신 정보를 얻을 수 있습니다. 

이 모바일 작업 공간은 재무 및 운영 모바일 앱과 함께 사용하기 위한 것입니다.

## <a name="overview"></a>개요
**판매 주문** 모바일 작업 영역을 사용하면 각 판매 주문에 대한 자세한 정보를 볼 수 있습니다. 이 정보에는 주문 상태, 고객의 연락처 정보, 주문 접수자의 연락처 정보가 포함됩니다. **판매 주문** 모바일 작업 영역에서는 판매 주문을 즉시 볼 수 있습니다. 모든 판매 주문을 보거나, 고객별 판매 주문을 보거나, 특정 판매 주문에 대한 정보를 볼 수 있습니다. 

모바일 작업 영역은 판매 주문을 심층적으로 분석하는 데 도움이 되는 두 가지 보기를 제공합니다.

### <a name="view-all-sales-orders"></a>모든 판매 주문 보기
이 보기에는 모든 판매 주문이 나열됩니다.

-   다음 필터 중 하나를 사용하여 보려는 판매 주문을 선택합니다.

    -   판매 주문으로 검색
    -   고객 계정으로 검색
    -   고객 이름으로 검색
    -   상태로 검색
    -   릴리스 상태로 검색
    -   생성 날짜 및 시간으로 검색
    
-   판매 주문을 선택하면 특정 주문의 세부 정보를 볼 수 있습니다. 특히 다음 정보를 볼 수 있습니다.

    -   고객 이름 및 주소 정보
    -   요청된 배송 날짜 및 확인된 배송 날짜와 같은 판매 주문에 대한 다양한 날짜
    -   주문 접수자의 연락처 정보
    -   고객 연락처 정보
    -   주문 라인
    -   판매 주문이 배송된 방법과 시기를 보여주는 배송

### <a name="view-orders-for-a-customer"></a>고객의 주문 보기
이 보기에는 고객별 판매 주문이 나열됩니다.

-   다음 필터 중 하나를 사용하여 고객의 주문을 봅니다.

    -   이름으로 검색
    -   계정으로 검색

-   고객을 선택하면 다음 정보를 볼 수 있습니다.

    -   고객 이름 및 그룹
    -   고객 연락처 정보
    -   고객 판매 주문 및 해당 판매 주문에 대한 세부 정보:
    
        -   고객 이름 및 주소 정보
        -   다양한 판매 주문 날짜
        -   주문 접수자의 연락처 정보
        -   고객 연락처 정보
        -   주문 라인
        -   판매 주문이 배송된 방법과 시기를 보여주는 배송

## <a name="prerequisites"></a>전제 조건
전제 조건은 조직에 배포된 Microsoft Dynamics 365 버전에 따라 다릅니다.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Supply Chain Management를 사용하는 경우 전제 조건 
Supply Chain Management가 조직에 배포된 경우 시스템 관리자는 **판매 주문** 모바일 작업 영역을 게시해야 합니다. 지침은 [모바일 작업 영역 게시](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)를 참조하세요.

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>플랫폼 업데이트 3 이상에서 Dynamics 365 for Operations 버전 1611을 사용하는 경우 전제 조건
플랫폼 업데이트 3 이상이 포함된 Dynamics 365 for Operations 버전 1611이 조직에 배포된 경우 시스템 관리자는 다음 사전 요구 사항을 완료해야 합니다. 

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

<td>KB 4013633은 <strong>판매 주문</strong> 모바일 작업 영역이 포함된 X++ 업데이트 또는 메타데이터 핫픽스입니다. 이 KB 4013633을 구현하려면 시스템 관리자가 다음 단계를 따라야 합니다.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Microsoft Dynamics Lifecycle Services(LCS)에서 메타데이터 핫픽스를 다운로드합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">메타데이터 핫픽스를 설치합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package"><strong>SCMMobile</strong> 모델이 포함된 배포 가능한 패키지를</a> 만든 다음 배포 가능한 패키지를 LCS에 업로드합니다.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">배포 가능한 패키지를 적용합니다</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td><strong>판매 주문</strong> 모바일 작업 영역을 게시합니다.</td>
<td>시스템 관리자</td>
<td><a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">모바일 작업 공간 게시</a>를 참조하세요.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>모바일 앱 다운로드 및 설치
재무 및 운영 모바일 앱 다운로드 및 설치:

-   [Android 휴대폰의 경우](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone의 경우](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>모바일 앱에 로그인

1.  모바일 디바이스에서 앱을 시작합니다.
2.  Dynamics 365 URL을 입력합니다.
3.  처음 로그인하면 사용자 이름과 암호를 묻는 메시지가 표시됩니다. 자격 증명을 입력합니다.
4.  로그인하면 회사에서 사용 가능한 작업 영역이 표시됩니다. 시스템 관리자가 나중에 새 작업 영역을 게시하는 경우 모바일 작업 영역 목록을 새로 고쳐야 합니다.

[![당겨서 새로 고침합니다.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>판매 주문 모바일 작업 영역을 사용하면 각 판매 주문에 대한 자세한 정보를 볼 수 있습니다.

1.  모바일 디바이스에서 **판매 주문** 작업 영역을 선택합니다.
2.  **고객의 주문 보기** 를 선택합니다.
3.  계정 또는 고객 이름 정보를 사용하여 고객을 찾습니다.
4.  고객을 선택합니다.
5.  **연락처 정보** 또는 **판매 주문** 을 선택합니다. **판매 주문** 을 선택하면 고객의 판매 주문 목록이 표시됩니다.
6.  **판매 주문** 을 선택합니다. 이제 판매 주문 라인에 대한 정보, 배송 정보, 고객 연락처 정보 및 주문 접수자의 연락처 정보를 볼 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]