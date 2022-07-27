---
title: 개인 자격증
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 자격증 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 300bf294bb4b2fadd4c5d3e68e74674a69dd48f2
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452401"
---
# <a name="person-certificate"></a>개인 자격증


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 자격증 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersoncertificateentity

## <a name="description"></a>설명

이 엔터티는 후보자의 전문 자격증을 나타냅니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 자격증 엔터티 ID**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | 읽기 전용<br>필수 | 개인 자격증 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 | 후보자의 당사자(개인) ID. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 당사자(개인) 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **자격증 유형 ID**<br>mshr_certificatetypeid<br>*문자열* | 읽기/쓰기<br>필수 |  Human Resources에 정의된 자격증 유형의 식별자. |
| **자격증 유형 ID 값**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmcertificatetypeentity의 mshr_hcmcertificatetypeentityid | 연결된 엔터티 유형의 자격증에 대한 시스템 생성 고유 식별자. |
| **시작 날짜**<br>mshr_startdate<br>*날짜/시간* | 읽기/쓰기<br>필수 | 자격증이 발급된 날짜. |
| **종료 날짜**<br>mshr_enddate<br>*날짜/시간* | 읽기/쓰기<br>옵션 | 자격증이 만료될 날짜. |
| **메모**<br>mshr_notes<br>*문자열* | 읽기/쓰기<br>옵션 | 채용 관리자 및 모집 담당자가 사용하기 위한 참고 사항. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 |  엔터티 레코드의 식별자로 사용될 필드. 당사자 번호, 자격증 유형 ID 및 시작 날짜의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
