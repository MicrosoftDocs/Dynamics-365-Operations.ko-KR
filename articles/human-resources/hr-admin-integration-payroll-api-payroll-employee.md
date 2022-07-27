---
title: 급여 직원
description: 이 항목에서는 Dynamics 365 Human Resources의 급여 직원 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
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
ms.openlocfilehash: e853a8a5730d397f253c8ce3a330794594dfd907
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452458"
---
# <a name="payroll-employee"></a>급여 직원


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 직원 엔터티에 관해 설명합니다.

실제 이름: mshr_payrollemployeeentity.

### <a name="description"></a>설명

이 엔터티는 직원에 관한 정보를 제공합니다. 이 엔터티를 사용하려면 먼저 [급여 통합 매개 변수](hr-admin-integration-payroll-api-parameters.md)를 설정해야 합니다.

>[!IMPORTANT] 
>더는 이 엔터티에서 **FirstName**, **MiddleName**, **LastName**, **NameValidFrom**, **NameValidTo** 필드를 사용할 수 없습니다. 이것은 이 엔터티를 지원하는 유효 날짜 데이터 원본이 하나만 있게 하기 위한 것입니다.
>이러한 필드는 플랫폼 업데이트 43에서 릴리스된 **DirPersonNameHistoricalEntity** 에서 사용할 수 있습니다. **PayrollEmployeeEntity** 에서 **DirPersonNameHistoricalEntity** 로의 OData 관계가 있습니다. 

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **법인 ID**</br>mshr_legalentityid</br>*문자열* | 읽기 전용 | 법인(회사)을 지정합니다. |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용 | 직원의 고유한 인사 번호. |
| **고용 시작 날짜**</br>mshr_employmentstartdate</br>*날짜 시간 오프셋* | 읽기 전용 | 직원의 고용 시작 날짜. |
| **고용 종료 날짜**</br>mshr_employmentenddate</br>*날짜 시간 오프셋* | 읽기 전용 |직원의 고용 종료.  |
| **생년월일**</br>mshr_birthdate</br>*날짜 시간 오프셋* | 읽기 전용 | 직원의 생년월일. |
| **성별**</br>mshr_gender</br>[mshr_hcmpersongender 옵션 집합](hr-admin-integration-payroll-api-gender.md) | 읽기 전용 | 직원의 성별. |
| **고용 유형**</br>mshr_employmenttype</br>[mshr_hcmemploymenttype 옵션 집합](hr-admin-integration-payroll-api-hcmemploymenttype.md) | 읽기 전용 | 고용 유형. |
| **식별 유형 ID**</br>mshr_identificationtypeid</br>*문자열* |읽기 전용 | 직원에 대해 정의된 식별 유형. |
| **식별 번호**</br>mshr_identificationnumber</br>*문자열* | 읽기 전용 |직원에 대해 정의된 식별 번호. |
| **지불 준비됨**</br>mshr_readytopay</br>[mshr_noyes 옵션 집합](hr-admin-integration-payroll-api-no-yes.md) | 읽기 전용 | 직원이 지불 준비로 표시되는지 나타냅니다. |
| **급여 직원 엔터티 ID**</br>mshr_payrollemployeeentityid</br>*GUID* | 시스템 생성 | 직원을 고유하게 식별하기 위해 시스템에서 생성한 GUID(Globally Unique Identifier) 값. |

## <a name="relations"></a>관계

|속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>직원 급여 예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**응답**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
