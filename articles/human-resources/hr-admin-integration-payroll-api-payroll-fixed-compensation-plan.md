---
title: 급여 고정 보상 계획
description: 이 항목에서는 Dynamics 365 Human Resources의 급여 고정 보상 계획 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: 14829f18fb5e3adde83e265cd6e70b60e1ff03ac
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452521"
---
# <a name="payroll-fixed-compensation-plan"></a>급여 고정 보상 계획


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 고정 보상 계획 엔터티에 관해 설명합니다.

### <a name="description"></a>설명

이 엔터티는 직원의 주어진 직위에 할당된 고정 보상 계획을 제공합니다.

실제 이름: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **계획 ID**</br>mshr_planid</br>*문자열* | 읽기 전용 | 보상 계획을 지정합니다.  |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용 | 직원의 고유한 인사 번호. |
| **지급 비율**</br>mshr_payrate</br>*십진수* | 읽기 전용 | 고정 보상 계획에 정의된 지급 비율. |
| **직책 ID**</br>mshr_positionid</br>*문자열* | 읽기 전용 | 직원 및 고정 보상 계획 등록과 연결된 직위 ID. |
| **유효 기간 시작**</br>mshr_validfrom</br>*날짜 시간 오프셋* |  읽기 전용 | 직원 고정 보상이 유효한 시작 날짜.  |
| **유효 기간 끝**</br>mshr_validto</br>*날짜 시간 오프셋* | 읽기 전용 | 직원 고정 보상이 유효한 종료 날짜. |
| **지급 빈도**</br>mshr_payfrequency</br>*문자열* | 읽기 전용 | 주어진 비급 비율에 대한 [보상 지급 빈도](hr-admin-integration-payroll-api-compensation-pay-frequency.md)의 ID. |
| **통화**</br>mshr_currency</br>*문자열* | 읽기 전용 | 고정 보상 계획에 대해 정의된 통화. |
| **급여 고정 보상 계획 엔터티**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | 시스템 생성 | 보상 계획을 고유하게 식별하기 위한 시스템 생성 GUID 값. |

## <a name="relations"></a>관계

|속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**응답**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
