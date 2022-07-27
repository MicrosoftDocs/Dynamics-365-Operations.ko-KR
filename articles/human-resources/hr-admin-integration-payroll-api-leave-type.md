---
title: 휴가 유형
description: 이 항목에서는 Dynamics 365 Human Resources의 휴가 유형 엔터티에 대한 세부 정보와 예제 쿼리를 제공합니다.
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
ms.openlocfilehash: dced58e6e9f6c20578e4582e4cf39162622713e7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452596"
---
# <a name="leave-type"></a>휴가 유형


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 휴가 유형 엔터티에 관해 설명합니다.

### <a name="description"></a>설명

이 엔터티는 주어진 휴가 유형에 대한 정보를 제공합니다.

실제 이름: mshr_essleavetypeentity.

## <a name="properties"></a>속성

| 속성</br>**실제 이름**</br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **휴가 유형 ID**</br>mshr_leavetypeid</br>*문자열* | 읽기 전용 | 휴가 유형 ID. |
| **설명**</br>mshr_description</br>*문자열* | 읽기 전용 | 휴가 유형에 대한 설명. |
| **카테고리**</br>mshr_category</br>*mshr_LeaveTypeCategory 옵션 집합* | 읽기 전용 | 휴가 유형 범주. |
| **사유 코드 필수**</br>mshr_isreasoncoderequired</br>*mshr_NoYes 옵션 집합* | 읽기 전용 | 휴가 유형에 사유 코드가 필요한지 정의합니다. |
| **휴가 단일성**</br>mshr_leaveamountunit</br>*mshr_LeaveAmountUnit 옵션 집합* | 읽기 전용 | 이 휴가 유형의 단일성. |
| **반일 활성화**</br>mshr_enablehalfdaydefinition</br>*mshr_NoYes 옵션 집합* | 휴가 유형으로 반일을 사용할 수 있는지 정의합니다. |
| **데이터 영역 ID**</br>mshr_dataareaid_id</br>*문자열* | 읽기 전용 | 법인(회사)을 지정합니다. |
| **휴가 유형 엔터티**</br>mshr_essleavetypeentityid</br>*GUID* | 시스템 생성 | 휴가 유형을 고유하게 식별하기 위한 시스템 생성 GUID 값. |

## <a name="example-query"></a>예제 쿼리

**요청**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**응답**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
