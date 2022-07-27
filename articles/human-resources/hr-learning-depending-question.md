---
title: 이전 질문의 응답에 따른 질문 만들기
description: 조건부 질문을 사용하면 이전 질문의 응답을 기반으로 응답자에게 제시할 후속 질문을 지정할 수 있습니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f28f75a902121f23c92a919b539517dbdb191447
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452260"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>이전 질문의 응답에 따른 질문 만들기


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



조건부 질문을 사용하면 이전 질문의 응답을 기반으로 응답자에게 제시할 후속 질문을 지정할 수 있습니다. 예를 들어, "커피를 선호합니까? 아니면 차를 선호합니까?"라고 묻는 경우 응답자가 응답으로 커피 또는 차를 선택하는지에 따라 논리적 후속 질문을 결정할 수 있습니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="find-the-existing-questionnaire"></a>기존 설문지 찾기
1. **설문지** > **디자인** > **설문지** 로 이동합니다.
2. 목록에서 WorkFH 설문지를 선택합니다.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>설문지에 모든 질문 및 하위 질문 추가
1. **질문** 을 클릭합니다.
2. **새로 만들기** 를 클릭합니다.
3. **질문** 필드에서 질문 번호 00016을 선택합니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. **저장** 을 클릭합니다.
7. 페이지를 닫습니다.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>질문 순서를 조건부로 설정하고 적절한 질문의 후속 질문 만들기
1. **편집** 을 클릭합니다.
2. **설정** 섹션을 확장합니다.
3. **질문 순서** 필드에 '조건부'를 선택합니다.
4. **조건부** 질문을 클릭합니다.
5. 트리에서 '질문\이전 질문에 그와 같이 답변한 이유를 설명해주세요'를 선택합니다.
6. **기본 질문** 필드에서 질문 00009를 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **응답** 필드에 질문이 종속될 응답 옵션의 응답 시퀀스 ID를 입력합니다. 예를 들어 첫 번째 응답 옵션의 경우 1을 입력합니다.
9. **저장** 을 클릭합니다.
10. 트리에서 '질문\내가 하는 일에 정당한 급여를 받습니다.'를 선택합니다.
    * 질문 트리가 업데이트되어 종속성이 표시됩니다.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
