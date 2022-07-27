---
title: 당사자 연락처
description: 이 항목에서는 Dynamics 365 Human Resources의 당사자 연락처 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: fca72cb73ef46a4eeee27d43e22254373a425a36
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452317"
---
# <a name="party-contact"></a>당사자 연락처


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 당사자 연락처 엔터티에 관해 설명합니다.

실제 이름: mshr_dirpartycontactentities

## <a name="description"></a>설명

이 엔터티는 전화, 이메일 및 소셜 미디어 계정을 포함한 후보자의 연락처 정보를 나타냅니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **당사자 연락처 엔터티 ID**<br>mshr_dirpartycontactentityid<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 | 관련 당사자(개인) 레코드의 ID. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 당사자(개인) 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **위치 ID**<br>mshr_locationid<br>*문자열* | 읽기/쓰기<br>필수 | 주소 레코드의 위치 ID. mshr_logisticspostaladdresslocationcdsentity 엔터티에서 설정합니다. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 연락처 세부 정보에 대한 설명. |
| **형식**<br>mshr_type<br>*mshr_logisticselectronicaddressmethodtype 옵션 집합* | 읽기/쓰기<br>필수 | 연락처 세부 정보 유형. |
| **국가 지역 코드**<br>mshr_countryregioncode<br>*문자열* | 읽기/쓰기<br>옵션 | 주소의 국가 또는 지역입니다. |
| **로케이터**<br>mshr_locator<br>*문자열* | 읽기/쓰기<br>옵션 | 연락처 세부 정보. 예를 들어 유형이 **이메일 주소** 인 경우 이 필드에는 후보자의 이메일 주소가 포함됩니다. |
| **로케이터 확장**<br>mshr_locatorextension<br>*문자열* | 읽기/쓰기<br>옵션 | 로케이터 확장. 예를 들어 유형이 **전화** 인 경우 이 속성에는 전화번호 확장이 포함됩니다. |
| **휴대전화**<br>mshr_ismobile<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 전화가 휴대전화 번호인지 지정합니다. |
| **인스턴트 메시지**<br>mshr_isinstantmessage<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 전화기에서 인스턴트 메시징을 사용할 수 있는지 지정합니다. |
| **기본임**<br>mshr_isprimary<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 연락처 유형의 기본 연락처를 결정합니다. 연락처 유형당 기본 레코드는 하나만 있어야 합니다. |
| **사적**<br>mshr_isprivate<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>필수 | 이 주소가 개인의 사적 주소인지 여부를 식별합니다. |
| **목적**<br>mshr_purpose<br>*문자열* | 읽기/쓰기<br>옵션 | 연락처 세부 정보의 목적/역할. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 기본 식별자로 사용되는 필드. 당사자 번호, 유형, 설명 및 로케이터의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
