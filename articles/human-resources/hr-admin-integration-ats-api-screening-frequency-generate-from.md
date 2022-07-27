---
title: 심사 빈도 생성
description: 이 항목에서는 Dynamics 365 Human Resources의 심사 빈도 생성 옵션 집합에 관해 설명합니다.
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
ms.openlocfilehash: 27c6c62f3ac312ee502df969f25f1b16761cba03
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452398"
---
# <a name="screening-frequency-generate-from"></a>심사 빈도 생성


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 심사 빈도 생성 옵션 집합에 관해 설명합니다.

실제 이름: mshr_hcmfrequencygeneratefrom

이 열거형은 다음 필수 심사에 대한 계산 시작 날짜를 결정하기 위한 옵션 값 집합을 제공합니다.

| 값 | 레이블 | 설명 |
| --- | --- | --- |
| 200000000 선택되지 않음 | 값이 선택되지 않았습니다. |
| 200000001 완료된 날짜 | 최종 심사가 완료된 날짜부터 계산됩니다. |
| 200000002 필요한 날짜 | 최종 심사가 필요한 날짜부터 계산됩니다. |

## <a name="see-also"></a>참고 항목

[지원자 추적 시스템 통합 API 소개](hr-admin-integration-ats-api-introduction.md)<br>
[채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
