---
title: 휴가 및 휴직 매개 변수 구성
description: 이 항목에서는 Dynamics 365 Human Resources에서 휴가 및 휴직에 대한 인적 자원 매개 변수를 정의하는 방법을 설명합니다.
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
ms.openlocfilehash: 7bd1aebd633af0530c550f8ec7510a0c09985ca1
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452338"
---
# <a name="configure-leave-and-absence-parameters"></a>휴가 및 휴직 매개 변수 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources에서 휴가 및 휴직 계획을 설정하기 전에 다음을 포함하여 관련된 모든 **인적 자원 매개 변수** 에 대한 설정을 확인하는 것이 좋습니다.

- 휴가 요청 번호 시퀀스
- 가족 및 의료 휴가법(FMLA) 설정
- 휴가 및 휴직 요청에 대한 직원 셀프 서비스 설정
- 휴가 및 휴직 매개 변수

## <a name="view-and-change-human-resources-parameters"></a>인적 자원 매개 변수 확인 및 변경

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **설정** 에서 **인적 자원 매개 변수** 를 선택합니다.

3. **숫자 시퀀스** 탭에서 **휴가 요청 ID** 에 대한 **숫자 시퀀스 코드** 를 확인하고 필요에 따라 변경합니다. 이 설정은 휴가 요청에 ID를 자동으로 할당하는 데 사용되는 순서를 결정합니다.

4. **FMLA** 탭에서 FMLA 설정을 확인하고 필요에 따라 변경합니다.

5. **직원 셀프 서비스** 탭에서 관리자가 직원을 대신하여 휴가 및 휴직 요청을 입력할 수 있는지를 지정합니다.

7. **저장** 을 선택합니다.

>[!IMPORTANT]
>회사 간 휴가 보기는 현재 미리 보기로 제공됩니다. 휴가 및 휴직 옵션을 표시하려면 **샌드박스** 환경에서 활성화해야 합니다. 미리 보기 기능의 활성화에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

## <a name="view-and-change-human-resources-shared-parameters"></a>인적 자원 공유 매개 변수 확인 및 변경

1. **인사 관리** 페이지에서 **연결** 탭을 선택합니다.

2. **설정** 에서 **Human Resources 공유 매개 변수** 를 선택합니다.

3. 회사 간에 휴가를 볼 수 있도록 하려면 **고급 액세스** 탭에서 **회사 간 휴가 보기 활성화** 에 **예** 를 선택합니다.

4. **저장** 을 선택합니다.

## <a name="view-and-change-leave-and-absence-parameters"></a>휴가 및 휴직 매개 변수 확인 및 변경

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **설정** 에서 **휴가 및 휴직 매개 변수** 를 선택합니다.

3. **일반** 탭에서 다음 매개 변수를 설정합니다.
 
    - **휴가 및 휴직 단위** 를 시간 또는 일로 설정합니다. 일을 선택한 경우 **반일 지정 활성화** 를 선택하여 직원이 휴가 요청에서 하루 중 전반기 또는 후반기를 선택할 수 있도록 할 수 있습니다. 

    - 근속 기간을 사용하는 휴가 계획에 대해 적립 비율이 적용되는 시점을 설정하려면 **근속 개월 적용 날짜** 을 선택합니다.

    - **잔액 계산** 을 선택하여 오늘 또는 적립 기간을 기준으로 잔액을 표시합니다. **오늘 기준 잔액** 을 선택하면 오늘을 기준으로 모든 적립, 조정 및 요청의 합계를 적용한 잔액이 표시됩니다. **적립 기간 기준 잔액** 을 선택하면 휴가 계획의 빈도로 정의된 적립 기간을 기준으로 모든 적립, 조정 및 요청의 합계를 적용한 잔액이 표시됩니다. 

    - **이월 만료** 일괄 작업의 **시작 시간** 을 설정합니다.  
    
    - **직원의 휴가 구매 허용** 및 **직원의 휴가 판매 허용** 에 **예** 를 선택합니다. 이러한 옵션에 **예** 를 선택하면 휴가 구매 및 판매 정책을 만들고 직원이 휴가 구매 및 판매 요청을 제출하도록 할 수 있습니다.

## <a name="configure-calendar-parameters"></a>일정 매개 변수 구성

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **설정** 에서 **휴가 및 휴직 매개 변수** 를 선택합니다.

3. **일정** 탭에서 일정 설정을 필요에 따라 변경합니다.

4. **저장** 을 선택합니다.

## <a name="see-also"></a>참고 항목

- [휴가 및 휴직 개요](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
