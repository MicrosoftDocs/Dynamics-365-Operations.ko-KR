---
title: 워크플로에서 병렬 활동 구성
description: 병렬 활동을 구성하려면 워크플로 편집기에서 다음 절차를 완료하십시오.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 054d62e2ff094aee987f8c6e04e2f2e173da633d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460907"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>워크플로에서 병렬 활동 구성

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

병렬 활동을 구성하려면 워크플로 편집기에서 다음 절차를 완료하십시오.

병렬 활동은 동시에 실행되는 워크플로 분기로 구성됩니다.

## <a name="name-a-parallel-activity"></a>병렬 활동 이름 지정

병렬 활동의 이름을 입력하려면 다음 단계를 따르십시오.

1. 병렬 작업을 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 클릭하여 **속성** 양식을 엽니다.
2. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
3. **이름** 필드에 병렬 활동의 고유 이름을 입력합니다.
4. **닫기** 를 클릭합니다.

## <a name="configure-the-branches-of-a-parallel-activity"></a>병렬 활동의 분기 구성

이 병렬 활동의 분기를 추가하고 구성하려면 다음 단계를 따르십시오.

1. 병렬 작업을 두 번 클릭하여 병렬 작업의 분기를 표시합니다.
2. **분기** 를 추가하려면 **워크플로 요소** 영역에서 캔버스의 삽입 지점으로 분기 요소를 끕니다. 다음 그림은 삽입점을 보여줍니다.

    ![삽입점.](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > 병렬 활동의 모든 분기가 동시에 실행되기 때문에 분기의 순서는 중요하지 않습니다.

3. 각 분기를 구성하려면 [워크플로에서 병렬 분기 구성](configure-parallel-branch-workflow.md)을 참조하십시오.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]