---
title: 휴가 잔량
description: 이 항목에서는 Dynamics 365 Human Resources의 휴가 잔량 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d26d9624ae8d99b208f77d12137262983499c51
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452068"
---
# <a name="leave-balance"></a>휴가 잔량


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 휴가 잔량 엔터티에 관해 설명합니다.

### <a name="description"></a>설명

이 엔터티는 지정된 직원의 휴가 유형별 휴가 잔량을 알려줍니다.

실제 이름: mshr_essleavebalanceentities.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **인사 번호**</br>mshr_personnelnumber</br>*문자열* | 읽기 전용 | 직원의 고유한 인사 번호. |
| **현재 잔량**</br>mshr_balanceavailable</br>*십진수* | 읽기 전용 | 직원의 현재 잔량. |
| **형식**</br>mshr_balanceavailable</br>*문자열* | 읽기 전용 | 휴가 유형 ID. |
| **적립 비율**</br>mshr_accrualratedescription</br> | 읽기 전용 | 적립 비율. |
| **마지막 이월 분량**</br>mshr_lastcarryforwardamount</br>*십진수* | 읽기 전용 | 마지막 이월 분량. |
| **올해 사용**</br>mshr_takenthisyear</br>*십진수* | 읽기 전용 | 올해 사용한 휴가 분량. |
| **올해 총계**</br>mshr_totalthisyear</br>*십진수* | 읽기 전용 | 올해의 총 휴가. |
| **데이터 영역 ID**</br>mshr_dataareaid_id</br>*문자열* | 읽기 전용 | 법인(회사)을 지정합니다. |
| **기본 필드**</br>mshr_primaryfield</br>*GUID* | 읽기 전용</br>시스템 생성 | |
| **휴가 유형 ID**</br>_mshr_fk_leavetype_id_value</br>*GUID* | 읽기 전용</br>외래 키: mshr_essleavetypeentity 엔터티의 mshr_essleavetypeentityid  | 휴가 유형 ID |
| **휴가 잔량 엔터티**</br>mshr_essleavebalanceentityid</br>*GUID* | 시스템 생성 | 잔량을 고유하게 식별하기 위한 시스템 생성 GUID 값. |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**응답**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
