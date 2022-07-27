---
title: 근무 시간 이후에 일괄 작업을 예약하여 성능 최적화
description: 이 항목에서는 근무 시간 이후에 장기 일괄 작업을 실행하도록 예약하여 Microsoft Dynamics 365 Human Resources의 성능 문제를 해결하는 방법을 설명합니다.
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 14354ba9454b8837246b75cd413497553423511e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452131"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>근무 시간 이후에 일괄 작업을 예약하여 성능 최적화


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>문제

장기 실행 일괄 작업이 일반 근무 시간 동안 실행되는 경우 Microsoft Dynamics 365 Human Resources에 성능 문제가 발생할 수 있습니다.

## <a name="resolution"></a>해결

다음 일괄 작업을 근무 외 시간에 예약합니다. 또한 자주 실행되는 일괄 작업의 빈도를 검토하는 것이 좋습니다. 가능하면 일괄 작업의 되풀이 횟수를 줄입니다. 대부분의 경우 기본 빈도로 충분합니다.

다음 일괄 작업은 야간 또는 근무 시간 이후에 실행해야 합니다. 다음과 같은 정기적인 일괄 작업의 표준 시간대를 확인하세요. 일부 일괄 작업은 태평양 표준시(PST)를 사용할 수 있습니다.

| 일괄 작업 | 기본 발생 빈도 |
| --- | --- |
| 일괄 작업 기록 정리 | 한 달에 1번 |
| 준비 정리 내보내기 | 하루에 1번 |
| Common Data Service 통합에 요청 동기화 누락 | 하루에 1번 |
| 업무 외 시간에 정기적으로 실행해야 하는 데이터베이스 압축 시스템 작업 | 하루에 1번 |
| 업무 외 시간에 정기적으로 실행해야 하는 데이터베이스 인덱스 재구축 시스템 작업 | 하루에 1번 |

1. Human Resources에서 **시스템 관리** 를 선택합니다.

2. **검색** 막대에서 위의 일괄 작업 중 하나를 검색합니다.

3. **백그라운드에서 실행** 을 선택한 다음 **되풀이** 를 선택합니다.

   ![되풀이를 설정합니다.](media/talent-batch-history-cleanup-recurrence.png)

4. **되풀이 정의** 에서 **시작 날짜** 와 **시작 시간** 이 업무 외 시간 또는 주말이 되도록 설정합니다. **종료 날짜 없음** 을 선택합니다. 

   ![반복 시작 날짜 및 시간을 정의합니다.](media/talent-batch-history-cleanup-define-recurrence.png)

5. **확인** 을 선택합니다.

6. 필요에 따라 **백그라운드에서 실행** 에서 다른 매개 변수를 변경한 다음 **확인** 을 선택합니다.

## <a name="additional-resources"></a>추가 리소스

[자동 정리 작업으로 성능 최적화](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
