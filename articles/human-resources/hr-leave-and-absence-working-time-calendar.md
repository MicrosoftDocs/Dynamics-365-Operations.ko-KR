---
title: 근무 시간 일정 만들기
description: Dynamics 365 Human Resources에서 근무 시간 일정, 공휴일, 휴무 시간을 정의합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 54aa85acb43c1e9a474bea9996c72c7e7017c245
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452497"
---
# <a name="create-a-working-time-calendar"></a>근무 시간 일정 만들기


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources의 근무 시간 일정은 직원이 조직에서 근무하는 날짜와 시간을 표시합니다. 직원이 휴가 요청을 제출하면 공휴일과 휴일에 대해 걱정할 필요가 없습니다.

휴가 요청을 간소화하려면 조직의 다음 항목을 구성합니다.

- 근무 시간 일정
- 공휴일 및 휴일
- 휴무 시간

근무 시간 일정을 설정하는 동안 마지막 두 항목을 추가할 수 있습니다. 별도로 구성하거나 업데이트할 수도 있습니다.

## <a name="set-up-a-working-time-calendar"></a>근무 시간 일정 설정

근무일과 시간을 표시하는 근무 시간 일정을 하나 이상 설정합니다. 여러 국가 및 지역에 위치가 있는 경우 각 지역의 근무 시간 일정을 설정할 수 있습니다.

1. **조직 관리** 페이지에서 **달력** 을 선택합니다.

2. **새로 만들기** 를 선택하고 일정의 이름과 설명을 입력합니다.

3. **생성 옵션** 에서 조직의 근무일을 선택하고 근무 시간을 입력합니다. 
   - 공휴일 또는 휴무를 추가하려면 **공휴일 및 휴무** 옆의 **추가** 버튼을 선택합니다.
   - 점심이나 휴식과 같은 휴무 시간을 추가하려면 **휴무 시간** 에서 **추가** 를 선택하고 이름과 시간 범위를 입력합니다.

4. **일** 에서 **생성** 을 선택하여 일정에 일수를 생성합니다. 일정의 날짜 범위를 입력한 다음 **일 생성** 을 선택합니다.

5. 근무 일정을 추가하려면 **근무 일정** 에서 **추가** 를 선택한 다음 각 근무 일정의 시간을 입력합니다.

## <a name="configure-holidays-and-closures"></a>공휴일 및 휴일 구성

근무 시간 일정과 별도로 공휴일 및 휴일을 추가하거나 변경할 수 있습니다.

1. **조직 관리** 페이지에서 **공휴일 및 휴일** 을 선택합니다.

2. **새로 만들기** 를 선택하고 공휴일 또는 휴일의 이름과 날짜를 입력합니다.

## <a name="configure-non-work-time"></a>휴무 시간 구성

근무 시간 일정과 별도로 휴무 시간을 추가하거나 변경할 수 있습니다.

1. **조직 관리** 페이지에서 **휴무 시간** 을 선택합니다.

2. **새로 만들기** 를 선택하고 휴무 시간의 이름과 시간 범위를 입력합니다.

휴가 및 휴직 은행 공휴일 수정 미리 보기 기능을 활성화한 경우 Human Resources는 공휴일 및 휴무 날짜를 사용하여 일정에 등록된 직원에 대해 조정할 일수를 결정합니다.

## <a name="see-also"></a>참고 항목

- [휴가 및 휴직 개요](hr-leave-and-absence-overview.md)
- [휴가 및 휴직 유형 구성](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
