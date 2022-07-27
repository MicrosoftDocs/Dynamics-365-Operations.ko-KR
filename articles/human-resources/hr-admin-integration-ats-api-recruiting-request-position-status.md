---
title: 모집 요청 직위 상태
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 직위 상태 옵션 집합에 관해 설명합니다.
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
ms.openlocfilehash: 6a63a95201583fa7b215e221a03715e56b55c11a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452074"
---
# <a name="recruiting-request-position-status"></a>모집 요청 직위 상태


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 직위 상태 옵션 집합에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequestpositionstatus

이 열거형은 RecruitingRequestPosition 엔터티의 모집 요청 직위 상태 값을 위한 옵션 집합을 제공합니다.

| 값 | 레이블 | 설명 |
| --- | --- | --- |
| 200000000 | 열기 | 모집 요청의 직위를 모집 중입니다. 해당 직위에 대한 현재 활성 직위 할당이 없다는 의미는 아닙니다. 모집 시 해당 직위에 직원이 있을 수 있습니다. 모집 요청의 맥락에서 해당 직위를 모집할 수 있음을 의미합니다. |
| 200000001 | 채워짐 | 직위에 할당할 근로자가 선택되었습니다. |
| 200000002 | 취소됨 | 이 직위에 대한 모집 요청이 취소되었습니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
