---
title: 직무 면제 상태
description: 이 항목에서는 Dynamics 365 Human Resources의 직무 면제 상태 옵션 집합에 관해 설명합니다.
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
ms.openlocfilehash: 29d3c4fd37a219b520172c6866c5fec488c698f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452086"
---
# <a name="job-exempt-status"></a>직무 면제 상태


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 직무 면제 상태 옵션 집합에 관해 설명합니다.

실제 이름: cdm_jobexemptstatus

이 열거형은 FLSA 직무 면제 상태 값의 옵션 집합을 지정합니다. 이는 기존 cdm_jobexemptstatus 옵션 집합에서 제공됩니다.

| 값 | 레이블 | 설명 |
| --- | --- | --- |
| 200000000 | 면제 | 직무가 FLSA 지침에 따라 면제 상태입니다. |
| 200000001 | 비면제 | 직무가 FLSA 지침에 따라 비면제 상태입니다. |
| 200000002 | 해당되지 않음 | FLSA 상태 지침은 해당 직무에 적용되지 않습니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
