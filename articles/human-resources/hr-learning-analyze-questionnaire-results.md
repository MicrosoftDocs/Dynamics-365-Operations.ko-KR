---
title: 설문지 결과 분석
description: 설문지 통계는 인구 통계 데이터 세트를 기반으로 평균, 합계 및 백분율을 계산하는 데 사용할 수 있습니다.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1ad98638810206dad04c34a8abbc8f757058cc0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452353"
---
# <a name="analyzing-questionnaire-results"></a>설문지 결과 분석


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



설문지 통계는 인구 통계 데이터 세트를 기반으로 평균, 합계 및 백분율을 계산하는 데 사용할 수 있습니다. 이 절차를 시작하려면 **설문지** > **결과 보기 및 분석** > **설문지 통계** 로 이동합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="create-a-questionnaire-statistics-record"></a>설문지 통계 레코드 만들기
1. **설문지 통계** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
4. **통계** 필드에 값을 입력합니다.
5. **설명** 필드에 값을 입력합니다.
6. **설문지** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **일반** 탭을 클릭합니다.
    * 익명 결과 또는 근로자, 연락처 및 지원자의 결과를 포함할지 선택합니다.  
9. **작업자** 확인란을 선택하거나 선택 취소합니다.
    * 연공서열 또는 연령별로 결과를 보려면 결과를 그룹화하는 데 사용할 간격을 지정합니다.  
    * 연령 간격에 5를 입력하면 5년 연령 간격을 기준으로 결과가 그룹으로 묶입니다.  
10. **나이** 필드에 숫자를 입력합니다.
    * 전체 설문지, 각 결과 그룹, 각 질문 또는 각 질문 행에 대해 계산을 실행할지 선택합니다.  
    * 결과를 그룹으로 묶을 방법을 선택합니다.  
    * 예를 들어 질문당 평균 점수를 계산하는 경우 결과 그룹별로 그룹으로 묶인 질문을 볼 수 있습니다.  
    * 보고서의 기반이 될 데이터를 선택합니다.  
    * 예를 들어, 설문지에서 직원 전체에 대해 받은 평균 백분율 대비 직원 전체에서 달성한 평균 점수를 확인하려는 경우입니다.  
11. **범위** 탭을 클릭합니다.
    * 범위를 사용하여 범위 기준을 충족하는 결과 집합으로만 결과 집합을 제한합니다.  
12. **그룹화 기준** 탭을 클릭합니다.
    * 그룹화를 사용하여 결과가 표시되는 방식을 결정합니다.  
    * 예를 들어 결과를 먼저 성별로 그룹화한 다음 연령별로 그룹화합니다.  
13. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 그룹화를 **선택됨** 쪽으로 이동하고 원하는 순서로 배치합니다.  

## <a name="execute-the-statistics-calculation"></a>통계 계산 실행
1. **실행** 을 클릭합니다.
    * 결과에 대해 수행할 계산 기능을 선택합니다.  
    * 예를 들어 선택한 그룹에 대한 설문지 전체의 평균 백분율을 계산하거나 선택한 그룹에 대한 결과 그룹 전체의 점수를 합산합니다.  
2. **이전 검색 삭제** 확인란을 선택 또는 삭제합니다.
3. **확인** 을 클릭합니다.

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>설문지 통계 실행 결과를 봅니다.
1. **결과** 를 클릭합니다.
2. **결과** 를 클릭합니다.
3. 페이지를 닫습니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
