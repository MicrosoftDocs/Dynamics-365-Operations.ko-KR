---
title: 자동 정리 작업으로 성능 최적화
description: 이 항목에서는 일괄 작업 기록을 정리하여 Microsoft Dynamics 365 Human Resources의 성능을 개선하는 방법을 설명합니다.
author: twheeloc
ms.date: 08/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a293b128364b8b0b293da03495d55e46f6b01fd6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452197"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>자동 정리 작업으로 성능 최적화


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**문제**

Microsoft Dynamics 365 Human Resources 일괄 작업 기록이 너무 커지면 성능 문제가 발생할 수 있습니다.

**원인**

일괄 작업을 자주 실행하면 일괄 작업 기록이 감당할 수 없게 증가할 수 있습니다. 이로 인해 성능 문제가 발생할 수 있습니다. 

**해결**

일괄 작업 기록을 정리하는 자동 작업을 예약합니다. 매주 실행되도록 작업을 설정하는 것이 좋지만 환경에 따라 정리를 더 또는 덜 자주 실행해야 할 수도 있습니다. 다음 절차에는 권장 설정이 포함되어 있지만 필요에 따라 설정을 변경할 수 있습니다.

1. Human Resources에서 **시스템 관리** 를 선택합니다.

2. **검색** 표시줄에 **일괄 작업 기록 정리** 를 입력합니다.

   ![일괄 작업 기록 정리를 검색합니다.](media/talent-batch-history-cleanup-search-bar.png)

3. **기록 한도(일)** 에 **30** 을 입력합니다.

   ![기록 한도를 30으로 설정합니다.](media/talent-batch-history-cleanup-history-limit.png)

4. **백그라운드에서 실행** 을 선택한 다음 **되풀이** 를 선택합니다.

   ![되풀이를 설정합니다.](media/talent-batch-history-cleanup-recurrence.png)

5. **되풀이 정의** 에서 **시작 날짜** 와 **시작 시간** 이 업무 외 시간 또는 주말이 되도록 설정하고 **종료 날짜 없음** 을 선택합니다. 

   ![반복 시작 날짜 및 시간을 정의합니다.](media/talent-batch-history-cleanup-define-recurrence.png)

6. **되풀이 패턴** 에서 **일** 을 선택하고 **지정된 간격 이후 반복** 을 **7** 로 설정합니다.

   ![정리를 매주 반복하도록 설정합니다.](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. **확인** 을 선택합니다.

8. 필요에 따라 **백그라운드에서 실행** 에서 다른 매개 변수를 변경한 다음 **확인** 을 선택합니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
