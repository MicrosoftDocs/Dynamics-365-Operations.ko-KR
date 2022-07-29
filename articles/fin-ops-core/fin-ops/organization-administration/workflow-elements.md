---
title: 워크플로 요소
description: 이 항목에서는 워크플로를 구성하는 다양한 요소에 대해 설명합니다.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9491b8ee6da69ba93c830bf0721c1d58fd4385b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460738"
---
# <a name="workflow-elements"></a>워크플로 요소

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 항목에서는 워크플로를 구성하는 다양한 요소에 대해 설명합니다.

워크플로는 요소로 구성됩니다. 다음 섹션에서는 각 요소 유형에 대해 설명합니다.

## <a name="tasks"></a>작업

*작업* 은 수행해야 하는 작업 단위입니다. 수동 작업과 자동화된 작업의 두 가지 작업 유형을 워크플로에 추가할 수 있습니다.

### <a name="manual-task"></a>수동 작업

*수동 작업* 은 사용자가 수행해야 하는 작업 단위입니다. 예를 들어 경비 보고서 워크플로에는 할당된 사용자가 다음 작업을 완료해야 하는 수동 작업이 있을 수 있습니다.

- 경비 보고서와 함께 제출된 영수증을 검토합니다.
- 직원의 관리자에게 전화합니다.

### <a name="automated-task"></a>자동화된 작업

*자동화된 작업* 은 시스템이 수행해야 하는 작업 단위입니다. 인간의 상호 작용이 필요하지 않습니다. 예를 들어 판매 주문 워크플로에는 시스템이 다음 작업을 완료해야 하는 자동화된 작업이 있을 수 있습니다.

- 신용 조회를 합니다.
- 레코드가 아직 존재하지 않는 경우 고객에 대한 고객 레코드를 생성합니다.

## <a name="approval-processes"></a>승인 프로세스

*승인 절차* 는 별도의 단계로 구성된 프로세스입니다. 각 승인 단계에서 사용자는 다음 작업을 수행할 수 있습니다.

- 문서를 승인합니다.
- 문서를 거부합니다.
- 문서 변경을 요청합니다.
- 승인을 위해 문서를 다른 사용자에게 할당합니다.

## <a name="line-item-workflow-elements"></a>라인-항목 워크플로 요소

문서 또는 문서의 개별 항목을 처리하는 워크플로를 만들 수 있습니다. 예를 들어 작업표에 대한 승인 워크플로를 만들었습니다. (이 워크플로를 *문서 워크플로* 라고 하겠습니다.) *광고 항목 워크플로* 요소를 해당 문서 워크플로에 추가할 수 있습니다. 라인 항목 요소가 실행되면 문서의 각 라인 항목이 처리를 위해 제출됩니다. 모든 광고 항목이 동일한 광고 항목 워크플로에서 처리되기를 원하거나 각 광고 항목이 다른 광고 항목 워크플로에서 처리되기를 원할 수 있습니다. 직원이 다음 그림과 유사한 작업표를 제출했다고 가정합니다.

![광고 항목 워크플로.](./media/workflow_lineitemworkflow.gif)

이 시나리오에서는 다음 품목 워크플로를 생성할 수 있습니다.

- **광고 항목 워크플로 1** – 이 워크플로는 프로젝트 ID가 1111인 라인 항목을 처리하는 데 사용됩니다.
- **광고 항목 워크플로 2** – 이 워크플로는 프로젝트 ID가 2222인 라인 항목을 처리하는 데 사용됩니다.
- **광고 항목 워크플로 3** – 이 워크플로는 프로젝트 ID가 3333인 라인 항목을 처리하는 데 사용됩니다.

## <a name="flow-control-elements"></a>흐름 제어 요소

다음 요소를 사용하면 동시에 실행되는 대체 분기 또는 분기가 있는 워크플로를 디자인할 수 있습니다.

### <a name="manual-decision"></a>수동 결정

*수동 결정* 은 워크플로가 두 개의 분기로 나뉘는 지점입니다. 사용자는 결정을 내려야 하며 이 결정은 제출된 문서를 처리하는 데 사용되는 분기를 결정합니다.

### <a name="conditional-decision"></a>조건부 결정

*조건부 결정* 도 워크플로가 두 개의 분기로 나뉘는 지점입니다. 그러나 시스템은 제출된 문서를 처리하는 데 사용되는 분기를 결정합니다. 이러한 결정을 내리기 위해 시스템은 문서를 평가하여 문서가 지정된 조건을 충족하는지 여부를 결정합니다.

### <a name="parallel-activity"></a>병렬 활동

*병렬 활동* 은 동시에 실행되는 둘 이상의 워크플로 분기를 포함하는 워크플로 요소입니다.

### <a name="subworkflow"></a>하위 워크플로

*하위 워크플로* 는 다른 워크플로의 컨텍스트에서 실행되는 워크플로입니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]