---
title: 급여 직위 직무
description: 이 항목에서는 Dynamics 365 Human Resources의 급여 직위 직무 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 349479d9e77861b54d879bcfd93f7af0e38cff95
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452590"
---
# <a name="payroll-position-job"></a>급여 직위 직무


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 직위 직무 엔터티에 관해 설명합니다.

### <a name="description"></a>설명

이 엔터티는 지정된 고정 보상 계획에 대한 직위와 직무 간의 관계를 제공합니다.

실제 이름: mshr_payrollpositionjobentity.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **직책 ID**</br>mshr_positionid</br>*문자열* | 읽기 전용 | 직위의 ID. |
| **유효 기간 시작**</br>mshr_validto</br>*날짜 시간 오프셋* | 읽기 전용 | 직위와 직무 관계가 유효한 시작 날짜. |
| **유효 기간 끝**</br>mshr_validto</br>*날짜 시간 오프셋* | 읽기 전용 | 직위와 직무 관계가 유효한 종료 날짜. |
| **직무 ID**</br>mshr_jobid</br>*문자열* | 읽기 전용 | 직무의 ID. |
| **기본 필드**</br>mshr_primaryfield</br>*문자열* | 시스템 생성 | 기본 필드. |
| **급여 직위 직무 엔터티 ID**</br>mshr_payrollpositionjobentityid</br>*GUID* | 시스템 생성. | 직무를 고유하게 식별하기 위해 시스템에서 생성한 GUID(Globally Unique Identifier) 값. |

## <a name="relations"></a>관계

| 속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | 해당 없음 |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**응답**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
