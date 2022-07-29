---
title: 인사 관리 작업 영역
description: 이 항목에서는 인사 관리 작업 영역의 개념적 요소에 관해 설명합니다.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a83dea308e3e2eec1edebd5d619f9455e1a2268
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452242"
---
# <a name="personnel-management-workspace"></a>인사 관리 작업 영역


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**인사 관리** 작업 영역에는 방대한 콘텐츠가 포함됩니다. 여기에는 인사 이동, 직원 변경 사항 추적, 열린 직위, 주소 변경, 만료되는 기록 및 분석이 포함되며 특정 정보에 대한 링크도 있습니다. 이 항목에서는 작업 영역의 각 부분에 관한 자세한 정보를 제공합니다.

## <a name="activity-tab"></a>활동 탭

**활동** 탭에는 고용 프로세스의 단계에 따라 작업자를 그룹화하는 섹션이 있습니다.

- **채용할 후보자**
- **곧 시작**
- **최근 채용**
- **퇴사 예정**
- **퇴사**

작업자가 이러한 단계 중 하나인 경우 카드의 버튼이나 오른쪽 상단 모서리에 있는 줄임표(**...**)를 선택하면 표시되는 메뉴에서 특정 작업을 사용할 수 있습니다. 다음 하위 섹션에서는 **활동** 탭의 섹션을 설명하고 사용 가능한 작업을 나열합니다.

### <a name="candidates-to-hire"></a>채용할 후보자

작업 영역의 **채용할 후보자** 섹션은 여러 원본의 정보로 채워집니다

- OData(Open Data Protocol) 엔터티
- LinkedIn 통합
- 제품에 수동으로 입력되는 데이터

**채용할 후보자** 섹션에 후보자가 나타나면 후보자 카드에서 줄임표를 선택하여 다음 작업을 수행할 수 있습니다.

- **후보자 제외**
- **채용 안 함**
- **채용**

> [!NOTE]
> Microsoft Dataverse에서 후보자 목록을 채우는 경우 법인이 후보자와 연결되지 않았기 때문에 모든 법인에 동일한 후보자가 표시됩니다.

### <a name="starting-soon"></a>곧 시작

**곧 시작** 섹션에는 시작 날짜가 미래인 작업자가 나열됩니다. 목록은 시작 날짜로 정렬됩니다. 오늘 날짜와 가장 가까운 시작 날짜가 먼저 나열됩니다.

관리자가 카드에 표시되지 않으면 해당 작업자에게 직위가 할당되지 않은 것입니다.

> [!NOTE] 
> 검사 목록을 적용하기 전에 직원에게 직위를 할당하는 것이 좋습니다. 때로는 새로 채용된 직원의 관리자에게 온보딩 작업이 할당됩니다. 그러나 직위가 할당되지 않은 경우에는 신입사원의 관리자를 확인할 수 없습니다. 이 경우 관리자를 위한 온보딩 작업이 대신 검사 목록 소유자에게 할당됩니다.

작업자가 **곧 시작** 섹션에 표시되면 다음 작업을 수행할 수 있습니다.

- 직위 할당
- 고용 확인
- 고정 보상 할당
- 변동 보상 할당
- 계층에서 보기
- 검사 목록 적용\*\*

\*\* 이 작업은 기본 작업입니다. 카드에 버튼으로 나타납니다.

### <a name="recent-hires"></a>최근 채용

**최근 채용** 섹션은 시작 날짜가 최근 과거인 작업자를 나열합니다. 목록은 시작 날짜로 정렬됩니다. 오늘 날짜와 가장 가까운 시작 날짜가 먼저 나열됩니다.

기본적으로 목록에는 지난 7일 동안 채용된 작업자가 표시됩니다. 이 설정을 변경하려면 **Human Resources 매개 변수** 페이지의 **일반** 탭에서 **최근 채용** 의 시간 프레임을 정의합니다. **최근 채용** 섹션의 데이터는 특정 일수, 개월 수 또는 연수로 표시할 수 있습니다. 예를 들어 지난 14일 동안 채용된 작업자 목록을 보려면 **기간** 필드를 **14** 로 설정하고 **단위** 필드를 **일** 로 설정합니다.

> [!NOTE]
> **Human Resources 매개 변수** 페이지의 설정은 회사별로 다릅니다. 따라서 최근 채용을 보는 시간 프레임은 회사마다 다를 수 있습니다. 예를 들어 USMF 회사에서는 지난 7일 동안의 모든 신규 채용을 보려고 할 수 있습니다. 반면에 USSI 회사에서는 지난 14일 동안의 모든 신규 채용을 보려고 할 수 있습니다. 이 경우 각 회사의 **Human Resources 매개 변수** 페이지를 열고 필요에 따라 매개 변수를 설정합니다.

관리자가 카드에 표시되지 않으면 해당 작업자에게 직위가 할당되지 않은 것입니다.

작업자가 **최근 채용** 섹션에 표시되면 다음 작업을 수행할 수 있습니다.

- 직위 할당
- 고용 확인
- 고정 보상
- 변동 보상 할당
- 계층에서 보기
- 검사 목록 적용\*\*

\*\* 이 작업은 기본 작업입니다. 카드에 버튼으로 나타납니다.

### <a name="exiting"></a>퇴사 예정

**퇴사 예정** 섹션에는 해고 날짜가 미래인 작업자가 나열됩니다. 목록은 해고 날짜로 정렬됩니다. 오늘 날짜와 가장 가까운 해고 날짜가 먼저 나열됩니다. 

기본적으로 목록에는 다음 7일 이내에 해고 날짜가 있는 작업자가 표시됩니다. 이 설정을 변경하려면 **Human Resources 매개 변수** 페이지의 **일반** 탭에서 **퇴사 예정 작업자 보기** 의 시간 프레임을 정의합니다. **퇴사 예정** 섹션의 데이터는 특정 일수, 개월 수 또는 연수로 표시할 수 있습니다. 예를 들어 지난 다음 14일 동안 퇴사할 작업자 목록을 보려면 **기간** 필드를 **14** 로 설정하고 **단위** 필드를 **일** 로 설정합니다.

작업자가 **퇴사 예정** 섹션에 표시되면 다음 작업을 수행할 수 있습니다.

- 검사 목록 적용\*\*
- 고용 확인
- 계층에서 보기

\*\* 이 작업은 기본 작업입니다. 카드에 버튼으로 나타납니다.

### <a name="exited"></a>퇴사

**퇴사** 섹션은 해고 날짜가 최근 과거인 작업자를 나열합니다. 목록은 해고 날짜로 정렬됩니다. 오늘 날짜와 가장 가까운 해고 날짜가 먼저 나열됩니다.

기본적으로 목록에는 최근 7일 이내에 해고 날짜가 있는 작업자가 표시됩니다. 이 설정을 변경하려면 **Human Resources 매개 변수** 페이지의 **일반** 탭에서 **퇴사 작업자 보기** 의 시간 프레임을 정의합니다. **퇴사** 섹션의 데이터는 특정 일수, 개월 수 또는 연수로 표시할 수 있습니다. 예를 들어 지난 14일 동안 퇴사한 작업자 목록을 보려면 **기간** 필드를 **14** 로 설정하고 **단위** 필드를 **일** 로 설정합니다.

작업자가 **퇴사** 섹션에 표시되면 다음 작업을 수행할 수 있습니다.

- 검사 목록 적용\*\*
- 고용 확인
- 계층에서 보기

\*\* 이 작업은 기본 작업입니다. 카드에 버튼으로 나타납니다.

## <a name="employee-changes-tab"></a>직원 변경 탭

**직원 변경** 탭은 모든 작업자 인사 조치 목록을 제공합니다. 이 목록은 기본적으로 사용할 수 없습니다. 기능을 활성화하려면 **Human Resources 공유 매개 변수** 페이지의 **인사 작업** 탭에서 **작업자 작업 활성화** 옵션을 **예** 로 설정합니다.

## <a name="position-changes-tab"></a>직위 변경 탭

**직위 변경** 탭은 모든 직위 인사 조치 목록을 제공합니다. 이 목록은 기본적으로 사용할 수 없습니다. 기능을 활성화하려면 **Human Resources 공유 매개 변수** 페이지의 **인사 작업** 탭에서 **직위 작업 활성화** 옵션을 **예** 로 설정합니다.

## <a name="open-positions-tab"></a>열린 직위 탭

**열린 직위** 탭에는 모든 열린 직위가 나열됩니다. 이 목록에 직위가 나오려면 직위의 활성화 날짜가 오늘 또는 그 이전이어야 하며 현재 작업자 할당이 없어야 합니다.

> [!NOTE]
> 이 목록은 현재의 작업자 할당을 고려합니다. 미래 날짜의 작업자 할당이 있는 모든 직위는 목록에 계속 표시됩니다. 그러나 작업자 할당의 적용 날짜에 도달한 후에는 해당 직위가 목록에서 제거됩니다.

## <a name="expiring-records-tab"></a>레코드 만료 탭

**레코드 만료** 탭에는 사용자가 로그인한 회사의 작업자에 대해 만료되었거나 만료될 모든 항목이 나열됩니다. 목록에 다음 항목이 나타납니다.

- **자격증**
- **ID**
- **수습 기간**
- **심사**
- **테스트**

목록에 만료된 레코드가 표시되는지 아니면 만료되는 레코드가 표시되는지를 지정하려면 **Human Resources 매개 변수** 페이지의 **일반** 탭에서 **만료되는 레코드** 또는 **만료된 레코드** 에 대한 기간을 정의합니다. **만료되는 레코드** 탭의 데이터는 특정 일수 동안 표시될 수 있습니다. 예를 들어 앞으로 14일 이내에 만료될 레코드의 목록을 보려면 **일수** 필드를 **14** 로 설정합니다.

> [!NOTE] 
> **Human Resources 매개 변수** 페이지에서 **만료된 레코드** 또는 **만료되는 레코드** 의 기간을 **0** 으로 설정하면 목록에 해당 레코드가 표시되지 않습니다.

## <a name="employees-tile"></a>직원 타일

**직원** 타일은 사용자가 현재 로그인한 회사에 고용된 모든 직원 수를 보여줍니다. **직원** 타일을 선택하면 새 페이지에 직원의 세부 정보가 표시됩니다.

## <a name="contractors-tile"></a>계약자 타일

**계약자** 타일은 사용자가 현재 로그인한 회사에 고용된 모든 계약자 수를 보여줍니다. **계약자** 타일을 선택하면 새 페이지에 계약자의 세부 정보가 표시됩니다.

## <a name="open-positions-tile"></a>열린 직위 타일

**열린 직위** 타일은 모든 열린 직위의 수를 보여줍니다. **열린 직위** 타일을 선택하면 새 페이지에 열린 직위의 세부 정보가 표시됩니다. 이 수에 포함되려면 직위의 활성화 날짜가 오늘 또는 그 이전이어야 하며 현재 작업자 할당이 없어야 합니다.

> [!NOTE]
> 이 타일은 현재의 작업자 할당을 고려합니다. 미래 날짜의 작업자 할당이 있는 모든 직위는 타일에 계속 포함됩니다. 그러나 작업자 할당 적용 날짜에 도달한 후에는 해당 직위가 수에서 제외됩니다.

## <a name="approvals-tile"></a>승인 타일

**승인** 타일은 현재 사용자의 승인을 보류 중인 모든 워크플로 항목의 수를 보여줍니다. **승인** 타일을 선택하면 새 페이지에 승인이 필요한 워크플로 항목의 세부 정보가 표시됩니다.

## <a name="address-changes-tile"></a>주소 변경 타일

**주소 변경** 타일은 **Human Resources 매개 변수** 페이지에 지정된 일수 동안 발생한 모든 주소 변경 수를 표시합니다. **주소 변경** 타일을 선택하면 새 페이지에 모든 주소 변경의 세부 정보가 표시됩니다. 페이지 오른쪽 상단에서 **향후 주소 변경 포함** 을 선택하여 향후 날짜의 주소 변경 사항을 볼 수 있습니다.

주소 변경을 보고 관리하는 방법에 대한 자세한 내용은 [주소 변경 보기 및 관리](hr-personnel-view-address-changes.md)를 참조하세요.