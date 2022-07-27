---
title: 중단된 일괄 작업 재설정
description: 이 항목에서는 중단된 일괄 작업 문제를 해결하는 방법을 설명합니다.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 859f039a928cdc57c9f227885d0f00ef79980f28
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452632"
---
# <a name="reset-stuck-batch-jobs"></a>중단된 일괄 작업 재설정


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>문제

Microsoft Dynamics 365 Human Resources가 **실행 중** 또는 **최소 중** 상태에서 멈추고 완료되지 않는 일괄 작업 문제가 발생할 수 있습니다.

## <a name="resolution"></a>해결

일괄 작업이 **실행 중** 또는 **취소 중** 상태로 멈추면 작업을 강제로 취소하여 상태를 재설정할 수 있습니다. 취소한 후 **대기 중** 상태로 설정하여 일괄 작업을 재설정할 수 있습니다. 그런 다음 예약된 다음 일괄 실행에서 실행을 위해 다시 선택됩니다.

1. **시스템 관리** 작업 공간에서 **연결** 페이지를 선택하고 **일괄 작업** 을 선택합니다.

2. **일괄 작업** 목록 페이지에서 재설정해야 하는 작업을 선택합니다.

3. 작업 리본에서 **강제 취소** 를 선택하고 작업을 확인합니다.

   > [!NOTE]
   > **강제 취소** 작업은 선택한 일괄 작업의 상태가 **실행 중** 또는 **취소 중** 이고 작업에 대해 실행 중인 일괄 실행 또는 취소 프로세스가 없는 경우에만 사용할 수 있습니다.

4. 작업 리본에서 **상태 변경** 을 선택합니다.

5. **새 상태 선택** 페이지에서 **대기 중** 을 선택하고 **확인** 을 선택합니다.

   ![새 일괄 작업 상태를 선택합니다.](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>참고 항목

[근무 시간 이후에 일괄 작업을 예약하여 성능 최적화](hr-admin-troubleshooting-batch-jobs.md)<br>
[자동 정리 작업으로 성능 최적화](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
