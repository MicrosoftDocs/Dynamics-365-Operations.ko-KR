---
title: 개인 전문 경험
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 전문 경험 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 38535b5dd56b3408ea582fbaf1594b7adefcd171
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452482"
---
# <a name="person-professional-experience"></a>개인 전문 경험


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 전문 경험 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>설명

이 엔터티는 후보자의 전문적인 경험이나 경력을 나타냅니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 전문 경험 엔터티 ID**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | 읽기 전용<br>필수 | 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 | 후보자의 당사자 레코드에 대한 고유 식별자. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 개인 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **고용주 직위**<br>mshr_employerposition<br>*문자열* | 읽기/쓰기<br>필수 | 재직 중 후보자가 보유한 직위. |
| **고용주 이름**<br>mshr_employername<br>*문자열* | 읽기/쓰기<br>필수 | 고용주의 이름. |
| **고용주 위치**<br>mshr_employerlocation<br>*문자열* | 읽기/쓰기<br>옵션 | 고용주의 위치. 최대 길이: 60. 특정 형식이 정의되거나 필요하지 않습니다. |
| **전화**<br>mshr_phone<br>*문자열* | 읽기/쓰기<br>옵션 | 고용주의 전화번호. |
| **URL**<br>mshr_url<br>*문자열* | 읽기/쓰기<br>옵션 | 고용주 웹사이트의 URL. |
| **시작 날짜**<br>mshr_startdate<br>*날짜/시간* | 읽기/쓰기<br>필수 | 후보자의 근무 시작 날짜. |
| **종료 날짜**<br>mshr_enddate<br>*날짜/시간* | 읽기/쓰기<br>옵션 | 후보자의 고용 종료 날짜 또는 후보자가 아직 고용된 경우 null. |
| **고용주에게 연락 허용**<br>mshr_allowcontactemployer<br>*mshr_hrmblankyesno 옵션 집합* | 읽기/쓰기<br>옵션 | 후보자가 이전 고용주와의 연락을 허용하는지 여부. |
| **메모**<br>mshr_note<br>*문자열* | 읽기/쓰기<br>옵션 | 모집 담당자 또는 채용 관리자가 사용하기 위한 참고 사항. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 기본 식별자로 사용되는 필드. 당사자 번호, 시작 날짜, 고용주 직위 및 고용주 이름의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
