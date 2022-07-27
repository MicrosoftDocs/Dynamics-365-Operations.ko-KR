---
title: 등급 수준
description: 이 항목에서는 Dynamics 365 Human Resources의 등급 수준 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: a821e3cd90e85571da4a09f5dd564beb2de35989
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452476"
---
# <a name="rating-level"></a>등급 수준


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 등급 수준 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmratinglevelentity

## <a name="description"></a>설명

이 엔터티는 기술의 사용 가능한 등급 수준을 제공합니다. 등급 수준은 모든 법인에 적용됩니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **등급 수준 엔터티 ID**<br>mshr_hcmratinglevelentityid<br>*GUID* | 읽기 전용<br>필수<br>시스템 생성 | 수준에 대한 시스템 생성 고유 식별자. |
| **등급 수준 ID**<br>mshr_ratinglevelid<br>*문자열* | 읽기/쓰기<br>필수 | 수준에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **등급 모델 ID**<br>mshr_ratingmodelid<br>*문자열* | 읽기/쓰기<br>필수 | 등급 수준이 속한 등급 모델. |
| **등급 모델 엔터티 ID**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | 읽기 전용<br>필수<br>외래 키: mshr_hcmratingmodelentity의 mshr_hcmratingmodelentityid | 등급 수준이 속한 등급 모델에 대한 시스템 생성 식별자. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 등급 수준에 대한 설명. |
| **계수**<br>mshr_factor<br>*정수* | 읽기/쓰기<br>필수 | 등급 수준에 대한 계수. 계수는 등급 수준 수가 다른 항목을 비교할 때 점수를 정규화하는 데 사용됩니다. 값은 0에서 9 사이의 정수여야 합니다. |
| **메모**<br>mshr_note<br>*문자열* | 읽기/쓰기<br>옵션 | 등급 수준과 관련된 모든 메모. |
| **기본 필드**<br>mshr_primaryfield<br>*문자열* | 읽기 전용<br>필수 | 엔터티 레코드의 식별자로 사용될 필드. 등급 수준 ID와 등급 모델 ID의 조합. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
