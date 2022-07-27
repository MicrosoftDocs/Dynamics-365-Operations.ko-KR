---
title: 웨이브 중 웨이브 라벨 인쇄 예약
description: 이 항목에서는 작업 기반 웨이브 라벨 인쇄 기능을 설정하고 사용하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1323538765308ec3dd366456e31f5e08b08ce5ab
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449560"
---
# <a name="schedule-wave-label-printing-during-wave"></a>웨이브 중 웨이브 라벨 인쇄 예약

[!include [banner](../../includes/banner.md)]

웨이빙 프로세스의 일부로 *작업 기반 웨이브 라벨 인쇄* 기능을 사용하여 효율성을 개선하고 시스템에서 웨이브 레이블을 생성하고 별도의 작업을 수행하도록 합니다.

웨이브 라벨 인쇄를 구성하는 프로세스는 복잡하고 정확한 구성과 마스터 데이터에 의존합니다. 웨이브 레이블 레코드 생성이 실패하는 것은 드문 일이 아니며 실패할 경우 전체 웨이브 처리가 롤백됩니다. *작업 기반 웨이브 레이블 인쇄* 기능을 사용하면 웨이브 라벨이 잘못 인쇄될 때마다 작업 및 작업 라인을 다시 생성하지 않아도 됩니다.

*작업 기반 웨이브 레이블 인쇄* 기능을 사용하면 시스템은 먼저 작업 및 작업 라인을 생성합니다. 그런 다음 웨이브 레이블을 만들고 인쇄합니다. 마지막으로 웨이브 레이블이 올바르게 생성되면 작업과 웨이브를 피킹을 위해 해제합니다.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>기능 관리에서 작업 기반 웨이브 라벨 인쇄 기능 켜기

이 항목에서 설명하는 기능을 사용하려면 시스템에 대해 켜져 있어야 합니다. [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역을 사용하여 다음 주문의 기능을 켜세요.

1. *웨이브 라벨 인쇄* – 이 기능은 웨이브 라벨 인쇄를 위한 웨이브 프로세스 방식을 활성화하기 위해 필요합니다.
1. *조직 전체 작업 차단* – 이 기능은 예약된 작업 생성의 수동 및 자동 구성 모두에 필요합니다. (Supply Chain Management 버전 10.0.21부터 이 기능은 필수이므로 기본적으로 켜져 있으며 다시 끌 수 없습니다.)
1. *작업 기반 웨이브 라벨 인쇄* – 이 기능은 웨이브 라벨 인쇄를 별도의 트랜잭션 범위로 분할하기 위해 필요합니다.

## <a name="manually-enable-the-new-wave-step-method"></a>수동으로 새 웨이브 단계 방법 활성화

먼저 새 웨이브 단계 방법을 만들고 병렬, 비동기 작업 처리를 위해 활성화해야 합니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 처리 방법** 으로 이동합니다.
1. 작업 창에서 **메서드 다시 생성** 을 선택합니다. *waveLabelPrinting* 이 배송 웨이브 템플릿에서 사용할 수 있는 웨이브 프로세스 방법 목록에 추가되어 있습니다.
1. **메서드 이름** 필드가 *waveLabelPrinting* 으로 설정된 레코드를 선택한 다음 작업 창에서 **작업 구성** 을 선택합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **창고** – 작업 생성 처리를 예약하는 데 사용할 창고를 선택합니다. (테스트 목적으로 데모 데이터를 사용하는 경우 창고 *24* 를 선택할 수 있습니다.)
    - **최대 일괄 작업 수** – 일괄 작업의 최대 수를 지정합니다. 대부분의 경우 값은 *8* 부터 *16* 까지여야 합니다. 그러나 시나리오에 대한 최적의 설정을 찾기 위해 실험하는 것이 좋습니다.
    - **웨이브 처리 일괄 그룹** – 일괄 대기열 처리를 최적화하려면 전용 웨이브 처리 일괄 그룹을 선택합니다.

이제 기존 웨이브 템플릿을 업데이트하여 *웨이브 라벨 인쇄* 웨이브 처리 방법을 사용하도록 합니다. 또는 이를 사용하는 새 웨이브 템플릿을 생성할 수 있습니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 템플릿** 으로 이동합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. 목록 창에서 업데이트할 웨이브 템플릿을 선택합니다. (테스트 목적으로 데모 데이터를 사용하는 경우 *24 배송 기본값* 을 선택할 수 있습니다.)
1. **메서드** 빠른 탭의 **나머지 메서드** 열에서 **이름** 필드가 *waveLabelPrinting* 으로 설정된 행을 선택합니다.
1. **추가**(오른쪽 화살표 단추)를 선택하여 선택한 행을 **선택한 메서드** 열로 이동합니다.
1. **웨이브 단계 코드** 필드에 웨이브 템플릿을 웨이브 레이블 템플릿과 연결하는 데 사용할 웨이브 단계 코드를 입력합니다.

## <a name="set-wave-task-processing-threshold-data"></a>웨이브 작업 처리 임계값 데이터 설정

작업 기반 처리를 사용하여 웨이브 프로세스를 처음 실행할 때 시스템은 기본 웨이브 작업 처리 임계값 데이터를 생성합니다. 이 데이터는 웨이브 처리가 비동기적으로 실행되고 작업 기반인지 여부를 제어하는 데 사용되어 웨이브 레이블을 병렬로 처리하고 생성할 수 있습니다.

기본 데이터는 처음에 최소 작업 ID 수로 *1* 의 임계값을 사용합니다(`MinimumWorkThresholdForLabelPrinting`). 따라서 시스템이 작업 ID가 두 개 이상인 웨이브를 처리할 때 별도의 트랜잭션에서 웨이브 레이블의 작업 기반 처리를 사용합니다. 테스트 환경의 `WHSWaveTaskProcessingThresholdParameters` 테이블에서 이 데이터를 수동으로 삽입하거나 업데이트할 수 있습니다. 프로덕션 환경에서 설정을 변경하려면 Microsoft 지원에 문의하여 업데이트를 요청해야 합니다.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>태스크 기반 웨이브 라벨 인쇄 사용 시 웨이브 처리 로직 변경

웨이브 레이블 처리가 웨이브 태스크 처리 임계값을 초과하면 태스크 기반 처리가 시작됩니다. 웨이브 템플릿에 맞는 다음 웨이브 처리에서 웨이브 라벨 인쇄는 작업 생성 직후 독립 실행형 *ttsbegin*/*ttscommit* 트랜잭션으로 실행됩니다. 웨이브 템플릿에 작업 해제(차단 해제)가 자동으로 실행되도록 구성되어 있으면 웨이브 라벨 인쇄 프로세스가 성공적으로 완료된 후에만 발생합니다.

웨이브 레이블 생성에 실패하면(예: 작업 수량을 웨이브 레이블 수량으로 변환하지 못하고 오류가 발생하는 경우) 해당 트랜잭션만 실패합니다. 이전에 생성된 작업은 고정된 상태로 유지됩니다. 오류를 수정하고 웨이브 레이블을 인쇄하려면 다음 단계를 따르세요.

1. **창고 관리 \> 아웃바운드 웨이브 \> 배송 웨이브 \> 모든 웨이브** 로 이동합니다.
1. 그리드에서 관련 웨이브를 선택합니다.
1. 작업 창의 **웨이브** 탭에 있는 **인쇄** 그룹에서 **웨이브 레이블** 을 선택합니다.
1. 화면의 지시에 따라 인쇄용 라벨을 보냅니다.
1. 작업 창의 **웨이브** 탭에서 **웨이브** 그룹에 있는 **릴리스** 를 선택하여 선택한 웨이브의 작업을 수동으로 해제합니다.

## <a name="additional-resources"></a>추가 리소스

- [웨이브 레이블 인쇄](configure-wave-label-printing.md)
- [웨이브 중 작업 생성 일정 잡기](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
