---
title: 급여 변동 보상 계획
description: 이 항목에서는 Dynamics 365 Human Resources의 급여 변동 보상 계획 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2f057fb0f492efd08674b3bbeef9f3fec3d7be0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452455"
---
# <a name="payroll-variable-compensation-plan"></a>급여 변동 보상 계획


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 변동 보상 계획 엔터티에 관해 설명합니다.

### <a name="description"></a>설명

이 엔터티는 직원의 주어진 직위에 할당된 변동 보상 계획을 제공합니다.

실제 이름: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용 | 직원의 고유한 인사 번호.  |
| **포상 날짜**</br>mshr_awarddate</br>*날짜 시간 오프셋* | 읽기 전용 | 포상 날짜. |
| **포상 유형**</br>mshr_awardtype</br>*[mshr_HrmCompVarAwardEmplType 옵션 집합](hr-admin-integration-payroll-api-award-type.md)* | 읽기 전용 | 변동 보상 계획에 대해 정의된 포상 유형. |
| **통화**</br>mshr_unitcurrencycode</br>*문자열* | 읽기 전용 |변동 보상 계획에 대해 정의된 통화.   |
| **고정 보상 계획 ID**</br>mshr_fixedplanid</br>*문자열* | 읽기 전용 | 포상 계산의 기초로 사용되는 고정 보상 계획. |
| **단위 값**</br>mshr_awardamount</br>*십진수* | 읽기 전용 | 단위의 값. |
| **프로세스 유형**</br>mshr_processtype</br>*[mshr_hrmCompProcessType 옵션 집합](hr-admin-integration-payroll-api-process-type.md)* | 읽기 전용 | 프로세스 유형. |
| **변동 보상 계획 유형**</br>문자열</br>*mshr_typeid* | 읽기 전용 | 변동 보상 계획의 유형. |
| **변동 보상 계획 ID**</br>문자열</br>*mshr_planid* | 읽기 전용 | 변동 보상 계획의 ID. |
| **단위 수**</br>십진수</br>*mshr_numberofunits* | 읽기 전용 | 포상의 단위 수. |
| **기본 필드**</br>mshr_primaryfield</br>*GUID* | 읽기 전용</br>시스템 생성. | |
| **급여 변동 보상 계획 엔터티**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | 시스템 생성 | 보상 계획을 고유하게 식별하기 위한 시스템 생성 GUID 값. |

## <a name="relations"></a>관계 

|속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_VariableCompAward |
| _mshr_fk_fixedcomp_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedComp_id | mshr_FK_PayrollFixedCompensationPlanEntity_VariableCompAward |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000046'
```

**응답**

```json
{
    "mshr_personnelnumber": "000046",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_unitvalue": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_numberofunits": 1500,
    "mshr_primaryfield": "000046 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000666-0000-0000-daff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a4-0000-0000-0d00-005001000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
