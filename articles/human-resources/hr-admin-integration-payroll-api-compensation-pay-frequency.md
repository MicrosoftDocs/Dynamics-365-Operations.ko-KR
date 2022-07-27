---
title: 보상 지급 빈도
description: 이 항목에서는 Dynamics 365 Human Resources의 보상 지급 빈도 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 171b7fb7b361bd1fe2e7e637cd555c88a81a8bcf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452203"
---
# <a name="compensation-pay-frequency"></a>보상 지급 빈도


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 보상 지급 빈도 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpayrateconversionentity.

### <a name="description"></a>설명

이 엔터티는 주어진 보상 지급 빈도의 지급 비율 환산에 대한 정보를 제공합니다.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **연봉 비율 환산**</br>mshr_annualconversionfactor</br>*십진수* | 읽기 전용 | 지불 빈도에 대한 연간 환산 계수. |
| **설명**</br>mshr_description</br>*문자열* | 읽기 전용 | 환산 비율에 대한 설명. |
| **시급 비율 환산**</br>mshr_hourlyconversionfactor</br>*십진수* | 읽기 전용 | 지불 빈도에 대한 시급 환산 계수. |
| **월급 비율 환산**</br>mshr_monthlyconversionfactor</br>*십진수* | 읽기 전용 | 지불 빈도에 대한 월급 환산 계수. |
| **지급 비율 환산**</br>mshr_payrateconversion</br>*문자열* | 읽기 전용 | 환산 비율을 식별하는 고유한 문자열. |
| **기간**</br>mshr_period</br>*기간 옵션 집합* | 읽기 전용 | 지정된 지급 비율 환산의 주요 기간. |
| **주급 비율 환산**</br>mshr_weeklyconversionfactor</br>*십진수* | 읽기 전용 | 지불 빈도에 대한 주급 환산 계수. |
| **데이터 영역 ID**</br>mshr_dataareaid</br>*문자열* | 읽기 전용 | 법인 변경(회사). |
| **보상 지급 빈도 엔터티 ID**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | 시스템 생성 | 레코드를 고유하게 식별하기 위해 시스템에서 생성한 GUID(Globally Unique Identifier) 값. |

## <a name="example-query-for-payroll-employee"></a>직원 급여 예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**응답**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
