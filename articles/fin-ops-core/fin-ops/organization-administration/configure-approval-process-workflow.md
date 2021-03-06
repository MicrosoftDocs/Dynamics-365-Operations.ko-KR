---
title: 워크플로에서 승인 프로세스 구성
description: 다음 절차를 사용하여 승인 프로세스의 속성을 구성합니다.
author: ChrisGarty
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99a4e131b2afa65152d8e9d41b8405895d997250
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460733"
---
# <a name="configure-approval-processes-in-a-workflow"></a>워크플로에서 승인 프로세스 구성

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

다음 절차를 사용하여 승인 프로세스의 속성을 구성합니다.

승인 프로세스를 구성하려면 워크플로 편집기에서 승인 요소를 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 클릭하여 **속성** 양식을 엽니다.

## <a name="name-the-approval-process"></a>승인 프로세스 이름 지정

다음 단계에 따라 승인 프로세스의 이름을 입력하십시오.

1. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
2. **이름** 필드에 승인 프로세스의 고유한 이름을 입력합니다.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>시스템이 문서에 대해 자동으로 작동하는 시기를 지정합니다.

특정 조건이 충족되면 문서에 대해 자동으로 작동하도록 시스템을 구성할 수 있습니다. 예를 들어, 시스템은 총 금액이 미화 100달러 미만인 경비 보고서를 승인할 수 있습니다. 시스템이 문서에 대해 작동하는 시기를 지정하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **자동 작업** 을 클릭합니다.
2. **자동 작업 활성화** 확인란을 선택합니다.
3. **조건 추가** 를 클릭합니다.
4. 조건을 입력합니다.
5. 필요한 경우 추가 조건을 입력합니다.
6. 입력한 조건이 올바르게 구성되었는지 확인하려면 다음 단계를 완료하십시오.

    1. **테스트** 를 클릭하여 **테스트 워크플로 조건** 양식을 엽니다.
    2. 양식의 **조건 확인** 영역에서 기록을 선택합니다.
    3. **테스트** 를 클릭합니다. 시스템은 기록을 평가하여 정의한 조건을 충족하는지 여부를 결정합니다.
    4. **확인** 또는 **취소** 를 클릭하여 **속성** 양식으로 돌아갑니다.

7. **자동 완성 작업** 목록에서 시스템이 문서에 대해 수행해야 하는 작업을 선택합니다.

## <a name="specify-when-notifications-are-sent"></a>알림을 보낼 때 지정

문서가 승인, 거부, 위임 또는 에스컬레이션되었거나 변경이 요청되었을 때 사람들에게 알림을 보낼 수 있습니다. 알림이 전송되는 시기와 알림이 전송되는 대상을 지정하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **알림** 을 클릭합니다.
2. 알림을 보낼 이벤트 옆의 확인란을 선택합니다.

    - **대리인** – 문서가 승인을 위해 다른 사용자에게 할당된 경우.
    - **에스컬레이션** – 할당된 사용자가 할당된 시간 내에 문서에 대해 조치를 취하지 않은 경우.
    - **승인** – 문서가 승인된 경우.
    - **거부** – 문서가 거부된 경우입니다.
    - **변경 요청** – 할당된 사용자가 제출된 문서에 대한 변경을 요청한 경우입니다.

3. 2단계에서 선택한 이벤트의 행을 선택합니다.
4. **알림 텍스트** 탭을 클릭합니다.
5. 텍스트 상자에 알림 텍스트를 입력합니다.
6. 텍스트를 개인화하려면 사용자에게 표시될 때 적절한 데이터로 대체되는 자리 표시자를 삽입할 수 있습니다. 자리 표시자를 삽입하려면 다음 단계를 따르십시오.

    1. 자리 표시자가 나타나야 하는 위치의 텍스트 상자를 클릭합니다.
    2. **자리 표시자 삽입** 을 클릭합니다.
    3. 표시되는 목록에서 삽입할 자리 표시자를 선택합니다.
    4. **삽입** 을 클릭합니다.

7. 알림 번역을 추가하려면 **번역** 을 클릭합니다. 표시되는 양식에서 다음 단계를 따르십시오.

    1. **추가** 를 클릭합니다.
    2. 표시되는 목록에서 텍스트를 입력할 언어를 선택합니다.
    3. **번역된 텍스트** 텍스트 상자에 텍스트를 입력합니다.
    4. 텍스트를 개인화하려면 자리 표시자를 삽입하십시오.
    5. **닫기** 를 클릭합니다.

8. **받는 사람** 탭을 클릭합니다.
9. 알림을 받을 사람을 지정합니다. 다음 표의 옵션 중 하나를 선택한 다음 10단계로 이동하기 전에 옵션에 대한 추가 단계를 따르십시오.

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
    <td><strong>참가자</strong></td>
    <td>특정 그룹 또는 역할에 할당된 사용자</td>
    <td>
    <ol>
    <li><strong>참가자</strong>를 선택한 후 <strong>역할 기반</strong> 탭을 클릭합니다.</li>
    <li><strong>참가자 유형</strong> 목록에서 알림을 보낼 그룹 또는 역할 유형을 선택합니다.</li>
    <li><strong>참가자</strong> 목록에서 알림을 보낼 그룹 또는 역할을 선택합니다.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>워크플로 사용자</strong></td>
    <td>현재 워크플로에 참여하는 사용자</td>
    <td>
    <ol>
    <li><strong>워크플로</strong> 사용자를 선택한 후 <strong>워크플로 사용자</strong> 탭을 클릭합니다.</li>
    <li><strong>워크플로 사용자</strong> 목록에서 워크플로에 참여하는 사용자를 선택합니다.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>사용자</strong></td>
    <td>특정 사용자</td>
    <td>
    <ol>
    <li><strong>사용자</strong>를 선택한 후 <strong>사용자</strong> 탭을 클릭합니다.</li>
    <li>알림을 보낼 사용자를 선택한 다음 이러한 사용자를 <strong>선택한 사용자</strong> 목록으로 이동합니다.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. 2단계에서 선택한 각 이벤트에 대해 3-9단계를 반복합니다.

## <a name="specify-a-final-approver"></a>최종 승인자 지정

승인자가 승인을 위해 문서를 제출한 사람이고 '제출자 승인 거부'를 사용하는 시나리오에 대해 최종 승인자를 지정할 수 있습니다. 최종 승인자를 지정하려면 다음 단계를 따르십시오.

1. 워크플로 편집기에서 승인 요소를 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 선택하여 **속성** 양식을 엽니다.
2. 왼쪽 창에서 **고급 설정** 을 클릭합니다.
3. **최종 승인자 사용** 확인란을 선택합니다.
4. 목록에서 최종 승인자가 될 사용자를 선택합니다.

## <a name="set-a-time-limit"></a>시간 제한 설정

승인 프로세스가 특정 시간에 완료되어야 하는 경우 다음 단계를 따르십시오.

> [!NOTE]
> 이 단계에서 선택하는 옵션은 각 승인 단계의 **할당** 및 **에스컬레이션** 영역에서 선택한 옵션보다 우선합니다.

1. 왼쪽 창에서 **고급 설정** 을 클릭합니다.
2. **워크플로 요소에 대한 시간 제한 설정** **확인란** 을 선택합니다.
3. **기간** 필드에서 승인 프로세스를 완료해야 하는 시간을 지정합니다. 다음 옵션 중 하나를 선택합니다.

    - **시간** – 승인 프로세스를 완료해야 하는 시간을 입력합니다. 이후 조직에서 사용하는 캘린더를 선택하고 조직의 작업 주에 대한 정보를 입력합니다.
    - **일** – 승인 프로세스를 완료해야 하는 일 수를 입력합니다. 이후 조직에서 사용하는 캘린더를 선택하고 조직의 작업 주에 대한 정보를 입력합니다.
    - **주** – 승인 프로세스를 완료해야 하는 주 수를 입력합니다.
    - **월** – 승인 프로세스를 완료해야 하는 날짜와 주를 선택합니다. 예를 들어 승인 프로세스가 매월 세 번째 주 금요일까지 완료되기를 원할 수 있습니다.
    - **년** – 승인 프로세스를 완료해야 하는 일, 주, 월을 선택합니다. 예를 들어 승인 프로세스가 12월 셋째 주 금요일까지 완료되기를 원할 수 있습니다.

4. 시간 제한이 초과되면 시스템이 문서에 대해 조치를 취합니다. **작업** 목록에서 시스템이 수행해야 하는 작업을 선택합니다.

## <a name="specify-which-actions-are-available-to-the-user"></a>사용자가 사용할 수 있는 작업 지정

문서가 승인을 위해 사용자에게 할당되면 사용자는 문서에 대해 조치를 취해야 합니다. 다음 단계에 따라 사용자가 제출된 문서에 대해 수행할 수 있는 작업을 지정합니다.

1. 왼쪽 창에서 **고급 설정** 을 클릭합니다.
2. 사용자가 문서를 승인할 수 있는 경우 **승인** 확인란을 선택합니다.
3. **거부** 확인란을 선택하면 사용자가 문서를 거부할 수 있습니다.
4. 사용자가 문서 변경을 요청할 수 있는 **변경 요청** 확인란을 선택합니다.
5. 사용자가 승인을 위해 문서를 다른 사용자에게 할당할 수 있는 경우 **위임** 확인란을 선택합니다.

> [!NOTE]
> **Enterprise Portal의 작업 목록에서 작업 활성화** 확인란은 더 이상 사용되지 않습니다.

## <a name="configure-the-approval-steps"></a>승인 단계 구성

승인 프로세스는 승인 단계로 구성됩니다. 승인 프로세스를 추가하고 단계를 구성하려면 다음 절차를 완료하십시오.

1. 워크플로 편집기에서 승인 프로세스를 두 번 클릭합니다. 워크플로 편집기는 승인 프로세스의 단계를 표시합니다.
2. 승인 단계를 추가하려면 **워크플로 요소** 영역에서 캔버스로 단계를 끕니다.
3. 승인 단계를 구성하려면 [워크플로에서 승인 단계 구성](configure-approval-step-workflow.md)을 참조하십시오.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]