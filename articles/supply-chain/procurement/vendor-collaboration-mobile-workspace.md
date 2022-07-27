---
title: 공급업체 협업 모바일 작업 영역
description: 이 항목에서는 공급업체 협력 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역은 공급업체가 승인을 위해 보낸 구매 주문에 대한 최신 정보를 유지하는 데 도움이 됩니다. 또한 신규 및 업데이트된 구매 주문 및 연락처에 대한 정보를 볼 수 있습니다.
author: Henrikan
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: efbd0afb0d84f76058b75126af200a9b10197559
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448960"
---
# <a name="vendor-collaboration-mobile-workspace"></a>공급업체 협업 모바일 작업 영역

[!include [banner](../includes/banner.md)]

이 항목에서는 **공급업체 협력** 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 영역은 공급업체가 승인을 위해 보낸 구매 주문에 대한 최신 정보를 유지하는 데 도움이 됩니다. 또한 신규 및 업데이트된 구매 주문 및 연락처에 대한 정보를 볼 수 있습니다.

이 모바일 작업 공간은 재무 및 운영 모바일 앱과 함께 사용하기 위한 것입니다.

## <a name="overview"></a>개요 
**공급업체 협업** 모바일 작업 공간은 공급업체에 새로운 구매 주문에 대한 정보를 제공하므로 구매 주문을 보고 웹 클라이언트에서 이에 응답할 수 있습니다. 

>[!NOTE]
> 모바일 작업 공간은 공급업체 협업 웹 인터페이스를 대체하는 것이 아니라 보완하는 역할을 해야 합니다. 

공급업체는 **공급업체 협업** 모바일 작업 공간을 사용하여 승인을 위해 전송된 새 구매 주문을 볼 수 있습니다. 제품, 수량, 요청된 배송 날짜와 같은 구매 주문 정보를 보여줍니다. 각 공급업체의 구성에 따라 가격 정보도 제공됩니다. 

공급업체로 로그인한 사용자는 어떤 구매 주문이 응답되었는지, 어떤 구매 주문이 아직 고객 조치를 기다리고 있는지 볼 수 있습니다. 예를 들어, 공급업체가 다른 배송 날짜를 제안했지만 고객이 아직 해당 날짜에 동의하지 않았기 때문에 구매 주문이 고객 조치를 기다리고 있을 수 있습니다. 공급업체는 확인되었지만 아직 배달되지 않은 구매 주문 목록도 볼 수 있습니다. 

구매 주문에 응답하려면 공급업체는 웹 클라이언트에서 사용할 수 있는 공급업체 협업 웹 인터페이스를 사용해야 합니다. 여기에서 공급업체는 문서 첨부, 라인별 배송 주소, 공급업체와 관련된 요금과 같은 주문에 대한 추가 정보를 얻을 수도 있습니다. 

특별한 보안 역할이 있는 공급업체는 공급업체 계정에 등록된 담당자를 볼 수 있습니다. 동일한 보안 역할을 통해 공급업체는 제출된 사용자 요청의 상태를 볼 수 있습니다. 

웹 클라이언트의 공급업체 협업 웹 인터페이스를 사용하여 새 연락처를 만들고 새 사용자 요청을 제출해야 합니다. 

**공급업체 협업** 모바일 작업 공간을 통해 공급업체는 다음 작업을 수행할 수 있습니다.

-   공급업체에 전송된 새 구매 주문을 봅니다.
-   공급업체가 응답했으며 고객 조치를 기다리고 있는 구매 주문을 봅니다.
-   확인되었지만 아직 완전히 접수되지 않은 구매 주문을 봅니다.
-   공급업체 계정에 등록된 담당자 정보를 봅니다. (이 작업에는 추가 보안 역할이 필요합니다.)
-   공급업체가 제출한 사용자 요청에 대한 정보를 보고 요청 상태를 따릅니다. (이 작업에는 추가 보안 역할이 필요합니다.)

## <a name="prerequisites"></a>전제 조건
전제 조건은 조직에 배포된 Microsoft Dynamics 365 버전에 따라 다릅니다.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Supply Chain Management를 사용하는 경우 전제 조건
Supply Chain Management가 조직에 배포된 경우 시스템 관리자는 **공급업체 협업** 모바일 작업 영역을 게시해야 합니다. 지침은 [모바일 작업 영역 게시](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md)를 참조하세요.

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
<td>&#39;플랫폼 업데이트 3을 사용하는 경우 KB 3216943을 구현해야 합니다.</td>
<td>시스템 관리자</td>
<td>&#39;KB 3216943은 플랫폼 업데이트 3을 사용하는 경우 필요한 바이너리 업데이트입니다. 이 KB를 구현하려면 시스템 관리자가 다음 단계를 따라야 합니다.
<ol>
<li>Microsoft Dynamics LCS(Lifecycle Services)에서 KB 3216943을 다운로드합니다.</li>
<li>배포 가능한 패키지로 제공되는 바이너리 업데이트를 설치합니다. 배포 가능한 패키지를 적용하는 방법에 대한 자세한 내용은 <a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">배포 가능한 패키지 적용</a>을 참조하세요.</li>
</ol></td>
</tr>
<tr class="even">
<td>KB 4013633를 구현해야 합니다.</td>
<td>시스템 관리자</td>
<td>KB 4013633은 <strong>현재고</strong> 모바일 작업 영역이 포함된 X++ 업데이트 또는 메타데이터 핫픽스입니다. 이 KB 4013633을 구현하려면 시스템 관리자가 다음 단계를 따라야 합니다.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">LCS에서 메타데이터 핫픽스를 다운로드합니다</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">메타데이터 핫픽스를 설치합니다</a>.</li><li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package"><strong>SCMMobile</strong> 모델이 포함된 배포 가능한 패키지를</a> 만든 다음 배포 가능한 패키지를 LCS에 업로드합니다.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">배포 가능한 패키지를 적용합니다</a>.</li>
</ol></td>
</tr>
<tr class="odd">
<td><strong>공급업체 협엽</strong> 모바일 작업 공간을 게시해야 합니다.</td><td>시스템 관리자</td>
<td><a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">모바일 작업 공간 게시</a>를 참조하세요.</td>
</tr>
<tr class="even">
<td>공급업체 사용자는 웹 클라이언트에서 공급업체 협업 웹 인터페이스에 액세스할 수 있어야 하며 공급업체 협업 사용자를 설정해야 합니다.</td><td>구매 전문가 및 시스템 관리자</td>
<td>다음 주제의 단계에 따라 공급업체 협업 웹 인터페이스를 설정하고 사용하세요.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">공급업체 협업을 사용하여 외부 공급업체와 협력</a></li>
<li><a href="manage-vendor-collaboration-users.md">공급업체 협업 사용자 관리</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">공급업체 협업 설정 및 유지 관리</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">공급업체 협업을 사용하여 Supply Chain Managements에서 고객과 협력</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>모바일 앱 다운로드 및 설치

재무 및 운영 모바일 앱 다운로드 및 설치:

-   [Android 휴대폰의 경우](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone의 경우](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>모바일 앱에 로그인
1.  모바일 디바이스에서 앱을 시작합니다.
2.  Microsoft Dynamics 365 URL을 입력합니다.
4.  처음 로그인하면 사용자 이름과 암호를 묻는 메시지가 표시됩니다. 자격 증명을 입력합니다.
5.  로그인하면 회사에서 사용 가능한 작업 영역이 표시됩니다. 시스템 관리자가 나중에 새 작업 영역을 게시하는 경우 모바일 작업 영역 목록을 새로 고쳐야 합니다.

    [![당겨서 새로 고침합니다.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>공급업체 협업 모바일 작업 영역 사용
**공급업체 협업** 작업 영역을 선택하면 다음 옵션이 표시됩니다.

![공급업체 협업 모바일 작업 영역.](./media/vendor-collaboration-mobile-app.png)

**공급업체 협업** 작업 공간에는 다음 페이지가 포함됩니다.

### <a name="contacts"></a>연락처
**연락처** 페이지에서는 공급업체 계정에 대해 설정된 모든 연락처를 볼 수 있습니다. 연락처에 별칭이 있는 경우 연락처 이름, 기본 이메일 주소 및 사용자 별칭이 표시됩니다. 이 페이지에는 담당자의 사용자 계정이 활성 상태인지 여부도 표시됩니다. 연락처를 선택하면 해당 개인이 연락처인 법인과 같은 연락처 세부 정보가 표시됩니다. 전화번호나 대체 이메일 주소와 같은 연락처 정보도 표시됩니다.

### <a name="user-requests"></a>사용자 요청
**사용자 요청** 페이지에서는 공급업체 협업 웹 인터페이스를 통해 제출한 모든 사용자 요청을 볼 수 있습니다. 이러한 요청의 상태를 추적할 수도 있습니다. 사용자 요청을 선택하면 요청된 내용을 확인하고, 사용자를 추가 또는 비활성화하고, 보안을 변경하고, 사용자에 대해 요청된 보안 역할을 확인할 수 있습니다.

### <a name="purchase-orders-ready-for-review"></a>검토 준비가 된 구매 주문
**구매 주문 검토 준비** 페이지에서는 고객이 보냈지만 아직 응답하지 않은 모든 구매 주문을 볼 수 있습니다. 어떤 제품이 요청되었는지, 언제 배송되어야 하는지와 같은 주문에 대해 선택한 정보를 볼 수 있습니다. 공급업체의 구성에 따라 가격 정보도 제공됩니다.

구매 주문에 메모나 첨부 파일이 있는지 여부도 확인할 수 있습니다. 그러나 메모 및 첨부 파일을 열려면 웹 클라이언트에서 공급업체 협업 웹 인터페이스를 사용해야 합니다. 상세 내역과 함께 모든 라인을 보려면 **구매 주문 라인** 을 선택합니다. 각 라인에 대해 표시기는 메모 또는 첨부 파일이 있는지 여부 또는 배송 주소가 헤더에 표시된 배송 주소와 다른지 여부를 표시합니다.

구매 주문에 응답하려면 웹 클라이언트에서 공급업체 협업 웹 인터페이스를 사용해야 합니다.

### <a name="awaiting-customer-action"></a>고객의 조치를 기다리는 중
**고객의 조치를 기다리는 중** 페이지에서는 귀하 또는 회사에서 공급업체 협업에 액세스할 수 있는 다른 사람이 응답한 구매 주문을 찾을 수 있습니다. 구매 주문은 고객이 구매 주문에 대해 다음 작업 중 하나를 수행해야 하는 경우에만 이 목록에 표시됩니다.

-   구매 주문이 거부된 경우 고객은 원래 주문을 업데이트하거나 취소한 다음 다시 보내야 합니다. 구매 주문이 다시 전송되면 **고객의 조치를 기다리는 중** 페이지에 더 이상 표시되지 않습니다.
-   구매 주문이 변경 사항과 함께 수락된 경우 고객은 원래 주문을 업데이트한 다음 검토를 위해 다시 보내거나 요청된 변경 사항에 따라 주문을 업데이트한 다음 즉시 확인해야 합니다. 두 경우 모두 더 이상 구매 주문이 **고객의 조치를 기다리는 중** 페이지에 더 이상 표시되지 않습니다.
-   구매 주문이 수락되었지만 여전히 **고객의 조치를 기다리는 중** 페이지에 표시되는 경우 구매 주문이 수락될 때 자동으로 확인되지 않은 것입니다. 이제 구매 에이전트가 주문 상태를 **확인됨** 으로 변경하기를 기다리고 있습니다. 일반적으로 구매 주문은 공급업체가 주문을 수락하는 즉시 고객과 공급업체 간의 계약으로 간주됩니다. 따라서 **확인됨** 상태로의 업데이트는 일반적으로 형식에 불과합니다.

구매 주문을 선택하면 응답에 대한 추가 세부 정보가 나타납니다. 각 라인에 대한 라인 세부 정보 및 응답을 볼 수 있습니다. 라인 상태는 다음 응답 중 어떤 것이 제공되었는지 보여줍니다.

-   수락됨
-   거부됨
-   변경 사항이 수락됨
-   대체됨/대체
-   일정/일정 라인으로 분할

**납품** 필드가 **예** 또는 **아니요** 로 설정되어 라인이 납품될 것인지 여부를 나타냅니다. 다음과 같은 이유로 라인이 배달되지 않을 수 있습니다.

- 회선이 거부되었습니다.
- 대체가 이루어졌으며 원래 라인이 입고된 주문에서 요청한 대로 배송될 것으로 예상되지 않습니다.
- 라인이 여러 일정 라인으로 분할되었으며 원래 라인이 입고된 주문에서 요청한 대로 배달될 것으로 예상되지 않습니다.

주문 라인 응답에 대한 모든 변경 사항이 표시됩니다. 그러나 업로드된 메모 및 첨부 파일은 표시되지 않습니다. 메모 및 첨부 파일을 보려면 웹 클라이언트에서 공급업체 협업 웹 인터페이스를 사용해야 합니다.

### <a name="open-confirmed-orders"></a>확인된 주문 열기
고객이 구매 주문을 확인하면(즉, 구매 주문 상태가 **확인됨** 으로 변경됨) 미결 확정 주문에 나타납니다. 고객이 수신한 것으로 등록될 때까지 목록에 남아 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]