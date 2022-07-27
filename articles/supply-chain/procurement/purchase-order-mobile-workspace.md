---
title: 구매 주문 승인 모바일 작업 영역
description: 이 항목에서는 구매 주문을 보고 작업을 통해 응답할 수 있는 구매 주문 승인 모바일 작업 영역에 대한 정보를 제공합니다. 예를 들어 구매 주문을 승인하거나 거부할 수 있습니다.
author: Henrikan
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fc88f20b50e034f2f27b7e2576fe6a4bb3486e23
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448309"
---
# <a name="purchase-order-approval-mobile-workspace"></a>구매 주문 승인 모바일 작업 영역

[!include [banner](../includes/banner.md)]

이 항목에서는 **구매 주문 승인** 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역을 통해 구매 주문을 보고 작업을 통해 주문에 응답할 수 있습니다. 예를 들어 구매 주문을 승인하거나 거부할 수 있습니다.
 
## <a name="overview"></a>개요 
승인이 필요한 구매 주문은 승인 워크플로를 거칩니다. 워크플로에는 한 명 이상의 사람이 조치를 취해야 하는 다양한 단계가 포함될 수 있습니다. 예를 들어, 한 사람이 작업을 완료하거나 구매 주문을 승인해야 할 수 있습니다. 

**구매 주문 승인** 모바일 작업 영역을 사용하면 모바일 디바이스에서 구매 주문을 쉽게 보고 응답할 수 있습니다. 이 작업 영역을 사용하면 웹 클라이언트에서 수행할 수 있는 것과 동일한 워크플로 작업을 수행할 수도 있습니다.

## <a name="prerequisites"></a>전제 조건
전제 조건은 조직에 배포된 Supply Chain Management 버전에 따라 다릅니다.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Supply Chain Management를 사용하는 경우 전제 조건 
Supply Chain Management가 조직에 배포된 경우 시스템 관리자는 **구매 주문 승인** 모바일 작업 영역을 게시해야 합니다. 지침은 [모바일 작업 영역 게시](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)를 참조하세요.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>플랫폼 업데이트 3 이상에서 Microsoft Dynamics 365 for Operations 버전 1611을 사용하는 경우 전제 조건
플랫폼 업데이트 3 이상이 포함된 Microsoft Dynamics 365 for Operations 버전 1611이 조직에 배포된 경우 시스템 관리자는 다음 사전 요구 사항을 완료해야 합니다. 

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
<td>KB 4017918을 구현합니다.</td>
<td>시스템 관리자</td>
<td>KB 4017918은 <strong>구매 주문 승인</strong> 모바일 작업 영역이 포함된 X++ 업데이트 또는 메타데이터 핫픽스입니다. 이 KB 4017918을 구현하려면 시스템 관리자가 다음 단계를 따라야 합니다.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Microsoft Dynamics Lifecycle Services(LCS)에서 메타데이터 핫픽스를 다운로드합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">메타데이터 핫픽스를 설치합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package"><strong>SCMMobile</strong> 모델이 포함된 배포 가능한 패키지를</a> 만든 다음 배포 가능한 패키지를 LCS에 업로드합니다.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">배포 가능한 패키지를 적용합니다</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td><strong>구매 주문 승인</strong> 모바일 작업 영역을 게시합니다.</td>
<td>시스템 관리자</td>
<td><a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">모바일 작업 공간 게시</a>를 참조하세요.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>모바일 앱 다운로드 및 설치
재무 및 운영 모바일 앱 다운로드 및 설치:

- [Android 휴대폰용](https://go.microsoft.com/fwlink/?linkid=850662)
- [iPhone의 경우](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>모바일 앱에 로그인

1. 모바일 디바이스에서 앱을 시작합니다.
2. Microsoft Dynamics 365 URL을 입력합니다.
3. 처음 로그인하면 사용자 이름과 암호를 묻는 메시지가 표시됩니다. 자격 증명을 입력합니다.
4. 로그인하면 회사에서 사용 가능한 작업 영역이 표시됩니다. 시스템 관리자가 나중에 새 작업 영역을 게시하는 경우 모바일 작업 영역 목록을 새로 고쳐야 합니다.

![사용 가능한 작업 공간 목록에서 구매 주문 승인 작업 공간.](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>나에게 할당된 주문 보기
1. 모바일 디바이스에서 **구매 주문 승인** 작업 영역을 선택합니다.
2. **나에게 할당된 주문** 을 선택하여 구매 주문 승인 워크플로에서 조치를 취하도록 요청받은 모든 구매 주문을 봅니다.
3. 주문을 선택합니다. **주문 세부 정보** 페이지에서 주문 헤더 정보와 라인을 볼 수 있습니다. 워크플로 작업에서 지침을 찾을 수도 있습니다.
4. **회계 분포** 를 선택하여 **헤더 회계 분포** 페이지를 엽니다.
5. **주문 세부 정보** 페이지로 돌아가 라인을 선택합니다. 주문 라인 세부 정보에서 라인별 회계 분포를 탐색할 수도 있습니다.

## <a name="complete-an-action-on-the-purchase-order"></a>구매 주문에 대한 작업 완료
자신에게 할당된 구매 주문서를 보고 워크플로 지침을 읽은 후에는 조치를 취할 준비가 된 것입니다.

1. 모바일 디바이스에서 **구매 주문 승인** 작업 영역을 선택합니다.
2. **나에게 할당된 주문** 을 선택하여 구매 주문 승인 워크플로에서 조치를 취하도록 요청받은 모든 구매 주문을 봅니다.
3. 주문을 선택하고 세부 정보 페이지를 봅니다.
4. **작업** 을 선택하여 사용 가능한 작업을 표시합니다. 사용 가능한 작업은 할당된 작업에 따라 다릅니다.

    | 작업 동작    | 승인 작업  |
    |----------------|------------------|
    | 완료       | 승인          |
    | 반환         | 거부           |
    | 변경 요청 | 변경 요청   |
    | 대리자       | 대리자         |

5. 적절한 작업을 선택하세요.
6. **작업 완료** 페이지에서 댓글을 입력합니다. **위임** 작업을 선택한 경우 작업을 위임할 사용자를 선택해야 합니다.
7. **완료** 를 선택합니다. 작업 영역을 새로 고치면 구매 주문이 더 이상 목록에 없습니다. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]