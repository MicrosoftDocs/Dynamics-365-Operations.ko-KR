---
title: 주소 변경 보기 및 관리
description: 이 항목에서는 Dynamics 365 Human Resources에서 주소 변경을 보고 관리하는 방법을 설명합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bd7180c8f53687d561c429456387e0fe999dd508
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452605"
---
# <a name="view-and-manage-address-changes"></a>주소 변경 보기 및 관리


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 **개인 세부 정보 편집** 페이지(**직원 셀프 서비스** 작업 영역에서 열 수 있음) 또는 Dynamics 365 Human Resources의 **작업자** 세부 정보 페이지에서 주소 변경을 보고 관리하는 방법을 설명합니다.

많은 조직에서는 직원이 셀프 서비스 환경에서 자신의 개인 정보를 관리하기를 원합니다. 사용자가 **직원 셀프 서비스** 작업 영역에서 주소를 업데이트하도록 허용할 수 있습니다. 그런 다음 **인사 관리** 작업 영역에서 이러한 변경을 모니터링할 수 있습니다. 이 기능을 사용하려면 **Human Resources 매개 변수** 페이지에서 변경을 볼 일수를 지정해야 합니다.

## <a name="configure-address-change-parameters"></a>주소 변경 매개 변수 구성

**인사 관리** 작업 영역에 주소 변경을 표시할 일수를 구성하려면 다음 단계를 따릅니다.

1. 탐색 창에서 **인사 관리** 를 선택합니다.
2. **연결** 을 선택합니다.
3. **Human Resources 매개 변수** 를 선택합니다.
4. **주소 변경** 의 **일수** 필드에 **인사 관리** 작업 영역에 주소 변경을 표시할 일수를 입력합니다.
5. 페이지를 닫습니다.

## <a name="create-or-change-an-employee-address"></a>직원 주소 만들기 또는 변경

직원이 **직원 셀프 서비스** 작업 영역에서 자기 주소를 업데이트하도록 허용할 수 있습니다. 주소를 만들거나 변경하려면 다음 단계를 따릅니다.

1. **홈** 페이지에서 **직원 셀프 서비스** 타일을 선택합니다.
2. **개인 세부 정보 편집** 을 선택합니다.
3. 주소를 추가하려면 **추가** 를 선택합니다. 기존 주소를 업데이트하려면 목록에서 주소를 선택한 다음 **편집** 을 선택합니다.
4. **이름 또는 설명** 을 입력합니다.
5. **목적** 드롭다운 상자를 선택한 다음 주소 유형을 선택합니다.
6. **국가/지역** 을 입력합니다.
7. **우편 번호** 를 입력합니다.
8. **상세 주소** 를 입력합니다.
9. **시**, **주/도** 및 **군** 을 선택합니다. 일반적으로 이러한 필드는 **우편 번호** 필드를 기준으로 자동으로 설정됩니다.
10. 선택적으로 **기본** 필드를 선택해 기본 주소임을 지정합니다. 하나의 주소만 기본 주소로 표시할 수 있습니다. 다른 주소가 이미 기본 주소로 표시된 경우 이 주소를 기본 주소로 사용할 것인지 확정해야 합니다.
11. 선택적으로 **비공개** 필드를 선택해 비공개 주소임을 지정합니다. 비공개 주소 정보를 볼 수 있는 명시적 권한이 있는 사용자만 이 주소를 볼 수 있습니다.
12. **확인** 을 선택합니다.

## <a name="create-or-change-a-worker-address"></a>작업자 주소 만들기 또는 변경

**인사 관리** 작업 영역에서 주소를 업데이트할 수 있습니다. 주소를 만들거나 변경하려면 다음 단계를 따릅니다.

1. **인사 관리** 작업 영역에서 **연결** 을 선택한 다음 **작업자** 를 선택합니다.
2. 작업자를 선택한 다음 **주소** 를 선택합니다.
3. 주소를 추가하려면 **추가** 를 선택합니다. 기존 주소를 업데이트하려면 목록에서 주소를 선택한 다음 **편집** 을 선택합니다.
4. **이름 또는 설명** 을 입력합니다.
5. **목적** 드롭다운 상자를 선택한 다음 주소 유형을 선택합니다.
6. **국가/지역** 을 입력합니다.
7. **우편 번호** 를 입력합니다.
8. **상세 주소** 를 입력합니다.
9. **시**, **주/도** 및 **군** 을 선택합니다. 일반적으로 이러한 필드는 **우편 번호** 필드를 기준으로 자동으로 설정됩니다.
10. 선택적으로 **기본** 필드를 선택해 기본 주소임을 지정합니다. 하나의 주소만 기본 주소로 표시할 수 있습니다. 다른 주소가 이미 기본 주소로 표시된 경우 이 주소를 기본 주소로 사용할 것인지 확정해야 합니다.
11. 선택적으로 **비공개** 필드를 선택해 비공개 주소임을 지정합니다. 비공개 주소 정보를 볼 수 있는 명시적 권한이 있는 사용자만 이 주소를 볼 수 있습니다.
12. **확인** 을 선택합니다.
 
## <a name="create-a-future-change-for-an-address"></a>주소의 향후 변경 만들기

어떤 경우에는 나중에 변경하도록 주소를 업데이트해야 할 수도 있습니다. 예를 들어 직원이 다음 달 15일에 이사를 하는 경우 이 기능이 유용합니다.

1. 주소 그리드에서 **추가 옵션 > 고급** 을 선택하여 **주소 관리** 페이지를 엽니다.
2. **새로 만들기** 를 선택하여 새 주소를 만듭니다.
3. 주소의 세부 정보를 입력합니다.
4. **일반** 빠른 탭을 선택합니다.
5. **적용 날짜** 필드에서 새 주소가 적용될 날짜를 선택합니다.
6. 선택적으로 **만료 날짜** 필드에서 주소가 더 이상 유효하지 않을 때를 선택합니다.
7. 페이지를 닫습니다.

## <a name="view-and-monitor-address-changes"></a>주소 변경 모니터링 및 관리

HR 담당자는 **인사 관리** 작업 영역에서 주소 변경을 보고 모니터링할 수 있습니다. 주소 변경을 보려면 **홈** 페이지에서 **인사 관리** 타일을 선택합니다. 주소 변경은 오른쪽 상단 모서리에 있는 타일에 나타납니다. **주소 변경** 위의 숫자는 **Human Resources 매개 변수** 페이지에 지정된 일수 동안 발생한 모든 주소 변경 횟수입니다. 

**주소 변경** 타일을 선택하면 새 페이지에 모든 주소 변경의 세부 정보가 표시됩니다. 선택적으로 오른쪽 상단 모서리에서 **미래 주소 변경 포함** 을 선택하여 미래 날짜의 주소 변경을 표시할 수 있습니다.

> [!NOTE]
> 이러한 주소 변경에 대한 알림이나 이메일을 받으려면 작업 창의 **옵션** 탭에서 새 경고 규칙을 만들 수 있습니다. 경고 규칙에 대한 자세한 내용은 [경고 규칙 만들기](../fin-ops-core/fin-ops/get-started/create-alerts.md)를 참조하세요.
>
> 주소 변경에 대한 워크플로를 구성하려면 경고 규칙에서 **외부로 보내기** 옵션을 선택한 다음 Power Automate를 사용하여 비즈니스 이벤트를 트리거하고 워크플로를 구성할 수 있습니다. 자세한 내용은 [비즈니스 이벤트로서의 경고](../fin-ops-core/fin-ops/get-started/create-alerts.md#alerts-as-business-events)를 참조하세요.


[!INCLUDE[footer-include](../includes/footer-banner.md)]