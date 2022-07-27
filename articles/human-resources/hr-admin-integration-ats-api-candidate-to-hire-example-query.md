---
title: 채용할 후보자에 대한 예제 쿼리
description: 이 항목에서는 Dynamics 365 Human Resources의 채용할 후보자 엔터티에 대한 예제 쿼리를 제공합니다.
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
ms.openlocfilehash: edb8687b9dae0afc1bc15a3a5c197e14e7e8cf1e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452536"
---
# <a name="example-query-for-candidate-to-hire"></a>채용할 후보자에 대한 예제 쿼리


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 채용할 후보자 엔터티에 대한 예제 쿼리를 제공합니다.

이 항목에서는 *깊은 삽입* 을 사용하여 단일 API 작업으로 새 후보자 레코드의 모든 세부 정보를 생성하는 방법을 보여주는 예를 제공합니다. 심증 삽입에 대한 자세한 내용은 [하나의 작업으로 관련 엔터티 레코드 만들기](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation)를 참조하세요.

**mshr_hcmcandidatetohireentity** 엔터티는 **mshr_dirpersonentity** 엔터티와의 관계 때문에 고유합니다. **mshr_hcmcandidatetohireentity** 의 많은 속성(예: **mshr_firstname**, **mshr_lastname** 및 **mshr_birthdate**)이 **mshr_dirpersonentity** 레코드에서 파생됩니다. 깊은 삽입을 사용하지 않고 **mshr_hcmcandidatetohireentity** 에 새 후보자 레코드를 게시하면 **mshr_hcmcandidatetohireentity** 레코드에서 직접 이러한 속성의 값을 정의할 수 있습니다. 연결된 **mshr_dirpersonentity** 레코드는 속성에 정의된 값을 사용하여 암시적으로 생성됩니다. 그런 다음 별도의 API 호출로 다른 관련 엔터티 레코드(예: 기술 또는 교육)를 생성할 수 있습니다.

그러나 하나의 작업에서 깊은 삽입으로 모든 관련 엔터티를 만들려면 **mshr_dirpersonentity** 엔터티와 관련된 속성을 작업의 중첩 수준에서 정의해야 합니다.

이 예는 하나의 API 작업에서 깊은 삽입으로 3개의 중첩된 수준에서 후보자 레코드, 관련 개인 레코드, 개인의 기술 및 교육을 생성하는 방법을 보여줍니다.

> [!NOTE]
> 이 예에는 각 API 엔터티의 모든 속성이 포함되어 있지 않습니다. 설명 목적으로 단순화되었습니다.

**요청**

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

**응답**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
