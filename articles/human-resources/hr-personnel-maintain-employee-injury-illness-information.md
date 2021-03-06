---
title: 직원 부상 및 질병 정보 유지
description: 이 작업은 부상 또는 질병 케이스를 만드는 방법을 설명합니다.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06307331db4d420e99de21c0eb0b3cf1c233f0d5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452251"
---
# <a name="maintain-employee-injury-and-illness-information"></a>직원 부상 및 질병 정보 유지


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



여기에서 일부 설정 정보가 사용되므로 '상해 및 질병 설정' 작업 가이드를 먼저 완료하는 것이 좋습니다. 



이 작업 기록은 부상 또는 질병 케이스를 만드는 기본 단계를 설명합니다. 부상이나 질병에 대한 세부 정보 외에도 케이스 상태가 추적됩니다. 기본적으로 케이스의 상태는 **열림** 입니다. 페이지 상단의 **케이스 상태** 메뉴 항목을 사용하여 상태를 관리할 수 있습니다.

1. **Human Resources \> 작업자 \> 부상 및 질병 \> 부상 및 질병 인시던트** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **케이스 설명** 필드에 값을 입력합니다(예: **손목 부상**).
4. **작업자** 필드에서 값을 입력하거나 선택합니다(예: **Ana Bowman**).
5. **인시던트의 날짜 및 시간** 필드에 날짜 및 시간을 입력합니다(예: 2016년 1월 20일 오전 10시).
6. **부상 및 질병 유형** 필드에 값을 입력하거나 선택합니다(예: **골절**).
7. **신체 부위** 필드에서 값을 입력하거나 선택합니다(예: **손목**).
8. **결과 유형** 필드에 값을 입력하거나 선택합니다(예: **치료**).
9. **보고된 날짜 및 시간** 필드에 날짜와 시간을 입력합니다.

    보고된 날짜 및 시간은 인시던트 날짜 및 시간 이후여야 합니다.

10. **케이스를 보고한 사람** 필드에 값을 입력하거나 선택합니다(예: **Ana Bowman**).

    지정된 사람은 해당 직원이거나 인시던트의 다른 증인일 수 있습니다.

11. **인시던트** 섹션의 **인시던트가 발생한 곳** 필드에 값을 입력합니다(예: **창고**).
12. 인시던트가 작업 현장에서 발생한 경우 **작업 현장에서** 필드에 **예** 를 선택합니다.
13. **작업을 시작한 날짜 및 시간** 필드에 해당 직원이 인시던트가 발생하기 전에 일을 시작한 날짜와 시간을 입력합니다.
14. **직원 작업 또는 태스크** 필드에 인시던트가 발생했을 때 작업자가 수행하고 있던 작업 또는 태스크를 입력합니다(예: **상자 싣기**) 
15. **인시던트 원인** 필드에 인시던트의 원인을 입력합니다(예: **젖은 바닥에 미끄러짐**).
16. **심각도 수준** 필드에 값을 입력하거나 선택합니다.
17. **취할 조치** 필드에 값을 입력합니다(예: **즉시 유출물 청소**).
18. **예상되는 결근 일수** 필드에 직원이 결근할 것으로 예상되는 일수를 입력합니다.

    직원이 직장에 복귀한 후 **결근 일수** 필드를 직원이 결근한 실제 일수로 업데이트합니다.

19. **부상 또는 질병 비용** 섹션에서 **추가** 를 선택합니다.
20. **날짜** 필드에 날짜를 입력합니다.
21. **비용 유형** 필드에 값을 입력하거나 선택합니다(예: **치료**).

    금액을 입력하고 비용에 증빙 서류(예: 송장 또는 의사 소견서)를 첨부할 수도 있습니다.

22. **추가** 를 선택합니다.
23. **날짜** 필드에 날짜를 입력합니다.
24. **비용 유형** 필드에 값을 입력하거나 선택합니다(예: **의사**).
25. **부상 또는 질병 치료** 섹션에서 **추가** 를 선택합니다.
26. **치료 날짜** 필드에 날짜와 시간을 입력합니다.
27. **치료 유형** 필드에 값을 입력하거나 선택합니다(예: **부목**).
28. 선택 사항: **병원 응급실 방문** 섹션에 **예** 를 선택합니다.
29. **치료 설명** 필드에 값을 입력하거나 선택합니다(예: **2주간 부목**).
30. **의사 이름** 필드에 값을 입력합니다(예: **Dr. Anderson**).
31. **치료 시설 및 위치** 필드에 값을 입력합니다(예: **Elm St. Emergency**).
32. **치료 세부 정보** 필드에 값을 입력합니다(예: **엑스레이로 골절 확인, 부목 착용**).
33. **저장** 을 선택합니다.

케이스 상태는 언제든지 업데이트할 수 있습니다. 부상이나 질병의 처리가 진행 중이면 상태를 **진행 중** 으로 설정합니다. 인시던트를 종료한 후에는 인시던트와 관련된 비용, 치료 또는 서류만 추가하거나 제거할 수 있습니다. 다른 정보를 변경하려면 케이스를 다시 열어야 합니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
