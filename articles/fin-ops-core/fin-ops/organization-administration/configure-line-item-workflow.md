---
title: 광고 항목 워크플로 구성
description: 이번에는 항목 워크플로 요소를 구성하는 방법에 대해 설명합니다.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d6d9dcb99e00d4ce3f99e525a72421cb12af178
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460806"
---
# <a name="configure-line-item-workflows"></a>광고 항목 워크플로 구성

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이번에는 항목 워크플로 요소를 구성하는 방법에 대해 설명합니다.

라인 항목 워크플로 요소를 구성하려면 워크플로 편집기에서 요소를 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 클릭하여 **속성** 페이지를 엽니다. 이후 다음 절차를 사용하여 항목 워크플로 요소의 속성을 구성합니다.

## <a name="name-the-line-item-workflow-element"></a>광고 항목 워크플로 요소의 이름 지정

라인 항목 워크플로 요소의 이름을 입력하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
2. **이름** 필드에 라인 항목 워크플로 요소의 고유한 이름을 입력합니다.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>모든 광고 항목을 처리하는 데 동일한 워크플로가 사용되는지 여부 지정

문서의 모든 항목을 처리하는 데 동일한 워크플로가 사용되는지 여부를 지정하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
2. 동일한 워크플로가 문서의 모든 항목을 처리해야 하는 경우 **모든 항목에 대해 단일 워크플로 호출** 을 클릭합니다. 이후 라인 항목을 처리하는 데 사용할 워크플로를 선택합니다.
3. 특정 워크플로가 특정 조건 집합을 충족하는 광고 항목을 처리해야 하는 경우 **각 광고 항목에 대해 워크플로 호출** 을 클릭합니다. 이후 다음 단계에 따라 조건 집합을 정의합니다.

    1. **추가** 를 클릭합니다.
    2. 표에서 조건을 선택합니다.
    3. **조건 이름** 탭에서 정의하려는 조건 집합의 이름을 입력합니다.
    4. **조건 추가** 를 클릭하여 조건을 입력합니다.
    5. 필요한 추가 조건을 입력합니다.
    6. 입력한 조건 세트가 올바르게 구성되었는지 확인하려면 **테스트** 를 클릭하십시오. **테스트 워크플로 조건** 페이지의 **조건 확인** 영역에서 기록을 선택한 다음 **테스트** 를 클릭합니다. 시스템은 기록을 평가하여 정의한 조건을 충족하는지 여부를 결정합니다. **확인** 또는 **취소** 를 클릭하여 **속성** 페이지로 돌아갑니다.

    **워크플로** 탭에서 워크플로를 선택하고 정의한 조건 집합을 충족하는 라인 항목을 처리하는 데 사용할 워크플로를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]