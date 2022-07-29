---
title: 필드 설명 보기 및 내보내기
description: 이 문서에서는 필드 설명을 보는 방법과 필드 설명 페이지를 사용하여 설명을 내보내는 방법에 대해 설명합니다.
author: rschloma
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea52c39ef1c7d7b62f20da9fe4d94103119ccc23
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460748"
---
# <a name="view-and-export-field-descriptions"></a>필드 설명 보기 및 내보내기

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 문서에서는 필드 설명을 보는 방법과 필드 설명 페이지를 사용하여 설명을 내보내는 방법에 대해 설명합니다.

더 복잡한 필드 중 일부에는 필드 설명이 있습니다. 이러한 설명은 필드 위로 마우스를 가져가면 나타납니다. **필드 설명** 페이지에서 설명을 보고 내보낼 수도 있습니다.

모든 페이지에 필드 설명이 있는 것은 아닙니다. 우리는 필드의 사용이 명백한 곳이 아닌 더 복잡한 필드에 대해서만 설명을 제공하려고 합니다. 따라서 일부 페이지에는 필드 설명이 없고 일부 페이지에는 몇 가지 설명이 있으며 많은 매개변수 페이지와 같은 더 복잡한 일부 페이지에는 많은 설명이 있습니다.

개발 환경에 대한 액세스 권한이 있는 경우 새 필드 설명을 추가하고 기존 설명을 사용자 지정할 수 있습니다. 예를 들어, 회사 관련 정보를 필드 설명에 추가할 수 있습니다. 자세한 내용은 [필드 설명 사용자 정의](../../dev-itpro/user-interface/customize-field-help.md)를 참조하세요.

## <a name="see-field-descriptions-in-the-user-interface"></a>사용자 인터페이스에서 필드 설명 보기

필드 위로 마우스를 가져가면 필드 설명을 볼 수 있습니다. 설명을 사용할 수 없는 경우 필드 위로 마우스를 가져가면 필드 이름이 표시됩니다.

> [!NOTE]
> Dynamics AX 7.0(2016년 2월)에서 필드 설명은 **필드 설명** 페이지에서만 볼 수 있습니다.

다음 그림은 마우스를 **카운트 중 항목 잠금** 필드 위로 가져가면 나타나는 필드 설명을 보여줍니다.

[![필드 설명의 예.](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>필드 설명 페이지를 사용하여 필드 도움말 보기 및 내보내기

**필드 설명** 페이지에서 필드 설명을 보고 내보낼 수 있습니다. 한 번에 한 페이지에 사용할 수 있는 설명을 볼 수 있습니다.

### <a name="view-the-descriptions-for-a-page"></a>페이지에 대한 설명 보기

페이지에 대한 설명을 보려면 다음 단계를 따르세요.

- **페이지 선택** 필드에 페이지 이름을 입력합니다. 또는 화살표를 클릭하여 모든 페이지 목록을 연 다음 목록을 찾아보거나 필터링합니다.

사용자 인터페이스(UI)에 표시되는 페이지 이름(예: **고객**) 또는 페이지를 마우스 오른쪽 버튼으로 클릭할 때 사용할 수 있는 코드 이름(AOT 이름)(예: **CustTable**)을 사용할 수 있습니다.

페이지 목록을 필터링하는 다양한 방법에 대한 자세한 내용은 이 문서 뒷부분의 "페이지 검색" 절을 참조하세요.

**설명이 없는 필드 포함** 옵션을 **네** 로 설정하면 필드 설명이 없는 경우에도 페이지의 모든 필드가 표시됩니다.

### <a name="export-the-descriptions-for-a-page"></a>페이지에 대한 설명 내보내기

페이지에 대한 설명을 내보내려면 다음 단계를 따르세요.

1. **페이지 선택** 필드에서 페이지를 선택합니다.
2. 오른쪽 상단에서 **Microsoft Office에서 열기** 버튼을 클릭한 다음 **FieldDescriptionTmp** 를 클릭합니다.

### <a name="searching-for-a-page"></a>페이지 검색

**페이지 선택** 필드에서 여러 가지 방법으로 페이지를 검색할 수 있습니다. 대부분의 경우 **페이지 선택** 필드에서 화살표를 클릭해 드롭다운 목록을 연 다음 필터링된 페이지 목록에서 선택합니다.

- 이름의 일부를 입력한 다음 드롭다운 목록을 열어 필터링된 페이지 목록에서 선택합니다.
- 드롭다운 목록을 열고 목록 상단의 **페이지 이름** 제목 또는 **페이지 AOT 이름** 제목을 클릭합니다. **다음으로 시작하는 페이지 이름** 과 같은 고급 필터링 옵션을 사용할 수 있는 대화 상자가 나타납니다.
- 페이지의 전체 이름을 입력합니다. 이 옵션을 사용하는 경우 필드 설명이 표시되더라도 드롭다운 목록을 열고 목록에 있는 다른 항목을 확인하는 것이 가장 좋습니다.

    - 이름과 정확히 일치하는 항목이 하나 있는 경우 해당 페이지에 대한 필드 설명이 표시됩니다.
    - 정확히 일치하는 항목이 두 개 이상 있으면 설명이 표시되지 않습니다. 드롭다운 목록을 열고 원하는 페이지를 선택해야 합니다.
    - 입력한 이름이 다른 페이지 이름의 일부인 경우 해당 페이지에 대한 설명이 표시됩니다. 그러나 드롭다운 목록을 열면 해당 이름이 포함된 추가 페이지가 표시됩니다.

예를 들어 **페이지 선택** 필드에 **계산** 을 입력할 때 설명이 표시되지 않습니다. 드롭다운 목록을 열고 이름이 **카운팅** 인 두 페이지가 있는지 확인하고 이름에 "Counting"이라는 단어가 포함된 여러 페이지가 있는지 확인합니다. AOT 이름 **InventJournalCount** 가 있는 페이지를 선택하면 해당 페이지에 대한 필드 설명이 표시됩니다. 그러나 드롭다운 목록을 다시 열면 이제 목록에 AOT 이름의 일부로 "InventJournalCount"가 있는 모든 페이지가 포함되어 있음을 알 수 있습니다.

## <a name="troubleshooting"></a>문제 해결

이 섹션에서는 필드 설명을 사용할 때 발생할 수 있는 문제를 해결하는 데 도움이 되는 정보를 제공합니다.

### <a name="i-cant-find-a-field-description"></a>필드 설명을 찾을 수 없습니다

더 복잡한 필드에 대한 설명을 추가하는 중입니다. 특정 필드에 대한 도움이 필요한 경우 이 주제에 대한 의견을 추가하여 알려주세요.

### <a name="the-field-description-isnt-helpful"></a>필드 설명이 도움이 되지 않습니다

이 주제에 대한 의견을 추가하여 알려주세요. 가능한 경우 필요한 추가 정보를 설명하세요.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>필드 설명 페이지에서 필드를 찾을 수 없습니다

페이지의 모든 필드를 표시하려면 **설명이 없는 필드 포함** 옵션을 **네** 로 설정합니다. **페이지 선택** 필드를 클릭하여 올바른 페이지를 선택했는지 확인합니다. 입력한 이름이 다른 필드 이름의 일부인 경우 이름이 더 긴 페이지를 선택했을 수 있습니다.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>필드 설명 페이지에서 페이지를 찾을 수 없습니다

페이지를 찾는 다양한 방법에 대한 자세한 내용은 이 문서 앞부분의 "페이지 검색" 섹션을 참조하세요. 페이지의 정확한 이름을 입력한 경우 두 개 이상의 페이지에 동일한 이름이 있는 경우 필드 설명이 표시되지 않을 수 있습니다. **페이지 선택** 필드에서 화살표를 클릭하여 사용 가능한 페이지의 필터링된 목록을 엽니다.

## <a name="additional-resources"></a>추가 리소스

[필드 설명 사용자 정의](../../dev-itpro/user-interface/customize-field-help.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]