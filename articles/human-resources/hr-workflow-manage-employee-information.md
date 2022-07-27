---
title: 워크플로를 사용하여 직원 정보 관리
description: 이 항목에서는 워크플로를 사용하여 직원 정보를 관리하는 방법에 관해 설명합니다.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d80ed49a4f423179997ac35562284a4e28af803f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452413"
---
# <a name="use-workflows-to-manage-employee-information"></a>워크플로를 사용하여 직원 정보 관리


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Human Resources에 대한 워크플로 기능을 사용하여 직원 정보를 관리하는 방법에 관해 설명합니다. 예를 들어 워크플로를 직위와 연결하고 직원이 레코드를 변경할 때 시작되는 승인 워크플로를 구성할 수 있습니다.

Human Resources에 대한 워크플로 기능은 Human Resources 활동을 관리하기 위한 다양한 워크플로를 제공합니다. 또한 특정 워크플로를 수정하고 보고 계층 구조와 연결하는 다양한 옵션을 사용할 수 있습니다. 여러 유형의 직원 정보에 대한 변경을 관리하는 데 도움이 되는 워크플로를 사용할 수 있습니다. 워크플로를 직위와 연결할 수 있습니다. 그런 다음 직원이 직원 레코드를 변경하면 새 정보를 저장하기 전에 승인이 필요한 워크플로가 시작됩니다. 워크플로는 변경을 효율적으로 관리하고 직원 데이터를 정확하게 유지하는 데 도움이 되도록 다음 유형의 정보에 대해 사전 정의됩니다.

-   식별 번호
-   과정
-   교육
-   이미지
-   대여 항목
-   전문 경험
-   프로젝트 경험
-   기술
-   책임자
-   Human Resources 작업
-   과정 등록

직원이 채용, 전환 또는 해고되면 워크플로에 검토 프로세스가 포함될 수 있습니다. 이러한 방식으로 문서를 수정하거나 작업 조건을 워크플로의 일부로 정의할 수 있습니다. 검토 프로세스가 완료되면 문서 또는 작업이 완료되고 워크플로가 최종 승인 단계로 이동합니다.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>워크플로를 직위 계층과 연결
구성하는 모든 계층 구조와 워크플로를 연결할 수 있습니다. 예를 들어 직위가 매트릭스 보고 계층 구조와 연결된 경우 특정 프로젝트의 비용을 해당 직위와 연결된 직원의 관리자 대신 프로젝트 리더에게 라우팅하는 워크플로를 구성할 수 있습니다. 새 워크플로를 만들거나 기존 워크플로를 수정하려면 **Human Resources 워크플로** 페이지에서 **새로 만들기** 를 선택합니다. 목록에서 워크플로를 선택하여 워크플로 디자이너를 엽니다. 디자이너를 사용하여 새 워크플로를 만들거나 기존 워크플로의 단계를 변경할 수 있습니다. 기존 워크플로를 변경하면 변경 내용이 새 버전으로 저장됩니다. 따라서 필요한 경우 언제든지 이전 버전으로 돌아갈 수 있습니다.

## <a name="configure-a-human-resources-workflow"></a>Human Resources 워크플로 구성
직원이 개인 ID 변경을 요청할 때 시작되는 기본 워크플로를 구성하려면 다음 단계를 따르세요.

1.  **Human Resources 워크플로** 페이지에서 **새로 만들기** 를 선택합니다.
2.  사용 가능한 워크플로 목록에서 **식별 번호** 를 선택합니다.
3.  **실행** 을 선택하여 워크플로 디자이너를 연 다음 메시지가 표시되면 사용자 이름과 암호를 입력합니다.
4.  워크플로 요소 목록에서 **식별 번호 승인** 요소를 디자이너 캔버스로 끌어서 놓습니다.
5.  승인 요소를 **시작** 및 **종료** 에 연결합니다.
6.  **요소 승인** 을 두 번 탭(또는 두 번 클릭)하고 길게 선택(또는 오른쪽 클릭)한 다음 **속성** 을 선택합니다.
7.  작업 항목 지침을 추가하려면 다음 단계를 따릅니다.

    1.  **할당** 을 선택한 다음 할당 유형에서 **계층 구조** 를 선택합니다.
    2.  **계층** 선택에서 **구성 가능한 계층** 을 선택합니다.
    3.  중지 조건을 추가하고 페이지를 닫습니다.

8.  추가 지침을 완료합니다(추가 경고가 없어야 함).
9.  **저장 및 닫기** 를 선택합니다. 대화 상자가 열리면 새 워크플로를 활성화하고 **활성화** 를 선택합니다.
10. **Human Resources** &gt; **직위** &gt; **직위 계층 유형** 으로 이동합니다.
11. **매트릭스** 를 선택합니다.
12. **작업자 식별 번호** 워크플로를 목록에 추가합니다.

## <a name="additional-resources"></a>추가 리소스

[주소 변경 보기 및 관리](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]
