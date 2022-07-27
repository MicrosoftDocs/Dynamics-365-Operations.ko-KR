---
title: 개인 이름 기록
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 이름 기록 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d87803b6ae0ada3ed2de6e4e7da5ffa57bf22eec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452071"
---
# <a name="person-name-history"></a>개인 이름 기록


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 이름 기록 엔터티에 관해 설명합니다.

실제 이름: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>설명

이 엔터티는 주어진 개인의 이름 기록에 대한 정보를 제공합니다.

> [!IMPORTANT] 
> 더는 급여 직원 엔터티에서 **FirstName**, **MiddleName**, **LastName**, **NameValidFrom**, **NameValidTo** 필드를 사용할 수 없습니다. 이 엔터티를 지원하는 유효 날짜 데이터 원본이 하나만 있게 하도록 제거되었습니다.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **이름**</br>mshr_firstname</br>*문자열* | 읽기 전용 | 이름. |
| **성 접두사**</br>mshr_lastnameprefix</br>*문자열* | 읽기 전용 | 성 이름 접두사. |
| **성**</br>mshr_lastname</br>*문자열* | 읽기 전용 | 성 이름. |
| **중간 이름**</br>mshr_middlename</br>*문자열* | 읽기 전용 | 중간 이름. |
| **유효 기간 끝**</br>mshr_validto</br>*문자열* | 읽기 전용 | 이름이 유효한 종료 날짜. |
| **당사자 번호**</br>mshr_partynumber</br>*문자열* | 읽기 전용 | 개인에 대한 사용자가 읽을 수 있는 시스템 생성 고유 식별자. |
| **기본 필드**</br>mshr_primaryfield</br>*문자열* | 읽기 전용 | 레코드의 고유 식별자. |
| **개인 성명 기록 엔터티 ID**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | 시스템 생성 | 레코드를 고유하게 식별하기 위해 시스템에서 생성한 GUID(Globally Unique Identifier) 값. |

## <a name="relations"></a>관계

| 속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| 해당 없음 | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | 해당 없음 | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>직원 급여 예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**응답**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
