---
title: 개인 주소
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 주소 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: d428c2b1ce69c55fda2e574715021d4763544a6b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452140"
---
# <a name="person-address"></a>개인 주소


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 주소 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersonaddressentities

## <a name="description"></a>설명

이 엔터티에는 후보자 레코드의 우편 주소 목록이 포함되어 있습니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 주소 엔터티 ID**<br>mshr_hcmpersonaddressentityid<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 | 관련 당사자(개인) 레코드의 ID. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 당사자(개인) 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **위치 ID**<br>mshr_locationid<br>*문자열* | 읽기/쓰기<br>필수 | 주소 레코드의 위치 ID. mshr_logisticspostaladdresslocationcdsentity 엔터티에서 설정합니다. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 후보자 주소에 대한 설명. |
| **역할**<br>mshr_roles<br>*문자열* | 읽기/쓰기<br>필수 | 이 주소에 할당된 역할. 둘 이상의 역할을 할당할 수 있습니다. 각 역할은 세미콜론으로 구분해야 합니다. 유효한 값은 mshr_logisticslocationroleentity 엔터티에 포함되어 있습니다. |
| **주소**<br>mshr_street<br>*문자열* | 읽기/쓰기<br>옵션 | 거리 번호. |
| **시**<br>mshr_city<br>*문자열* | 읽기/쓰기<br>옵션 | 주소의 도시입니다. mshr_logisticsaddresscityentity 엔터티에서 설정합니다. |
| **주**<br>mshr_state<br>*문자열* | 읽기/쓰기<br>옵션 | 주소의 주. mshr_logisticsaddressstateentity 엔터티에서 설정합니다. |
| **군/구**<br>mshr_county<br>*문자열* | 읽기/쓰기<br>옵션 | 주소의 구/군/시입니다. mshr_logisticsaddresscountyentity 엔터티에서 설정합니다. |
| **우편 번호**<br>mshr_zipcode<br>*문자열* | 읽기/쓰기<br>옵션 | 주소의 우편 번호. mshr_logisticsaddresspostalcodeentity 엔터티에서 설정합니다. |
| **국가 지역 ID**<br>mshr_countryregionid<br>*문자열* | 읽기/쓰기<br>옵션 | 주소의 국가 또는 지역입니다. |
| **국가/지역 ID 값**<br>_mshr_fk_countriregion_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_logisticsaddresscountryregionentity의 mshr_logisticaddresscountryregionentityid | 주소 국가/지역에 대한 시스템 생성 고유 식별자. |
| **기본임**<br>mshr_isprimary<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 이 주소가 정의된 역할의 개인에 대한 기본 주소인지 식별합니다. |
| **사적**<br>mshr_isprivate<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 이 주소가 개인의 사적 주소인지 여부를 식별합니다. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 기본 식별자로 사용되는 필드. 당사자 번호와 위치 ID의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
