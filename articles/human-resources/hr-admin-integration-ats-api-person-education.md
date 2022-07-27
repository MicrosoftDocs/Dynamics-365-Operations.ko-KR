---
title: 개인 교육
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 교육 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 6334467de488ed24ce684a2a059a5ffd0cf04959
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452083"
---
# <a name="person-education"></a>개인 교육


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 교육 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersoneducationentity

## <a name="description"></a>설명

이 엔터티에는 후보자 개인의 교육이 포함됩니다. 교육은 개인 레코드와 연계되며 후보자 레코드(근로자, 계약자 등) 외에 개인을 위해 만들어진 다른 역할과 연관될 수 있습니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 교육 엔터티 ID**<br>mshr_hcmpersoneducationentityid<br>*GUID* | 읽기 전용<br>필수 | 개인 교육 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 | 후보자의 당사자(개인) 레코드에 대한 고유 식별자. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 후보자의 개인 레코드에 대한 시스템 생성 고유 식별자. |
| **학점 기준**<br>mshr_creditbasis<br>*mshr_hcmeducationcreditbasis 옵션 집합* | 읽기/쓰기<br>옵션 | 교육 학위의 학점 기준. |
| **이수 학점**<br>mshr_creditscompleted<br>*십진수* | 읽기/쓰기<br>옵션 | 교육을 위해 이수한 학점. |
| **취득한 학점**<br>mshr_creditsearned<br>*십진수* | 읽기/쓰기<br>옵션 | 진행 중인 학위의 교육 레코드에 취득한 학점 수. |
| **필요한 학점**<br>mshr_creditsneeded<br>*십진수* | 읽기/쓰기<br>옵션 | 진행 중인 학위에 필요한 학점 수. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>옵션 | 후보자 학위에 대한 설명. |
| **교육 수준 ID**<br>mshr_educationlevelid<br>*문자열* | 읽기/쓰기<br>옵션 | 교육 수준의 ID. | 
| **교육 수준 ID 값**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmeducationdegreeentity 엔터티의 mshr_hcmeducationdegreeentityid | 교육 학위 레코드에 대한 시스템 생성 식별자. 이 식별자는 조직에 정의된 학위 및 교육 수준을 제공합니다. |
| **교육 학과 ID**<br>mshr_educationdisciplineid<br>*문자열* | 읽기/쓰기<br>필수<br>외래 키: EducationDiscipline | 교육 학과의 ID. |
| **교육 학과 ID 값**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmeducationdisciplineentity 엔터티의 mshr_hcmeducationdisciplineentityid | 교육 레코드의 교육 학과에 대한 시스템 생성 고유 식별자. |
| **부전공**<br>mshr_secondaryemphasis<br>*문자열* | 읽기/쓰기<br>옵션 | 취득 학위의 부전공. |
| **교육 기관 ID**<br>mshr_educationinstitutionid<br>*문자열* | 읽기/쓰기<br>옵션 | 재학 중인 교육 기관의 ID. |
| **교육 기관 ID 값**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmeducationinstitutionentity의 mshr_hcmeducationinstitutionentityid | 교육 기관에 대한 시스템 생성 식별자. |
| **시작 날짜**<br>mshr_startdate<br>*날짜/시간* | 읽기/쓰기<br>옵션 | 취득한 학위의 교육 시작 날짜. |
| **종료 날짜**<br>mshr_enddate<br>*날짜/시간* | 읽기/쓰기<br>필수 | 자격 증명이 발급된 날짜. |
| **기간**<br>mshr_duration<br>*십진수* | 읽기/쓰기<br>옵션 | 교육 레코드의 기간. |
| **기간 단위**<br>mshr_durationunit<br>*mshr_periodunit 옵션 집합* | 읽기/쓰기<br>옵션 | 교육 레코드의 기간과 관련된 시간 단위. |
| **평균 성적**<br>mshr_gradepointaverage<br>*십진수* | 읽기/쓰기<br>옵션 | 학위에 대한 획득한 학점 평균. |
| **척도**<br>mshr_gradescale<br>*문자열* | 읽기/쓰기<br>옵션 | 학점 평균에 사용되는 척도. |
| **메모**<br>mshr_notes<br>*문자열* | 읽기/쓰기<br>옵션 | 모집 담당자 또는 채용 관리자가 사용하기 위한 참고 사항. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 다른 기본 식별자로 사용되는 필드. 당사자 번호, 교육 학과 ID, 교육 기관 ID, 교육 수준 ID의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
