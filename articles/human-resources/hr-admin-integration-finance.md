---
title: Finance와의 통합 구성
description: 이 항목에서는 Dynamics 365 Human Resources 및 Dynamics 365 Finance 간의 통합에 관해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0a2c5dd0ce97f33f5f8b65c801fbc15dfc65e8d4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452089"
---
# <a name="configure-integration-with-finance"></a>Finance와의 통합 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Dynamics 365 Human Resources를 Dynamics 365 Finance와 통합하려면 [데이터 통합자](/powerapps/administrator/data-integrator)에서 Human Resources to Finance 템플릿을 사용할 수 있습니다. Human Resources to Finance 템플릿을 사용하면 직무, 직위, 근로자에 대한 데이터 흐름을 활성화할 수 있습니다. 이 템플릿을 사용하면 데이터가 Human Resources에서 Finance로 이동할 수 있지만 Finance에서 Human Resources로 이동하는 것은 허용되지 않습니다.

![Human Resources to Finance 통합 흐름.](./media/hr-admin-integration-finance-flow.png)

Human Resources to Finance 솔루션은 다음과 같은 유형의 데이터 동기화를 제공합니다.

- Human Resources에 직무를 유지하고 Human Resources에서 Finance로 동기화
- Human Resources에 직위 및 직위 할당을 유지하고 Human Resources에서 Finance로 동기화
- Human Resources에 고용을 유지하고 Human Resources에서 Finance로 동기화
- Human Resources에 근로자 및 근로자 주소를 유지하고 Human Resources에서 Finance로 동기화

## <a name="system-requirements-for-human-resources"></a>Human Resources의 시스템 요구 사항

통합 솔루션에는 다음 버전의 Human Resources 및 Finance가 필요합니다. 

- Dataverse 상의 Dynamics 365 Human Resources
- Dynamics 365 Finance 버전 7.2 이상

## <a name="template-and-tasks"></a>템플릿 및 작업

Human Resources to Finance 템플릿에 액세스하려면 다음을 수행합니다.

1. [Power Apps 관리 센터](https://admin.powerapps.com/)를 엽니다. 

2. **프로젝트** 를 선택하고 오른쪽 상단 모서리의 **새 프로젝트** 를 선택합니다. Finance에 통합하려는 각 법인의 새 프로젝트를 만듭니다.

3. Human Resources에서 Finance로 레코드를 동기화하려면 **Human Resources(Human Resources Dataverse to Finance)** 를 선택합니다.

템플릿은 다음 기본 작업을 사용하여 Human Resources에서 Finance로 레코드를 동기화합니다.

- **직무 기능에서 보상 직무 기능으로**
- **부서에서 운영 단위로**
- **직무 유형에서 보상 직무 유형으로**
- **직무에서 직무로**
- **직무에서 직무 세부 정보로**
- **직위 유형에서 직위 유형으로**
- **직무 직위에서 기본 직위**
- **직무 직위에서 직위 세부 정보**
- **직무 직위에서 직위 기간**
- **직무 직위에서 직위 계층**
- **근로자에서 근로자로**
- **고용에서 고용으로**
- **고용에서 고용 세부 정보로**
- **직위 근로자 할당에서 직위 근로자 할당으로**
- **근로자 주소에서 근로자 우편 주소 V2로**

## <a name="template-mappings"></a>템플릿 매핑

다음 템플릿 매핑 테이블에서 작업 이름에는 각 애플리케이션에서 사용되는 엔터티가 포함됩니다. 원본(Human Resources)는 왼쪽에 있고 대상(Finance)은 오른쪽에 있습니다.

### <a name="job-functions-to-compensation-job-function"></a>직무 기능에서 보상 직무 기능으로

| Dataverse 테이블(원본) | Finance 엔터티(대상) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job Function Name)  | JOBFUNCTIONID (JOBFUNCTIONID)            |
| cdm_description (cdm_description) | DESCRIPTION (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>부서에서 운영 단위로

| Dataverse 테이블(원본)           | Finance 엔터티(대상) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber (cdm_departmentnumber) | OPERATINGUNITNUMBER (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE (OPERATINGUNITTYPE)     |
| cdm_description (cdm_description)           | NAMEALIAS (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>직무 유형에서 보상 직무 유형으로

| Dataverse 테이블(원본)   | Finance 엔터티(대상) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID (JOBTYPEID)                     |
| cdm_description (cdm_description)   | DESCRIPTION (DESCRIPTION)                 |
| cdm_exemptstatus (cdm_exemptstatus) | EXEMPTSTATUS (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>직무에서 직무로

| Dataverse 테이블(원본)                           | Finance 엔터티(대상)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description (cdm_description)                           | DESCRIPTION (DESCRIPTION)                           |
| cdm_jobdescription (cdm_jobdescription)                     | JOBDESCRIPTION (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>직무에서 직무 세부 정보로

| Dataverse 테이블(원본)                             | Finance 엔터티(대상) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name (Job Type (Job Type Name))             | JOBTYPEID (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name (Job Function (Job Function Name)) | FUNCTIONID (FUCNTIONID)                   |
| cdm_validfrom (Valid From)                                    | VALIDFROM (VALIDFROM)                     |
| cdm_validto (Valid To)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent (Default Full-time Equivalent)   | FULLTIMEEQUIVALENT (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>직위 유형에서 직위 유형으로

| Dataverse 테이블(원본)       | Finance 엔터티(대상) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID (POSITIONTYPEID)           |
| cdm_description (cdm_description)       | DESCRIPTION (DESCRIPTION)                 |
| cdm_classification (cdm_classification) | CLASSIFICATION (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>직무 직위에서 기본 직위

| Dataverse 테이블(원본)           | Finance 엔터티(대상) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber (Job Position Number) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>직무 직위에서 직위 세부 정보

| Dataverse 테이블(원본)              | Finance 엔터티(대상)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber (Job Position Number)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name (Job (Name))                                        | JOBID (JOBID)                                    |
| cdm_description (cdm_description)                                        | DESCRIPTION (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber (Department (Department Number)) | DEPARTMENTNUMBER (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name (Position Type (Name))                     | POSITIONTYPEID (POSITIONTYPEID)                 |
| cdm_avaialableforassignment (Available for Assignment)                 | AVAILABLEFORASSIGNMENT (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom (Valid From)                                            | VALIDFROM (VALIDFROM)                           |
| cdm_validto (Valid To)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent (Full-time Equivalent)                           | FULLTIMEEQUIVALENT (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>직무 직위에서 직위 기간

| Dataverse 테이블(원본)             | Finance 엔터티(대상) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber (Job Position Number)   | POSITIONID (POSITIONID)                      |
| Calculated Activation (Calculated Activation) | VALIDFROM (VALIDFROM)                        |
| Calculated Retirement (Calculated Retirement) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>직무 직위에서 직위 계층

| Dataverse 테이블(원본)        | Finance 엔터티(대상) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber (Job Position Number)                                                 | POSITIONID (POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom (Valid From)                                                                  | VALIDFROM (VALIDFROM)                     |
| cdm_validto (Valid To)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>근로자에서 근로자로
| Dataverse 테이블(원본)           | Finance 엔터티(대상)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate (cdm_birthdate)               | BIRTHDATE (BIRTHDATE)                           |
| cdm_gender (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone (cdm_primarytelephone) | PRIMARYCONTACTPHONE (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl (cdm_websiteurl)             | PRIMARYCONTACTURL (PRIMARYCONTACTURL)           |
| cdm_firstname (cdm_firstname)               | FIRSTNAME (FIRSTNAME)                           |
| cdm_middlename (cdm_middlename)             | MIDDLENAME (MIDDLENAME)                         |
| cdm_lastname (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber (cdm_workernumber)         | PERSONNELNUMBER (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE (WORKERTYPE)                         |
| cdm_state (cdm_state)                       | WORKSTATUS (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>고용에서 고용으로

| Dataverse 테이블(원본)                             | Finance 엔터티(대상) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate (cdm_employmentenddate)                 | EMPLOYMENTENDDATE (EMPLOYMENTENDDATE)     |
| cdm_workertype (cdm_workertype)                               | WORKERTYPE (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode (cdm_companyid.cdm_companycode) | LEGALENTITYID (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>고용에서 고용 세부 정보로

| Dataverse 테이블(원본)                             | Finance 엔터티(대상)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate (cdm_employmentenddate)                 | EMPLOYMENTENDDATE (EMPLOYMENTENDDATE)       |
| cdm_validfrom (Valid From)                                    | VALIDFROM (VALIDFROM)                       |
| cdm_validto (Valid To)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate (cdm_workerstartdate)                     | WORKERSTARTDATE (WORKERSTARTDATE)           |
| cdm_lastdateworked (cdm_lastdateworked)                       | LASTDATEWORKED (LASTDATEWORKED)             |
| cdm_transitiondate (cdm_transitiondate)                       | TRANSITIONDATE (TRANSITIONDATE)             |
| cdm_employerunitofnotice (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode (cdm_companyid.cdm_companycode) | LEGALENTITYID (LEGALENTITYID)               |
| cdm_employernoticeamount (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>직위 근로자 할당에서 직위 근로자 할당으로

| Dataverse 테이블(원본)                             | Finance 엔터티(대상)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)           |
| cdm_jobpositionnumber (Job Position Number)                   | POSITIONID (POSITIONID)                        |
| cdm_validfrom (Valid From)                                    | VALIDFROM (VALIDFROM)                       |
| cdm_validto (Valid To)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>근로자 주소에서 근로자 우편 주소 V2로

| Dataverse 테이블(원본)                             | Finance 엔터티(대상)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER (PERSONNELNUMBER)           |
| cdm_addresstype (cdm_addresstype)                             | ADDRESSLOCATIONROLES (ADDRESSLOCATIONROLES) |
| cdm_line1 (cdm_line1)                                         | ADDRESSSTREET (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY (ADDRESSCITY)                   |
| cdm_stateorprovince (cdm_stateorprovince)                     | ADDRESSSTATE (ADDRESSSTATE)                 |
| cdm_postalcode (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion (cdm_countryregion)                         | ADDRESSCOUNTRYREGION (ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber (cdm_addressnumber)                         | ADDRESSLOCATIONID (ADDRESSLOCATIONID)          |
| cdm_ispreferred (cdm_ispreferred)                             | ISPRIMARY (ISPRIMARY)                       |
| cdm_county (cdm_county)                                       | ADDRESSCOUNTYID (ADDRESSCOUNTYID)              |
| cdm_addresstype (cdm_addresstype)                             | ADDRESSDESCRIPTION (ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>통합 고려 사항

Human Resources에서 Finance로의 통합은 ID를 기반으로 레코드를 일치시키려고 시도합니다. 레코드가 일치하는 경우 데이터 통합자는 Finance의 데이터를 Human Resources의 값으로 덮어씁니다. 그러나 논리적으로 서로 다른 레코드이고 각각의 번호 시퀀스를 기반으로 Human Resources 또는 Finance에서 동일한 ID가 생성된 경우 문제가 발생할 수 있습니다.

이 문제는 **인사 번호** 를 사용하여 일치시키는 **근로자** 와 **직위** 에서 발생할 수 있습니다. 직무는 숫자 시퀀스를 사용하지 않습니다. 결과적으로 Human Resources 및 Finance에 동일한 작업 ID가 있는 경우 Human Resources 정보가 Dynamics 365 Finance 정보를 덮어씁니다. 

중복 ID 문제를 방지하려면 [번호 시퀀스](/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)에 접두사를 추가하거나 다른 시스템의 범위를 벗어나는 번호 시퀀스의 시작 번호를 설정할 수 있습니다. 

근로자 주소에 사용된 위치 ID가 숫자 시퀀스의 일부가 아닙니다. Human Resources에서 Finance로 근로자 주소를 통합할 때 근로자 주소가 Finance에 이미 있는 경우 중복 주소 레코드가 생성될 수 있습니다. 

다음 그림은 데이터 통합자에서 템플릿 매핑의 예를 보여줍니다. 

![템플릿 매핑.](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
