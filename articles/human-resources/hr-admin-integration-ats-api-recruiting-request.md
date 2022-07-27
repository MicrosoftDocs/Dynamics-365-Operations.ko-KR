---
title: 모집 요청
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: a1f160d828c8fe5babb96d39afd911052767f67b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452470"
---
# <a name="recruiting-request"></a>모집 요청


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequestentity

### <a name="description"></a>설명

채용 요청을 나타냅니다.

### <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **모집 요청 ID**<br>mshr_recruitingrequestid<br>*문자열* | 읽기 전용<br>필수<br>시스템 생성 | HR 애플리케이션에 표시된 요청에 대한 사용자가 읽을 수 있는 고유 식별자. 숫자 시퀀스. |
| **모집 요청 엔터티 ID**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | 읽기 전용<br>필수<br>시스템 생성 | 모집 요청을 고유하게 식별하기 위한 시스템 생성 GUID 값. |
| **데이터 영역 ID**<br>mshr_dataareaid<br>*문자열* | 읽기/쓰기<br>옵션<br> | 모집 요청에 대한 법인(회사)을 지정합니다. |
| **데이터 영역 ID 값**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | 읽기 전용<br>옵션<br>외래 키: cdm_company 엔터티의 cdm_companyid | 모집 요청에 대한 법인(회사)을 식별하는 시스템 생성 GUID 값. |
| **채용 관리자 인사 번호**<br>mshr_hiringmanagerpersonnelnumber<br>*문자열* | 읽기/쓰기<br>옵션 | 이 채용 요청을 담당하는 채용 관리자의 인사 번호. |
| **채용 관리자 ID 값**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmworkerbaseentity 엔터티의 mshr_hcmworkerbaseentityid | 모집 요청을 담당하는 관리자를 식별하기 위한 시스템 생성 GUID 값. |
| **모집 담당자 번호**<br>mshr_recruiterpartynumber<br>*문자열* | 읽기/쓰기<br>옵션 | 요청을 담당하는 모집 담당자의 개인(당사자) 번호. |
| **모집 담당자 ID 값**<br>_mshr_fk_recruiter_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_dirpersonentity 엔터티의 mshr_dirpersonentityid | 모집 요청을 담당하는 모집 담당자를 식별하기 위한 시스템 생성 GUID 값. |
| **상태**<br>mshr_status<br>*RecruitingRequestStatus* 옵션 집합 | 읽기/쓰기<br>필수<br> | 모집 요청의 상태를 나타냅니다. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 요청을 나타냅니다. |
| **모집 요청 위치 ID**<br>mshr_recruitingrequestlocationid<br>*문자열* | 읽기/쓰기<br>옵션 | 이 요청에 연결된 근무 위치에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **모집 위치 ID 값**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmrecruitingrequestlocationentity 엔터티의 mshr_hcmrecruitingrequestlocationentityid | 요청에 대해 선택된 모집 요청 위치를 식별하기 위한 시스템 생성 GUID 값. |
| **코멘트**<br>mshr_comments<br>*문자열* | 읽기/쓰기<br>옵션 | 요청에 대한 채용 관리자 및 모집 담당자의 의견. |
| **직무 ID**<br>mshr_jobid<br>*문자열* | 한 번 쓰기<br>필수 |   이 요청에 연결된 모든 직위에 공유되는 직무에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **직무 ID 값**<br>_mshr_fk_job_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmjobentity 엔터티의 mshr_hcmjobentityid | 모집 요청에 연결된 모든 직위에 공유되는 직무에 대한 시스템 생성 고유 식별자. |
| **직함 ID**<br>mshr_titleid<br>*문자열* | 읽기 전용<br>필수 | 이 요청에 연결된 직함에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **직함 ID 값**<br>_mshr_fk_title_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmtitleentity 엔터티의 mshr_hcmtitleid | 모집 요청에 선택된 직함에 대한 시스템 생성 고유 식별자. |
| **직무 기능 ID**<br>mshr_jobfunctionid<br>*문자열* | 읽기 전용<br>필수<br>외래 키: mshr_hcmjobfunctionentity 엔터티의 mshr_jobfunctionid | 이 요청에 연결된 직무 기능에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **기본 정규직 상응**<br>mshr_defaultfulltimeequivalency<br>*배정도* | 읽기 전용<br>필수 | 직무의 정규직 상응 값이며 1.0은 정규직 근로자를 나타냅니다. |
| **규제 직종**<br>mshr_regulatoryjobcategory<br>*RegulatoryJobCategory* 옵션 집합 | 읽기 전용<br>옵션 | 해당 직무에 대해 선택된 직무 기능의 EEO 직종. 유효한 값은 HcmRegulatoryJobCatetory(mshr_hcmregulatoryjobcategory) 옵션 집합에 포함되어 있습니다. |
| **직무 유형 ID**<br>mshr_jobtypeid<br>*문자열* | 읽기 전용<br>옵션 | 직위와 관련된 직무 유형. 작업 유형은 mshr_hcmjobtypeentity 엔터티에서 사용할 수 있는 사용자 정의 값입니다. |
| **직무 유형 ID 값**<br>_mshr_fk_jobtype_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmjobtypenentity 엔터티의 mshr_hcmjobtypeentityid | 모집 요청에 연결된 직무와 연결된 직무 유형에 대한 시스템 생성 고유 식별자. |
| **면제 상태**<br>mshr_exemptstatus<br>*JobExemptStatus* 옵션 집합 | 읽기 전용<br>옵션 | 직무 유형에 따른 FLSA 면제 상태. |
| **예상 시작 날짜**<br>mshr_estimatedstartdate<br>*날짜* | 읽기/쓰기<br>필수 | 후보자가 근무를 시작할 예정 날짜. |
| **외부 설명**<br>mshr_externaldescription<br>*문자열* | 읽기/쓰기<br>옵션 | 직무/직위에 대한 후보자 대면 설명. | 
| **보상 하한 임계값**<br>mshr_compensationlowthreshold<br>*배정도* | 읽기/쓰기<br>옵션 | 보상 수준의 하한. |
| **보상 제어 지점**<br>mshr_compensationcontrolpoint<br>*배정도* | 읽기/쓰기<br>옵션 | 보상 수준에 대한 제어점. |
| **보상 상한 임계값**<br>mshr_compensationhighthreshold<br>*배정도* | 읽기/쓰기<br>옵션 | 보상 수준의 상한. |
| **보상 수준**<br>mshr_compensationlevelid<br>*문자열* | 읽기/쓰기<br>옵션 | 직무의 보상 수준. 직무의 여러 보상 수준을 설정할 수 있습니다. 이 특성은 이 요청에 대해 선택된 직무 보상 수준을 나타냅니다. |
| **직무 보상 ID**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | 읽기 전용<br>옵션<br>외래 키: mshr_hcmjobcompensationentity 엔터티의 mshr_hcmjobcompensationentityid | 모집 요청의 직무와 연결된 보상 수준에 대한 시스템 생성 고유 식별자. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
