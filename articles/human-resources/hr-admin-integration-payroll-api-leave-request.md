---
title: 휴가 요청
description: 이 항목에서는 Dynamics 365 Human Resources의 휴가 요청 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f14c143a59553786fe85284c128cec80905810b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452383"
---
# <a name="leave-request"></a>휴가 요청


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 휴가 요청 엔터티에 관해 설명합니다.

### <a name="description"></a>설명

이 엔터티는 휴가 요청에 대한 정보를 제공합니다.

실제 이름: mshr_essleaverequestentity.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **요청 ID**</br>mshr_requestid</br>*문자열* | 읽기 전용 | 요청 ID. |
| **휴가 유형 ID**</br>mshr_leavetypeid</br>*문자열* | 읽기 전용 | 휴가 유형 ID. |
| **날짜**</br>mshr_leavedate</br>*날짜 시간 오프셋* | 읽기 전용 | 휴가 신청 날짜. |
| **금액**</br>mshr_amount</br>*십진수* | 읽기 전용 | 휴가 신청 기간. |
| **반일 유형**</br>mshr_halfdaydefinition</br>*mshr_LeaveHalfDayDefinition 옵션 집합* | 읽기 전용 | 반일 휴가 유형. |
| **설명**</br>mshr_comment</br>*문자열* | 읽기 전용 | 신청에 대한 설명. |
| **상태**</br>mshr_status</br>*mshr_status 옵션 집합* | 읽기 전용 | 신청 상태. |
| **날짜**</br>mshr_requestdate</br>*날짜 시간 오프셋* | 읽기 전용 | 신청 날짜. |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용 | 직원의 고유한 인사 번호. |
| **사유 코드 ID**</br>mshr_reasoncodeid</br>*문자열* | 읽기 전용 | 사유 코드 ID. |
| **데이터 영역 ID**</br>mshr_dataareaid</br>*문자열* | 읽기 전용 | 법인(회사)을 지정합니다. |
| **기본 필드**</br>mshr_primaryfield</br>*GUID* | 읽기 전용</br>시스템 생성 | |
| **휴가 유형 엔터티**</br>mshr_essleaverequestentityid</br>*GUID* | 시스템 생성 | 휴가 신청을 고유하게 식별하기 위한 시스템 생성 GUID 값. |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**응답**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
