---
title: 모바일 앱 홈 페이지
description: 이 항목에서는 재무 및 운영(Dynamics 365) 모바일 앱에 대해 설명하고 조직에서 이를 구현하는 데 도움이 되는 리소스에 대한 링크를 제공합니다.
author: ChrisGarty
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: intro-internal
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 8a91f603b4dd058341110c59039a6d3c782e06ee768fbf0e7f94e9527a6354ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460784"
---
# <a name="mobile-app-home-page"></a>모바일 앱 홈 페이지

[!include [banner](../includes/banner.md)]

이 항목에서는 **재무 및 운영(Dynamics 365)** 모바일 앱에 대해 설명하고 조직에서 이를 구현하는 데 도움이 되는 리소스에 대한 링크를 제공합니다.

## <a name="overview"></a>개요

모바일 앱을 사용하면 조직에서 모바일 장치에서 비즈니스 프로세스를 사용할 수 있습니다. IT 관리자가 조직의 모바일 작업 공간을 활성화하면 사용자는 앱에 로그인하여 모바일 장치에서 즉시 비즈니스 프로세스를 실행할 수 있습니다. 모바일 앱에는 생산성을 높이는 데 도움이 될 수 있는 다음과 같은 기능이 포함되어 있습니다.

- 사용자는 간헐적인 네트워크 연결이 있거나 모바일 장치가 완전히 오프라인 상태인 경우에도 비즈니스 데이터를 보고 편집하고 작업을 수행할 수 있습니다. 장치가 네트워크 연결을 다시 설정하면 오프라인 데이터 작업이 자동으로 동기화됩니다.
- IT 관리자 또는 개발자는 조직에 맞게 조정된 모바일 작업 공간을 구축하고 게시할 수 있습니다. 앱은 기존 코드 자산을 사용합니다. 따라서 유효성 검사 절차, 비즈니스 논리 또는 보안 구성을 다시 구현할 필요가 없습니다.
- IT 관리자 또는 개발자는 웹 클라이언트에 포함된 포인트 앤 클릭 작업 공간 디자이너를 사용하여 모바일 작업 공간을 쉽게 디자인할 수 있습니다.
- IT 관리자 또는 개발자는 선택적으로 비즈니스 논리 확장성 프레임워크를 사용하여 작업 영역의 오프라인 기능을 최적화할 수 있습니다. 장치가 오프라인 상태인 동안에도 데이터가 계속 처리되기 때문에 장치가 네트워크에 지속적으로 연결되어 있지 않더라도 모바일 시나리오는 풍부하고 유동적입니다.

## <a name="elements-of-the-mobile-app"></a>모바일 앱의 요소
모바일 앱의 탐색은 대시보드, 작업 영역, 페이지 및 작업의 네 가지 기본 개념으로 구성됩니다. 

[![모바일 앱의 탐색 개념.](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. 앱을 시작하면 **대시보드** 로 이동합니다.
2. 대시보드에서 게시된 **작업 영역** 목록을 볼 수 있습니다.
3. 각 작업 공간에서 해당 작업 영역에서 사용할 수 있는 **페이지** 목록을 볼 수 있습니다.
4. 페이지에서 여러 작업을 수행할 수 있습니다. 여기 예시들이 있습니다 :

    - 자세한 데이터를 봅니다.
    - 엔티티 세부 정보 또는 라인과 같은 관련 데이터에 대한 다른 페이지로 이동합니다.
    - 해당 페이지에서 사용할 수 있는 **작업** 목록을 봅니다. 작업을 통해 기존 데이터를 생성하거나 편집할 수 있습니다.

## <a name="implementation-process"></a>구현 프로세스
다음 그림은 Microsoft에서 제공하는 모바일 작업 영역과 사용자 지정 모바일 작업 영역을 모두 구현하는 프로세스를 보여줍니다. 

[![모바일 앱 구현 프로세스.](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

다음 표에는 Microsoft에서 제공하는 모바일 작업 영역과 사용자 지정 모바일 작업 영역을 모두 구현하는 데 도움이 되는 리소스에 대한 링크가 포함되어 있습니다. 첫 번째 열의 숫자는 이전 그림의 번호가 매겨진 단계에 해당합니다.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>역할</th>
<th>작업</th>
<th>작업을 완료하는 데 도움이 되는 리소스</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>시스템 관리자</td>
<td>조직에서 재무 및 운영 앱을 구현합니다.</td>
<td><ul><li>아직 Microsoft Dynamics 365 버전을 배포하지 않은 경우&#39;<a href="../deployment/deploy-demo-environment.md">데모 환경 배포</a>를 참조하세요.</li><li>사용할 수 있는 모바일 작업 영역 목록을 보려면 <a href="mobile-workspaces-released.md">최근 출시된 모바일 작업 공간</a>을 참조하세요.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>시스템 관리자</td>
<td><strong>Microsoft Dynamics 365 for Operations 버전 1611을 사용하는 경우:</strong>&#39; Microsoft에서 제공하는 모바일 작업 영역을 활성화하는 KB를 다운로드하고 설치합니다.</td>
<td>자세한 내용은 다음 토픽을 참조하세요.
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">비용 관리 모바일 작업 공간</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">재고 보유 모바일 작업 공간</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">판매 주문 모바일 작업 영역</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">공급업체 협업 모바일 작업 영역</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">프로젝트 시간 입력 모바일 작업 공간</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">비용 관리 모바일 작업 영역</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>시스템 관리자</td>
<td>Microsoft에서 제공하는 모바일 작업 영역을 게시합니다.</td>
<td><a href="publish-mobile-workspace.md">모바일 작업 공간 게시</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>개발자 또는 ISV(독립 소프트웨어 공급업체)</td>
<td>모바일 플랫폼을 사용하여 맞춤형 모바일 작업 공간을 만드세요.</td>
<td><a href="platform/mobile-platform-home-page.md">모바일 플랫폼</a></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>사용자 지정 모바일 작업 공간이 포함된 배포 가능한 패키지를 만들고 패키지를 Microsoft Dynamics Lifecycle Services(LCS)에 업로드합니다.</td>
<td><a href="../deployment/create-apply-deployable-package.md">배포 가능한 패키지 만들기</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>시스템 관리자</td>
<td>ISV(독립 소프트웨어 공급업체)에서 제공하는 사용자 지정 작업 영역이 포함된 배포 가능한 패키지를 적용합니다.</td>
<td><a href="../deployment/apply-deployable-package-system.md">배포 가능한 패키지 적용</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>시스템 관리자</td>
<td>ISV에서 제공하는 사용자 지정 모바일 작업 영역을 게시합니다.</td>
<td><a href="publish-mobile-workspace.md">모바일 작업 공간 게시</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>사용자</td>
<td>모바일 앱을 다운로드하여 설치합니다.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Android용 금융 및 운영 앱</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">iOS용 금융 및 운영 앱</a><BR/>
(Windows Phone 지원 안 됨)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>사용자</td>
<td>로그인하고 모바일 앱을 사용하세요. 앱에는 시스템 관리자가 게시한 모바일 작업 공간이 포함되어 있습니다.</td>
<td>Microsoft에서 제공되는 모바일 작업 영역 목록을 보려면 <a href="mobile-workspaces-released.md">최근 출시된 모바일 작업 공간</a>을 참조하세요.
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>문제 해결
[모바일 플랫폼 리소스](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]