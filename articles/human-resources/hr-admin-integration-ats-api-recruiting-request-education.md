---
title: 모집 요청 교육
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 교육 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 9fe1a99debac3dc784ba82b711143337d4077be0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452311"
---
# <a name="recruiting-request-education"></a>모집 요청 교육


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 교육 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>설명

모집 요청에 대한 교육 요구 사항을 나타냅니다.

### <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **모집 요청 교육 엔터티 ID**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | 읽기 전용<br>필수 | 모집 요청 교육 레코드에 대한 시스템 생성 고유 식별자. |
| **모집 요청 ID**<br>mshr_recruitingrequestid<br>*문자열* | 한 번 쓰기<br>필수 | 관련 모집 요청에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **모집 요청 ID 값**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmrecruitingrequestentity의 mshr_hcmrecruitingrequestentityid | 관련 모집 요청에 대한 시스템 생성 고유 식별자. |
| **교육 수준 ID**<br>mshr_educationlevelid<br>*문자열* | 한 번 쓰기<br>필수 | 필요한 교육 수준. |
| **교육 수준 ID 값**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmeducationlevelentity의 mshr_hcmeducationlevelentityid | 필요한 교육 수준에 대한 시스템 생성 고유 식별자. |
| **교육 수준 설명**<br>mshr_educationleveldescription<br>*문자열* | 읽기 전용<br>필수 | 스킬에 필요한 수준에 대한 설명. |
| **교육 학과 ID**<br>mshr_educationdisciplinedescription<br>*문자열* | 한 번 쓰기<br>필수 | 교육 학과 영역. |
| **교육 학과 ID 값**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmeducationdisciplineentity 엔터티의 mshr_hcmeducationdisciplineentityid | 교육 학과 영역에 대한 시스템 생성 고유 식별자. |
| **교육 학과 설명**<br>mshr_educationdisciplinedescription<br>문자열 | 읽기 전용<br>필수 | 교육 학과 영역에 대한 설명. |
| **데이터 영역 ID**<br>mshr_dataareaid<br>*문자열* | 읽기/쓰기<br>옵션 | 법인(회사)을 지정합니다.|
| **데이터 영역 ID 값**<br>_mshr_dataareaid_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: cdm_company 엔터티의 cdm_companyid | 법인(회사)을 식별하는 시스템 생성 GUID 값. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 레코드를 고유하게 식별하는 또 다른 방법으로 모집 요청 값, 교육 수준 ID 및 교육 학과 ID를 연결합니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
