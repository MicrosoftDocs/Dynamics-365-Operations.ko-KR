---
title: 워크플로에서 조건부 결정 구성
description: 다음 절차를 사용하여 조건부 결정의 속성을 구성합니다.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fa708b4ac1f17a9ed6852a9eeb3e764b750a4a4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460807"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a>워크플로에서 조건부 결정 구성

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

다음 절차를 사용하여 조건부 결정의 속성을 구성합니다.

조건부 결정은 워크플로가 두 개의 분기로 나뉘는 지점입니다. 조건부 결정을 구성하려면 워크플로 편집기에서 조건부 결정을 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 클릭하여 **속성** 양식을 엽니다.

## <a name="name-a-decision"></a>결정 이름 지정

조건부 결정의 이름을 입력하려면 다음 단계를 따르십시오.

1. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
2. **이름** 필드에 조건부 결정에 대한 고유한 이름을 입력합니다.

## <a name="set-conditions"></a>조건 설정

시스템은 제출된 문서를 평가하여 특정 조건을 충족하는지 여부를 판단하여 사용되는 분기를 결정합니다.

1. 왼쪽 창에서 **기본 설정** 을 클릭합니다.
2. **조건 추가** 를 클릭합니다.
3. 조건을 입력합니다.
4. 필요한 경우 추가 조건을 입력합니다.
5. 입력한 조건이 올바르게 구성되었는지 확인하려면 다음 단계를 완료하십시오.

    1. **테스트** 를 클릭하여 **테스트 워크플로 조건** 양식을 엽니다.
    2. 양식의 **조건 확인** 영역에서 기록을 선택합니다.
    3. **테스트** 를 클릭합니다. 시스템은 기록을 평가하여 정의한 조건을 충족하는지 여부를 결정합니다.
    4. **확인** 또는 **취소** 를 클릭하여 **속성** 양식으로 돌아갑니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]