---
title: 개인 심사
description: 이 항목에서는 Dynamics 365 Human Resources의 개인 심사 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 5129348f928fd709a5fabe73917522799a2d47e0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452221"
---
# <a name="person-screening"></a>개인 심사


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 개인 심사 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmpersonscreeningentity

## <a name="description"></a>설명

이 엔터티는 후보자가 합격했거나 채용을 위해 합격해야 하는 심사를 나타냅니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **개인 심사 엔터티 ID**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | 읽기 전용<br>필수<br>시스템 생성 | 개인 심사 레코드의 고유한 기본 식별자. |
| **당사자 번호**<br>mshr_partynumber<br>*문자열* | 읽기/쓰기<br>필수 | 후보자의 당사자(개인) 번호. |
| **개인 ID 값**<br>_mshr_fk_person_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_dirpersonentity의 mshr_dirpersonentityid | 당사자(개인) 엔터티 레코드에 대한 시스템 생성 고유 식별자. |
| **심사 유형 ID**<br>mshr_screeningtypeid<br>*문자열* | 읽기/쓰기<br>필수<br>외래 키: ScreeningType | Human Resources에 정의된 심사 유형의 식별자. |
| **심사 유형 ID 값**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmscreeningtypeentity의 mshr_hcmscreeningtypeentityid | 연결된 엔터티의 심사 유형 레코드에 대한 시스템 생성 식별자. |
| **요구 날짜**<br>mshr_requiredby<br>*날짜/시간* | 읽기/쓰기<br>옵션 | 심사를 완료해야 하는 날짜. |
| **상태**<br>mshr_status<br>*mshr_hcmcompletionstatus 옵션 집합*<br>읽기/쓰기<br>필수 | 심사를 위한 후보자의 상태를 제공합니다. |
| **완료된 날짜**<br>mshr_completeddate<br>*날짜/시간* | 읽기/쓰기<br>옵션 | 심사가 완료된 날짜. |
| **메모**<br>mshr_note<br>*문자열* | 읽기/쓰기<br>옵션 | 채용 관리자 및 모집 담당자가 사용하기 위한 참고 사항. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
