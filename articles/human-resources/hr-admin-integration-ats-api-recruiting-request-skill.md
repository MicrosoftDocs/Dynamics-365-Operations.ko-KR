---
title: 모집 요청 기술
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 기술 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 245b9a1ff4f140b9288b79c70820204f3082568b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452473"
---
# <a name="recruiting-request-skill"></a>모집 요청 기술


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 기술 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>설명

모집 요청에 대한 기술 요구 사항을 나타냅니다.

### <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **모집 요청 기술 엔터티 ID**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | 읽기 전용<br>필수 | **모집 요청 기술** 레코드에 대한 시스템 생성 고유 식별자. |
| **모집 요청 ID**<br>mshr_recruitingrequestid<br>*문자열* | 한 번 쓰기<br>필수 | 연결된 모집 요청에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **모집 요청 ID 값**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | 읽기 전용<br>필수<br> 외래 키: mshr_hcmrecruitingrequestentity 엔터티의 mshr_hcmrecruitingrequestentityid | 연결된 모집 요청에 대한 시스템 생성 고유 식별자. |
| **기술 ID**<br>mshr_skillid<br>*문자열*<br> | 한 번 쓰기<br>필수 | 필요한 기술에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **기술 ID 값**<br>_mshr_fk_skill_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmskillentity 엔터티의 mshr_hcmskillentityid | 필요한 기술에 대한 시스템 생성 고유 식별자. |
| **등급 수준 ID**<br>mshr_ratinglevelid<br>*문자열* | 한 번 쓰기<br>옵션 | 기술에 할당된 등급 모델을 기반으로 직무에 선택한 필수 기술 수준 값. |
| **등급 수준 ID 값**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmratinglevelentity 엔터티의 mshr_hcmratinglevelentityid | 수준에 대한 시스템 생성 고유 식별자. |
| **기술 설명.**<br>mshr_skilldescription<br>*문자열* | 읽기 전용<br>필수 | 기술 설명. |
| **등급 수준 설명**<br>mshr_ratingleveldescription<br>*문자열* | 읽기 전용<br>옵션 | 선택된 기술 수준에 대한 설명. |
| **데이터 영역 ID**<br>mshr_dataareaid<br>*문자열* | 읽기/쓰기<br>옵션 | 법인(회사)을 지정합니다. |
| **데이터 영역 ID 값**<br>_mshr_dataareaid_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: cdm_company 엔터티의 cdm_companyid | 법인(회사)을 식별하는 시스템 생성 GUID 값. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 레코드를 고유하게 식별하는 다른 방법으로 모집 요청 값, 기술 ID를 연결합니다. |
| **등급 모델 ID**<br>mshr_ratingmodelid<br>*문자열* | 읽기-쓰기<br>필수 | 기술을 평가하는 데 사용되는 등급 모델. |
| **등급 모델 ID 값**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmratingmodelentity 엔터티의 mshr_hcmratingmodelentityid | 기술을 평가하는 데 사용되는 평가 모델의 시스템 생성 고유 식별자. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
