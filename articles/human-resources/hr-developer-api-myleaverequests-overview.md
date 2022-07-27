---
title: MyLeaveRequests 개요
description: Microsoft Dynamics 365 Human Resources의 MyLeaveRequests 엔터티는 엔터티를 쿼리하는 현재 사용자가 액세스할 수 있는 요청으로 범위가 지정된(제한된) 시스템의 휴가 요청 목록을 제공합니다.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 41ef8c6fc0e896e7f2cefd94801abab610083b81
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452665"
---
# <a name="myleaverequests-overview"></a>MyLeaveRequests 개요


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources의 MyLeaveRequests 엔터티는 엔터티를 쿼리하는 현재 사용자가 액세스할 수 있는 요청으로 범위가 지정된(제한된) 시스템의 휴가 요청 목록을 제공합니다.

## <a name="key"></a>키

  | 속성 이름 | 데이터 형식 |
  |---------------|-----------|
  | dataAreaId    | 문자열    |
  | RequestId     | 문자열    |
  | LeaveType     | 문자열    |
  | LeaveDate     | 날짜      |
  
## <a name="properties"></a>속성

  | 속성 이름     | 데이터 형식 | 필수 |
  |-------------------|-----------|----------|
  | dataAreaId        | 문자열    | X        |
  | RequestId         | 문자열    | X        |
  | LeaveType         | 문자열    | X        |
  | LeaveDate         | 날짜      | X        |
  | ReasonCodeId      | 문자열    |          |
  | PersonnelNumber   | 문자열    | X        |
  | RequestDate       | 날짜      | X        |
  | 설명           | 문자열    |          |
  | 상태            | 열거형      | X        |
  | 금액            | 실수      |          |
  | HalfDayDefinition | 열거형      |          |

## <a name="actions"></a>작업

 | 작업 이름                               | 설명                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [제출](hr-developer-api-myleaverequests-submit.md)   | 워크플로에서 처리할 요청을 제출합니다. |

## <a name="see-also"></a>참고 항목

- [워크플로에 휴가 요청 제출](hr-developer-api-myleaverequests-submit.md)
- [인증](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
