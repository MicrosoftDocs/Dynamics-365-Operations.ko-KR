---
title: 수동 재고 이동의 지연 처리
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management에서 수동 재고 이동의 지연 처리를 사용하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: Mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 21dd01448fcf6c2b3ca90a5476fad061bb0f55e4
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449914"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>수동 재고 이동의 지연 처리

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management에서 수동 재고 이동의 지연 처리를 사용하는 방법에 대해 설명합니다.

지연 처리를 통해 창고 작업자는 백그라운드에서 넣기 작업이 처리되는 동안 계속 다른 작업을 수행할 수 있습니다. 지연된 처리는 서버에서 처리 시간이 비정기적으로 또는 계획되지 않은 증가가 있을 수 있고 증가된 처리 시간이 작업자 생산성에 영향을 미칠 수 있는 경우에 유용합니다. 이제 *재고 이동* 작업 유형이 이 기능이 지원하는 작업 유형 세트에 추가되었습니다.

백그라운드 처리는 [창고 앱 이벤트 처리 기능](warehouse-app-events.md)을 사용하여 수행됩니다.

## <a name="turn-on-this-feature-for-your-system"></a>시스템에 이 기능 사용 설정

이 기능을 사용 가능하게 하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 다음 기능을 켜세요. 다음 순서로 켜야 합니다.

1. *조직 전체 작업 차단*<br>(Supply Chain Management 버전 10.0.21부터 이 기능은 필수이므로 기본적으로 켜져 있으며 다시 끌 수 없습니다.)
1. *창고 앱 이벤트 처리*<br>(Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다.)
1. *지연된 넣기 작업*
1. *수동 재고 이동 작업의 지연 처리*<br>(Supply Chain Management 버전 10.0.25부터 이 기능은 필수이므로 기본적으로 켜져 있으며 다시 끌 수 없습니다.)

## <a name="configure-the-work-processing-policies"></a>작업 처리 정책 구성

지연 처리를 사용하려면 작업 처리 정책을 설정하고 사용해야 합니다. 지연된 넣기 처리의 경우 [창고 작업의 지연된 처리 기능](deferred-put.md)은 *판매 주문*, *이전 주문 이슈* 및 *보충* 작업 유형을 지원합니다. *수동 재고 이동 작업 기능의 지연된 처리* 는 *재고 이동* 이라는 새로운 작업 유형을 추가합니다.

작업 처리 정책을 설정하려면 다음 단계를 따르세요.

1. **창고 관리 \> 설정 \> 작업 \> 작업 처리 정책** 으로 이동합니다.
1. 목록에서 기존 정책을 선택하거나 작업 창에서 **새로 만들기** 를 선택하여 새 정책을 만듭니다. 모든 정책의 헤더에는 다음 필드가 있습니다.

    - **작업 처리 정책 이름** – 작업 처리 정책의 이름입니다.
    - **설명** – 작업 처리 정책에 대한 설명.

1. **처리 규칙** 빠른 탭에서 정책을 적용할 규칙 모음을 설정합니다. 도구 모음의 단추를 사용하여 필요에 따라 규칙을 추가하거나 제거합니다. 각 규칙에 대해 다음 필드를 설정합니다.

    - **작업 주문 유형** – 정책이 적용되는 작업 유형을 선택합니다.
    - **작업** – 정책이 처리하는 데 사용되는 작업을 선택합니다. **작업 주문 유형** 필드에서 *재고 이동* 을 선택한 경우 피킹 작업과 넣기 작업이 모두 단일 이벤트로 처리되기 때문에 이 필드를 설정할 필요가 없습니다.
    - **작업 처리 방법** – 작업 라인을 처리하는 데 사용되는 방법을 선택합니다. *즉시* 를 선택하면 라인을 처리하는 데 작업 처리 정책이 사용되지 않을 때의 동작과 유사합니다. *지연됨* 을 선택하면 시스템은 배치 프레임워크를 사용하는 지연 처리를 적용합니다.
    - **지연된 처리 임계값** – 이 필드를 *0*(영)으로 설정하면 임계값이 없습니다. 이 경우 가능하면 *지연된* 처리 방식을 사용합니다. 특정 임계값 집계가 임계값 미만이면 *즉시* 방법이 사용됩니다. 그렇지 않으면 *지연된* 방법을 사용할 수 있으면 사용됩니다. 판매 및 이전 관련 작업의 경우 임계값은 해당 작업에 대해 처리 중인 연결된 소스 로드 라인의 수로 집계됩니다. 보충 작업의 경우 임계값은 작업에 의해 보충되는 작업 라인 수로 집계됩니다. 예를 들어 판매 임계값을 *5* 로 설정하면 초기 소스 로드 라인이 5개 미만인 소규모 작업은 지연 처리를 사용하지 않지만 대규모 작업에서는 지연 처리를 사용하도록 합니다. 임계값은 **작업 처리 방법** 필드가 *지연* 으로 설정된 경우에만 적용됩니다.
    - **지연 처리 일괄 그룹** – 처리에 사용할 일괄 그룹을 지정합니다. **작업 주문 유형** 필드에서 *재고 이동* 을 선택한 경우 **창고 앱 이벤트 처리** 대화 상자에서 일괄 그룹이 선택되기 때문에 이 필드를 설정할 필요가 없습니다.

## <a name="assign-the-work-creation-policy"></a>작업 생성 정책 할당

작업 생성 정책을 할당하는 방법에 대한 자세한 내용은 [창고 작업 지연 처리](deferred-put.md)를 참조하세요.

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>창고 앱 이벤트를 처리하기 위한 배치 작업 설정

*수동 재고 이동 작업 프로세스의 지연 처리* 를 사용하려면 예약된 배치 작업을 설정합니다.

1. **창고 관리 \> 정기 작업 \> 창고 앱 이벤트 처리** 로 이동합니다.
1. **창고 앱 이벤트 처리** 대화 상자의 **백그라운드에서 실행** 빠른 탭에서 **일괄 처리** 옵션을 *예* 로 설정합니다.
1. **되풀이** 를 선택하고 비즈니스 요구 사항에 맞는 실행 일정을 설정합니다.
1. 각 대화 상자에서 **확인** 을 선택합니다.

## <a name="inquire-about-the-warehouse-app-events"></a>창고 앱 이벤트 문의하기

**창고 관리 \> 문의 및 보고서 \> 모바일 디바이스 로그 \>> 창고 앱 이벤트** 로 이동하여 창고 앱이 생성하는 이벤트 큐 및 이벤트 메시지를 볼 수 있습니다.

*재고 이동* 이벤트 메시지는 처음 생성될 때 *대기 중* 상태가 됩니다. 이 상태는 **창고 앱 이벤트** 처리 일괄 작업이 이벤트 메시지를 선택하고 처리함을 나타냅니다. 상태가 *완료됨* 으로 업데이트되면 모든 관련 이벤트가 대기열에서 삭제됩니다.

모든 *재고 이동* 이벤트는 이벤트 유형 및 창고별로 하나의 컬렉션으로 누적됩니다.

일괄 작업은 **창고 앱 이벤트 처리** 대화 상자에 설정된 반복에 따라 창고 앱 이벤트를 처리합니다. 따라서 메시지가 처리될 때까지 **식별자** 필드를 보면 창고 ID를 찾을 수 있습니다.

메시지 세부 정보에는 이동 세부 정보(예: "from" 및 "to" 위치)가 포함됩니다.

자세한 내용은 [창고 앱 이벤트 처리](warehouse-app-events.md)를 참조하세요.

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>지연된 처리 정책을 건너뛰도록 모바일 디바이스 메뉴 구성

지연 처리 정책을 건너뛰도록 모바일 디바이스 메뉴를 구성하는 방법에 대한 자세한 내용은 [창고 작업 지연 처리](deferred-put.md)를 참조하세요.

## <a name="impact-on-closed-work-dates"></a>마감됨 작업 날짜에 미치는 영향

[지연된 창고 처리 정책을](deferred-put.md) 건너뛰도록 모바일 디바이스 메뉴를 구성하는 방법에 대한 자세한 내용은 창고 작업 지연 처리를 참조하세요.

## <a name="additional-resources"></a>추가 리소스

- [창고 작업의 지연 처리](deferred-put.md)
- [창고 앱 이벤트 처리](warehouse-app-events.md)
- [창고 작업을 위한 모바일 디바이스 설정](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
