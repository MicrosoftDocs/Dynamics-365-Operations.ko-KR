---
title: 심사 유형
description: 이 항목에서는 Dynamics 365 Human Resources의 심사 유형 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: bcbf22aac78f1ff96edb7dd927721453f8d10fa5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452392"
---
# <a name="screening-types"></a>심사 유형


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 심사 유형 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmscreeningtypeentity

## <a name="description"></a>설명

이 엔터티는 고용 전 및 지속적인 직원 심사 프로세스를 위해 회사에서 설정한 심사 유형을 나타냅니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **심사 유형 엔터티 ID**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | 읽기 전용<br>필수<br>시스템 생성 | 심사 유형 레코드의 고유한 기본 식별자. |
| **심사 유형 ID**<br>mshr_screeningtypeid<br>*문자열* | 읽기/쓰기<br>필수 | 심사 유형에 대한 사용자 정의 고유 식별자. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 심사 유형에 대한 설명. |
| **빈도 단위**<br>mshr_frequencyunit<br>*mshr_hcmfrequencyunit 옵션 집합* | 읽기/쓰기<br>필수 | 할당된 개인에 대해 심사를 완료해야 하는 빈도를 나타냅니다. |
| **생성 날짜**<br>mshr_generatefrom<br>*mshr_hcmfrequencygeneratefrom 옵션 집합* | 읽기-쓰기<br>필수 | 빈도 값이 "한 번만" 이외의 값이면 생성 날짜 값으로 다음 심사 이벤트를 계산할 날짜를 결정해야 합니다. |
| **빈도 간격**<br>mshr_frequencyinterval<br>*정수* | 읽기-쓰기<br>필수 | 빈도 값이 "한 번만" 이외의 값이면 각 심사 이벤트 간의 시간 단위 간격을 정의해야 합니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
