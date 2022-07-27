---
title: 휴가 구매 및 판매 정책 관리
description: 직원이 Dynamics 365 Human Resources에서 휴가를 사고팔도록 할 수 있습니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1fe7ce7eafdec175e3395a6ac37b33cb2bb8dbda
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452254"
---
# <a name="manage-buy-and-sell-leave-policies"></a>휴가 구매 및 판매 정책 관리


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

휴가 구매 및 판매 정책을 만들어 직원이 휴가를 사고팔 수 있도록 할 수 있습니다. 승인을 위해 워크플로를 사용하고, 최대 금액 및 비율을 설정하며, 구매 및 판매 비율을 설정하도록 이러한 정책을 구성할 수 있습니다. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>직원이 휴가를 사고팔 수 있도록 활성화

1. **휴가 및 휴직 매개 변수** 페이지에서 **직원의 휴가 구매 허용** 및 **직원의 휴가 판매 허용** 에 **예** 를 선택합니다.

## <a name="create-a-buy-and-sell-leave-policy"></a>휴가 구매 및 판매 정책 만들기

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다. 

2. **휴가 구매 및 판매 정책** 을 선택합니다.

3. **새로 만들기** 를 선택합니다.

4. **휴가 구매 및 판매 정책** 에서 정책의 **이름** 및 **설명** 을 입력합니다. 

5. **정책 유형** 을 선택합니다. 

   사용 가능한 정책 유형은 **금액** 및 **주당 시간** 입니다. **금액** 을 선택하여 직원이 사고팔 수 있는 최대 금액의 **고정 금액** 을 입력합니다. **주당 시간** 을 선택하면 직원에게 할당된 근무 시간 일정에 정의된 근무 시간이 정책의 최대 금액을 결정하는 데 사용됩니다. 

6. 정책의 **시작 날짜** 및 **종료 날짜** 를 선택합니다. 휴가 구매 또는 판매 요청은 이 기간에만 제출할 수 있습니다. 

7. 정책의 **워크플로 ID** 를 선택합니다. 모든 구매 및 판매 요청은 검토 및 승인을 위해 이 워크플로를 사용합니다. 

8. **구매 정책** 아래에서 **정규직 상응**(FTE)을 선택하여 직원의 직위에 정의된 FTE를 기준으로 최대 금액을 비례 배분합니다. 정책 유형이 **금액** 인 경우 **최대 고정 금액** 을 입력합니다. 

9. 직원이 휴가를 구매할 수 있도록 휴가 유형을 추가하려면 **추가** 를 선택합니다. 정책에 여러 휴가 유형을 추가할 수 있습니다. 

10. 직원이 구매할 수 있는 최대 금액을 결정하기 위해 다른 근무 월을 활성화하려면 휴가 유형에 **근속 개월** 을 입력합니다. 

11. 휴가 유형에 대한 **최대 금액** 을 입력합니다. 

12. 직원이 휴가를 구매하는 **비율** 을 입력합니다. 

13. 선택적으로 휴가 구매에 사용할 **소득 코드** 를 입력합니다. 

14. 휴가 유형에 대한 최대 금액을 결정하기 위해 FTE를 사용할지를 선택적으로 설정합니다. 

15. 판매 정책을 만들려면 **판매 정책** 의 8~14단계를 따릅니다. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>휴가 및 휴직 계획에 휴가 구매 및 판매 정책 추가

1. **휴가 및 휴직** 페이지에서 휴가 및 휴직 계획을 선택합니다.

2. **규칙** 에서 **휴가 구매 및 판매 정책** 을 선택합니다.

## <a name="see-also"></a>참고 항목

[휴가 및 휴직 개요](hr-leave-and-absence-overview.md)</br>
[휴가 및 휴직 유형 구성](hr-leave-and-absence-types.md)</br>
[휴가 및 휴직 적립 계획](hr-leave-and-absence-accrue.md)</br>
[휴가 구매 및 판매](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
