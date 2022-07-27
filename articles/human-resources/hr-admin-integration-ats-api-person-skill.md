---
title: 개인 기술
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 기술 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: c37001c82be34e802835515db86f7ab29e6735bf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452218"
---
# <a name="person-skill"></a>개인 기술


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 기술 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersonskillentity

## <a name="description"></a>설명

이 엔터티는 후보자의 기술을 나타냅니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 기술 엔터티 ID**<br>mshr_hcmpersonskillentityid<br>*GUID* | 읽기 전용<br>필수 | 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 |   관련 당사자(개인) 레코드의 ID. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 당사자(개인) 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **인증자**<br>mshr_certifier<br>*문자열* | 읽기/쓰기<br>옵션 | 이 기술을 인증한 근로자의 인사 번호. |
| **인증자 ID 값**<br>_mshr_fk_certifier_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmworkerentity의 mshr_hcmworkerentityid | 기술을 인증한 근로자에 대한 근로자 레코드에 대한 시스템 생성 고유 식별자. |
| **기술 ID**<br>mshr_skillid<br>*문자열* | 읽기/쓰기<br>필수 | Human Resources에 정의된 기술의 식별자. |
| **기술 ID 값**<br>_mshr_fk_skill_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmskillentity의 mshr_hcmskillentityid | 선택된 기술에 대한 시스템 생성 식별자. |
| **경험 기간(년)**<br>mshr_yearsofexperience<br>*십진수* | 읽기/쓰기<br>옵션 | 후보자가 이 기술에 대해 가지고 있는 경험 기간(년). |
| **등급 ID**<br>mshr_ratingid<br>*문자열* | 읽기/쓰기<br>필수 | 등급 척도 유형. 이 엔터티의 경우 값은 **기술** 입니다. |
| **수준 유형**<br>mshr_leveltype<br>*mshr_hrmskillleveltype 옵션 집합* | 읽기/쓰기<br>필수 | 기술에 할당된 수준의 유형 분류. |
| **수준 ID**<br>mshr_levelid<br>*문자열* | 읽기/쓰기<br>필수 | 후보자가 이 기술에 대해 가지고 있는 등급 수준의 ID. |
| **등급 수준 ID 값**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmratinglevelentity의 mshr_hcmratinglevelentityid | 등급 수준에 대한 시스템 생성 식별자. |
| **수준 날짜**<br>mshr_leveldate<br>*날짜/시간* | 읽기/쓰기<br>필수 | 후보자의 기술이 평가된 날짜. |
| **등급 수준 심사관**<br>mshr_ratinglevelexaminer<br>*문자열* | 읽기/쓰기<br>옵션 | 후보자의 등급을 조사한 근로자의 인사 번호. |
| **등급 수준 심사관 ID 값**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmworkerentity의 mshr_hcmworkerentityid | 후보자의 기술 수준을 조사한 근로자에 대한 시스템 생성 식별자. |
| **확인됨**<br>mshr_verified<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 평가된 기술 수준이 확인되었는지 여부. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 식별자로 사용될 필드. 당사자 번호, 수준 유형, 기술 ID, 수준 날짜의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
