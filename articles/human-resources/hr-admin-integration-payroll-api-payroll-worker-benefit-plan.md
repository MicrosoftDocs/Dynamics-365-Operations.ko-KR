---
title: 급여 근로자 복리후생 계획
description: 이 항목에서는 Dynamics 365 Human Resources의 급여 근로자 복리후생 계획 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: marcelbf
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1805f7efaf2efc48d5996776f3aa27d75606886f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452452"
---
# <a name="payroll-worker-benefit-plan"></a>급여 근로자 복리후생 계획


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 근로자 복리후생 계획 엔터티에 관해 설명합니다.

실제 이름: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>설명

이 엔터티는 주어진 근로자의 복리후생 계획에 대한 정보를 제공합니다.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용</br>필수 | 직원의 고유한 인사 번호. |
| **법인 ID**</br>mshr_legalentityID</br>*문자열* | 읽기 전용 | 법인(회사)을 지정합니다. |
| **기간 ID**</br>mshr_periodid</br>*문자열* | 읽기 전용 | 기간의 식별자. |
| **계획 ID**</br>mshr_planid</br>*문자열* | 읽기 전용 | 계획의 식별자. |
| **적용 범위 옵션**</br>mshr_coverageoptionid</br>*문자열* | 읽기 전용 | 적용 범위 옵션의 식별. |
| **공제 시작 날짜**</br>mshr_deductionstartdatetime</br>*날짜 시간 오프셋* | 읽기 전용 | 공제 시작 날짜. |
| **공제 종료 날짜**</br>mshr_deductionenddatetime</br>*날짜 시간 오프셋* | 읽기 전용 | 공제 종료 날짜. |
| **상태**</br>mshr_status</br>*[복리후생 직원 계획 상태 옵션 집합](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | 읽기 전용 | 복리후생 계획의 상태. |
| **유효 기간 시작**</br>mshr_validfrom</br>*날짜 시간 오프셋* | 읽기 전용 | 이 레코드가 유효성을 갖는 시작 시각입니다. |
| **유효 기간 끝**</br>mshr_validto</br>*날짜 시간 오프셋* |  읽기 전용 | 이 레코드가 유효성을 갖는 마지막 시각입니다. |
| **계획 유형 ID**</br>mshr_plantypeid</br>*문자열* | 읽기 전용 | 계획 유형의 식별자. |
| **계획 유형 코드**</br>mshr_plantypecode</br>*[복리후생 계획 유형 지원 범위 옵션 집합](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | 읽기 전용 | 계획 유형의 사양. |
| **급여 기간 수**</br>mshr_payperiod</br>*정수* | 읽기 전용 | 복리후생 공급자 또는 직원에게 지급되는 빈도를 나타내는 지급 기간 수. 이 금액은 직원의 연간 복리후생 급여 금액을 계산하는 데 사용됩니다. |
| **직원 금액**</br>mshr_amountemployee</br>*십진수* | 읽기 전용 | 직원 금액 또는 백분율. |
| **고용주 금액**</br>mshr_amountemployer</br>*십진수* | 읽기 전용 | 고용주 금액 또는 백분율. |
| **기본 필드**</br>mshr_primaryfield</br>*문자열* | 시스템 생성 | 기본 필드. |
| **근로자 ID 값** </br>_mshr_fk_worker_id_value</br>*GUID* | 외래 키: mshr_hcmworkerbaseentity 엔터티의 mshr_hcmworkerbaseentityid. | 근로자에 대한 시스템 생성 고유 식별자. |
| **기간 ID 값**</br> _mshr_fk_period_id_value</br>*GUID* | 외래 키: mshr_benefitperiodentity 엔터티의 mshr_benefitperiodentityid. | 기간에 대한 시스템 생성 고유 식별자. |
| **계획 ID 값**</br> _mshr_fk_plan_id_value</br>*GUID* | 외래 키: mshr_benefitplanentity 엔터티의 mshr_benefitplanentityid. | 계획에 대한 시스템 생성 고유 식별자. |
| **계획 유형 ID 값**</br> _mshr_fk_plantype_id_value</br>*GUID* | 외래 키: mshr_benefitplantypeentity 엔터티의 mshr_benefitplantypeentityid. | 계획에 대한 시스템 생성 고유 식별자. |
| **적용 범위 옵션 ID 값**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | 외래 키: mshr_benefitcoverageoptionentity 엔터티의 mshr_benefitcoverageoptionentityid. | 계획에 대한 시스템 생성 고유 식별자. |
| **급여 근로자 복리후생 계획 엔터티 ID 값**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | 읽기 전용 </br> 시스템 생성 | 레코드에 대한 시스템 생성 고유 식별자. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>급여 근로자 복리후생 계획에 대한 예제 쿼리

**요청**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**응답**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
