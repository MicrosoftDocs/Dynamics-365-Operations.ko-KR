---
title: 모집 요청 직위
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 직위 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 24ea00c13030d09fb9cda02950ac7b79bfe0d03d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452137"
---
# <a name="recruiting-request-position"></a>모집 요청 직위


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 직위 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>설명

모집 요청으로 충원할 직위를 나타냅니다. 채용 요청에 직위를 추가하는 것은 선택 사항입니다. 직위 속성은 모집 요청의 직위 속성이 직위 마스터 레코드의 직위 속성과 다르지 않아야 하므로 읽기 전용입니다. 속성을 변경해야 하는 경우 모집 요청에 직위를 추가하기 전에 직위 마스터 레코드에서 변경해야 합니다.

### <a name="json-representation"></a>JSON 표현
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **모집 요청 직위 엔터티 ID**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | 읽기 전용<br>필수 |    모집 요청 직위 레코드에 대한 시스템 생성 고유 식별자. |
| **모집 요청 ID**<br>mshr_recruitingrequestid<br>*문자열* | 한 번 쓰기<br>필수 | 모집 요청에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **모집 요청 ID 값**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmrecruitingrequestentity 엔터티의 mshr_hcmrecruitingrequestentityid | 직위가 할당된 모집 요청에 대한 시스템 생성 고유 식별자. |
| **직책 ID**<br>mshr_positionid<br>*문자열* | 한 번 쓰기<br>필수 | 직위에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **직위 ID 값**<br>_mshr_fk_position_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmpositionv2entity 엔터티의 mshr_hcmpositionv2entityid | 직위에 대한 시스템 생성 식별자. |
| **설명**<br>mshr_description<br>*문자열* | 읽기 전용<br>필수 | 직위 설명 |
| **직위 유형 ID**<br>mshr_positiontypeid<br>*문자열* | 읽기 전용<br>옵션 | 이 직위의 직위 유형에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **직위 유형 ID 값**<br>_mshr_fk_positiontype_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmpositiontypeentity 엔터티의 mshr_hcmpositiontypeentityid | 이 직위의 직위 유형에 대한 시스템 생성 고유 식별자. |
| **상태**<br>mshr_status<br>*RecruitingRequestPositionStatus* 옵션 집합 | 읽기/쓰기<br>필수 | 모집 요청에 대한 직위의 상태. |
| **부서 번호**<br>mshr_departmentnumber<br>*문자열* | 읽기 전용<br>옵션<br> | 직위의 부서 번호. |
| **부서 ID 값**<br>_mshr_fk_department_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_omdepartmententity 엔터티의 mshr_omdepartmententityid | 직위의 부서에 대한 시스템 생성 고유 식별자. |
| **보고 대상 직위 ID**<br>mshr_reportstopositionid<br>*문자열* | 읽기 전용<br>필수 | 모집된 직위가 조직 계층에서 보고하는 직위에 대한 사용자가 읽을 수 있는 ID. |
| **보고 대상 직위 ID 값**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmpositionv2entity 엔터티의 mshr_hcmpositionv2entityid | 모집된 직위가 보고하는 직위에 대한 시스템 생성 ID. |
| **보고 대상 인사 번호**<br>mshr_reportstopersonnelnumber<br>*문자열* | 읽기 전용<br>필수 | 채용된 후보자가 보고할 근로자의 근로자 ID. |
| **보고 대상 근로자 ID 값**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmworkerbaseentity 엔터티의 mshr_hcmworkerbaseentityid | 채용된 후보자가 보고할 근로자에 대한 시스템 생성 ID. |
| **재무 차원**<br>mshr_financialdimension<br>*문자열* | 읽기 전용<br>옵션 | 직위에 할당된 재무 차원(예: 비용 센터). 재무 차원은 법인별로 각 직위에 할당됩니다. 차원에 정의된 비용 센터는 mshr_dimattributeomcostcenterentity 엔터티를 통해 액세스할 수 있습니다. |
| **데이터 영역 ID**<br>mshr_dataareaid<br>*문자열* | 읽기/쓰기<br>옵션 | 모집 요청 직위에 대한 법인(회사)을 지정합니다. |
| **데이터 영역 ID 값**<br>_mshr_dataareaid_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: cdm_company 엔터티의 cdm_companyid | 모집 요청 직위에 대한 법인(회사)을 식별하는 시스템 생성 GUID 값. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 레코드를 고유하게 식별하는 다른 방법으로 모집 요청 값, 직위 ID를 연결합니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
