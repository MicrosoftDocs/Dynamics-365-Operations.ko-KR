---
title: 자격증 유형
description: 이 항목에서는 Dynamics 365 Human Resources의 자격증 유형 엔터티에 관해 설명합니다.
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
ms.openlocfilehash: 3d01c7f01657af1501aed14f63dfb2cfbc133f8b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452320"
---
# <a name="certificate-type"></a>자격증 유형


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 자격증 유형 엔터티에 관해 설명합니다.

실제 이름: mshr_hcmcertificatetypeentity

## <a name="description"></a>설명

이 엔터티는 Human Resources의 전문 자격증 유형 목록 설정을 정의합니다. 엔터티는 한 법인(회사)으로 한정되지 않습니다.

## <a name="json-representation"></a>JSON 표현

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>속성

| 속성<br>**실제 이름**<br>**_형식_** | 사용 | 설명 |
| --- | --- | --- |
| **자격증 유형 엔터티 ID**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | 읽기 전용<br>필수 
시스템 생성 | 자격증 유형에 대한 고유 기본 식별자. |
| **자격증 유형**<br>mshr_certificatetype<br>*문자열* | 읽기/쓰기<br>필수 | 자격증 유형에 대한 사용자가 읽을 수 있는 고유 식별자. |
| **설명**<br>mshr_description<br>*문자열* | 읽기/쓰기<br>필수 | 자격증 유형에 대한 설명. |
| **갱신 필요**<br>mshr_requirerenewal<br>*mshr_noyes 옵션 집합* | 읽기/쓰기<br>옵션 | 자격증 갱신이 필요한지 여부. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
