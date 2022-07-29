---
title: 탐색 검색
description: 이 토픽에서는 검색 기능을 사용하여 페이지를 탐색하는 방법에 대해 설명합니다.
author: aneesmsft
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e689bef43930dbe364baefaa9f4d0231394ff4f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460856"
---
# <a name="navigation-search"></a>탐색 검색

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 토픽에서는 검색 기능을 사용하여 페이지를 탐색하는 방법에 대해 설명합니다.

응용 프로그램에는 다양한 작업을 수행하는 데 도움이 되는 여러 영역과 페이지가 포함되어 있습니다. 작업을 완료하는 데 필요한 페이지를 빠르게 찾으려면 탐색 검색 기능을 사용하세요.

이 기능을 사용하려면 **검색** 아이콘을 클릭하여 **검색** 상자를 표시합니다. 그런 다음 상자에 하나 이상의 단어를 입력할 수 있습니다. 시스템은 입력한 단어와 일치하는 응용 프로그램의 관련 페이지를 즉시 검색합니다. 예를 들어, "공급업체 송장"을 입력으로 입력하면 시스템이 해당 입력과 일치하는 결과를 표시합니다.

> [!NOTE]
> **검색** 상자는 페이지를 찾고 탐색하는 데 도움이 됩니다. 특정 데이터나 작업을 찾는 데 도움이 되지 않습니다.

![검색 상자.](media/navigation-search.png "검색 상자")

## <a name="quickly-navigate-to-a-particular-page"></a>특정 페이지로 빠르게 이동

탐색 검색 기능은 특정 페이지로 빠르게 이동할 수 있는 좋은 방법이기도 합니다. 예를 들어, **지불 분개장** 페이지를 자주 사용하는 지급 계정 직원인 경우 **검색** 상자에 "지불 저널"을 입력할 수 있습니다. 입력이 페이지 제목과 정확히 일치하기 때문에 페이지가 검색 결과의 맨 위에 나열되고 빠르게 탐색할 수 있습니다.

검색 결과 목록에는 페이지 제목과 탐색 경로가 표시됩니다. 이것은 애플리케이션에서 페이지의 위치를 보여줍니다. 또한 결과에서 두 개 이상의 유사한 페이지를 구별하는 데 도움이 됩니다.

페이지를 검색할 때 입력은 페이지 제목 및 탐색 경로와 일치합니다. 예를 들어, **검색** 상자에 "receivable"을 입력하면 페이지 제목에 "미수금"이라는 단어가 포함되어 있지 않더라도 매출 채권 영역에서 사용 가능한 페이지에 대한 결과를 볼 수 있습니다.

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>기술 양식 이름을 기반으로 페이지로 빠르게 이동

탐색 검색 기능에는 고급 사용자가 많이 요청한 기능인 기술 양식 이름을 기반으로 페이지를 빠르게 탐색하는 기능도 포함되어 있습니다. 많은 사용자가 시스템에 너무 익숙하여 작업하는 정확한 양식 이름을 알고 있습니다. 이러한 사용자 중 하나인 경우 **형태:** 를 입력하고 찾고 있는 양식의 이름을 입력할 수 있습니다. 예를 들어 **형식: vendinvoice** 를 입력하면 검색 결과에는 양식 이름이 **vendinvoice** 로 시작하는 모든 페이지가 표시됩니다.

## <a name="administration-and-security"></a>관리 및 보안

관리 및 보안 관점에서 탐색 검색 기능은 두 가지 유형의 결과만 표시합니다.

- 현재 구성에서 활성화된 페이지(구성 키를 통해).
- 사용자의 역할에 따라 사용자가 액세스할 수 있는 페이지입니다.

검색 결과 목록은 10개 항목으로 제한됩니다. 결과에서 원하는 것을 찾지 못하면 입력을 수정하거나 업데이트해야 합니다.

## <a name="development"></a>개발

개발 관점에서 탐색 검색 기능은 메뉴 항목 배포와 검색 결과에 나타나는 기능 사이에 거의 지연이 없기 때문에 활용하기 쉽습니다. 메뉴 항목이 탐색 창이나 대시보드에서 연결되어 있는 한 자동으로 검색 가능하게 됩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
