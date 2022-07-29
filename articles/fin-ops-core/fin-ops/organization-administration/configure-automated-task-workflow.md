---
title: 워크플로에서 자동화된 작업 구성
description: 이번에는 자동화된 작업의 속성을 구성하는 방법에 대해 설명합니다.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7346649108824eb4e7209a2476456a469affa1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460808"
---
# <a name="configure-automated-tasks-in-a-workflow"></a>워크플로에서 자동화된 작업 구성

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이번에는 자동화된 작업의 속성을 구성하는 방법에 대해 설명합니다.

워크플로 편집기에서 자동화된 작업을 구성하려면 작업을 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 클릭하여 **속성** 페이지를 엽니다. 이후 다음 절차를 사용하여 자동화된 작업의 속성을 구성합니다.

## <a name="name-the-task"></a>작업 이름 지정

자동화된 작업의 이름을 입력하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
2. **이름** 필드에 작업의 고유한 이름을 입력합니다.

## <a name="specify-when-notifications-are-sent"></a>알림을 보낼 때 지정

자동화된 작업이 실행되거나 취소되면 사람들에게 알림을 보낼 수 있습니다. 알림이 전송되는 시기와 알림을 받을 대상을 지정하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **알림** 을 클릭합니다.
2. 알림을 보낼 이벤트 옆의 확인란을 선택합니다.

    - **실행** – 작업이 실행되면 알림이 전송됩니다.
    - **취소됨** – 작업이 취소되면 알림이 전송됩니다.

3. 2단계에서 선택한 이벤트의 행을 선택합니다.
4. **알림 텍스트** 탭의 텍스트 상자에 알림 텍스트를 입력합니다.
5. 알림을 개인화하기 위해 자리 표시자를 삽입할 수 있습니다. 알림이 사용자에게 표시되면 자리 표시자가 적절한 데이터로 바뀝니다. 자리 표시자를 삽입하려면 다음 단계를 따르십시오.

    1. 텍스트 상자에서 자리 표시자가 나타날 위치를 클릭합니다.
    2. **자리 표시자 삽입** 을 클릭합니다.
    3. 표시되는 목록에서 삽입할 자리 표시자를 선택합니다.
    4. **삽입** 을 클릭합니다.

6. 알림 번역을 추가하려면 다음 단계를 따르십시오.

    1. **번역** 을 클릭합니다.
    2. 표시되는 페이지에서 **추가** 를 클릭합니다.
    3. 표시되는 목록에서 텍스트를 입력할 언어를 선택합니다.
    4. **번역된 텍스트** 필드에 텍스트를 입력합니다.
    5. 텍스트를 개인화하려면 5단계에 설명된 대로 자리 표시자를 삽입할 수 있습니다.
    6. **닫기** 를 클릭합니다.

7. **받는 사람** 탭에서 알림을 받을 사람을 지정합니다. 다음 표의 옵션 중 하나를 선택하고 8단계로 이동하기 전에 해당 옵션에 대한 추가 단계를 따르십시오.

    <table>
    <thead>
    <tr>
    <th>선택사항</th>
    <th>알림 수신자</th>
    <th>추가 단계</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>참가자</td>
    <td>특정 그룹 또는 역할에 할당된 사용자</td>
    <td>
    <ol>
    <li><strong>참가자</strong>를 선택한 후 <strong>역할 기반</strong> 탭의 <strong>참가자 유형</strong> 목록에서 알림을 보낼 그룹 또는 역할 유형을 선택합니다.</li>
    <li><strong>참가자</strong> 목록에서 알림을 보낼 그룹 또는 역할을 선택합니다.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>워크플로 사용자</td>
    <td>현재 워크플로에 참여하는 사용자</td>
    <td>
    <ul>
    <li><strong>워크플로 사용자</strong>를 선택한 후 <strong>워크플로 사용자</strong> 탭의 <strong>워크플로 사용자</strong> 목록에서 워크플로에 참여하는 사용자를 선택합니다.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>사용자</td>
    <td>특정 사용자</td>
    <td>
    <ol>
    <li><strong>사용자</strong>를 선택한 후 <strong>사용자</strong> 탭을 클릭합니다.</li>
    <li><strong>사용 가능한 사용자</strong> 목록에는 모든 사용자가 포함됩니다. 알림을 보낼 사용자를 선택한 다음 해당 사용자를 <strong>선택한 사용자</strong> 목록으로 이동합니다.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. 2단계에서 선택한 각 이벤트에 대해 3~7단계를 반복합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]