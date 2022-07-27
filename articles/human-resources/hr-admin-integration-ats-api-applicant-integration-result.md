---
title: 지원자 통합 결과
description: 이 항목에서는 Dynamics 365 Human Resources의 지원자 통합 결과 옵션 집합에 관해 설명합니다.
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
ms.openlocfilehash: 425fc78edc933b79879c330284ef911c6fd4fd1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452230"
---
# <a name="applicant-integration-result"></a>지원자 통합 결과


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 지원자 통합 결과 옵션 집합에 관해 설명합니다.

실제 이름: mshr_hcmapplicantintegrationresult

이 열거는 후보 레코드의 상태를 제공합니다.

| 값 | 레이블 | 설명 |
| --- | --- | --- |
| 200000000 | 처리되지 않음 | 후보자가 아직 고려 중입니다. |
| 200000001 | 채용 | 후보자가 채용되었습니다. |
| 200000002 | 채용되지 않음 | 후보자를 채용하지 않기로 했습니다. |
| 200000003 | 탈락 | 후보자가 고려 대상에서 제외되었습니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
