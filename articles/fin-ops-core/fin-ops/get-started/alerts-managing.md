---
title: 경고 일괄 처리
description: 이번에는 경고의 일괄 처리에 대한 정보를 제공합니다.
author: RichdiMSFT
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 0ec2a9bd925ccd7dc7c6a8251629bf565ece2268
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2021
ms.locfileid: "8460694"
---
# <a name="batch-processing-of-alerts"></a>경고 일괄 처리

[!include [banner](../includes/banner.md)]

경고는 일괄 처리 함수에 의해 처리됩니다. 프로세스 전에 일괄 처리를 설정하고 경고를 전달해야 합니다.

일괄 처리 함수은 두 가지 유형의 이벤트를 지원합니다.

- 변경 기반 이벤트에 의해 트리거된 이벤트입니다. 이러한 이벤트는 생성/삭제 및 업데이트 이벤트라고도 합니다.
- 마감일에 의해 트리거된 이벤트.

이벤트 유형별로 일괄 처리를 설정할 수 있습니다.

## <a name="batch-processing-for-change-based-events"></a>변경 기반 이벤트에 대한 일괄 처리

시스템은 일괄 처리가 마지막으로 실행된 이후 발생한 모든 변경 기반 이벤트를 읽습니다. 변경 기반 이벤트에는 필드 업데이트, 기록 삭제 및 기록 생성이 포함됩니다. 이러한 이벤트는 경고 규칙에서 설정한 조건과 비교됩니다. 이벤트가 규칙의 조건과 일치하면 일괄 처리 프로세스에서 경고를 생성합니다.

### <a name="frequency-for-change-based-events"></a>변경 기반 이벤트의 빈도

변경 기반 이벤트의 경우 시스템이 이벤트를 기록한 직후 이벤트 처리를 트리거하는 일괄 작업을 설정할 수 있습니다. 더 자주 반복하도록 배치 작업을 설정하면 변경 사항이 발생한 후 사용자가 더 빨리 경고를 받습니다. 그러나 일괄 처리의 빈도가 높으면 시스템 성능이 저하될 수 있습니다.

반면에 덜 자주 반복되고 시스템 부하가 낮은 시간에 예약하는 일괄 작업은 시스템 성능을 개선하는 데 도움이 될 수 있습니다. 그러나 일괄 처리의 빈도가 낮으면 시기 적절한 경고에 대한 사용자 요구를 충족하지 못할 수 있습니다.

따라서 변경 기반 이벤트에 대한 일괄 처리 빈도를 설정할 때 경보의 적시성과 전체 시스템 성능 간의 균형을 고려하십시오. 이러한 고려 사항은 경고 규칙을 만드는 사용자의 수가 증가함에 따라 더 관련성이 높아집니다. 빈도는 시스템이 처리하는 이벤트 수에 영향을 주지 않습니다. 그러나 더 많은 사용자가 규칙을 만들면 프로세스에서 더 많은 검사를 실행합니다. 이러한 유형의 데이터 교환은 시스템 성능에 영향을 줄 수 있습니다.

#### <a name="the-risks-of-low-batch-frequency"></a>낮은 배치 빈도의 위험

변경 기반 이벤트에 대한 일괄 처리 빈도를 낮게 설정하면 경고 규칙의 조건과 관련된 데이터가 처리 전에 변경될 수 있습니다. 따라서 경고를 잃을 수 있습니다.

예를 들어 이벤트가 **고객 연락처 변경** 이고 조건이 **고객 = BB** 일 때 트리거할 경고를 생성합니다. 즉, 고객 BB의 고객 연락처가 변경되면 프로세스가 이벤트를 기록합니다. 그러나 일괄 처리 시스템은 일괄 처리가 데이터 입력보다 덜 자주 발생하도록 설정됩니다. 이벤트가 처리되기 전에 고객 이름이 **BB** 에서 **AA** 로 변경되면 데이터베이스의 데이터가 더 이상 규칙의 조건(**customer = BB**)과 일치하지 않습니다. 따라서 이벤트가 최종적으로 처리될 때 경고가 생성되지 않습니다.

### <a name="set-up-processing-for-change-based-alerts"></a>변경 기반 경고 처리 설정

1. **시스템 관리** 로 이동 &gt; **정기 작업** &gt; **경고** &gt; **변경 기반 경고**.
2. **변경 기반 경고** 대화 상자에서 적절한 정보를 입력합니다.

## <a name="batch-processing-for-due-date-events"></a>기한 이벤트에 대한 일괄 처리

시스템은 기한으로 인해 발생하는 모든 이벤트를 감지하고 이러한 이벤트는 경고 규칙에 설정된 조건과 비교됩니다. 이벤트가 규칙의 조건과 일치하면 일괄 처리 프로세스에서 경고를 생성합니다.

### <a name="frequency-for-due-date-events"></a>마감일 이벤트의 빈도

기한 이벤트의 경우 밤이나 하루 중 특정 시간에 실행되는 일괄 작업을 설정하여 시스템 부하의 균형을 맞출 수 있습니다. 하루에 한 번 이상 실행되도록 배치 작업을 설정하는 것이 좋습니다. 경고를 가능한 한 빨리 보내야 하는 경우 시스템 날짜가 변경된 직후에 발생하도록 일괄 처리를 설정하십시오. 일괄 작업에서 이미 경고를 처리한 후 발생하는 기한 이벤트에 대한 경고를 생성하려는 경우 동일한 날에 일괄 작업을 다시 실행할 수 있습니다.

예를 들어, 배치 작업이 특정 날짜에 실행되었습니다. 이후 같은 날짜에 경고를 트리거해야 하는 기한이 있는 구매 주문을 생성합니다. 해당 날짜에 알림을 받으려면 구매 오더가 생성된 후 배치 작업을 다시 실행해야 합니다. 그러나 해당 날짜에 일괄 작업을 다시 실행하지 않으면 다음 날 일괄 작업에서 이전 날짜에 처리되지 않은 기한 이벤트를 감지합니다.

> [!NOTE]
> 일괄 처리가 하루에 두 번 이상 실행되는 경우에도 동일한 기한 이벤트 및 조건에 대해 경고가 중복되지 않습니다. 경고는 마지막 배치 작업이 실행된 후 시스템에서 발생한 변경으로 인해 만기가 된 날짜에 대해서만 생성됩니다.

### <a name="batch-processing-window"></a>일괄 처리 창

회사에서 경고 규칙 처리는 여러 가지 이유로 중지될 수 있습니다. 이러한 이유에는 휴가, 시스템 오류 또는 배치 작업이 한동안 실행되지 않는 기타 문제가 포함됩니다.

배치 작업이 며칠 동안 실행되지 않아 만기 알림이 더 이상 사용되지 않도록 하려면 배치 처리 창을 설정할 수 있습니다. 일괄 처리 창을 사용하여 지정된 일 수 동안 일괄 작업이 실행되지 않도록 할 수 있습니다.

일괄 처리 창을 설정하면 알림이 기한 기준에 정의된 시간 제한을 초과하더라도 알림 규칙이 처리될 때 알림이 전송됩니다. 이 시간 제한과 일괄 처리 창으로 정의된 기간을 초과하지 않는 한 경고가 계속 전송됩니다. 그러나 기간이 시간 제한에 일괄 처리 창을 더한 값을 초과하면 더 이상 경고가 전송되지 않습니다.

### <a name="set-up-processing-for-due-date-alerts"></a>마감일 알림 처리 설정

1. **시스템 관리** &gt; **정기 작업** &gt; **알림** &gt; **기한 알림** 으로 이동합니다.
2. **기한 경고** 대화 상자에서 적절한 정보를 입력합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
