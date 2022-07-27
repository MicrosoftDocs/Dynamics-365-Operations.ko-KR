---
title: 휴가 및 휴직 적립 계획
description: Dynamics 365 Human Resources에서 여러 직원 또는 개인의 휴가 및 휴직을 적립할 수 있습니다.
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a5f3ae95d0670369ac63e5a5d521885fe55ce8af
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452650"
---
# <a name="accrue-leave-and-absence-plans"></a>휴가 및 휴직 적립 계획


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources에서 여러 직원 또는 개인의 휴가 및 휴직을 적립할 수 있습니다.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>여러 직원의 휴가 및 휴직 적립

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **휴가 관리** 에서 **휴가 및 휴직 적립 계획** 을 선택합니다.

3. **휴가 및 휴직 적립 계획** 대화 상자가 나타납니다. **적립 기준** 에서 **오늘 날짜** 를 선택하거나 **사용자 지정 날짜** 를 선택하고 사용자 지정 날짜를 입력합니다.

4. 모든 회사에 대해 휴가 적립을 실행하려면 **모든 회사** 를 선택합니다. 단일 휴가 계획을 위한 휴가 적립을 처리하려면 **모든 계획** 에 **아니요** 를 선택하고 **휴가 계획** 을 선택합니다. 모든 회사를 선택하면 개별 휴가 계획을 선택할 수 없습니다.

5. 백그라운드에서 적립 프로세스를 실행하려면 **백그라운드에서 실행** 을 선택하고 다음 작업을 수행합니다.

    1. 적립 프로세스에 대한 정보를 입력합니다.
    2. 되풀이 작업을 설정하려면 **되풀이** 를 선택하고 되풀이 정보를 입력한 다음 **확인** 을 선택합니다.
    3. 작업 알림을 설정하려면 **알림** 을 선택하고 수신할 알림을 선택한 다음 **확인** 을 선택합니다.
    4. **확인** 을 선택합니다. 적립 프로세스는 설정한 매개 변수로 실행됩니다. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>직원의 휴가 및 휴직 적립

1. 직원의 레코드에서 **휴가** 를 선택합니다.

2. **휴가 및 휴직 적립** 을 선택합니다.

3. **휴가 및 휴직 적립 계획** 대화 상자가 나타납니다. **적립 기준** 에서 **오늘 날짜** 를 선택하거나 **사용자 지정 날짜** 를 선택하고 사용자 지정 날짜를 입력합니다.

4. 모든 회사에 대해 휴가 적립을 실행하려면 **모든 회사** 를 선택합니다. 단일 휴가 계획을 위한 휴가 적립을 처리하려면 **모든 계획** 에 **아니요** 를 선택하고 **휴가 계획** 을 선택합니다. 모든 회사를 선택하면 개별 휴가 계획을 선택할 수 없습니다.

5. 백그라운드에서 적립 프로세스를 실행하려면 **백그라운드에서 실행** 을 선택하고 다음 작업을 수행합니다.

   1. 적립 프로세스에 대한 정보를 입력합니다.

   2. 되풀이 작업을 설정하려면 **되풀이** 를 선택하고 되풀이 정보를 입력한 다음 **확인** 을 선택합니다.

   3. 작업 알림을 설정하려면 **알림** 을 선택하고 수신할 알림을 선택한 다음 **확인** 을 선택합니다.

   4. **확인** 을 선택합니다. 적립 프로세스는 설정한 매개 변수로 실행됩니다.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>여러 직원의 휴가 및 휴직 적립 삭제

특정 계획 및 날짜 범위에 대한 적립 레코드를 삭제합니다. 적립 날짜는 오늘 또는 미래 날짜여야 합니다.

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **휴가 관리** 에서 **휴가 및 휴직 적립 계획 삭제** 를 선택합니다.

3. **휴가 및 휴직 적립 계획 삭제** 대화 상자에서 **휴가 계획** 을 선택합니다.

4. 해당하는 경우 **잔액 조정 삭제** 를 선택합니다.

5. **휴가 적립 날짜** 를 입력하거나 선택합니다. 이 날짜는 오늘이거나 미래여야 합니다.

6. **확인** 을 선택합니다. 적립 프로세스는 설정한 매개 변수로 적립을 삭제합니다.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>한 직원의 휴가 및 휴직 적립 삭제

1. 직원의 레코드에서 **휴가** 를 선택합니다.

2. **휴가 및 휴직 적립 계획 삭제** 를 선택합니다.

3. **휴가 및 휴직 적립 계획 삭제** 대화 상자에서 **휴가 계획** 을 선택합니다.

4. 해당하는 경우 **잔액 조정 삭제** 를 선택합니다.

5. **휴가 적립 날짜** 를 입력하거나 선택합니다. 이 날짜는 오늘이거나 미래여야 합니다.

6. **확인** 을 선택합니다. 적립 프로세스는 설정한 매개 변수로 적립을 삭제합니다.

## <a name="review-leave-accrual-and-deletion-processes"></a>휴가 적립 및 삭제 프로세스 검토

**휴가 적립 감사** 는 직원 한 명 또는 전체에 대한 휴가 적립을 실행하거나 삭제할 때마다 표시됩니다. 작업을 수행한 날짜와 사람도 표시됩니다.

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **휴가 관리** 에서 **휴가 적립 삭제 감사** 를 선택합니다.

## <a name="leave-accrual-transaction-auditing"></a>휴가 적립 거래 감사

이 기능은 휴가 및 휴직 관리자가 특정 휴가 유형에 대한 직원의 휴가 잔액과 관련 휴가 및 휴직 적립 거래를 이해하는 데 도움이 됩니다.

거래 세부 정보를 보려면 다음 단계를 따릅니다.

1. 직원의 레코드에서 **휴가** 를 선택합니다.

2. **휴가 보기** 를 선택하고 **잔액** 탭을 선택합니다.

특정 휴가 유형과 관련된 적립 거래를 보려면 **현재 잔액** 열에서 숫자 값을 선택합니다.

특정 적립 금액에 대한 거래 세부 정보를 보려면 적립 행을 선택하고 오른쪽의 **관련 정보** 패널을 연 다음 **거래 세부 정보** 섹션을 엽니다. 거래 세부 정보 섹션에 다음 사항이 표시됩니다.

- 직원의 휴가 유형 잔액 변경 내용
- 지정된 적립 기간에 대한 고용 세부 정보
- 적립 기간 및 비율에 대한 세부 정보
- 휴가 계획 구성에 대한 모든 변경 내용

![휴가 적립 거래 감사를 표시합니다.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>참고 항목

[휴가 및 휴직 개요](hr-leave-and-absence-overview.md)</br>
[휴가 및 휴직 계획 만들기](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
