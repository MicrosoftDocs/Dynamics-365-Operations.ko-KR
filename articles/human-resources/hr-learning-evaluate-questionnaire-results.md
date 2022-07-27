---
title: 설문지 결과 보기 및 평가
description: 이 항목에서는 응답자가 작성한 설문지의 결과를 보고 평가하는 방법을 설명합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: dc71748a5081b90feb69ed0da936c42b4d0e572a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452656"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a>설문지 결과 보기 및 평가


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 응답자가 작성한 설문지의 결과를 보고 평가하는 방법을 설명합니다. 

응답자가 설문지를 완료한 후 다음과 같은 방법으로 설문지 결과를 보고 평가할 수 있습니다.

-   **작성된 응답 세션** – 응답자가 작성한 설문지에 대한 세부 정보를 보고 얻은 답변과 점수를 요약하는 보고서를 생성합니다.
-   **결과 그룹** – 설문지에 관한 결과 그룹 세부 정보와 통계를 봅니다. 설문지의 단일 응답 세션 또는 모든 응답 세션에 대해 결과 그룹 통계를 생성할 수 있습니다.
-   **설문지 통계** – 특정 응답자 그룹에 대한 통계를 계산하는 기준을 지정합니다.

또한 다양한 보고서를 생성하여 사람, 응답 세션 또는 결과 그룹별로 정렬된 결과를 볼 수 있습니다. 작성된 설문지와 관련된 다음 보고서를 사용할 수 있습니다.

-   응답
-   설문지별 응답
-   사람별 응답
-   피드백 분석

## <a name="answer-session-results"></a>응답 세션 결과

응답자가 설문지를 작성한 후 완료된 응답 세션의 결과를 볼 수 있습니다. 응답 세션은 설문지에 대한 한 사용자의 응답입니다. **응답** 페이지에서 완료된 응답 세션에 대한 세부 정보를 볼 수 있습니다. **응답** 페이지에 포함된 응답 세션은 페이지를 여는 방식에 따라 다양한 방식으로 필터링됩니다.

-   모든 설문지
-   특정 설문지
-   특정 사람

**응답** 페이지에서 응답, 획득 점수, 각 결과 그룹의 응답자 응답, 질문 계층 구조가 사용된 경우 선택한 설문지에 사용된 질문 계층 구조에 대한 세부 정보를 볼 수 있습니다. 다음 보고서를 생성하고 인쇄할 수도 있습니다.

-   **결과 보고서** – 이 보고서는 선택한 응답 세션에 대해 결과 그룹별로 얻은 점수를 그래픽으로 표시합니다.
-   **응답 보고서** – 이 보고서는 설문지의 각 질문에 대해 응답자가 선택한 응답을 보여줍니다.
-   **오답** – 이 보고서는 응답자가 선택한 오답과 관련된 정보를 보여줍니다.

> [!NOTE]
> **결과** 보고서는 설문지에 결과 그룹을 사용하고 **설문지** 페이지에서 **결과 페이지** 를 선택해야 사용할 수 있습니다. **응답** 보고서와 **오답** 보고서는 **설문지** 페이지에서 **응답 보고서** 를 선택해야 사용할 수 있습니다.

## <a name="questionnaire-statistics"></a>설문지 통계

설문지 통계를 사용하면 작성된 설문지의 결과를 정의한 계산을 기반으로 분석할 수 있습니다. 계산을 정의하려면 다음 작업을 완료해야 합니다.

-   통계를 계산하고 표시할 기준을 선택합니다.
    -   설문지, 질문, 질문 행 또는 결과 그룹별로 통계를 표시할 수 있습니다.
    -   결과를 볼 때 사용할 차트 유형을 선택합니다.
    -   직원, 담당자 또는 지원자와 같이 네트워크에서 응답을 포함할 사람 유형을 선택합니다. 익명으로 작성된 설문지의 응답을 포함할 수도 있습니다.
    -   결과를 분석하기 위해 나이 또는 연공 서열을 기반으로 간격을 설정합니다.
-   통계 주제를 구체화하는 설정을 선택하거나 확인합니다. 예를 들어 우편 번호를 선택하여 특정 지역의 모든 응답자에 관한 결과를 분석할 수 있습니다.
-   응답자 또는 설문지 특성별로 결과를 분석할 기준을 선택하거나 검증합니다. 예를 들어 **우편 번호** 를 선택하면 응답자의 위치와 정답 간의 상관 관계를 분석할 수 있습니다.

정의한 설정은 저장되고 주기적으로 결과를 다시 계산하는 데 사용할 수 있습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
