---
title: 청구서 승인 모바일 작업 영역
description: 이 항목에서는 청구서 승인 모바일 작업 영역에 대한 정보를 제공합니다.
author: abruer
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0d19e99776f04eab28eb7371bc0ac90ac046b62af0ad785fd3ab28309cae43ab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460782"
---
# <a name="invoice-approvals-mobile-workspace"></a>청구서 승인 모바일 작업 영역

[!include [banner](../includes/banner.md)]

이 항목에서는 **청구서 승인** 모바일 작업 영역에 대한 정보를 제공합니다. 이 작업 공간은 공급업체 송장 헤더 워크플로 프로세스를 통해 할당된 송장의 목록을 제공합니다. 

이 모바일 작업 공간은 재무 및 운영 모바일 앱과 함께 사용하기 위한 것입니다.

## <a name="overview"></a>개요

**송장 승인** 모바일 작업 공간을 사용하면 미지급금 사무원과 관리자가 공급업체 송장 헤더 워크플로 프로세스의 일부로 할당된 송장을 볼 수 있습니다. 송장 정보는 물론 라인 및 분배 상세기록까지 확인하여 정보에 입각한 승인 결정을 내리는 데 도움이 됩니다. 작업 공간에서 워크플로 프로세스를 통해 송장을 이동하는 작업을 수행할 수 있습니다. 

## <a name="prerequisites"></a>전제 조건

이 모바일 작업 공간을 사용하려면 다음 전제 조건이 충족되어야 합니다.

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
<td>Microsoft Dynamics 365 Finance를 조직에 배포해야 합니다.</td>
<td>시스템 관리자</td>
<td><a href="../deployment/deploy-demo-environment.md">데모 환경 배포</a>를 참조하세요.
</td>
</tr>
<tr class="even">
<td><strong>송장 승인</strong> 모바일 작업 공간을 게시해야 합니다.</td>
<td>시스템 관리자</td>
<td><a href="publish-mobile-workspace.md">모바일 작업 영역 게시</a>를 참조하십시오.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>모바일 앱 다운로드 및 설치

재무 및 운영 모바일 앱 다운로드 및 설치:

-   [Android 휴대폰의 경우](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhones의 경우](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>모바일 앱에 로그인

1.  모바일 장치에서 앱을 시작합니다.
2.  Microsoft Dynamics 365 URL을 입력하십시오.
3.  처음 로그인하면 사용자 이름과 암호를 입력하라는 메시지가 표시됩니다. 자격 증명을 입력합니다.
4.  로그인하면 회사에 사용 가능한 작업 영역이 표시됩니다. 시스템 관리자가 나중에 새 작업 영역을 게시하는 경우 모바일 작업 영역 목록을 새로 고쳐야 합니다.

    [![당겨서 새로 고침합니다.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>송장 승인 모바일 작업 영역을 사용하여 송장 승인
1.  모바일 디바이스에서 **청구서 승인** 작업 영역을 선택합니다.
2.  공급업체 송장 헤더 워크플로 프로세스에 의해 할당된 송장을 선택합니다.
3.  **인보이스 세부정보** 페이지에서 공급업체 및 날짜 정보와 같은 송장 헤더 정보를 검토합니다.
4.  송장의 라인을 선택하면 **청구서 라인 세부 정보** 에서 송장에 대한 자세한 정보를 볼 수 있습니다.
5.  **송장 라인 상세기록** 보기에서 **분포** 를 선택하여 라인 분포를 표시합니다. 여기에서 송장 라인에 대한 회계를 볼 수 있습니다. 표시되는 정보에는 재무 차원과 기본 계정이 포함됩니다.
6.  **송장 상세기록** 페이지에서 **분포** 를 선택하여 모든 분포를 표시합니다. 여기에서 전체 송장에 대한 회계를 볼 수 있습니다. 표시되는 정보에는 재무 차원과 기본 계정이 포함됩니다. 
7.  **첨부 파일** 을 선택하여 송장에 첨부된 메모나 파일을 봅니다.
8.  **인보이스 세부정보** 페이지에서 적절한 워크플로 작업을 선택하여 검토 프로세스를 완료합니다.
9.  **완료** 를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]