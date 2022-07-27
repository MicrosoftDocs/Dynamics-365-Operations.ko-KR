---
title: 모집 요청 위치
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 위치 엔터티에 관해 설명합니다.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4dbc676e25c1ec24350607b10787924b0738e102
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452530"
---
# <a name="recruiting-request-location"></a>모집 요청 위치


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 위치 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>설명

채용된 직원이 근무할 위치로 정의된 위치 목록. 이는 법인 전체에서 생성된 위치입니다.

### <a name="json-representation"></a>JSON 표현

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **위치 ID**<br>mshr_locationid<br>*문자열* | 한 번 쓰기<br>필수 | 모집 위치에 대한 사용자가 읽을 수 있는 시스템 생성 식별자. |
| **모집 요청 위치**<br>mshr_recruitingrequestlocationid<br>*문자열* | 한 번 쓰기<br>필수 | 모집 위치에 대한 사용자 정의 고유 식별자. |
| **모집 요청 위치 엔터티 ID**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | 읽기 전용<br>필수 | 모집 요청 위치 레코드에 대한 시스템 생성 고유 식별자. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 위치에 대한 설명. |
| **국가/지역 ID**<br>mshr_countryregionid<br>*문자열* | 읽기 전용<br>옵션 | 후보자가 시민권을 가지고 있는 국가/지역을 지정합니다. |
| **국가/지역 ID 값**<br>_mshr_fk_countriregion_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_logisticsaddresscountryregionentity의 mshr_logisticaddresscountryregionentityid | 주소 국가/지역에 대한 시스템 생성 고유 식별자. |
| **우편 번호**<br>mshr_zipcode<br>*문자열* | 읽기 전용<br>옵션 | 우편 번호. |
| **주소**<br>mshr_street<br>*문자열* | 읽기 전용<br>옵션 | 상세 주소. |
| **시**<br>mshr_city<br>*문자열* | 읽기 전용<br>옵션 | 시. |
| **상태**<br>mshr_state<br>*문자열* | 읽기 전용<br>옵션 | 주 또는 도. |
| **군/구**<br>mshr_county<br>*문자열* | 읽기 전용<br>옵션 | 구/군. |
| **전화 번호**<br>mshr_telephone<br>*문자열* | 읽기/쓰기<br>옵션 | 위치의 전화번호. |
| **이메일**<br>mshr_email<br>*문자열* | 읽기/쓰기<br>옵션 | 이메일 주소. |
| **인터넷 주소**<br>mshr_internetaddress<br>*문자열* | 읽기/쓰기<br>옵션 | 위치의 웹 사이트의 URL. |
| **데이터 영역 ID**<br>mshr_dataareaid<br>*문자열* | 읽기/쓰기<br>옵션 | 법인(회사)을 지정합니다. |
| **데이터 영역 ID 값**<br>_mshr_dataareaid_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: cdm_company 엔터티의 cdm_companyid | 법인(회사)을 식별하는 시스템 생성 GUID 값. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
