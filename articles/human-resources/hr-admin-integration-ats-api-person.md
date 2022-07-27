---
title: 개인
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 728e383be44949ec7f1e51feb5157c61679b3e7b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452479"
---
# <a name="person"></a>개인


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 엔터티에 관해 설명합니다.

실제 이름: mshr_dirpersonentity

### <a name="description"></a>설명

이 엔터티는 후보자 개인에 대한 개인 정보를 제공합니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 엔터티 ID**<br>mshr_dirpersonentityid<br>*GUID* | 읽기 전용<br>필수<br>시스템 생성 | 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기 전용<br>필수<br>시스템 생성 | 개인에 대한 사용자가 읽을 수 있는 시스템 생성 고유 식별자.  |
| **이름**<br>mshr_name<br>*문자열* | 읽기 전용<br>필수 | 필드 값은 **이름 시퀀스 표시 방법** 필드에 정의된 순서대로 이름, 중간 이름, 성 접두사 및 성을 연결한 것입니다. |
| **이름 별칭**<br>mshr_namealias<br>*문자열* | 읽기/쓰기<br>옵션 | 개인에게 제공할 수 있는 이름 별칭. |
| **다음으로 알려짐**<br>mshr_knownas<br>*문자열* | 읽기/쓰기<br>옵션 | 일반적으로 다른 이름으로 알려진 경우 그 사람에게 사용될 수 있는 이름. |
| **언어 ID**<br>mshr_languageid<br>*문자열* | 읽기/쓰기<br>옵션 | ISO 639-1 형식으로 정의된 개인의 기본 언어의 언어 ID. |
| **주소록**<br>mshr_addressbooks<br>*문자열* | 읽기/쓰기<br>옵션 | 개인이 할당될 수 있는 주소록. 조직에 대해 설정된 주소록은 mshr_diraddressbooksentity 엔터티에 나열됩니다. |
| **기념일**<br>mshr_anniversaryday<br>*정수* | 읽기/쓰기<br>옵션 | 개인의 기념일 일. |
| **기념일 월**<br>mshr_anniversarymonth<br>*mshr_monthsofyear 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 기념일 월. |
| **기념일 년**<br>mshr_anniversaryyear<br>*정수* | 읽기/쓰기<br>옵션 | 개인의 기념일 년도. |
| **출생 일**<br>mshr_birthday<br>*정수* | 읽기/쓰기<br>옵션 | 개인의 출생 일. |
| **출생 월**<br>mshr_birthmonth<br>*mshr_monthsofyear 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 출생 월. |
| **출생 연도**<br>mshr_birthyear<br>*정수* | 읽기/쓰기<br>옵션 | 개인의 출생 연도. |
| **어린이 이름**<br>mshr_childrennames<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 자녀 이름 문자열. 필수 구분은 없습니다. |
| **성별**<br>mshr_gender<br>*mshr_hcmpersongender 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 성별. |
| **취미**<br>mshr_hobbies<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 취미. |
| **이니셜**<br>mshr_initials<br>*문자열* | 읽기/쓰기<br>옵션 | 개인 이름의 이니셜. |
| **결혼 상태**<br>mshr_maritalstatus<br>*mshr_hcmpersonmaritalstatus 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 결혼 상태. |
| **음성 이름**<br>mshr_phoneticfirstname<br>*문자열* | 읽기/쓰기<br>옵션 | 개인 이름의 음성 발음. |
| **음성 성**<br>mshr_phoneticlastname<br>*문자열* | 읽기/쓰기<br>옵션 | 개인 성의 음성 발음. |
| **음성 중간 이름**<br>mshr_phoneticmiddlename<br>*문자열* | 읽기/쓰기<br>옵션 | 개인 성의 음성 발음. |
| **개인 접미사**<br>mshr_personalsuffix<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 개인 접미사. 유효한 값은 mshr_dirnameaffixentity 엔터티에 있으며 mshr_type은 접미사(200000001)입니다. |
| **직함**<br>mshr_personaltitle<br>*문자열* | 읽기/쓰기<br>옵션 | 개인에 대한 개인 직함. 유효한 값은 mshr_dirnameaffixentity 엔터티에 있으며 mshr_type은 직함(200000000)입니다.
| **전문 접미사**<br>mshr_professionalsuffix<br>*문자열* | 읽기/쓰기<br>옵션 | 전문 접미사. |
| **전문 직함**<br>mshr_professionaltitle<br>*문자열* | 읽기/쓰기<br>옵션 | 전문 직함. |
| **전체 기본 주소**<br>mshr_fullprimaryaddress<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 전체 기본 주소, 기본 주소 필드의 연결. |
| **주소 도시**<br>mshr_addresscity<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 도시. mshr_logisticsaddresscityentity 엔터티에서 설정합니다. |
| **주소 국가 지역**<br>mshr_addresscountryregionid<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 국가/지역. 유효한 값은 mshr_logisticsaddresscountryregionentity 엔터티에 있습니다. |
| **주소 국가 지역 ISO 코드**<br>mshr_addresscountryregionisocode<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 국가 ISO 코드. |
| **주소 구/군**<br>mshr_addresscounty<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 구/군. mshr_logisticsaddresscountyentity 엔터티에서 설정합니다. |
| **주소 지구 이름**<br>mshr_addressdistrictname<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 지구. mshr_logisticsaddressdistrictentity 엔터티에서 설정합니다. |
| **주소 위도**<br>mshr_addresslatitude<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 위도. |
| **주소 위치 ID**<br>mshr_addresslocationid<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소 위치에 대한 고유 식별자. 유효한 값은 mshr_logisticspostaladdresslocationcdsentity 엔터티에 있습니다. |
| **주소 위치 역할**<br>mshr_addresslocationroles<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 위치 역할. mshr_logisticslocationrolecdsentity 엔터티에서 설정합니다. |
| **주소 경도**<br>mshr_addresslongitude<br>*문자열* |  읽기/쓰기<br>옵션 | 개인의 기본 주소의 경도. |
| **주소 상태**<br>mshr_addressstate<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 주. mshr_logisticsaddressstateentity 엔터티에서 설정합니다. |
| **주소 번지**<br>mshr_addressstreet<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 상세 주소. |
| **주소 유효 기간(시작)**<br>mshr_addressvalidfrom<br>*날짜* | 읽기/쓰기<br>옵션 | 개인의 기본 주소가 유효한 시작 날짜. |
| **주소 유효 기간(종료)**<br>mshr_addressvalidto<br>*날짜* | 읽기/쓰기<br>옵션 | 개인의 기본 주소가 유효한 종료 날짜. |
| **주소 우편 번호**<br>mshr_addresszipcode<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 우편 번호. mshr_logisticsaddresspostalcodeentity 엔터티에서 설정합니다. |
| **사적인 주소임**<br>mshr_addressisprivate<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 기본 주소가 조직의 다른 사람과 공유되는지 결정합니다. |
| **주소 설명**<br>mshr_addressdescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 주소에 대한 설명. |
| **기본 연락처 이메일**<br>mshr_primarycontactemail<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 이메일 주소. |
| **기본 연락처 이메일 설명**<br>mshr_primarycontactemaildescription<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 이메일 주소에 대해 제공되는 설명. |
| **기본 연락처 이메일이 IM임**<br>mshr_primarycontactemailisim<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 기본 전자 메일 주소를 인스턴트 메시지에 사용할 수 있는지 결정합니다. |
| **기본 연락처 이메일 목적**<br>mshr_primarycontactemailpurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 이메일 주소의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **기본 연락처 팩스**<br>mshr_primarycontactfax<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 팩스 번호. |
| **기본 연락처 팩스 설명**<br>mshr_primarycontactfaxdescription<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 팩스 번호에 대해 제공되는 설명. |
| **기본 연락처 팩스 내선 번호**<br>mshr_primarycontactfaxextension<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 팩스 번호의 내선 번호. |
| **기본 연락처 팩스 목적**<br>mshr_primarycontactfaxpurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 팩스 번호의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다.
| **기본 연락처 전화**<br>mshr_primarycontactphone<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 전화번호. |
| **기본 연락처 전화 설명**<br>mshr_primarycontactphonedescription<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 전화번호에 대해 제공되는 설명. |
| **기본 연락처 전화 내선 번호**<br>mshr_primarycontactphoneextension<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 전화번호의 내선 번호. |
| **기본 연락처 전화가 휴대 전화임**<br>mshr_primarycontactphoneismobile<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 기본 전화번호가 휴대 전화인지 결정합니다. |
| **기본 연락처 전화 목적**<br>mshr_primarycontactphonepurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 전화번호의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **기본 연락처 텔렉스**<br>mshr_primarycontacttelex<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 텔렉스 번호. |
| **기본 연락처 텔렉스 설명**<br>mshr_primarycontacttelexdescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 텔렉스 번호에 대해 제공되는 설명. |
| **기본 연락처 텔렉스 목적**<br>mshr_primarycontacttelexpurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 텔렉스 번호의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **기본 연락처 URL**<br>mshr_primarycontacturl<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 URL. |
| **기본 연락처 URL 설명**<br>mshr_primarycontacturldescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 URL에 대한 설명. |
| **기본 연락처 URL 목적**<br>mshr_primarycontacturldescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 URL의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **기본 연락처 Facebook**<br>mshr_primarycontactfacebook<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 Facebook 계정. 사용자 ID로 식별됩니다. |
| **기본 연락처 Facebook 설명**<br>mshr_primarycontactfacebookdescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 Facebook 계정에 대한 설명. |
| **기본 연락처 Facebook이 사적임**<br>mshr_primarycontactfacebookisprivate<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 기본 Facebook 계정이 다른 사용자에게 표시될지 결정합니다. |
| **기본 연락처 Facebook 목적**<br>mshr_primarycontactfacebookpurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 Facebook 계정의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **기본 연락처 LinkedIn**<br>mshr_primarycontactlinkedin<br>*문자열* | 읽기/쓰기<br>옵션 | 기본 LinkedIn 계정. 사용자 이름으로 식별됩니다. |
| **기본 연락처 LinkedIn 설명**<br>mshr_primarycontactlinkedindescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 LinkedIn 계정에 대한 설명. |
| **기본 연락처 LinkedIn이 사적임**<br>mshr_primarycontactlinkedinisprivate<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 기본 LinkedIn 계정 정보가 다른 사용자와 공유되는지 결정합니다. |
| **기본 연락처 LinkedIn 목적**<br>mshr_primarycontactlinkedinpurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 LinkedIn 계정의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **기본 연락처 Twitter**<br>mshr_primarycontacttwitter<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 Twitter 계정. @username으로 식별됩니다. |
| **기본 연락처 Twitter 설명**<br>mshr_primarycontacttwitterdescription<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 Twitter 계정에 대한 설명. |
| **기본 연락처 Twitter가 사적임**<br>mshr_primarycontacttwitterisprivate<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 개인의 기본 Twitter 계정 정보가 다른 사용자와 공유되는지 결정합니다. |
| **기본 연락처 Twitter 목적**<br>mshr_primarycontacttwitterpurpose<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 기본 Twitter 계정의 목적. mshr_logisticslocationroleentity 엔터티에서 설정합니다. |
| **당사자 유형**<br>mshr_partytype<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 당사자 유형. 항상 후보자의 **개인** 입니다. |
| **이름 시퀀스 표시 방법**<br>mshr_namesequencedisplayas<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 이름 속성이 이름(mshr_name) 속성 값에서 연결되는 순서. |
| **이름**<br>mshr_firstname<br>*문자열* | 읽기/쓰기<br>필수 | 개인의 이름. |
| **중간 이름**<br>mshr_middlename<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 중간 이름. |
| **성 접두사**<br>mshr_lastnameprefix<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 성의 접두사. |
| **성**<br>mshr_lastname<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 성. |
| **전자 위치 ID**<br>mshr_electroniclocationid<br>*문자열* | 읽기/쓰기<br>옵션 | 개인의 전자 위치 ID. |
| **주소 표준 시간대**<br>mshr_addresstimezone<br>*정수* | 읽기/쓰기<br>옵션 | 개인의 기본 주소의 표준 시간대. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
