---
title: 개인 식별 번호
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 식별 번호 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 0991f5b2e17e64e23f78b346c451f7c43bc20378
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452314"
---
# <a name="person-identification-number"></a>개인 식별 번호


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 식별 번호 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>설명

이 엔터티는 후보자의 식별 번호를 나타냅니다. 이를 통해 API 소비자는 사회 보장 번호 또는 여권 번호와 같은 식별 번호를 후보자 레코드에 기록할 수 있습니다. 식별 번호는 근로자 기록에 표시되지만 후보자 기록에는 표시되지 않습니다. 통합 애플리케이션은 Human Resources 데이터베이스에 값을 쓸 수 있지만 후보자의 근로자 레코드가 생성될 때까지 숫자는 인적 자원에 표시되지 않습니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 식별 번호 엔터티 ID**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | 읽기 전용<br>필수<br>시스템 생성 | 개인 식별 번호 레코드의 고유한 기본 식별자. |
| **항목 유형**<br>mshr_entrytype<br>*문자열* | 읽기-쓰기<br>옵션 | 식별 번호에 대한 항목 유형을 참조하는 자유 값. |
| **설명**<br>mshr_description<br>*문자열* | 읽기-쓰기<br>옵션 | ID 번호에 대한 설명입니다. |
| **만료 날짜**<br>mshr_expirationdate<br>*날짜/시간* | 읽기-쓰기<br>옵션 | 식별 번호 또는 관련 문서가 만료되는 날짜. |
| **기본임**<br>mshr_isprimary<br>*mshr_noyes 옵션 집합* | 읽기-쓰기<br>옵션 | 식별 번호가 이 식별 유형에 대한 개인의 기본 레코드인지 정의합니다. |
| **ID 번호**<br>mshr_identificationnumber<br>*문자열* | 읽기-쓰기<br>필수 | ID 번호입니다. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기-쓰기<br>필수 | 식별 번호를 소유하는 당사자(개인)의 고유 식별자. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity 엔터티의 mshr_dirpersonentityid | 당사자(개인)의 고유 식별자. |
| **식별 유형 ID**<br>mshr_identificationtypeid<br>*문자열* | 읽기-쓰기<br>필수 | 식별 번호의 유형. |
| **식별 유형 ID 값**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmidentificationtypeentity 엔터티의 mshr_hcmidentificationtypeentityid | 식별 유형에 대한 시스템 생성 고유 식별자. |
| **발급기관 ID**<br>mshr_issuingagencyid<br>*문자열* | 읽기-쓰기<br>옵션 | 식별 번호를 발급하는 기관 또는 조직. |
| **발급기관 ID 값**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmissuingagencyentity 엔터티의 mshr_hcmissuingagencyentityid | 식별 번호를 발급하는 기관에 대한 시스템 생성 고유 식별자. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 식별자로 사용될 필드. 당사자 번호, 식별 유형 ID 및 식별 번호의 조합. |
| **발행일**<br>mshr_issuedate<br>*날짜* | 읽기-쓰기<br>옵션 | 식별 번호가 발급된 날짜. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
