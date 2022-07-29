---
title: 워크플로 만들기 개요
description: 이번에는 워크플로를 만드는 방법에 대해 설명합니다.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "195583"
- intro-internal
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: abdb8ce3186806ac1b756c9161d53547dd8ae40b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460904"
---
# <a name="create-workflows-overview"></a>워크플로 만들기 개요

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이번에는 워크플로를 만드는 방법에 대해 설명합니다.

## <a name="open-the-workflow-editor"></a>워크플로 편집기 열기

작업 중인 모듈에 따라 생성할 수 있는 워크플로 유형이 결정됩니다. 다음 단계에 따라 생성할 워크플로 유형을 선택하고 워크플로 편집기를 엽니다.

1. 새 워크플로를 만들려는 모듈을 엽니다. 예를 들어 구매 요청에 대한 워크플로를 생성하려면 **조달 및 소싱** 을 클릭합니다.
2. **설정** &gt; **\[모듈 이름\] 워크플로** 를 클릭합니다.
3. 표시되는 목록 페이지의 작업 창에서 **새로 만들기** 를 클릭합니다.
4. **워크플로 만들기** 페이지에서 만들 워크플로 유형을 선택한 다음 **워크플로 만들기** 를 클릭합니다. 워크플로 편집기가 나타납니다. 이제 다음 절차를 사용하여 워크플로를 디자인할 수 있습니다.

## <a name="drag-workflow-elements-onto-the-canvas"></a>워크플로 요소를 캔버스로 드래그

워크플로 편집기의 **워크플로 요소** 영역에는 워크플로에 추가할 수 있는 요소가 있습니다. 워크플로에 요소를 추가하려면 캔버스로 끌어다 놓습니다.

## <a name="connect-the-elements"></a>요소 연결

한 워크플로 요소를 다른 요소에 연결하려면 연결점이 나타날 때까지 요소 위에 포인터를 둡니다. 연결 지점을 클릭하고 다른 요소로 끕니다. 모든 요소를 연결해야 합니다.

## <a name="configure-the-properties-of-the-workflow"></a>워크플로 속성 구성

다음 단계에 따라 워크플로 속성을 구성합니다.

1. 캔버스를 클릭하여 워크플로 요소가 선택되지 않았는지 확인합니다.
2. **속성** 을 클릭하여 워크플로의 **속성** 페이지를 엽니다.
3. [워크플로 속성 구성](configure-workflow-properties.md) 항목의 절차를 따릅니다.

## <a name="configure-the-elements-of-the-workflow"></a>워크플로 요소 구성

캔버스로 끌어온 각 요소를 구성합니다. 각 워크플로 요소를 구성하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.

- [워크플로에서 수동 작업 구성](configure-manual-task-workflow.md)
- [워크플로에서 자동화된 작업 구성](configure-automated-task-workflow.md)
- [워크플로에서 승인 프로세스 구성](configure-approval-process-workflow.md)
- [워크플로에서 승인 단계 구성](configure-approval-step-workflow.md)
- [워크플로에서 수동 결정 구성](configure-manual-decision-workflow.md)
- [워크플로에서 조건부 결정 구성](configure-conditional-decision-workflow.md)
- [워크플로에서 병렬 분기 구성](configure-parallel-activity-workflow.md)
- [병렬 분기 구성](configure-parallel-branch-workflow.md)
- [광고 항목 워크플로 구성](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>오류 또는 경고 해결

워크플로 편집기 하단의 **오류 및 경고** 창에는 워크플로에 대해 생성된 메시지가 표시됩니다. 오류 또는 경고가 발생한 요소를 찾으려면 오류 또는 경고 메시지를 두 번 클릭합니다. 워크플로를 활성화하려면 먼저 모든 오류와 경고를 해결해야 합니다.

## <a name="save-and-activate-the-workflow"></a>워크플로 저장 및 활성화

워크플로를 저장하고 활성화할 준비가 되면 다음 단계를 따르십시오.

1. **저장 후 닫기** 를 클릭하여 워크플로 편집기를 닫고 **워크플로 저장** 페이지를 엽니다.
2. 워크플로의 변경 사항에 대한 설명을 입력한 다음 **확인** 을 클릭합니다.
3. 모든 오류 및 경고가 해결되면 **워크플로 활성화** 페이지가 나타납니다. 다음 옵션 중 하나를 선택합니다.

    - 이 버전의 워크플로를 활성화하려면 **새 버전 활성화** 를 클릭합니다. 워크플로가 활성화되면 사용자는 처리를 위해 문서를 제출할 수 있습니다.
    - 이 버전을 활성화하지 않으려면 **새 버전 활성화 안 함** 을 클릭합니다. 나중에 워크플로를 활성화할 수 있습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]