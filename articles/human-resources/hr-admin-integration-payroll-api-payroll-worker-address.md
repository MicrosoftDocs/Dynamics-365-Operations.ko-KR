---
title: 급여 근로자 주소
description: 이 항목에서는 Dynamics 365 Human Resources의 급여 근로자 주소 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
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
ms.openlocfilehash: 70e42cbf657a28327699d927731edd36de7c4a64
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452581"
---
# <a name="payroll-worker-address"></a>급여 근로자 주소


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 급여 근로자 주소 엔터티에 관해 설명합니다.

실제 이름: mshr_payrollworkeraddressentity.

### <a name="description"></a>설명

이 엔터티는 지정된 직원의 급여 거주지 위치와 급여 근무 위치를 제공합니다.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용 | 직원의 고유한 인사 번호. |
| **위치 ID**</br>mshr_locationidbr *문자열* | 읽기 전용 | 주소의 ID. |
| **거주지 주소**</br>mshr_islivedinaddressbr </br> *[mshr_NoYes 옵션 집합](hr-admin-integration-payroll-api-no-yes.md)* | 읽기 전용 | 주소가 직원이 사는 곳인지 나타내는 값. |
| **근무지 주소** </br> mshr_isworkedinaddressbr </br>*[mshr_NoYes 옵션 집합](hr-admin-integration-payroll-api-no-yes.md)* | 읽기 전용 | 주소가 직원이 근무하는 곳인지 나타내는 값. |
| **국가 지역**</br>mshr_countryregionid</br>*문자열* | 읽기 전용</br>필수 | 주소에 대해 정의된 국가 또는 지역. |
| **우편 번호**</br>mshr_zipcode<br>*문자열* | 읽기 전용 | 직원에 대해 정의된 식별 번호. |
| **주소**</br>mshr_street</br>*문자열* | 읽기 전용 | 주소에 대해 정의된 거리. |
| **시**</br>mshr_city</br>*문자열* | 읽기 전용 | 주소에 대해 정의된 도시. |
| **상태**</br>mshr_state</br>*문자열* | 읽기 전용 | 주소에 대해 정의된 주/도. |
| **군/구**</br>mshr_county</br>*문자열* | 읽기 전용 | 주소에 대해 정의된 군/구. |
| **유효 기간 시작**</br>mshr_postaladdressvalidfrom</br>*날짜 시간 오프셋* | 읽기 전용 | 주소가 유효한 시작 날짜. |
| **유효 기간 끝**</br>mshr_postaladdressvalidto</br>*날짜 시간 오프셋* | 읽기 전용 | 주소가 유효한 종료 날짜. |
| **기본 필드**</br>mshr_primaryfield</br>*문자열* | 읽기 전용 | 기본 필드. |
| **급여 근로자 주소 ID**</br>mshr_payrollworkeraddressentityid</br>*GUID* | 시스템 생성 | 주소를 고유하게 식별하기 위해 시스템에서 생성한 GUID(Globally Unique Identifier) 값. |

## <a name="relations"></a>관계

| 속성 값 | 관련 엔터티 | 탐색 속성 | 컬렉션 유형 |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**응답**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
