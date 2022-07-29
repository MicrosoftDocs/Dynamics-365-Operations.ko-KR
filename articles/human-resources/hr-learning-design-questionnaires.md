---
title: 설문지 만들기
description: 이 항목은 설문지를 만드는 절차를 설명합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 90dd59b605c21abd03d2e0d64a89dc787850c26e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452104"
---
# <a name="create-questionnaires"></a>설문지 만들기


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목은 설문지를 만드는 절차를 설명합니다. 첫 번째 단계는 설문지를 디자인하는 것입니다. 설문지를 디자인할 때는 질문과 응답을 작성하는 것은 물론 응답을 기록하고 표로 만들 수 있는 구조도 만듭니다. 

신중하게 디자인된 설문지는 수집하는 데이터의 품질을 높이는 데 도움이 될 수 있습니다. 세심한 디자인을 통해 적절한 옵션을 적절한 시점에 선택하여 설문지를 작성할 수 있습니다. 다음 사항은 효과적인 설문지를 계획하는 데 도움이 될 수 있습니다.

-   질문이 목적을 뒷받침할 수 있도록 설문지의 목적을 명확하게 정의합니다.
-   설문지를 작성해야 하는 개인 또는 그룹을 결정합니다.
-   설문지에 표시될 질문을 작성하고 해당되는 경우 응답 선택을 포함합니다.
-   응답자가 집중할 수 있도록 설문지가 논리적으로 흘러야 합니다.
-   질문과 답변을 응답자에게 제시해야 하는 순서대로 배열합니다.
-   해당되는 경우 결과를 평가하는 방법을 결정합니다.
-   추가 기능이 필요한지를 결정합니다. 예를 들어 결과를 분류해야 하는지와 그 방법, 시간 제한이 필요한지 또는 모든 질문이 필수 항목인지를 결정합니다.

디자인 단계에는 이 순서로 완료해야 하는 네 범주의 작업이 포함됩니다.

1.  필요에 따라 전제 조건을 설정합니다.
2.  해당하면 응답 그룹 및 응답을 설정합니다.
3.  질문 및 응답 그룹과의 연결을 설정합니다.
4.  설문지 자체를 설정하고 질문을 첨부합니다.

## <a name="prerequisites"></a>전제 조건
설문지, 응답 및 질문을 만들려면 몇 가지 전제 조건이 있어야 합니다. 그러나 모든 전제 조건이 전체 기능에 필요한 것은 아닙니다.

### <a name="required"></a>필수

| 전제 조건        | 설명                |
|---------------------|----------------------------|
| 설문지 유형 | 설문지 범주를 지정합니다. |
| 질문 유형      | 질문 범주를 지정합니다.      |

### <a name="optional"></a>옵션

| 전제 조건             | 설명                                                    |
|--------------------------|----------------------------------------------------------------|
| 설문지 매개 변수 | 설문지에 대한 기본 제어와 기본 설정을 수정합니다. |

### <a name="questionnaire-types"></a>설문지 유형

**설문지 유형** 은 필수 항목이며 설문지를 만들 때 할당해야 합니다. **설문지 유형** 으로 설문지를 더 쉽게 관리하고 분류할 수 있습니다. 설문지 유형을 사용하여 설문지를 분류하고 서로 구분합니다. 예를 들어 선택할 설문지가 여러 개인 경우 유형별로 필터링하여 특정 설문지를 더 쉽게 찾을 수 있습니다. 다음은 설문지 유형의 몇 가지 예입니다.

-   인적 자원 개발
-   고객 설문 조사
-   리뷰 프로세스

### <a name="question-types"></a>질문 유형

**질문 유형** 은 필수 항목이며 질문을 만들 때 할당해야 합니다. 

**질문 유형** 을 사용하여 보고할 질문을 분류합니다. **질문 유형** 을 사용하면 **질문** 페이지에서 유형을 필터로 사용할 수 있으므로 질문을 더 쉽게 찾을 수 있습니다. 다음은 질문 유형의 몇 가지 예입니다.

-   인적 자원
-   사업 관리
-   과정 평가

### <a name="questionnaire-parameters"></a>설문지 매개 변수

설문지 매개 변수는 선택 사항입니다. 회사의 요구 사항에 따라 사용하지 않을 수도 있습니다. 

설문지 매개 변수는 설문지의 익명성, 번호 시퀀스 코드 및 참조 유형을 정의합니다. 조직에서 설문지를 배포할 때 응답자가 익명으로 유지되도록 허용하는 옵션이 문제가 될 수 있습니다. 

일련 번호 코드는 질문과 답변을 구성하는 데 사용됩니다. 이러한 일련 번호 코드를 기반으로 항목에 값이 자동으로 할당됩니다. 

데이터 생성을 시작하기 전에 모든 매개 변수를 정의해야 합니다. 설문지 매개 변수 설정은 언제든지 수정할 수 있습니다.

## <a name="questionnaire-components"></a>설문지 구성 요소
설문지는 객관식 질문에 대한 응답을 포함하는 응답 그룹, 질문 및 설문지 자체의 세 주요 요소로 구성됩니다. 선택적으로 설문지의 질문을 결과 그룹으로 그룹화할 수 있습니다. 결과 그룹을 사용하면 질문을 분류하고 설문지에 대한 추가 분석을 제공할 수 있습니다. 

[![QuestionnaireComponents.](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>응답 그룹 및 응답

응답자는 질문의 주제에 따라 두 가지 방법으로 질문에 대답할 수 있습니다.

-   개방형 질문에는 특정 형식의 응답이 필요하지 않습니다. 응답자는 텍스트, 숫자, 날짜 또는 시간으로 응답을 입력할 수 있습니다. 이러한 질문에 대해 일반적으로 응답자는 의견, 설명, 평가 또는 추정과 같은 주관적인 정보를 제공해야 합니다.
-   폐쇄형 질문은 응답자가 가능한 정답 목록에서 답을 선택해야 합니다.

비공개 질문에 대해 가능한 응답 목록을 제공하려면 **응답 그룹** 페이지에서 응답을 만들 수 있습니다. 

응답 그룹 및 응답은 질문이 생성되는 정보의 본문을 구성하는 구성 요소입니다. 응답 그룹을 만든 후 **질문** 페이지의 **응답 그룹** 필드에 있는 질문과 응답 그룹을 연결할 수 있습니다. 

**응답 그룹** 은 동일한 설문지에서 둘 이상의 질문에 사용할 수 있으며 둘 이상의 설문지에도 사용할 수 있습니다. 

> [!NOTE]
> 완료된 설문지에 이미 사용된 응답 그룹의 응답 텍스트를 수정하면 데이터를 평가하기 어려워지고 설문지 결과가 더는 유효하지 않을 수 있습니다. 응답 그룹을 변경해야 하는 경우 기존 응답 그룹을 변경하는 대신 새 응답 그룹을 만드는 것이 좋습니다. 질문이나 응답에 연결되거나 응답한 응답 그룹은 삭제할 수 없습니다.

### <a name="questions"></a>질문

설문지에는 질문이 포함되어야 합니다. 질문은 개방형이거나 폐쇄형일 수 있습니다.

-   개방형 질문에 대한 응답은 통제되지 않으며 응답자는 응답을 입력할 수 있습니다.
-   폐쇄형 질문에는 미리 정의된 응답 옵션 목록이 필요하며 응답자가 여러 응답을 선택할 수 있도록 질문을 구성할 수 있습니다. 질문은 응답자로부터 특정 정보를 끌어내도록 설계되어야 하며 각 폐쇄형 질문에 대해 응답 옵션을 제공하는 응답 그룹에 연결되어야 합니다. 

    > [!NOTE]
    > 폐쇄형 질문을 설정하려면 먼저 응답 그룹과 응답을 만들어야 합니다.

질문을 조건부 질문 계층 구조로 정렬할 수 있으며 보조 질문은 응답자가 이전 질문에 대해 선택한 응답에 따라 달라집니다. 먼저 질문을 작성한 다음 나중에 계층 구조로 정렬할 수 있습니다.

## <a name="setting-up-questionnaires"></a>설문지 설정

> [!NOTE]
> 설문지를 설정하기 전에 응답, 질문 및 전제 조건을 설정해야 합니다. 

각 질문에 대해 다음 정보를 지정할 수 있습니다.

-   필수 질문에 응답하는 총시간 또는 시간 제한.
-   모든 질문이 필수인지 여부.
-   설문지에서 점수를 계산할지 여부.
-   결과를 분류하는 방법.
-   제한된 응답자 집합에만 설문지가 제공되는지 여부.
-   양식 서식 파일을 설문지의 각 페이지 뒤에 배경으로 표시할지 여부.
-   응답자에게 설문지의 의도를 명확히 하기 위해 추가 메모가 필요한지 여부.
-   질문을 고정된 순서로 표시할지 아니면 풀에서 무작위로 선택할지 여부.
-   이전 응답에 대해 특정 응답이 제공된 경우에만 질문할지 여부.

### <a name="set-up-a-questionnaire"></a>설문지 설정

설문지를 설정하는 데 사용하는 기본 페이지는 **설문지** 페이지입니다. 설문지를 설정하려면 다음 작업을 순서대로 완료합니다.

1.  설문지를 만듭니다.
2.  설문지에 질문을 첨부하려면 다음 단계 중 하나를 따릅니다.
    -   결과 그룹을 사용하는 경우 결과 그룹을 사용하여 질문을 설문지에 첨부할 수 있습니다. 먼저 설문지에 대한 결과 그룹을 설정한 다음 결과 그룹에 질문을 추가합니다.
    -   결과 그룹을 사용하지 않는 경우 결과 질문을 곧바로 설문지에 첨부할 수 있습니다.

3.  필요한 경우 조건부 질문 계층을 설정합니다.
4.  설문지를 테스트합니다.

**설문지** 페이지에서 **유효성 검사** 를 클릭하여 설문지가 올바로 구성되었는지 테스트합니다. 그러나 설문지를 작성하고 배포하기 전에 직접 테스트하는 것도 좋은 생각입니다.

### <a name="modify-a-questionnaire"></a>설문지 수정

**설문지** 페이지에서 다음 작업을 완료할 수 있습니다.

-   결과 그룹 및 질문과 같은 설문지의 정보를 수정합니다.
-   질문을 삭제하고 추가합니다.
-   결과 그룹 및 시퀀스 번호를 변경합니다. 

> [!CAUTION]
> 이미 응답한 설문지를 변경할 때는 주의하세요. 변경하면 통계의 정확성을 떨어뜨리고 평가의 기반을 악화할 수 있습니다. 이미 응답한 질문을 변경하는 대신 새 질문을 만드는 것을 고려하세요.

설문지에서 다음 유형의 질문은 삭제할 수 없습니다.

-   설문지에 첨부된 질문
-   이미 응답하여 **응답** 대화 상자에 표시되는 질문.

### <a name="result-groups"></a>결과 그룹

**결과 그룹** 은 질문을 설문지에 첨부할 때 선택 사항입니다. 

결과 그룹은 점수를 계산하고 설문지 결과를 분류하는 데 사용됩니다. 결과 그룹을 사용하면 다음 작업을 수행할 수 있습니다.

-   포인트 통계를 기반으로 설문지 결과를 평가합니다.
-   설정한 각 결과 그룹에 대한 응답자의 점수를 평가합니다.
-   결과 분석에 도움이 되도록 각 결과 그룹에 대한 통계를 생성합니다.
-   각 결과 그룹에 대한 결과를 표시하는 보고서와 각 결과 그룹에서 획득한 점수에 기반을 두는 선택적인 점수/텍스트를 출력합니다.

> [!NOTE]
> 결과 그룹을 설정하려면 먼저 다음 작업을 완료해야 합니다.

-   폐쇄형 질문을 설정합니다. 폐쇄형 질문의 경우 **질문** 페이지의 입력 유형이 **확인란**, **대체 버튼** 또는 **콤보 상자** 여야 합니다.
-   각 질문에 할당된 응답 그룹에서 응답에 대한 점수를 정의합니다.
-   설문지를 설정합니다.

결과 그룹을 사용하여 질문을 설문지에 첨부하려면 먼저 설문지에 대한 결과 그룹을 설정하고 결과 그룹에 질문을 추가합니다. 결과 그룹을 사용하지 않는 경우 결과 질문을 곧바로 설문지에 첨부할 수 있습니다. 

여러 결과 그룹을 설정하여 응답자가 각 범주에서 얻은 점수를 평가할 수 있습니다. 설문지가 완료되면 각 결과 그룹에 대해 달성한 포인트를 볼 수 있습니다. 

> [!TIP]
> 개별 범주가 아닌 점수로 설문지를 평가하려면 모든 질문을 단일 결과 그룹에 추가할 수 있습니다. 

각 결과 그룹에 대해 응답자가 설문지를 완료한 후 받는 하나 이상의 점수 기반 메시지를 설정할 수도 있습니다. 응답자가 결과 그룹에서 달성한 점수에 따라 다른 텍스트를 표시할 수 있습니다. 점수 기반 메시지를 사용하려면 점수 간격과 각 간격에 대한 설명을 정의해야 합니다. 응답자의 점수가 특정 간격에 해당하면 그 간격에 대한 텍스트가 결과 보고서에 포함됩니다. 

결과 그룹은 설문지의 특정 질문 집합과 연결된 점수와 관련이 있으므로 특정 결과 그룹만 설문지에 사용할 수 있습니다.

#### <a name="example-pointstexts-for-result-group-3"></a>예: 결과 그룹 3의 점수/텍스트

3개 범주의 15개 질문이 있는 리더십 테스트에 대한 설문지를 사용하고 있습니다. 3개의 결과 그룹을 만들고 각 결과 그룹에 5개의 질문을 추가합니다. 그런 다음 점수는 세 그룹으로 합산됩니다. 세 결과 그룹은 다음과 같습니다.

-   창의적 능력
-   리더십 능력
-   기술적 능력

점수 기반 메시지를 사용하려면 각 결과 그룹에 대한 텍스트 간격을 설정합니다. 각 질문에 2점이 부여됩니다. 따라서 각 결과 그룹의 최대 총점은 10입니다. 

다음 표는 "리더십 능력" 결과 그룹에 대해 정의하는 점수 기반 메시지를 보여줍니다.

| 점수 간격 | 텍스트                                       |
|----------------|--------------------------------------------|
| 1~3         | 당신은 평균적인 리더십 능력을 갖추고 있습니다.     |
| 4~7         | 당신은 우수한 리더십 능력을 갖추고 있습니다.        |
| 8~10        | 당신은 탁월한 리더십 능력을 갖추고 있습니다. |

설문지의 각 결과 그룹에 대한 점수 간격과 텍스트를 설정할 수 있습니다. 각 응답자의 점수에 해당하는 텍스트가 각 결과 그룹에 대해 표시됩니다. 

> [!NOTE]
> 간격과 텍스트를 변경할 수 있습니다. 단, 설문지를 완료한 경우 변경하면 이전 및 새 결과 보고서 간에 차이가 발생할 수 있습니다.

### <a name="conditional-question-hierarchies"></a>조건부 질문 계층

설문지를 설정할 때 조건부 질문 계층은 선택 사항입니다. 

> [!NOTE]
> 조건부 질문 계층을 설정하려면 먼저 응답 그룹이 할당된 질문을 설문지에 첨부해야 합니다. 

조건부 질문을 사용하여 설문지에 질문 계층을 만들려면 응답자가 각 질문에 대해 선택한 응답에 따라 질문이 표시되는 순서를 만들 수 있습니다. 응답자의 응답을 기반으로 질문 순서를 지정하면 응답자가 완료하는 대로 설문지를 수정할 수 있습니다.

#### <a name="examples"></a>예

법인은 고객에게 품목과 서비스를 모두 제공합니다. 이 경우 일반적으로 발생하는 것처럼, 일부 고객은 품목만 구매하거나 서비스만 구매하며 일부 고객은 품목과 서비스를 모두 구매합니다. 따라서 법인은 고객만족도 설문 조사를 배포할 때 설문지에 조건부 구조를 적용하여 서비스만 구매하는 고객은 품목에 관한 질문에 답하지 않아도 되도록 할 수 있습니다. 

또는 응답자가 질문 1에 응답 A를 선택하면 질문 순서에서 질문 2가 다음이 되도록 설문지를 설정합니다. 그러나 응답자가 질문 1에 응답 B를 선택하면 질문 5가 다음입니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]