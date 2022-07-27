---
title: 채용할 후보자
description: 이 항목에서는 Dynamics 365 Human Resources의 채용할 후보자 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: ef76a84c8a4edd1d209b976fc4c65a16cd020e96
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452410"
---
# <a name="candidate-to-hire"></a>채용할 후보자


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 채용할 후보자 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmcandidatetohireentity

## <a name="description"></a>설명

이 엔터티는 Dynamics 365 Human Resources에서 근로자를 만드는 데 사용되는 후보자 세부 정보를 제공합니다. 모든 후보자 레코드를 읽고 내부 및 외부 후보자 레코드를 생성하는 데 사용하여 새 후보자의 개인 세부 정보를 생성할 수 있습니다.

시스템에서 새 개인 레코드가 될 외부 후보자 레코드를 생성할 때 새 후보 레코드를 게시하는 당사자(개인) 번호를 정의하면 안 됩니다. 새 후보자 레코드를 사용하여 새 개인 엔터티 레코드가 생성됩니다.

내부 후보자 레코드(이미 회사에 직원 레코드가 있는 직위의 후보자)를 생성할 때는 새 개인 레코드를 만들기 위한 개인 정보(예: 이름, 성별 또는 생년월일)를 정의하는 대신 후보자 레코드의 mshr_partynumber 속성에 이미 개인에 대해 존재하는 레코드의 당사자(개인) 번호를 정의합니다.

## <a name="json-representation"></a>JSON 표현

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **채용할 후보자 엔터티 ID**<br>mshr_hcmcandidatetohireentityid<br>GUID | 읽기 전용<br>필수<br>시스템 생성 | 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **후보자 ID**<br>mshr_candidateid<br>문자열 | 읽기 전용<br>필수<br>시스템 생성 | 엔터티의 고유 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>문자열 | 읽기 전용<br>필수 | 후보자 개인 레코드의 당사자(개인) 번호. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>GUID | 읽기 전용<br>필수<br>외래 키: mshr_direpersonentity의 mshr_dirpersonentityid | 후보자의 당사자(개인) 레코드에 대한 시스템 생성 고유 식별자. |
| **당사자 유형**<br>mshr_partytype<br>mshr_dirpartytype 옵션 집합 | 읽기 전용<br>필수 | mshr_dirpartytype 옵션 집합에 정의된 레코드의 당사자 유형. 이 엔터티의 유형은 항상 "개인"입니다. |
| **모집 요청 ID**<br>mshr_recruitingrequestid<br>문자열 | 한 번 쓰기<br>옵션 | 이 후보자가 수행하는 모집 요청을 참조합니다. |
| **모집 요청 ID 값**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | 읽기/쓰기<br>옵션<br>외래 키: mshr_hcmrecruitingrequestentity의 mshr_hcmrecruitingrequestentityid | 후보자가 수행하는 채용 요청에 대한 시스템 생성 고유 식별자. |
| **직책 ID**<br>mshr_positionid<br>문자열 | 읽기/쓰기<br>옵션 | 후보자를 고려 중인 직위의 ID. |
| **직위 ID 값**<br>_mshr_fk_position_if_value<br>GUID | 읽기 전용<br>옵션<br>외래 키: mshr_hcmpositionv2entity의 mshr_hcmpositionv2entityid | 후보자를 고려 중인 직위에 대한 시스템 생성 식별자. |
| **이름**<br>mshr_firstname<br>문자열 | 읽기/쓰기<br>필수 | 후보자 이름. |
| **중간 이름**<br>mshr_middlename<br>문자열 | 읽기/쓰기<br>옵션 | 후보자 중간 이름. |
| **성 접두사**<br>mshr_lastnameprefix<br>문자열 | 읽기/쓰기<br>옵션 | 후보자 성 접두사. |
| **성**<br>mshr_lastname<br>문자열 | 읽기/쓰기<br>옵션 | 후보자 성. |
| **성별**<br>mshr_gender<br>mshr_hcmpersongender 옵션 집합 | 읽기/쓰기<br>옵션 | 후보자의 성별. |
| **생년월일**<br>mshr_birthdate<br>날짜/시간 | 읽기/쓰기<br>옵션 | 후보자의 생년월일. |
| **시민권 국가 번호**<br>mshr_citizenshipcountrycode<br>문자열 | 읽기/쓰기<br>옵션 | 후보자가 시민권을 가지고 있는 국가를 지정합니다. 유효한 국가 번호는 mshr_logisticaddresscountryregionentity에 있습니다. |
| **재향 군인 신분 ID**<br>mshr_veteranstatusid<br>문자열 | 읽기/쓰기<br>옵션 | 후보자의 재향 군인 신분을 나타냅니다. |
| **재향 군인 신분 ID 값**<br>_mshr_fk_veteranstatus_id_value<br>GUID | 읽기 전용<br>옵션<br>외래 키: mshr_hcmveteranstatusentity의 mshr_hcmveteranstatusentityid | 재향 군인 신분 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **병역 복무 시작 날짜**<br>mshr_militaryservicestartdate<br>날짜/시간 | 읽기/쓰기<br>옵션 | 후보자의 병영 복무 시작 날짜. |
| **병역 복무 종료 날짜**<br>mshr_militaryserviceenddate<br>날짜/시간 | 읽기/쓰기<br>옵션 | 후보자의 병영 복무 종료 날짜. |
| **장애가 있는 베테랑**<br>mshr_isdisabledveteran<br>mshr_noyes 옵션 집합 | 읽기/쓰기<br>옵션 | 후보자의 재향 군인 신분이 비활성화되었는지 나타냅니다. |
| **가용성 날짜**<br>mshr_availabilitydate<br>날짜/시간 | 읽기/쓰기<br>옵션 | 후보자가 일할 수 있는 가장 빠른 날짜. |
| **이전할 의향이 있음**<br>mshr_iswillingtorelocate<br>mshr_noyes 옵션 집합 | 읽기/쓰기<br>옵션 | 후보자가 해당 직위를 위해 이전할 의향이 있는지 여부를 나타냅니다. |
| **코멘트**<br>mshr_comments<br>문자열 | 읽기/쓰기<br>옵션 | 모집 담당자 또는 채용 관리자가 사용할 설명. |
| **지원 통합 결과**<br>mshr_applcantintegrationresult<br>mshr_applicantintegrationresult 옵션 집합 | 읽기/쓰기<br>필수 | 통합에 관한 채용 프로세스에서 후보자의 상태. |
| **채용하지 않은 이유 코드 ID**<br>mshr_donothirereasoncodeid<br>문자열 | 읽기/쓰기<br>옵션 | 상태(지원 통합 결과)가 "채용되지 않음"으로 설정된 경우 선택적으로 제공되는 이유 코드. |
| **이유 코드 ID 값**<br>_mshr_fk_reasoncode_id_value<br>GUID | 읽기 전용<br>옵션<br>외래 키: mshr_hcmreasoncodeentity 엔터티의 mshr_hcmreasoncodeentityid | **채용하지 않음** 이유 코드에 대한 시스템 생성 고유 식별자. |
| **데이터 영역 ID**<br>mshr_dataareaid<br>문자열 | 읽기/쓰기<br>옵션 |  법인(회사)을 지정합니다. |
| **데이터 영역 ID 값**<br>_mshr_dataareaid_id_value<br>GUID | 읽기 전용<br>옵션<br>외래 키: cdm_company 엔터티의 cdm_companyid | 법인(회사)을 식별하는 시스템 생성 GUID 값. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
