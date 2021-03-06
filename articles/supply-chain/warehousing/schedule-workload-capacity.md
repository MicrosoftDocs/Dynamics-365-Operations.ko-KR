---
title: 워크로드 용량 예약
description: 이 토픽에서는 창고 또는 전체 창고에 있는 작업자의 워크로드 용량을 설정하고 예약하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f66eb1b2f35d19aba0f4f8f2804577a62ac14e79
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449515"
---
# <a name="schedule-workload-capacity"></a>워크로드 용량 예약

[!include[banner](../includes/banner.md)]

창고에 대한 워크로드 용량을 예약할 수 있으며 개별 창고에 있는 작업자의 현재 및 미래 워크로드를 예측할 수도 있습니다. 전체 창고에 대한 워크로드를 예측하거나 수신 및 발신 워크로드에 대해 개별적으로 워크로드를 예측할 수 있습니다.

선택한 창고에 대한 워크로드 출력을 예측하려면 해당 창고에 대해 기준 일정 계획 데이터를 사용할 수 있어야 합니다. 자세한 내용은 [기준 계획 개요](../master-planning/master-plans.md)를 참조하세요.

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>창고에 대한 워크로드 예약 및 보기

창고에 대한 워크로드 용량을 예약하려면 하나 이상의 창고에 대한 워크로드 설정을 생성한 다음 워크로드 설정을 기준 계획과 연결합니다. 워크로드 용량 설정에서 들어오고 나가는 트랜잭션의 무게 또는 부피에 대한 제한을 정의할 수 있습니다. 각 창고에 대해 둘 이상의 설정을 생성한 다음 설정을 개별 기준 계획과 연결할 수도 있습니다. 예를 들어, 인력의 계절적 변화를 수용하기 위해 이 접근 방식을 사용할 수 있습니다.

창고 작업자가 들어오는 워크로드와 나가는 워크로드 모두에 대한 트랜잭션으로 작업하는 경우 워크로드가 결합된 보기에서 예상되도록 창고 용량 설정을 구성할 수 있습니다.

창고에 대한 워크로드를 예약하고 보려면 다음 작업을 완료해야 합니다.

1. 워크로드 용량 설정을 생성하고 하나 이상의 창고에 대한 워크로드 용량 제한을 정의합니다.
2. 워크로드 용량 설정을 기준 계획과 연결하여 워크로드 예측을 생성하고 해당 예측이 적용되는 기간을 지정합니다.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>창고에 대한 워크로드 용량 설정 생성

1. **재고 관리** \> **설정** \> **창고 모니터링** \> **워크로드 용량** 을 선택합니다.
2. 작업 창에서 **새로 만들기** 를 선택하여 워크로드 용량 설정을 생성합니다.
3. **창고** 빠른 탭에서 **새로 만들기** 를 선택한 다음 행에 값을 입력하여 창고를 워크로드 용량 설정과 연결합니다.
4. **워크로드 용량** 보고서가 수신 및 발신 트랜잭션에 대한 총 워크로드를 하나의 보기에 표시해야 하는 경우 **결합된 인바운드 및 아웃바운드 워크로드** 선택란을 선택합니다.
5. **트랜잭션 유형** 빠른 탭에서 워크로드 제한이 적용될 수신 및 발신 트랜잭션 유형을 선택합니다.

    > [!NOTE]
    > 들어오는 워크로드와 나가는 워크로드 모두에 대해 하나 이상의 트랜잭션 유형을 선택해야 합니다.

#### <a name="define-limits-for-volume-or-weight"></a>부피 또는 무게에 대한 한계 정의

창고 인력과 관련된 제한 사항에 따라 부피 또는 중량 제한을 설정할 수 있습니다. 지정한 제한은 **워크로드 용량** 보고서에서 볼 수 있는 워크로드 용량 예측에 포함됩니다.

항목의 부피 및 중량에 대한 정보를 투영하려면 모든 제품에 대해 하나의 재고 항목의 표준 부피와 하나의 재고 항목의 중량을 지정해야 합니다. 필수 필드는 **출시된 제품 세부 정보** 페이지의 **재고 관리** 빠른 탭에 있는 다음 필드 그룹에서 사용할 수 있습니다.

- 처리
- 실제 치수
- 무게 측정

이 정보가 올바르게 지정되지 않은 경우 **워크로드 용량** 보고서를 생성할 때 메시지를 수신합니다. 그런 다음 보고서에서 드릴다운하여 향후 워크로드를 예측하는 데 필요한 누락된 정보를 식별할 수 있습니다.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>워크로드 용량 설정을 기준 계획과 연결

1. **재고 관리** \> **정기** \> **워크로드 예약** 을 선택합니다.
2. **기준 계획** 필드에서 워크로드 예측에 사용할 기준 계획을 선택합니다.
3. **일 수** 필드에 워크로드 예측이 적용되는 일 수를 지정합니다.
4. **워크로드** 필드에서 기준 계획과 연결할 워크로드 설정을 선택합니다.

### <a name="view-workload-capacity"></a>워크로드 용량 보기

1. **재고 관리** \> **조회 및 보고서** \> **실제 재고 보고서** \> **워크로드 용량** 을 선택합니다.
2. **열 수** 필드에서 보고서에 표시할 열 수를 지정합니다.
3. **주문 유형** 필드에서 **계획 및 확인됨**, **계획됨** 또는 **확인됨** 을 선택하여 보고서에 투영할 주문 유형을 나타냅니다.
4. **로드 유형** 필드에서 로드 유형을 선택하여 워크로드 용량을 부피 또는 무게에 대해 예측할지 여부를 지정합니다.
5. **워크로드 용량** 필드에서 워크로드 용량 설정을 선택합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]