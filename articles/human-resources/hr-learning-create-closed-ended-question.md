---
title: 폐쇄형 질문 만들기
description: 폐쇄형 질문으로 응답자가 선택할 수 있는 옵션을 제공할 수 있습니다.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3b90bb2a4981f32feb10ee1192e9c4d2e604e7a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452350"
---
# <a name="create-a-closed-ended-question"></a>폐쇄형 질문 만들기


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



폐쇄형 질문으로 응답자가 선택할 수 있는 옵션을 제공할 수 있습니다. 먼저 응답이 포함된 응답 그룹을 만든 다음 해당 응답 그룹을 사용할 질문을 만들어야 합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="create-an-answer-group"></a>응답 그룹 만들기
1. **설문지** > **설계** > **응답 그룹** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **응답 그룹** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
    * **임의 지정** 기능을 사용하여 질문에 응답 그룹이 사용될 때마다 응답을 무작위로 다른 순서로 배치합니다.  
5. **응답** 을 클릭합니다.
6. **새로 만들기** 를 클릭합니다.
    * 시퀀스 번호는 **응답 그룹** 에 **임의 지정** 을 선택하지 않는 한 응답이 표시되는 순서를 제어합니다.  
    * 설문지 채점에 사용하기 위해 응답에 점수를 부여할 수 있습니다.  
7. **점수** 필드에 숫자를 입력합니다.
    * 정답은 선택한 응답이 정답임을 나타내기 위해 표시될 수 있습니다. 이는 설문지를 채점하는 데 사용할 수 있습니다.  
8. **응답** 필드에 값을 입력합니다.
    * 계속해서 응답 그룹에 대한 응답 선택 옵션을 만듭니다.  
9. **새로 만들기** 를 클릭합니다.
10. **점수** 필드에 숫자를 입력합니다.
11. **응답** 필드에 값을 입력합니다.
12. **새로 만들기** 를 클릭합니다.
13. **점수** 필드에 숫자를 입력합니다.
14. **응답** 필드에 값을 입력합니다.
15. **새로 만들기** 를 클릭합니다.
16. **점수** 필드에 숫자를 입력합니다.
17. **응답** 필드에 값을 입력합니다.
18. **새로 만들기** 를 클릭합니다.
19. **점수** 필드에 숫자를 입력합니다.
20. **응답** 필드에 값을 입력합니다.
21. 페이지를 닫습니다.
22. 페이지를 닫습니다.

## <a name="create-the-question"></a>질문 만들기
1. **설문지** > **디자인** > **질문** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **유형** 필드를 사용하여 관련 질문을 함께 그룹화합니다.
    * 폐쇄형 질문에 **확인란**, **대체 버튼** 또는 **콤보 상자** 입력 유형을 사용할 수 있습니다.  
4. **입력 유형** 필드에서 옵션을 선택합니다.
5. **응답 그룹** 필드에 값을 입력하거나 선택합니다.
6. **텍스트** 필드에 값을 입력합니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
