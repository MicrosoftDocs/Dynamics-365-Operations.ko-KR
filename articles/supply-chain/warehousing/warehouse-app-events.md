---
title: 창고 앱 이벤트
description: 이 토픽에서는 배치 작업의 일부로 창고 앱 이벤트 메시지를 처리하는 데 사용되는 창고 앱 이벤트 처리에 대해 설명합니다.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8c92bf179006d668f8673e9abc3419a10e644184
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449974"
---
# <a name="warehouse-app-event-processing"></a>창고 앱 이벤트 처리

[!include [banner](../includes/banner.md)]

Supply Chain Management에서 실행 중인 배치 작업은 Warehouse Management 모바일 앱에서 발행한 이벤트를 처리하기 위해 대기열의 데이터를 사용하여 신호된 이벤트에 필요에 따라 반응할 수 있습니다. 이 기능은 앱을 사용하는 작업자가 취한 특정 유형의 작업에 대한 응답으로 관련 이벤트를 대기열에 추가합니다. 예를 들어 *창고 앱에서 이전 주문 생성 및 처리* 기능을 사용할 때 시스템이 **창고 앱 이벤트 처리** 배치 작업을 실행할 때 백엔드에서 이전 주문 헤더와 라인이 생성되고 업데이트됩니다.

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>창고 앱 이벤트 처리 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *창고 앱 이벤트 처리* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>창고 앱 이벤트를 처리하기 위한 배치 작업 설정

### <a name="process-warehouse-app-events"></a>창고 앱 이벤트 처리

이전 주문 생성 및 라인 업데이트를 위한 창고 앱 이벤트를 처리하도록 예약된 일괄 작업을 설정합니다.

1. **창고 관리 \> 정기 작업 \> 창고 앱 이벤트 처리** 로 이동합니다.
1. 창고 앱 이벤트 처리 대화 상자가 열립니다. **백그라운드에서 실행** 빠른 탭을 확장하고 **배치 처리** 를 **예** 로 설정합니다.
1. **백그라운드에서 실행** 빠른 탭에서 **되풀이** 를 선택합니다.
1. **반복 정의** 대화 상자가 열립니다. 비즈니스에 필요한 실행 일정을 설정합니다.
1. **확인** 을 선택하여 **창고 앱 이벤트 처리** 대화 상자로 돌아갑니다.
1. **창고 앱 이벤트 처리** 대화 상자에서 **확인** 을 선택하여 배치 작업을 배치 대기열에 추가합니다.

## <a name="query-warehouse-app-events"></a>창고 앱 이벤트 쿼리

**창고 관리 \> 조회 및 보고서 \> 모바일 디바이스 로그 \> 창고 앱 이벤트** 로 이동하여 Warehouse Management 모바일 앱에서 생성된 이벤트 대기열 및 이벤트 메시지를 볼 수 있습니다.

## <a name="the-standard-event-queue-process"></a>표준 이벤트 대기열 프로세스

창고 앱 이벤트 대기열은 일반적으로 다음과 같은 설명 흐름과 함께 사용됩니다.

1. 이벤트 메시지와 함께 이벤트가 대기열에 추가됩니다. 새 메시지는 처음에 이벤트 상태가 **대기 중** 이며, 이는 **창고 앱 이벤트 처리** 일괄 작업이 이 메시지를 선택 및 처리하지 않음을 의미합니다.
1. 메시지 상태가 **대기 중** 으로 업데이트되는 즉시 **창고 앱 처리** 이벤트 일괄 작업이 이벤트를 선택하고 처리합니다.
1. 일괄 작업은 요청된 프로세스가 가능한지 여부에 따라 이벤트 상태를 **완료됨** 또는 **실패** 로 업데이트합니다.
1. 관련된 모든 이벤트 메시지가 **완료되면** 해당 이벤트는 큐에서 삭제됩니다.

 자세한 예는 [창고 앱 프로세스에서 이전 주문 생성](create-transfer-order-from-warehouse-app.md)을 참조하세요.

## <a name="handle-event-errors"></a>이벤트 오류 처리

창고 이벤트 처리의 일부로 요청된 메시지 활동이 일괄 작업에서 프로세스를 수신하지 못할 수 있습니다. 이 경우 이벤트 메시지가 **실패** 로 변경됩니다. **배치 로그** 정보를 사용하여 이유를 알아보고 문제를 수정하는 데 필요한 조치를 취할 수 있습니다.

자세한 예는 [창고 앱에서 이전 주문 생성](create-transfer-order-from-warehouse-app.md)을 참조하세요.

실패한 창고 앱 이벤트 메시지를 재설정하려면:

1. **창고 관리 \> 문의 및 보고 \> 모바일 디바이스 로그 \> 창고 앱 이벤트** 로 이동합니다.
1. **창고 앱 이벤트 메시지** 빠른 탭에서 **이벤트 상태** 열에 **실패** 를 표시하는 관련 이벤트를 찾아 선택합니다.
1. **창고 앱 이벤트 메시지** 도구 모음에서 **재설정** 을 선택합니다.
1. 모든 관련 메시지가 재설정될 때까지 작업을 계속합니다.

**창고 앱 이벤트 메시지** 도구 모음에서 **삭제** 옵션을 사용하여 **실패** 이벤트 메시지를 제거할 수도 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]