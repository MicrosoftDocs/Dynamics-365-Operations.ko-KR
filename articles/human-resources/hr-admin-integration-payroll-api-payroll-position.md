---
title: 직위에 대한 급여 세부 정보
description: 이 항목에서는 Dynamics 365 Human Resources의 직위에 대한 급여 세부 정보 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
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
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452587"
---
# <a name="payroll-position"></a>급여 직위


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 직위 엔터티에 관해 설명합니다.

실제 이름: mshr_payrollpositionentity.

### <a name="description"></a>설명

이 엔터티는 주어진 직원에 대한 직위 관련 정보를 제공합니다.

실제 이름: mshr_payrollpositionentity.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **직책 ID**</br>mshr_positionid</br>*문자열* | 읽기 전용 | 직위의 ID. |
| **급여 주기 ID**</br>mshr_paycycleid</br>*문자열* | 읽기 전용 | 직위에 정의된 급여 주기. |
| **연간 정규 시간**</br>annualregularhours</br>*십진수* | 읽기 전용 | 직위에 정의된 연간 정규 시간. |
| **법인 지급**</br>paidbylegalentity</br>*문자열* | 읽기 전용 | 직위에 정의되어 있고 지급을 담당하는 법인. |
| **유효 기간 끝**</br>validto</br>*날짜 시간 오프셋* | 읽기 전용 | 직위 세부 정보가 유효한 종료 날짜. |
| **유효 기간 시작**</br>validfrom</br>*날짜 시간 오프셋* | 읽기 전용 | 직위 세부 정보가 유효한 시작 날짜. |
| **기본 필드**</br>mshr_primaryfield</br>*문자열* | 시스템 생성 | 기본 필드. |
| **급여 직위 세부 정보 엔터티 ID**</br>payrollpositiondetailsentityid</br>*GUID* | 필수</br>시스템 생성. | 직위를 고유하게 식별하기 위해 시스템에서 생성한 GUID(Globally Unique Identifier) 값. |

## <a name="relations"></a>관계

| 속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | 해당 없음 |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | 해당 없음 |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**응답**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
