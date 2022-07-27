---
title: 모집 요청 상태
description: 이 항목에서는 Dynamics 365 Human Resources의 모집 요청 상태 옵션 집합에 관해 설명합니다.
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
ms.openlocfilehash: d845179077fc2e04dfb3bd05eaa70b0a2a016121
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452308"
---
# <a name="recruiting-request-status"></a>모집 요청 상태


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 모집 요청 상태 옵션 집합에 관해 설명합니다.

실제 이름: mshr_hcmrecruitingrequeststatus

이 열거형은 모집 요청을 위한 상태 값의 옵션 집합을 제공합니다.

| 값 | 레이블 | 설명 |
| --- | --- | --- |
| 200000000 | 초안 | 요청이 초안이며 모집을 실행할 준비가 되지 않았습니다. |
| 200000001 | 검토 중 | 요청이 제출되었으며 워크플로 승인을 위해 라우팅되고 있습니다. 워크플로가 활성화된 경우에만 사용할 수 있습니다. |
| 200000002 | 보류 중 | 요청이 보류 중인 워크플로 작업입니다. 워크플로가 활성화된 경우에만 사용할 수 있습니다. |
| 200000003 | 취소됨 | 요청이 취소되었습니다. 워크플로가 활성화된 경우에만 사용할 수 있습니다. |
| 200000004 | 거부됨 | 요청이 거부되었습니다. 워크플로가 활성화된 경우에만 사용할 수 있습니다. |
| 200000005 | 활성 | 모든 워크플로가 완료되고 승인되었으며 모집 요청이 준비되었습니다. |
| 200000006 | 닫힘 | 모집 요청이 마감되었습니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
