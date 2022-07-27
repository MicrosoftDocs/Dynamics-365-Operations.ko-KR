---
title: Dataverse 동기화 재설정
description: 이 항목에서는 Microsoft Dataverse의 Microsoft Dynamics 365 Human Resources와 HCM(Human Capital Management) 공통 솔루션 간에 올바르게 동기화되지 않는 레코드를 해결하는 방법에 대해 설명합니다.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d6b20b6b2ae4fdbbfb27a765dfb7a1dc82fe7981
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452677"
---
# <a name="reset-dataverse-synchronization"></a>Dataverse 동기화 재설정


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>문제

Microsoft Dynamics 365 Human Resources와 Microsoft Dataverse의 HCM(Human Capital Management) Common 솔루션의 엔티티 간에 레코드가 동기화되지 않습니다. 동기화에 대한 자세한 내용은 [Dataverse 통합 구성](hr-admin-integration-common-data-service.md)을 참조하십시오. **Dataverse 통합 재시도** 또는 **Dataverse 통합 누락된 요청 동기화** 일괄 작업이 **실행 중** 상태로 멈추면 동기화 실패가 발생할 수 있습니다.

## <a name="resolution"></a>해결

**Dataverse 통합 재시도** 또는 **Dataverse 통합 누락된 요청 동기화** 일괄 작업이 **실행 중** 또는 **취소 중** 상태로 멈춘 경우 상태를 재설정할 수 있습니다. [멈춘 일괄 작업 재설정](hr-admin-troubleshooting-batch-execution.md)의 지침에 따라 일괄 작업을 취소할 수 있습니다. 일괄 작업을 취소한 후 일괄 작업을 **대기 중** 상태로 설정하여 재설정할 수 있습니다. 그러면 다음 예약된 실행 시간에 일괄 작업이 실행됩니다.

1. 아직 실행하지 않은 경우 **기능 관리** 에서 **향상된 일괄 중단** 기능을 사용하도록 설정하십시오.
   1. **기능 관리** 페이지(**시스템 관리** > **요약** > **기능 관리**)로 이동합니다.
   2. **모두** 탭을 선택합니다.
   3. **기능 이름** 열을 선택하고 **향상된 일괄 중단** 으로 필터링합니다.
   4. 아직 활성화되지 않은 경우 **사용** 작업을 선택합니다.

2. Dataverse 통합을 끕니다.
   1. **Microsoft Dataverse 통합** 페이지로 이동합니다(**시스템 관리** 에서 **링크** > **통합** > **Dataverse 구성** 으로 이동).
   2. **Dataverse 통합 사용** 을 **아니요** 로 설정합니다.

3. **Dataverse 통합 재시도** 일괄 작업을 취소합니다.
   1. **일괄 작업** 페이지로 이동합니다(**시스템 관리** 에서 **링크** > **일괄 작업** > **일괄 작업** 으로 이동).
   2. **통합** 별로 **작업 설명** 열을 필터링합니다.
   3. **Dataverse 통합 재시도** 일괄 작업을 선택합니다.
   4. 작업 리본에서 **일괄 작업**, **강제 취소** 를 선택한 다음 **예** 를 선택하여 확인합니다.

   > [!NOTE]
   > 처음 통합을 실행한 시기에 따라 일괄 작업에 **Common Data Service 통합 재시도** 라는 설명이 있을 수 있습니다. **Dataverse 통합 재시도** 일괄 작업 대신 이 일괄 작업이 나열된 경우 선택하십시오.

4. 모든 Dataverse 통합 일괄 작업을 삭제합니다.
   1. **일괄 작업** 페이지에서 **Dataverse 통합 누락 요청 동기화**, **Dataverse 통합 재시도** 및 **Dataverse 통합 초기 동기화** 일괄 작업을 선택합니다.
   2. 작업 리본에서 **상태 변경** 작업을 선택합니다. 
   3. **보류** 를 선택한 후 **확인** 을 선택합니다.
   4. 작업 리본에서 **삭제** 작업을 선택한 후 **예** 를 선택하여 작업을 확인합니다.

5. Dataverse 통합 일괄 작업을 켭니다.
   1. **Microsoft Dataverse 통합** 페이지(**시스템 관리** > **링크** > **통합** > **Dataverse 구성**)로 이동합니다.
   2. **Dataverse 통합 사용** 을 **예** 로 설정합니다.

6. **일괄 작업** 페이지로 이동하여 **Dataverse 통합 재시도** 및 **Dataverse 통합 누락 요청** 일괄 작업이 생성되었는지 확인합니다.

이제 일괄 작업이 재생성되어 **Dataverse 통합 재시도** 배치 작업을 모니터링하여 작업을 실행하는 데 걸리는 시간을 확인할 수 있습니다. 그런 다음 레코드가 Microsoft Dataverse의 HCM 공통 솔루션과 올바르게 동기화되는지 확인할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Dataverse 통합 구성](hr-admin-integration-common-data-service.md)<br>
[중단된 일괄 작업 재설정](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
