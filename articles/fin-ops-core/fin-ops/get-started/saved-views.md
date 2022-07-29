---
title: 저장된 보기
description: 이 토픽에서는 저장된 보기 기능을 사용하는 방법에 대해 설명합니다.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: bd1b034ebb66b996e20173c2ad4f958e643f9c2e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460774"
---
# <a name="saved-views"></a>저장된 보기

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

## <a name="introduction"></a>소개

개인화는 사용자와 조직이 필요에 맞게 사용자 경험을 최적화할 수 있도록 하는 데 중요한 역할을 합니다. 개인화에 대한 자세한 내용은 [사용자 경험 개인화](personalize-user-experience.md)를 참조하세요.

기존의 개인화에서는 사용자가 페이지당 단 하나의 개인화 세트만 가질 수 있습니다. **저장된 조회수** 기능은 다음과 같은 몇 가지 중요한 방식으로 개인화를 확장합니다.

- 보기를 통해 사용자는 양식당 여러 개의 명명된 개인 설정 세트를 가질 수 있으며 필요에 따라 빠르게 전환할 수 있습니다. 이를 통해 사용자는 페이지의 여러 최적화된 보기를 만들 수 있으며 각 보기는 특정 비즈니스 작업 수행의 요구 사항에 맞게 조정됩니다. 
- 특정 페이지 유형에 대해 생성된 보기에는 사용자가 추가한 필터 또는 정렬이 포함될 수도 있으며, 이를 통해 사용자는 일반적으로 필터링된 데이터 세트로 빠르게 돌아갈 수 있습니다. 자세한 내용은 [보기를 지원하는 페이지](saved-views.md#what-pages-support-views) 섹션을 참조하세요. 
- 특정 보안 역할 및 특정 법인의 사용자에게 보기를 게시할 수 있습니다. 따라서 지정된 역할과 지정된 법인에 대한 액세스 권한이 있는 모든 사용자는 해당 사용자에게 개인화 권한이 없더라도 해당 보기에 액세스하고 사용할 수 있습니다. 이 게시 기능을 통해 조직은 비즈니스에 최적화된 기업의 표준 보기를 정의할 수 있습니다. 자세한 내용은 [보기를 사용하여 조직 수준에서 개인화 관리](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) 섹션을 참조하세요.
- 기존 개인화와 달리 사용자가 개인화를 수행하거나 목록을 필터링할 때 보기가 자동으로 저장되지 않습니다. 명시적 저장은 사용자에게 해당 보기와 관련된 변경이 수행되기 전이나 후에 보기를 작성할 수 있는 유연성을 제공하는 데 필요합니다. 이 요구 사항은 또한 장기간 사용을 위한 것이 아닌 필터 또는 개인화에 의해 뷰 정의가 의도치 않게 변경되지 않도록 합니다. 시스템이 일반적인 페이지 사용의 일부로 자동으로 저장하는 항목(예: 열 너비 또는 섹션의 확장 또는 축소 상태)은 보기별로 저장됩니다.
- 보기는 타일, 목록 또는 링크로 작업 공간에 추가할 수 있습니다. 따라서 필터링된 데이터 세트는 작업 공간에 표시될 수 있으며 사용자는 해당 데이터 세트와 관련된 개인 설정 세트를 타일 또는 링크와 연결할 수 있습니다.

## <a name="switching-between-views"></a>보기 간 전환

환경에서 보기를 사용할 수 있게 되면 보기를 지원하는 모든 페이지의 맨 위에 현재 보기의 이름을 표시하는 축소된 보기 선택기 컨트롤이 포함됩니다.

보기 선택기에는 두 가지 크기 변형이 있습니다. 

- **큰 보기 선택기** – 목록이 눈에 띄게 표시되는 페이지는 몇 가지 이유로 더 큰 보기 선택기를 갖게 됩니다. 가장 중요한 것은 더 큰 보기 선택기가 보기에 사용자 정의 필터를 포함할 수 있는 페이지를 나타냅니다. 보기에 필터가 포함되어 있기 때문에 보기 이름이 화면에 표시되는 데이터를 가장 잘 설명할 수 있고 사용자가 이러한 페이지 유형에서 보기 사이를 더 자주 전환할 것으로 예상되므로 더 큰 선택기 크기도 보장됩니다.
- **작은 보기 선택기** – 다른 모든 전체 화면 페이지(작업 영역 및 대시보드 제외)에는 페이지 캡션 옆에 표시되는 더 작은 보기 선택기가 있습니다. 이 페이지의 보기에는 사용자 정의 필터가 아닌 개인화만 포함됩니다. 이러한 페이지에서 캡션 또는 레코드 제목은 페이지 상단의 가장 중요한 정보인 경우가 많습니다. 보기 선택기의 크기가 작을수록 이러한 페이지에서 예상되는 보기 전환 빈도가 낮아집니다. 
 
보기 이름을 선택하면 보기 선택기가 열리고 페이지에 사용 가능한 보기 목록이 표시됩니다.

**버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있으면 보기 선택기가 사용 가능한 보기를 두 섹션으로 표시합니다. 첫 번째 섹션에는 현재 법인과 관련된 보기가 표시되고 두 번째 섹션에는 모든 법인에서 사용할 수 있는 보기가 표시됩니다. 첫 번째 섹션은 페이지에 대한 법인별 보기가 있는 경우에만 표시됩니다.

- **표준 보기** – **표준** 보기는 개인 설정이 적용되지 않은 페이지의 기본 보기입니다.
- **개인적인 견해** – 자물쇠가 없는 보기는 귀하의 개인적인 견해를 나타냅니다. 이것은 귀하가 작성했거나 관리자가 귀하에게 제공한 보기입니다.
- **잠긴 보기** – 일부 보기(예: **기준** 보기 및 역할에 게시된 모든 보기)는 보기 선택기 옆에 자물쇠 기호가 있습니다. 이 기호는 해당 보기를 편집할 수 없음을 나타냅니다. 그러나 페이지 사용을 반영하는 변경 사항은 자동으로 저장됩니다. 이러한 변경에는 그리드 열 너비의 변경 및 FastTab의 확장 또는 축소 상태 변경이 포함됩니다. 그럼에도 불구하고 개인화 권한이 있는 경우 **다른 이름으로 저장** 작업을 사용하여 잠긴 보기를 기반으로 하는 개인 보기를 만들 수 있습니다.
- **새로운 보기** – 아직 열지 않은 게시된 보기에는 보기 이름 왼쪽에 스파크 기호가 있습니다.

다른 보기로 전환하려면 먼저 보기 선택기를 연 다음 로드할 보기를 선택합니다. 

## <a name="creating-and-modifying-views"></a>보기 생성 및 수정

기존 개인화와 달리 사용자가 페이지를 개인화하거나 사용자가 목록에 필터를 적용하거나 정렬할 때 보기가 자동으로 저장되지 않습니다. 이러한 변경 사항을 보기에 저장하려면 명시적 작업이 필요합니다. 이 요구 사항은 사용자에게 해당 보기와 관련된 변경이 수행되기 전이나 후에 보기를 작성할 수 있는 유연성을 제공하는 데 필요합니다. 또한 보기 정의가 일회성 필터 또는 개인화에 의해 의도치 않게 변경되지 않도록 합니다. 시스템이 일반적인 페이지 사용 항목(예: 열 너비 또는 섹션의 확장 또는 축소 상태)은 잠긴 보기에 대해서도 현재 보기에 자동으로 저장됩니다.

보기의 현재 상태를 알 수 있도록 보기를 개인화하거나 필터링하여 보기를 변경하기 시작할 때 별표(\*)가 현재 보기 이름 옆에 나타납니다. 이 기호는 해당 보기의 저장되지 않고 수정된 버전을 보고 있음을 나타냅니다.

이러한 변경 사항을 저장하려면 다음 단계를 따르세요.

1. 보기 이름을 선택하여 보기 선택기를 엽니다.
2. 기존 보기를 수정하려면 **저장** 을 선택합니다. 잠긴 보기에는 이 작업을 사용할 수 없습니다. 
3. 새 보기 만들기:

    1. **다른 이름으로 저장** 을 선택합니다. 
    2. **다른 이름으로 보기 저장** 창에서 이름을 입력하고 선택적으로 보기에 대한 설명을 입력합니다.
    3. 이 보기를 기본 보기로 하려면 **기본으로 고정** 을 선택합니다. 기본 보기에 대한 자세한 내용은 이어지는 [기본 보기 변경](#changing-the-default-view) 섹션을 참조하세요. 
    4. **버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있는 경우 이 보기를 모든 법인에 대해 사용할 것인지 아니면 그 하위 집합에 대해서만 사용할 수 있도록 할 것인지 선택할 수 있습니다.
    5. **저장** 을 선택합니다.

## <a name="changing-the-default-view"></a>기본 보기 변경

기본 보기는 페이지를 처음 열 때 시스템이 열려고 하는 보기입니다. 가장 자주 사용할 것으로 예상되는 보기로 기본 보기를 설정해야 합니다. 

> [!NOTE]
> - 베이스 **저장된 조회수** 기능에는 법인 전체에 단일 글로벌 기본 보기가 있습니다. 기본 보기를 변경하면 현재 속해 있는 법인에 관계없이 기본적으로 해당 보기가 열립니다.
> - **버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있으면 각 법인은 페이지당 고유한 기본 보기를 가질 수 있습니다.

페이지의 기본 보기를 변경하려면 다음 단계를 따르세요.

1. 기본값으로 사용하는 보기로 전환합니다. 
2. 보기 이름을 선택하여 보기 선택기를 엽니다. 
3. **더 보기** 를 선택한 다음 **기본으로 고정** 을 선택합니다.

또는 새 보기를 만들 때(**다른 이름으로 저장** 작업을 사용하여), 보기를 저장하기 전에 **기본으로 고정** 옵션을 설정하여 새 보기를 기본 보기로 만들 수 있습니다.

> [!WARNING]
> 경우에 따라 페이지를 처음 열 때 기본 보기와 연결된 쿼리가 실행되지 않습니다. 예를 들어 타일을 통해 페이지를 열면 기본 보기와 연결된 쿼리에 관계없이 타일의 쿼리가 실행됩니다. 또한 이미 정의된 쿼리가 있는 **표준** 보기가 있는 페이지를 열면 기본 뷰의 쿼리 대신 원래 쿼리가 실행됩니다. 이 경우 보기가 로드될 때 정보 메시지를 받게 됩니다. 페이지가 로드된 후 보기를 전환하면 보기 쿼리가 예상대로 실행될 수 있어야 합니다. 버전 10.0.10 이상에서 수신하는 정보 메시지에는 기본 보기의 쿼리를 직접 로드할 수 있는 포함된 작업이 있습니다.

## <a name="managing-personal-views"></a>개인 보기 관리

**내 보기 관리** 대화 상자는 개인 보기와 보기 선택기의 보기 순서에 대한 기본 유지 관리 기능을 제공합니다. 이 페이지를 열려면 보기 이름을 선택하여 보기 선택기 드롭다운 메뉴를 열고 **더 보기** 를 선택한 다음 **내 보기 관리** 를 선택합니다.

**버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있으면 **내 보기 관리** 대화 상자의 **내 보기** 섹션에 페이지에 대해 사용 가능한 보기를 표시합니다. 현재 법인과 관련된 모든 보기는 자체 섹션에 표시됩니다. **글로벌 뷰** 섹션이 항상 표시되므로 모든 법인의 페이지에 사용할 수 있는 보기를 관리할 수 있습니다. 

해당 페이지에 대해 사용 가능한 보기 목록에 대해 다음 작업 세트를 사용할 수 있습니다.

- **기본 보기 변경** - **기본으로 고정** 작업을 사용하여 현재 선택된 보기를 이 페이지의 기본 보기로 만들 수 있습니다. **저장된 보기에 대한 법인 지원 가져오기** 기능이 켜져 있으면 **글로벌 뷰** 섹션을 사용하면 현재 법인 또는 모든 법인에 대한 기본 보기를 만들 수 있습니다.
- **보기 재정렬** - **위로 이동** 및 **아래로 이동** 작업을 사용하여 특정 순서로 보기를 재정렬합니다.
- **보기 이름 바꾸기** - **이름 바꾸기** 작업을 사용하여 현재 선택한 개인 보기의 이름을 변경합니다. 이 작업은 잠긴 보기에 대해 꺼져 있습니다. 
- **보기 삭제** - **삭제** 작업을 사용하여 페이지에서 현재 선택한 보기를 영구적으로 삭제합니다. 보기를 제거한 후에는 복구할 방법이 없습니다.

이 대화 상자에서 변경한 사항은 **업데이트** 버튼을 선택한 후에 적용됩니다.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>보기를 사용하여 조직 수준에서 개인화 관리

저장된 보기가 조직 수준에서 개인화 관리를 개선하는 데 어떻게 도움이 되는지 이해하는 데 도움이 되도록 이 섹션에서는 **저장된 보기** 기능을 사용 및 사용하지 않는 개인화 관리의 몇 가지 차이점에 대해 설명합니다.

보기가 없으면 관리자는 개인화 페이지를 통해 사용자 또는 사용자 그룹에 페이지에 대한 개인화 세트를 적용합니다. 해당 사용자에게 개인화 권한이 있는 경우 해당 페이지에 개인화가 적용됩니다. 그러나 사용자가 페이지를 추가로 개인화하는 것을 방지할 수 있는 기능이 없었습니다. 이는 조직에서 사용자가 일관된 사용자 인터페이스를 가지고 있는지 확인할 수 없음을 의미했습니다. 이러한 사용자 중 개인 설정 권한이 없는 사용자가 있는 경우 관리자가 제공한 개인 설정이 로드되지 않았습니다. 또한 새 사용자가 조직에 고용된 경우 관리자는 사용자에 대한 일련의 개인 설정을 수동으로 로드해야 했습니다. 해당 역할의 사용자가 특정 개인 설정 세트를 사용할 수 있도록 지정하는 자동 메커니즘이 없었습니다.

**저장된 조회수** 기능을 사용하면 주로 사용자 그룹에 보기를 게시할 수 있기 때문에 조직에서 개인 설정을 훨씬 쉽게 관리할 수 있습니다. 보기가 게시된 후 정의된 보안 역할 중 하나가 있고 지정된 법인에 대한 액세스 권한이 있는 사용자는 개인 설정에 대한 액세스 권한이 없더라도 보기를 보고 사용할 수 있습니다. 모든 사용자는 페이지 사용 항목이 자동으로 적용되는 게시된 보기의 복사본을 가지고 있지만 어떤 사용자도 게시된 보기에 대한 개인 설정 또는 쿼리 업데이트를 저장할 수 없습니다. 즉, 게시된 보기가 잠겨 있습니다. 또한 보기가 게시된 법인의 역할에 새 사용자가 할당되면 해당 역할 및 법인과 연결된 보기가 자동으로 표시됩니다. 관리자가 추가 작업을 수행할 필요가 없습니다. 마찬가지로 사용자가 조직에서 역할을 변경하거나 다른 법인에 대한 액세스 권한이 부여된 경우 이전에 사용자에게 게시된 보기에 더 이상 액세스하지 못할 수 있습니다. 다시 말하지만, 관리자는 추가 조치를 취하지 않아도 됩니다.

게시된 보기에 대한 업데이트는 보기를 적절한 보안 역할 및 법인에 다시 게시하여 사용자에게 쉽게 배포할 수 있습니다.

게시 기능을 통해 조직은 특정 보안 역할의 사용자를 대상으로 하는 비즈니스에 최적화된 기업 표준 보기를 정의할 수 있습니다.

## <a name="publishing-views"></a>게시 보기

게시 프로세스 중에 하나 이상의 법인에 대한 하나 이상의 보안 역할에 보기를 할당할 수 있습니다. 따라서 법인에 대한 액세스 권한이 있고 해당 역할 중 하나에 할당된 모든 사용자는 보기에 액세스하고 사용할 수 있습니다. 그러나 사용자는 보기를 편집할 수 없습니다. 기본적으로 시스템 관리자는 보기 선택기 드롭다운 메뉴에서 **게시** 작업에 액세스할 수 있습니다. 그러나 조직의 다른 신뢰할 수 있는 사용자도 새 **저장된 보기 관리자** 역할을 통해 게시 보기에 액세스할 수 있습니다.

보기를 게시하려면 다음 단계를 따르세요.

1. 게시할 보기의 개인 복사본을 만들고 저장합니다. 
2. 해당 보기가 현재 로드된 상태에서 보기 이름을 선택하여 보기 선택기 드롭다운 메뉴를 엽니다. 
3. **더 보기** 버튼을 누른 다음 **게시** 를 선택합니다. 게시 대화 상자가 열립니다.
4. 보기 이름을 입력합니다. 입력하는 이름은 이 보기를 받는 사용자가 보기 선택기에서 보게 될 이름입니다. 페이지에 대해 게시된 보기의 이름은 고유해야 합니다. 보기가 적용되는 역할 또는 법인 목록이 다르더라도 중복 이름은 허용되지 않습니다.
5. **10.0.17 이상 업데이트:** **(프리뷰) 조직 보기에 대한 번역 지원** 기능이 켜져 있으면 **이름** 필드 옆의 **번역** 버튼을 선택하여 조직에서 요구하는 많은 언어로 보기 이름에 대한 번역을 추가할 수 있습니다. 그러면 보기 이름이 현재 언어로 사용자에게 표시됩니다. 번역이 정의되지 않은 언어를 실행하는 사용자에게 표시될 번역을 지정하도록 기본 언어를 설정할 수도 있습니다.
5. 선택 사항: 이 보기를 받는 사용자가 보기의 목적을 더 잘 이해할 수 있도록 보기에 대한 설명을 입력합니다. 
6. 보기를 선택한 사용자의 기본 보기로 게시해야 하는지 여부를 결정합니다. 보기가 기본 보기로 설정되면 사용자는 다음에 대상 페이지를 열 때 해당 보기를 보게 됩니다. 모든 대상 사용자의 단일 글로벌 기본 보기가 변경됩니다. 그러나 사용자는 게시가 발생한 후에도 기본 보기를 변경할 수 있습니다.

    > [!NOTE]
    > 보기를 기본 보기로 게시할 때 다음 동작에 유의하세요.
    >
    > - 보기를 일부 또는 모든 법인에 기본 보기로 게시하면 다음 동작이 발생합니다.
    >
    >    - 베이스 **저장된 조회수** 기능이 켜져 있으면 모든 대상 사용자에 대해 단일 전역 기본 보기가 변경됩니다. 
    >    - **버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있고 보기를 법인의 하위 집합에 게시하면 해당 법인의 기본 보기가 모든 대상 사용자에 대해 변경됩니다.
    >
    > - 사용자에게 여러 보기가 기본 보기로 게시되는 역할이 있는 경우 게시된 마지막 보기가 사용자의 기본 보기로 사용됩니다. 

8. 이 보기의 대상이 되는 사용자에 해당하는 보안 역할을 추가합니다. 
9. 선택한 각 보안 역할의 하위 역할에 보기를 게시할지 여부를 결정합니다. 수행하는 경우 해당 보안 역할 행의 **하위 역할 포함** 확인란을 선택합니다. 이 확인란은 하위 역할이 없는 역할에는 사용할 수 없습니다.
10. 이 보기를 사용할 수 있는 법인을 추가합니다. 

    > [!NOTE]
    > 특정 법인에 보기를 게시하지만 해당 보기를 기본 보기로 게시하지 않는 경우 다음 동작에 유의하세요.
    >
    > - 베이스 **저장된 조회수** 기능만 켜져 있으면 페이지에 대한 사용자의 보기 선택기가 처음에 지정된 법인에 대한 보기만 표시합니다. 그러나 보기가 처음 로드된 후에는 법인에 관계없이 페이지의 보기 선택기가 항상 보기를 표시합니다.
    > - **버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있으면 보기 지정된 법인에 대한 보기만 표시합니다.

11. **게시** 를 선택합니다.

일부 환경에서는 사용자에게 게시된 보기가 표시되기까지 시간(최대 1시간)이 걸릴 수 있습니다.

## <a name="modifying-a-published-view"></a>게시된 보기 수정

보기를 게시한 후 변경하고 싶은 경우가 있습니다. 게시된 보기를 실시간으로 변경할 수는 없지만 이러한 보기는 모든 사용자(게시자 포함)의 편집을 위해 잠겨 있기 때문에 보기를 다시 게시하여 업데이트할 수 있습니다.

게시된 보기를 변경하려는 경우 게시 매개변수(보기의 이름 및 설명 또는 보기가 게시되는 보안 역할)만 포함하는 경우 다음을 수행합니다.

1. 업데이트할 매개변수에 대해 게시된 보기로 전환합니다. 
2. 보기 선택기 드롭다운 메뉴에서 **다시 게시** 를 선택합니다. 버전 10.0.12 또는 이전 버전을 사용하는 경우 **게시** 를 선택한 다음 **네** 를 선택하여 기존 보기를 업데이트해야 합니다.
3. 보기의 이름, 설명, 보안 역할 및 법인을 업데이트합니다. 
4. **게시** 를 선택합니다. 원래 이 게시된 보기를 기본 보기로 선택한 경우 다시 게시한 후 사용자의 기본 보기가 됩니다. 

게시된 보기에 대한 변경 사항에 보기와 연결된 개인 설정 또는 필터의 수정이 포함되는 경우 다음 단계를 따르세요.

1. 변경하려는 게시된 보기를 로드합니다. 
2. 로컬 초안에 필요한 변경을 수행합니다.
3. 보기 선택기 드롭다운 메뉴에서 **다시 게시** 를 선택합니다.
4. **네** 를 선택하여 저장되지 않은 변경 사항과 함께 보기를 게시하려는 것을 나타냅니다. 
5. 조정이 필요한 게시 매개변수를 조정한 다음 **게시** 를 선택합니다. 

## <a name="managing-published-views"></a>게시된 보기 관리

개인적인 견해를 관리하는 것과 같이, **내 보기 관리** 대화 상자는 게시 권한이 있는 사용자에게 해당 페이지의 게시된 보기(자신의 개인 보기 추가)에 대한 기본 유지 관리 기능을 제공합니다. 이 페이지를 열려면 보기 이름을 선택하여 보기 선택기 드롭다운 메뉴를 열고 **더 보기** 를 선택한 다음 **내 보기 관리** 를 선택합니다.

모든 사용자의 **내 견해** 탭에 개인 보기를 표시하지만 게시 권한이 있는 사용자도 **조직 보기** 탭이 있고 여기에는 해당 페이지에 대해 게시된 보기와 게시되지 않은 보기가 모두 표시됩니다. 여러 사용자가 보기를 게시할 수 있으므로 지정된 보기를 게시한 사용자가 아니더라도 게시된 보기의 전체 목록을 관리할 수 있어야 합니다.

페이지에 대해 게시된 모든 보기 목록에 대해 다음 작업 세트를 사용할 수 있습니다. 

- **다시 게시** - **다시 게시** 작업을 사용하여 매개 변수(이름, 설명, 보안 역할 또는 법인)를 게시한 후 뷰를 다시 게시합니다.
- **게시** - **게시** 작업을 사용하여 현재 게시되지 않은 보기를 게시합니다. 
- **게시 취소** - **게시 취소** 작업을 사용하여 보기를 비활성화합니다. 보기는 시스템에서 계속 사용할 수 있지만 보기가 다시 게시될 때까지 사용자는 보기 선택기에서 보기를 볼 수 없습니다.
- **개인으로 저장** - **개인으로 저장** 작업을 사용하여 게시된 보기의 개인 초안 복사본을 만듭니다. 이 기능은 게시되지 않았거나 아직 게시되지 않은 보기의 내용을 이해하는 데 도움이 될 수 있습니다. 뷰를 편집한 다음 다시 게시하는 데 사용할 수도 있습니다.
- **삭제** - **삭제** 작업을 사용하여 게시되거나 게시되지 않은 보기를 영구적으로 삭제합니다. 이 작업은 시스템의 모든 사용자에 대한 보기도 제거합니다. 게시된 보기의 제거는 **저장** 버튼이 선택된 이후에 적용됩니다. 삭제된 보기는 복구할 수 없습니다. 

## <a name="managing-views-globally"></a>전 세계적으로 보기 관리

이 항목에 표시된 대로 일부 관리 기능이 모든 페이지에 표시되지만 **시스템 관리자** 및 **저장된 보기 관리자** 가 **개인화** 페이지를 통해 시스템에 대한 보기를 보다 총체적으로 관리할 수 있습니다. 특히 이 페이지에는 다음 섹션과 기능이 있습니다. 

- **게시된 보기** – 이 섹션에는 조직에 대해 게시된 모든 보기가 나열됩니다. 여기에서 보기가 대상으로 하는 보안 역할 또는 법인을 조정한 후 보기를 다시 게시할 수 있습니다. 보기를 내보내거나 삭제하거나 게시 취소할 수도 있습니다. **개인으로 저장** 작업을 사용하여 보기를 업데이트하거나 내용을 더 잘 이해할 수 있도록 보기의 개인 복사본을 만들 수 있습니다. 
- **미공개 조회수** – 이 섹션에는 현재 게시되지 않은 시스템의 모든 조직 보기가 나열됩니다. 이러한 보기는 대부분 가져오기 기능을 통해 시스템에 들어옵니다. 이러한 보기를 게시하거나 내보내거나 삭제할 수 있습니다. 버전 10.0.12에 추가된 **빠른 게시** 작업을 사용하면 기존 보안 역할 및 법인 구성을 사용하여 이 섹션의 여러 보기를 하나의 작업으로 게시할 수 있습니다. **개인으로 저장** 작업을 사용하여 보기를 업데이트하거나 내용을 더 잘 이해할 수 있도록 이러한 보기의 개인 복사본을 만들 수 있습니다.
- **개인적인 견해** – 이 섹션에는 시스템에서 사용자가 만든 모든 보기가 나열됩니다. 여기에서 개인 보기를 조직에 게시하거나 이러한 보기 중 하나 이상을 다른 사용자에게 복사할 수 있습니다. 필요한 경우 이러한 보기를 내보내거나 삭제할 수도 있습니다.
- **사용자 설정** – 볼 사용자를 선택하거나 전체 시스템 또는 사용자가 방문한 특정 페이지에 대해 개인화를 사용할 수 있는 사용자의 능력을 조정합니다. 시스템에서 사용자의 개인 설정을 보고 상호 작용할 수 있습니다. 해당 사용자에 대한 모든 개인화를 삭제하거나 사용자에 대한 기능 설명을 재설정할 수도 있습니다. 기능 콜아웃이 재설정되면 사용자가 이전에 닫은 새 기능을 소개하는 팝업 창이 다음에 사용자가 해당 기능을 접할 때 다시 나타납니다.
- **시스템 설정** – 시스템의 모든 사용자에 대해 개인화를 일시적으로 끌 수 있습니다. 이 경우 사용자에게 개인 설정이 적용되지 않고 모든 페이지가 기본 상태로 재설정됩니다. 나중에 개인 설정을 다시 켜면 모든 개인 설정이 다시 적용됩니다. 시스템의 모든 사용자에 대한 모든 개인 설정을 영구적으로 삭제할 수도 있습니다. 삭제된 개인화는 복구할 수 없습니다. 따라서 이 작업을 수행하기 전에 나중에 원할 수 있는 모든 개인 설정을 내보냅니다.

**개인화** 페이지에 대한 액세스 권한이 있는 사용자는 작업 창의 **보기 가져오기** 버튼을 사용하여 개인 또는 조직 보기를 가져올 수도 있습니다. 조직 보기의 경우 **즉시 게시** 를 선택하여 추가 명시적 게시 없이 사용자가 보기를 사용할 수 있도록 합니다.

## <a name="known-issues"></a>알려진 문제

저장된 보기의 알려진 문제 목록은 [저장된 보기를 완전히 활용하는 양식 작성](../../dev-itpro/user-interface/understanding-saved-views.md)을 참조하세요.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>내 환경에서 저장된 보기를 활성화하려면 어떻게 합니까?

> [!NOTE]
> **저장된 조회수** 기능을 사용하려면 재무 및 운영의 개인화 시스템이 활성화되어 있어야 합니다. 전체 환경에 대해 개인화를 끄면 아래 단계를 따라도 보기가 비활성화됩니다. 

모든 환경에서 기능 관리를 통해 **저장된 조회수** 기능을 켜고 끌 수 있습니다. 이 기능을 켜면 저장된 보기가 모든 후속 사용자 세션에서 활성화됩니다.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>보기가 활성화되면 기존 개인화는 어떻게 됩니까? 

보기가 활성화되면 사용자 및 양식에 대한 기존 개인 설정이 자동으로 기본 보기로 설정되는 **내 보기** 라는 새 보기에 저장됩니다. 이는 양식에 표시되는 보기 선택기 컨트롤을 제외하고 보기가 활성화되기 전과 후에 일관된 사용자 경험이 있는지 확인하기 위한 것입니다.

### <a name="what-pages-support-views"></a>보기를 지원하는 페이지는 무엇입니까? 

보기는 대부분의 페이지에서 사용할 수 있지만 모든 페이지에서 사용할 수 있는 것은 아닙니다. 특히 보기는 현재 대시보드 및 작업 영역을 제외한 모든 전체 화면 페이지에서 사용할 수 있습니다. 대화 상자, 드롭다운 대화 상자, 조회, 향상된 미리 보기를 포함하는 전체 화면이 아닌 페이지는 현재 보기를 지원하지 않습니다. 작업 공간 및 대화 상자와 같은 추가 페이지 유형에 대한 보기 지원은 향후 업데이트에서 고려할 수 있습니다.

### <a name="who-is-allowed-to-publish-views"></a>누가 보기를 게시할 수 있습니까?

**저장된 보기 관리자** 에 할당된 시스템 관리자 및 사용자만 보기를 게시할 수 있는 권한이 있습니다. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>이 보기에서 필터를 저장할 수 없는 이유는 무엇입니까? 

필터가 보기와 함께 저장되지 않는 것처럼 보이는 데에는 몇 가지 이유가 있습니다. 

- 페이지는 보기 정의의 일부로 필터 저장을 지원하지 않을 수 있습니다. 보기 선택기가 큰 페이지에서만 개인 설정 및 쿼리 수정 사항을 보기로 저장할 수 있습니다. 자세한 내용은 **보기 전환** 섹션을 참조하세요. 
- 문제의 페이지는 보기 쿼리를 완전히 무시하거나 데이터가 영구적이지 않은 임시 테이블에서 작동할 수 있으므로 보기를 제대로 지원하지 않을 수 있습니다. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>페이지를 방문하면 어떤 데이터가 표시되나요?

보기 선택기가 작은 페이지의 경우(보기에 개인 설정만 저장할 수 있음) 페이지를 방문할 때 항상 표시되는 것과 동일한 데이터가 표시됩니다. 

보기 선택기가 큰 페이지의 경우(개인화 및 쿼리 모두 보기에 저장할 수 있음) 일반적으로 기본 보기와 연결된 쿼리에 연결된 데이터를 볼 수 있습니다. 두 가지 주요 예외가 있습니다.

- 타일에서 페이지로 이동하는 경우 기본 보기와 연결된 쿼리에 관계없이 타일 쿼리가 실행됩니다. 보기가 활성화된 후 해당 타일을 만든 경우 타일을 선택하면 해당 타일과 연결된 보기가 있는 페이지가 열립니다.
- 페이지로 이동하고 해당 진입점에 쿼리가 포함된 경우 원래 쿼리는 기본 보기의 쿼리 대신 원래 실행됩니다. 보기가 로드될 때 정보 메시지를 통해 이러한 일이 발생하면 경고를 받아야 합니다. 페이지가 로드된 후 이 보기로 전환하여 확인할 수도 있습니다. 그렇게 하면 보기 쿼리가 상관없이 실행될 수 있기 때문입니다.

### <a name="why-is-a-view-that-was-published-for-a-specific-legal-entity-visible-in-all-legal-entities"></a>특정 법인에 대해 게시된 보기가 모든 법인에 표시되는 이유는 무엇입니까?

특정 법인에 보기를 게시하지만 해당 보기를 기본 보기로 게시하지 않는 경우 다음 동작이 발생합니다.

- 베이스 **저장된 조회수** 기능만 켜져 있으면 페이지에 대한 사용자의 보기 선택기가 처음에 지정된 법인에 대한 보기만 표시합니다. 그러나 보기가 처음 로드된 후에는 법인에 관계없이 페이지의 보기 선택기가 항상 보기를 표시합니다. 이 문제는 게시된 보기가 로드될 때 사용자가 자신의 개인 복사본을 가져오고 개인 보기가 전역이기 때문에 발생합니다.
- **버전 10.0.21 이상:** **저장된 보기에 대한 법인 지원 개선** 기능이 켜져 있으면 보기 지정된 법인에 대한 보기만 표시합니다. 이 동작은 보기(개인 보기 포함)를 특정 법인에 연결할 수 있도록 하기 때문에 발생합니다.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]