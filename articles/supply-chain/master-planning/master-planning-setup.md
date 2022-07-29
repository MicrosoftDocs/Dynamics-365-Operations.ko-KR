---
title: 기준 계획 설정
description: 이 항목에서는 기준 계획을 설정하는 데 사용되는 다양한 중요한 전략 및 매개변수에 대해 설명합니다.
author: ChristianRytt
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 6d33fd53dd088ae4c6b4680d2604f783a3e1a5a0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449344"
---
# <a name="set-up-master-planning"></a>기준 계획 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 기준 계획을 설정하는 데 사용되는 다양한 중요한 전략 및 매개변수에 대해 설명합니다. 여기에는 기준 계획에서 사용하는 계획 유형에 대한 개요가 포함되어 있으며 비즈니스 요구 사항에 따라 사용해야 하는 계획 전략이 설명되어 있습니다. 또한 계획에 영향을 미치는 주요 매개변수를 설명하고 이러한 매개변수가 제안된 계획 주문에 어떻게 영향을 미치는지 설명합니다.

## <a name="types-of-master-plans"></a>기준 계획의 종류

기준 계획에는 정적 및 동적의 두 가지 유형의 계획이 있습니다. 각 유형은 다른 용도로 설계되었습니다. 최상의 성능을 위해 시나리오에 적절한 계획을 사용하는 것이 좋습니다.

### <a name="static-plan"></a>정적 계획

정적 계획은 다음 기준 계획이 실행될 때까지 수요와 공급의 변경에 관계없이 변경되지 않은 상태로 유지됩니다.

정적 계획은 제안된 주문을 승인하고 확정하는 데 사용됩니다. 다양한 회사 직원(예: 구매자 또는 생산 계획자)이 자신의 결정을 기반으로 일상 업무 및 활동을 수행하는 데 사용할 수 있는 운영 계획입니다.

정적 계획은 재생성도 지원합니다. 기준 계획이 실행될 때마다 완전히 새로운 최적화된 계획이 계산되고 승인되지 않은 기존 주문은 삭제됩니다.

### <a name="dynamic-plan"></a>동적 계획

동적 계획은 일반적으로 정적 계획의 복사본으로 시작하지만 마스터 데이터가 변경될 때마다 업데이트할 수 있습니다. 예를 들어 데이터가 변경되면 새 판매 주문이 생성됩니다.

동적 계획은 임시 계획에 사용됩니다. 이를 통해 회사는 다른 사람들이 작업 프로세스에 사용하는 고정 계획을 방해하지 않고 주문 변경 네트워크와 항목 가용성을 모니터링할 수 있습니다. 특히 CTP(Capable to Promise)에 사용됩니다. 동적 계획은 순 소요량이 주문 페이지(예: 판매 주문, 구매 주문 또는 생산 주문 페이지)에서 열릴 때 기본 계획입니다.

동적 계획은 순 변경을 사용합니다. 따라서 더 빠른 실행 시간을 보장하는 데 도움이 됩니다.

## <a name="strategies-for-using-master-plans"></a>기준 계획 사용 전략

기준 계획에서 하나의 계획 또는 두 개의 계획을 사용할 수 있습니다. 사용하는 전략은 비즈니스 요구 사항에 따라 다릅니다.

### <a name="one-plan-strategy"></a>원계획 전략

단일 계획 전략의 경우 정적 계획과 동적 계획에 대해 동일한 기준 계획을 사용합니다. 이 전략은 일반적으로 주문을 이행하는 계획을 시뮬레이션할 필요가 없는 재고 제작 시나리오에 사용됩니다.

단일 계획 전략은 일반적으로 소매 및 유통 산업에서 사용되거나 SLA(서비스 수준 계약) 또는 리드 타임을 기반으로 판매 배송 날짜가 확인되는 경우에 사용됩니다. 계획의 경우 CTP 없이 배송 날짜 제어를 사용할 수 있습니다.

시뮬레이션을 해야 하는 경우 시뮬레이션이 필요한 항목에 대해 계획을 다시 실행할 수 있습니다. 주문 시뮬레이션이 생성하는 계획 주문은 일반적으로 확정됩니다.

### <a name="two-plan-strategy"></a>투계획 전략

두 가지 계획 전략의 경우 정적 계획과 다른 동적 계획을 사용합니다. 투계획 전략은 일반적으로 판매 주문 시뮬레이션을 수행하고 판매 주문의 정확한 배송 날짜를 계산해야 하지만 계산이 일상적인 작업에 영향을 미치지 않아야 하는 주문 구성 및 주문 제작 시나리오에 사용됩니다. 이러한 시뮬레이션은 항상 동적 계획에서 수행됩니다. 이중 계획 전략은 예를 들어 자동차 및 OEM(주문자 상표 부착) 산업에서 유용합니다.

투계획 전략의 경우 납기일 제어 CTP를 사용할 수 있습니다. CTP를 사용하면 동적 계획에서 자동으로 실행을 트리거합니다.

### <a name="setting-up-the-plans"></a>계획 수립

**기준 계획** 페이지에서 계획을 작성할 수 있습니다(**기준 계획 \> 설정 \> 계획 \> 기준 계획**).

**기준 계획 매개 변수** 페이지(**기준 계획 \> 설정 \> 기준 계획 매개 변수**)에서 **현재 정적 기준 계획** 및 **현재 동적 기준 계획** 필드를 설정하여 정적 계획 및 동적 계획에 사용할 계획을 지정할 수 있습니다. 원계획 전략을 사용하려면 **현재 정적 기준 계획** 및 **현재 동적 기준 계획** 필드에서 동일한 계획을 선택합니다.

## <a name="types-of-planning-methods"></a>계획 방법의 유형

기준 계획을 실행하는 데 세 가지 계산 방법(재생 및 순 변경)을 사용할 수 있습니다. 각 방법은 실행될 때 다른 계획을 생성합니다.

**기준 계획 실행** 대화 상자에서 계획 방법을 지정합니다. 이 대화 상자를 열려면 **기준 계획 \> 기준 계획 \> 실행 \> 기준 계획** 으로 이동하거나 **기준 계획** 작업 영역에서 **실행** 을 선택합니다.

### <a name="regeneration"></a>다시 생성

다시 생성 계획 방법은 확정되지 않은 기존 계획 주문을 삭제합니다. 모든 요구 사항을 기반으로 새로운 계획 주문을 생성합니다. 다시 생성은 정적 계획에 사용할 수 있는 유일한 계획 방법입니다.

- 공급 변경이 고려됩니다. 이러한 변경에는 예측 변경이 포함됩니다.
- 이 방법은 **기간** 적용 코드를 따릅니다.
- 이 방법은 제품 대체 기능(PI)을 지원합니다.

### <a name="net-change"></a>순변화

순변화 계획 방법은 마지막 기준 계획 실행 이후 생성되거나 변경된 소요량을 처리하는 계획 주문을 생성합니다. 이 방법이 실행될 때 공급 변경은 고려되지 않습니다. 시스템은 새로운 공급을 고려하지 않으며 이전에 생성된 계획 주문이 더 이상 필요하지 않은 경우 삭제되지 않습니다. 순변화 계획 방법은 다시 생성 방법보다 빠르게 실행됩니다. 동적 계획에만 사용할 수 있습니다.

- 모든 요구 사항에 대해 조치 날짜와 미래가 업데이트됩니다.
- 이 방법은 **기간** 적용 코드를 따르지 않습니다.
- 이 방법은 계획에서 선택한 경우에도 예측을 충족하지 않습니다.
- 이 방법은 제품 대체 기능(PI)을 지원하지 않습니다.

### <a name="net-change-minimized"></a>순변화 최소화

순변화 최소화 계획 방법은 마지막 기준 계획 스케줄링 실행 이후 생성되거나 변경된 소요량만 포함하는 계획 주문을 생성합니다. 이 방법의 경우 순변화 방법과 달리 조치 날짜와 미래 날짜는 새 요구 사항이나 변경된 요구 사항에 대해서만 업데이트됩니다. 이 계획 방법은 동적 계획에만 사용할 수 있습니다.

## <a name="types-of-scheduling-methods"></a>예약 방법의 유형

각 계획에 대해 **기준 계획** 페이지의 **일반** 빠른 탭(**기준 계획 \> 설정 \> 계획 \> 기준 계획**)에서 생산 주문에 사용되는 예약 방법을 선택해야 합니다. 작업 수준 및 작업 수준에서 생산을 예약할 수 있습니다.

### <a name="operations-scheduling"></a>작업 예약

작업 일정을 사용하여 시간 경과에 따른 생산 프로세스의 일반적인 추정치를 제공할 수 있습니다. 작업 예약은 생산 경로에 대한 작업을 작업으로 확대하지 않습니다. 작업 예약에 대한 자세한 내용은 [작업 예약](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling)을 참조하세요.

### <a name="job-scheduling"></a>작업 예약

작업 예약은 각 작업이 개별 작업 또는 작업으로 분할되는 보다 자세한 예약 방법입니다. 작업 예약에는 용량에 대한 정보가 포함됩니다. 일반적으로 즉시 또는 단기 기간 동안 작업 현장에서 개별 작업을 예약하는 데 사용됩니다. 작업 예약에 대한 자세한 내용은 [작업 예약](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling)을 참조하세요.

## <a name="time-fences-in-days"></a>일 단위의 타임펜스

각 계획에 대해 향후 기준 계획에서 다양한 요구 사항 및 기타 고려 사항을 계산해야 하는 기간을 선택할 수 있습니다. 기간은 *타임펜스* 로 알려져 있습니다. 기준 계획에서 최상의 성능을 얻으려면 비즈니스 요구 사항에 맞게 다양한 타임펜스를 조정하는 것이 좋습니다. 각 계획에 대해 **기준 계획** 페이지(**기준 계획 \> 설정 \> 계획 \> 기준 계획**)의 **일 단위의 타임펜스** 빠른 탭에서 타임펜스를 찾을 수 있습니다.

> [!NOTE]
> 타임펜스는 다양한 요구 사항 및 기타 고려 사항이 기준 계획에 의해 계산되는 미래의 시간을 나타냅니다. 이 페이지에서 선택한 타임펜스는 적용 범위 그룹에 정의된 타임펜스를 재정의합니다. 이것은 타임펜스 옵션을 예로 설정하고 날짜를 정의하면 적용 범위 그룹에 정의된 타임펜스를 재정의한다는 것을 의미합니다. 아니요로 설정하면 적용 범위 그룹에 타임펜스가 정의됩니다. 마지막으로 옵션을 사용하지 않거나 사용해야 하는 경우(예: 작업 메시지를 사용하지 않으려는 경우) **예** 로 설정한 다음 타임펜스를 **0**(영)일로 설정합니다.

### <a name="coverage"></a>적용 범위

적용 범위 타임펜스는 예약 기간 또는 수요가 포함되어야 하는 범위를 나타냅니다. 즉, 계획 범위를 나타냅니다.

**적용 범위** 옵션을 **예** 로 설정하면 기준 일정 계획 중에 항목에 대해 정의된 적용 범위 타임펜스를 재정의할 수 있습니다. 이 경우 기준 일정 계획 계산이 요구 사항을 포함해야 하는 일 수를 입력합니다. 적용 타임펜스는 현재 일자로부터 앞으로 계산됩니다. 현재 날짜 이전에 발생하는 요구 사항은 항상 처리됩니다.

> [!NOTE]
> 기준 계획에서 최상의 성과를 얻으려면 적용 범위 타임펜스를 계획 대상 기간에 맞게 조정하는 것이 좋습니다.

### <a name="freeze"></a>고정

고정 타임펜스는 새로운 마스터 일정이 실행될 때 기존 계획 주문이 변경되지 않는 기간을 나타냅니다. 계획 주문이 고정되었으며 새로운 계획 주문이 제안되지 않습니다.

**고정** 옵션을 **예** 로 설정하면 기준 일정 계획 중에 항목에 대해 정의된 고정 타임펜스를 재정의할 수 있습니다. 이 경우 계획 활동을 고정해야 하는 일수를 입력합니다. 이 기간 동안에는 새로운 계획 주문이 생성되지 않으며 기존 계획 주문을 변경할 수 없습니다.

### <a name="firming"></a>확정

확정 타임펜스는 계획 주문이 생산 및 구매 주문으로 자동 변환되는 시간 범위를 나타냅니다. 이 프로세스는 *계획 주문의 자동 확정* 이라고도 합니다.

**확정** 옵션을 **예** 로 설정하면 기준 일정 계획 중에 항목에 대해 정의된 확정 타임펜스를 재정의할 수 있습니다. 이 경우 계획된 구매 주문과 계획 생산 주문이 자동으로 확정되어야 하는 일수를 입력합니다. 확정 타임펜스는 기준 일정 계획 날짜로부터 앞으로 계산됩니다. 계획된 구매 주문의 자동 확정은 항목이 공급업체와 연관된 경우에만 발생할 수 있습니다.

### <a name="forecast-plan"></a>계획 예측

계획 예측 타임펜스는 향후 기준 계획에서 수요가 예측된 항목에 대한 계획 주문을 생성하는 기간을 나타냅니다.

**계획 예측** 옵션을 **예** 로 설정하면 기준 일정 계획 중에 항목에 대해 정의된 계획 예측 타임펜스를 재정의할 수 있습니다. 이 경우 계획 예측의 판매 예측이 기준 계획에 포함되어야 하는 일수를 입력합니다.

### <a name="capacity"></a>생산 능력

용량 타임펜스는 주문을 예약할 때 시스템이 리소스의 최대 용량을 고려하는 미래의 시간을 나타냅니다. 즉, 계획은 항목에 대한 생산 루트를 사용하여 생산 주문을 예약하고 생산 루트의 리소스와 각 리소스의 최대 능력을 고려합니다.

**용량** 옵션을 **예** 로 설정하면 기준 일정 계획 중에 항목에 대해 정의된 용량 타임펜스를 재정의할 수 있습니다. 이 경우 계획 생산 주문에 대해 용량을 계획해야 하는 일수를 입력합니다. 기준 일정 계획은 항목에 대한 활성 생산 경로를 사용하고 소요 일자로부터 뒤로 스케줄링합니다. 계획된 생산 주문에 대한 요구 일자가 용량 타임펜스 밖에 있는 경우 리드 타임은 항목의 납품 시간에 따라 결정됩니다. 용량 타임펜스는 현재 일자로부터 앞으로 계산됩니다.

### <a name="action-message"></a>작업 메시지

작업 메시지는 공급 계획을 최적화하는 데 도움이 되도록 기존 공급 주문을 변경할 수 있음을 제안합니다. 예를 들어 주문을 앞당기거나 연기하거나 주문 수량을 늘리거나 줄이도록 권장할 수 있습니다.

**작업 메시지** 옵션을 **예** 로 설정하면 기준 일정 계획 중에 항목에 대해 정의된 작업 메시지 타임펜스를 재정의할 수 있습니다. 이 경우 기준 일정 계획이 요구 사항에 대한 작업 메시지를 생성해야 하는 일 수를 입력합니다. 작업 메시지 타임펜스는 현재 일자로부터 앞으로 계산됩니다.

작업 메시지에 대한 자세한 내용은 [작업 메시지](/dynamics365/unified-operations/supply-chain/master-planning/action-messages)를 참조하세요.

> [!NOTE]
> 작업 메시지를 계산하면 기준 계획 실행 시간이 길어집니다. 작업 메시지가 정기적으로 분석 및 적용되지 않는 경우(매일, 매주 등) 기준 계획 실행 중에 계산을 끄는 것이 좋습니다. 계산을 끄려면 **기준 계획** 페이지에서 실행 중인 기준 계획에 대해 **작업 메시지** 타임펜스를 **0** 으로 설정합니다. 또한 모든 커버리지 그룹에 대해 **조치 메시지** 설정이 꺼져 있는지 확인하세요.

### <a name="calculated-delays"></a>계산된 지연

향후 계획 주문의 지연 가능성이 감지되고 보고되는 시간을 지정할 수 있습니다. 이러한 방식으로 가능한(지연된) 배송 날짜를 예약할 수 있습니다.

계획 주문을 요청한 날짜에 이행할 수 없는 경우 리드 타임, 자재 및 용량 가용성을 기반으로 트랜잭션의 가장 빠른 이행 날짜로 계획됩니다.

### <a name="approved-requisitions-time-fence"></a>승인된 요청 타임 펜스

구매 요청 수요에 대한 계획 주문을 생성하도록 기준 계획을 설정할 수 있습니다. **기준 계획** 페이지의 **일반** 빠른 탭에서 **요청 포함** 옵션을 **예** 로 설정합니다. 그런 다음 승인된 구매 요청의 목적이 보충인 경우 기준 계획은 이를 이행하기 위해 해당 계획 주문을 자동으로 생성합니다. 보충 방법은 조직의 항목에 대해 설정된 공급 정책에 따라 결정됩니다. 보충 요청이 생성되고 승인된 후에는 추가 사용자 작업이 필요하지 않습니다.

**일 단위의 타임펜스** 빠른 탭에서 **승인된 요청 타임펜스** 옵션을 **예** 로 설정하여 기준 일정 계획 동안 항목에 대해 정의된 승인된 요청 타임펜스를 재정의할 수 있습니다. 이 경우 보충 목적이 있는 승인된 요청의 수요가 기준 일정 계획에 포함되어야 했던 과거 일수를 입력합니다. 예를 들어, 지난 10일 동안 생성된 승인된 요청의 이행되지 않은 납기 경과 수요만 고려하고 계획하도록 지정할 수 있습니다.

### <a name="sequencing"></a>시퀀싱

시퀀싱을 사용하면 완제품과 연관된 시퀀싱 속성을 기반으로 계획 주문을 정렬할 수 있습니다. 포장용 생산 주문을 준비하는 데 자주 사용됩니다. 예를 들어 색상과 크기에 따라 특정 순서로 상자를 포장하는 데 사용할 수 있습니다.

**시퀀싱** 옵션을 **예** 로 설정하면 향후 작업이나 작업의 시퀀싱을 지정할 수 있습니다. 타임펜스가 길수록 기준 계획이 실행되는 데 더 오래 걸립니다.

### <a name="calculated-delays"></a>계산된 지연

지연 옵션은 주문이 실행 가능한 계획 날짜를 갖도록 보장하는 데 도움이 됩니다. **기준 계획** 페이지의 **계산된 지연** 빠른 탭에서 다음 옵션을 사용할 수 있습니다.:

- **계획 주문이 기준 계획 실행 날짜 이전에 생성되지 않았는지 확인** - 과거 날짜에 주문을 예약할 수 없도록 하려면 이 옵션을 **예** 로 설정합니다.
- **요구 사항 날짜에 계산된 지연 추가**(**계획된 구매 주문** 아래) – 이 옵션을 **예** 로 설정하여 요구 사항에 계산된 지연을 추가합니다.
- **요구 사항 날짜에 계산된 지연 추가**(**계획된 생산 주문** 아래) – 이 옵션을 **예** 로 설정하여 요구 사항에 계산된 지연을 추가합니다.
- **요구 사항 날짜에 계산된 지연 추가**(**계획된 전송** 아래) – 이 옵션을 **예** 로 설정하여 요구 사항에 계산된 지연을 추가합니다.
- **요구 사항 날짜에 계산된 지연 추가**(**계획된 칸반** 아래) – 이 옵션을 **예** 로 설정하여 요구 사항에 계산된 지연을 추가합니다.

**요구 사항 날짜에 계산된 지연 추가** 옵션을 **예** 로 설정하여 요구 사항에 지연을 추가하면 시스템에서 리소스의 능력을 고려하고 실현 가능한 계획 주문을 생성합니다. 계획 주문 날짜를 다시 계산하면 기준 계획의 실행 시간이 늘어납니다. 따라서 지연을 사용할 필요가 없는 경우 옵션을 **아니요** 로 설정합니다.

## <a name="positive-and-negative-days"></a>양수 및 음수 일수

양수 및 음수 일수는 기준 계획이 계획 주문 및 조치를 제안하는 방법에 영향을 줍니다. 양수 및 음수 일수는 항목의 항목 적용 범위 그룹에 설정됩니다. 다양한 적용 범위 그룹을 정의하고 **적용 범위 그룹** 페이지(**기준 계획 \> 설정 \> 적용 범위 \> 적용 범위 그룹**)에서 매개 변수를 설정할 수 있습니다.

### <a name="positive-days"></a>양수 일수

양수 일수는 미래 기준 계획이 미래 수요를 충족하기 위해 현재 재고 또는 입고를 고려하는 기간을 나타냅니다. 예를 들어 양수 일수가 **100** 으로 설정된 경우, 현재 재고를 사용하여 향후 100일 동안 수요를 충족할 수 있습니다. 현재 날짜로부터 150일 후에 주문이 있는 경우 기준 계획은 항목의 현재고가 주문을 충족할 수 있더라도 해당 수요를 충족하기 위해 계획 주문을 생성합니다. 리드 타임이 짧고 빠르게 움직이는 항목의 경우 먼 미래의 주문에 대해 현재고를 사용하고 싶지 않을 수 있습니다. 이 빠르게 움직이는 경우 현재 보유 재고가 빠르게 소진되고 미래 수요를 제시간에 충족하기 위해 더 많은 주문을 할 수 있습니다. 이는 항목의 짧은 리드 타임으로 인해 가능합니다.

양수 일수는 행동 메시지에도 영향을 미칩니다. 예를 들어, 시스템은 미래의 양수 일수 내에 있는 수요를 포함하도록 계획된 구매 주문을 늘리도록 권장할 수 있습니다. 양수 일수가 **100** 으로 설정된 경우, 그리고 현재 날짜로부터 30일 이내에 항목에 대한 수요가 있는 경우 시스템은 해당 수요를 충족시키기 위해 계획 주문을 생성합니다. 현재 날짜로부터 90일 이내에 동일한 항목에 대한 수요가 있는 경우 시스템은 현재 날짜로부터 30일 이내에 주문 수량을 늘리도록 권장하여 해당 주문이 90일 이내에 수요를 처리합니다. 그러나 현재 날짜로부터 150일 이내에 항목에 대한 수요가 있는 경우 시스템은 이미 계획된 주문 수량을 늘리는 것을 권장하지 않습니다. 대신 새 계획 주문이 생성됩니다.

일반적으로 양수 일수는 항목의 가장 긴 리드 타임과 적용 타임펜스 사이의 숫자로 설정됩니다. 정기적으로 조달되거나 생산되는 항목을 양수 일수가 항목의 리드 타임과 동일한 적용 범위 그룹에 할당하는 것이 좋습니다.

### <a name="negative-days"></a>음수 일수

음수 일수는 늦게 항목 수령이 허용되는 방법을 나타냅니다. 마이너스 재고가 있거나 재고가 충분하지 않을 때 새로운 보충을 주문하기 전에 기다릴 수 있는 일수를 나타냅니다. 음수 일수는 항목에 대해 새 구매 주문을 생성해야 합니까, 아니면 항목이 지연될 것임을 알고 있음에도 기존 구매를 사용해야 합니까?라는 질문에 대답합니다.

예를 들어, 현재 날짜로부터 15일 후에 항목에 대한 판매 주문이 있습니다. 같은 항목에 대한 구매 주문도 있습니다. 이 구매 주문은 현재 날짜로부터 20일 이내에 접수됩니다. 시스템에서 해당 판매 주문에 대한 구매 주문을 생성하기를 원하십니까, 아니면 판매 주문을 제시간에 이행할 수 없는 경우에도 기존 주문을 사용하시겠습니까? 음수 일수가 **5** 보다 작게 설정된 경우 항목이 최대 5일까지 지연될 수 있음을 나타내기 위해 시스템은 판매 주문을 충족하기 위해 새로운 계획 구매 주문을 생성합니다. 음수 일수가 **5** 보다 크게 설정된 경우, 시스템은 항목에 대해 기존 주문을 사용합니다.

음수 일수는 기준 계획의 성과에도 영향을 미칩니다. 음수 일수를 높게 설정하면 많은 작업 메시지가 생성됩니다.

항목의 리드 타임보다 짧은 숫자로 음수 일수를 설정하는 것이 좋습니다.

### <a name="dynamic-negative-days"></a>동적 음수 일수

동적 음수 일수는 항목의 리드 타임과 지정한 음수 일수를 고려합니다. 시스템은 다음 공식을 사용하여 계산된 음수 일수 타임펜스를 기반으로 새로운 계획 구매 발주를 생성합니다.

리드 타임 + 음수 날짜 + 현재 날짜 – 요구 날짜

시스템은 이 타임펜스 내에 있는 계획 공급 주문만 사용하고 타임펜스 외부에 새로운 계획 주문을 생성합니다. 동적 음수 일수의 장점은 개별 제품 리드 타임이 포함되어 기존 주문을 재사용하고 리드 타임으로 인한 지연으로 인해 나중에 끝날 새 계획 주문을 생성하지 않도록 한다는 것입니다. 

자세한 내용은 [음수 일수 및 동적 음수 일수](/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]