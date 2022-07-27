---
title: 일정을 사용하여 설문지 배포
description: 설문지 일정을 사용하면 설문지를 계획하고 여러 응답자에게 배포할 수 있습니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4885c11f0cb508edb8ebf3aef14748e819113264
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452344"
---
# <a name="distribute-questionnaires-using-scheduling"></a>일정을 사용하여 설문지 배포


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

설문지 일정을 사용하면 설문지를 계획하고 여러 응답자에게 배포할 수 있습니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.

## <a name="create-a-questionnaire-schedule"></a>설문지 일정 만들기

1. **설문지** > **배포** > **설문지 일정** 으로 이동합니다.

2. **새로 만들기** 를 클릭합니다.

3. **일정** 필드에 값을 입력합니다.

4. **설명** 필드에 값을 입력합니다.
    * 응답에 이름을 연결하지 않고 응답을 기록해야 하는 경우 일정을 **익명** 으로 설정합니다.  
    * 익명 결과를 허용하려면 먼저 HR 매개 변수에서 설정해야 합니다.  

5. **유형** 필드에서 계획 유형을 선택합니다.  이 예에서는 **만족도** 유형을 사용합니다.

6. 목록에서 원하는 레코드를 찾아 선택합니다.

7. 목록에서 선택한 행의 링크를 클릭합니다.

8. **날짜** 필드에 날짜를 입력합니다.

9. **직원 셀프 서비스용 이메일** 섹션을 확장합니다.

10. **제목** 필드에 값을 입력합니다.

    * 예: 사용 가능한 설문지  

11. **텍스트** 필드에 이메일 메시지의 본문을 입력합니다. 변수는 시스템의 값을 대체하는 데 사용할 수 있습니다.

    * 예: %P% 님, 직원 건강 설문지를 작성하려면 직원 셀프 서비스에 로그인하세요.  Contoso  

12. **저장** 을 클릭합니다.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>설정 세부 정보를 사용하여 응답할 설문지와 응답자를 선택하는 데 사용할 쿼리를 선택합니다.

1. **설정 세부 정보** 를 클릭합니다.

2. 목록에서 설문지에 대한 응답자의 시스템을 검색하는 데 사용할 쿼리를 선택합니다.

    * 예: 작업자  

3. **쿼리 보기 또는 수정** 을 클릭하여 특정 사람을 선택하거나 특정 기준과 일치하는 사람을 찾을 쿼리를 조정합니다.

    * 모든 응답자는 또한 시스템의 사용자여야 합니다.  

4. 목록에서 사람의 행을 표시합니다.

5. **기준** 필드에서 값을 입력하거나 선택합니다.

    * Julia Funderburk 선택  

6. 목록에서 Julia Funderburk를 선택합니다.

7. **확인** 을 클릭합니다.

8. **설문지** 탭을 클릭합니다.

9. 트리에서 설문지 유형 **만족도 설문 조사** 의 노드를 확장합니다 .

10. 트리에서 '인력 건강 평가'를 확인합니다.

11. **확인** 을 클릭합니다.

12. **계획된 응답 세션** 을 클릭합니다.

    * 선택/쿼리한 각 사용자에 대해 **계획된 응답 세션** 이 생성되었습니다.  

13. 페이지를 닫습니다.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>응답자가 설문지를 작성할 수 있도록 설문지 일정을 시작합니다.

1. **기능** 을 클릭합니다.

2. **시작** 을 클릭합니다.

3. **확인** 을 클릭합니다.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>사용 가능한 설문지를 응답자에게 알리기 위해 이메일을 보냅니다.

1. **기능** 을 클릭합니다.

2. **이메일 보내기** 를 클릭합니다.

3. **취소** 를 클릭합니다.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>계획된 응답 세션을 사용하여 설문지를 작성해야 하는 사람을 모니터링합니다.

1. **계획된 응답 세션** 을 클릭합니다.

    * 예약된 세션을 종료할 준비가 되면 나머지 계획된 응답 세션을 삭제합니다.  

2. **삭제** 를 클릭합니다.

3. **예** 를 클릭합니다.

4. 페이지를 닫습니다.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>모든 응답자가 설문지를 완료하거나 나머지 계획된 응답 세션이 모두 삭제되면 일정을 종료합니다.

1. **기능** 을 클릭합니다.
2. **종료** 를 클릭합니다.
3. **확인** 을 클릭합니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
