---
title: 웨이브 중 작업 생성 일정 잡기
description: 이 항목에서는 일정 작업 생성 웨이브 처리 방법을 설정하고 사용하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5b1e798ac0558e7c5b0bbe4b6a732cbdcf5729a1
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449557"
---
# <a name="schedule-work-creation-during-wave"></a>웨이브 중 작업 생성 일정 잡기

[!include [banner](../../includes/banner.md)]

웨이빙 프로세스의 일부로 *작업 생성 일정 잡기* 기능을 사용하여 시스템이 병렬 처리를 사용하여 작업을 생성하도록 하여 웨이브 처리 처리량을 높이는 데 도움이 되도록 합니다.

기능이 활성화되면 계획된 작업이 자동으로 생성되고 시스템은 최종적으로 이를 처리하여 실제 작업을 생성합니다. 웨이브 로드 라인의 수가 미리 정해진 임계값에 도달하면 시스템은 병렬, 비동기 처리를 적용하여 실제 작업을 더 빠르게 생성합니다.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>기능 관리에서 예약된 작업 생성 기능 켜기

이 항목에서 설명하는 기능을 사용하려면 시스템에 대해 켜져 있어야 합니다. [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역을 사용하여 다음 주문의 다음 기능을 켜세요.

1. **조직 전체 작업 차단** – 예약된 작업 생성의 수동 및 자동 구성 모두에 필요합니다. (Supply Chain Management 버전 10.0.21부터 이 기능은 필수이므로 기본적으로 켜져 있으며 다시 끌 수 없습니다.)
1. **작업 생성 예약** – 예약된 작업 생성의 수동 및 자동 구성 모두에 필요합니다.
1. **조직 전체 "작업 생성 예약" 웨이브 메서드** – 예약된 작업 생성의 자동 구성에 필요합니다. 수동 구성만 사용하는 경우에는 이 기능이 필요하지 않습니다.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>예약된 작업 생성 자동 구성

*조직 전체의 "작업 생성 일정" 웨이브 방식* 기능을 사용하면 시스템에서 다음이 자동으로 발생합니다.

- *작업 생성 일정 잡기* 웨이브 방식(`WHSScheduleWorkCreationWaveStepMethod`)이 추가되고 모든 법인에서 병렬로 실행되도록 구성됩니다.
- **웨이브 템플릿 유형** 이 *배송* 으로 설정되고 **템플릿 상태** 가 *유효* 로 설정된 모든 합법적인 엔터티의 웨이브 템플릿은 *작업 만들기* 방법이 *작업 생성 일정 잡기* 방법으로 대체됩니다. 그러나 *작업 만들기* 메소드를 반복 가능하도록 허용된 합법적인 엔터티의 웨이브 템플릿은 수정되지 않습니다.
- *작업 생성 일정 잡기* 메서드의 작업 구성은 **창고 관리 프로세스 사용** 이 활성화된 모든 법인의 모든 창고에 대해 메소드가 생성됩니다. 이는 *작업 생성 일정 잡기* 메서드가 이제 기본적으로 병렬로 실행됨을 의미합니다. **창고 관리 프로세스 사용** 이 *아니요* 에서 *예* 로 변경되는 기존 창고의 경우에도 기본적으로 이 메서드를 병렬로 실행합니다.
- 이전에 *0* ms로 설정된 경우 모든 법인은 웨이브를 일괄 처리하고 **잠금 대기(ms)** 가 기본값인 *60,000* 으로 설정됩니다.
- 만드는 모든 새 웨이브 템플릿은 *작업 만들기* 메서드 대신 *작업 생성 예약* 웨이브 메서드를 사용하게 됩니다.

기존 작업 및 웨이브 처리 구성은 이미 웨이브를 일괄 처리하도록 구성된 모든 법인과 이미 *작업 생성 일정 잡기* 메서드를 병렬로 사용하도록 구성된 모든 창고에 대해 유지됩니다.

필요한 경우 다음을 수행하여 *조직 전체 일정 작업 생성 웨이브 방식* 기능을 활성화할 때 자동으로 지정된 일부 또는 전체 설정을 수동으로 되돌릴 수 있습니다.

- 창고 템플릿의 경우 **창고 관리 \> 설정 \> 웨이브 \> 웨이브 템플릿** 으로 이동합니다. *작업 생성 일정 잡기* 방법을 *작업 만들기* 로 대체합니다.
- 창고 관리의 경우 **창고 관리 \> 설정 \> 창고 관리 매개 변수** 로 이동합니다. **웨이브 처리** 탭에서 **일괄 처리 웨이브** 및 **잠금 대기(ms)** 에 대해 원하는 값을 적용합니다.
- 웨이브 메서드의 경우 **창고 관리 \> 설정 \> 웨이브 \> 웨이브 프로세스 방법** 으로 이동합니다. `WHSScheduleWorkCreationWaveStepMethod`를 선택한 다음 작업 창에서 **작업 구성** 을 선택합니다. 필요에 따라 나열된 각 창고에 대해 배치 작업 수와 할당된 웨이브 그룹을 수정하거나 삭제합니다.

## <a name="manually-configure-scheduled-work-creation"></a>예약된 작업 생성 수동 구성

[*조직 전체의 "작업 생성 일정" 웨이브 방식* 기능](#Auto-enable-schedule-work-creation)을 활성화하지 않은 경우 이 섹션에 제공된 절차를 사용하여 필요에 따라 예약된 작업 생성을 수동으로 구성할 수 있습니다.

### <a name="manually-enable-batch-processing-of-waves"></a>수동으로 웨이브 일괄 처리 활성화

병렬 비동기 방식을 활용하여 창고 작업을 생성하려면 웨이브 프로세스가 일괄 처리로 실행되어야 합니다. 이 기능을 설정하려면:

1. **Warehouse Management \> 설정 \> Warehouse Management 매개 변수** 로 이동합니다.
1. **알번** 탭에서 **일괄 웨이브 처리** 를 *예* 로 설정합니다. 선택적으로 전용 **웨이브 처리 일괄 그룹** 을 선택하여 일괄 대기열 처리가 다른 프로세스와 동시에 실행되는 것을 방지할 수도 있습니다.
1. 시스템이 동시에 여러 웨이브를 처리할 때 적용되는 **잠금(ms) 시간 대기** 를 설정합니다. 대부분의 더 큰 웨이빙 프로세스의 경우 *60000* 값을 권장합니다.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>기존 웨이브 템플릿에 대한 새 웨이브 단계 방법을 수동으로 활성화

먼저 새 웨이브 단계 방법을 만들고 병렬 비동기 작업 처리를 위해 활성화합니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 처리 방법** 으로 이동합니다.
1. **재생성 방법** 을 선택하고 *WHSScheduleWorkCreationWaveStepMethod* 가 배송 웨이브 템플릿에서 사용할 수 있는 웨이브 프로세스 방법 목록에 추가되었습니다.
1. **메소드 이름** 이 *WHSScheduleWorkCreationWaveStepMethod* 인 레코드를 선택하고 **작업 구성** 을 선택합니다.
1. 그리드에 새 행을 추가하려면 작업 창에서 **새로 만들기** 를 선택하고 다음 설정을 사용합니다.

    - **창고** - 작업 생성 처리를 예약하는 데 사용할 창고를 선택합니다.
    - **최대 일괄 작업 수** - 일괄 작업의 최대 수를 지정합니다. 대부분의 경우 이 값은 8-16 범위에 있어야 하지만 시나리오에 따라 최적의 설정으로 실험하는 것이 좋습니다.
    - **웨이브 처리 일괄 그룹** - 일괄 대기열 처리를 최적화하려면 전용 웨이브 처리 일괄 그룹을 선택합니다.

이제 기존 웨이브 템플릿을 업데이트하거나 새 템플릿을 생성하여 *작업 생성 일정 잡기* 웨이브 처리 방법을 사용할 준비가 되었습니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 템플릿** 으로 이동합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. 목록 창에서 업데이트하려는 웨이브 템플릿을 선택합니다(데모 데이터를 사용하여 테스트하는 경우 *24 배송 기본값* 을 사용할 수 있습니다.).
1. **메서드** 빠른 탭을 펼치고 **남은 메서드** 그리드에서 **이름** *작업 생성 일정 잡기* 인 행을 선택합니다.
1. **선택한 메서드** 열을 가리키는 화살표를 선택하여 선택한 행을 해당 열로 이동합니다. (`WHSScheduleWorkCreationWaveStepMethod` 또는 `createWork` 중 하나를 사용하는 한 번에 하나의 방법만 선택할 수 있습니다. 따라서 **메소드 이름** 이 `createWork`인 기존 행이 **남은 방법** 그리드로 자동으로 이동합니다.)

## <a name="set-wave-task-processing-threshold-data"></a>웨이브 작업 처리 임계값 데이터 설정

작업 기반 처리를 사용하여 웨이브 프로세스를 처음 실행할 때 시스템은 기본 웨이브 작업 처리 임계값 데이터를 생성하게 됩니다. 데이터는 웨이브 처리가 비동기적으로 실행되고 작업 기반인 경우를 제어하는 데 사용되어 웨이브 레이블을 병렬로 처리하고 생성할 수 있습니다.

기본 데이터는 처음에 최소 로드 라인 수로 15의 임계값을 사용합니다(`MINIMUMWAVELOADLINES`). 이는 시스템이 15개 이상의 로드 라인이 있는 웨이브를 처리할 때 비동기 작업 처리를 사용한다는 것을 의미합니다. 테스트 환경의 `WHSWaveTaskProcessingThresholdParameters` 테이블에서 이 데이터를 수동으로 삽입/업데이트할 수 있습니다. 프로덕션 환경에서 설정을 변경하려는 경우 Microsoft 지원에 문의하여 업데이트를 요청해야 합니다.

## <a name="work-with-the-scheduled-work-creation"></a>예약된 작업 생성 작업

예약된 작업 생성 작업 방법에 대한 자세한 내용은 [웨이브 생성 및 처리](wave-processing.md)를 참조하세요. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
