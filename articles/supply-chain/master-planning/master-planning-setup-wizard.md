---
title: 기준 계획 설정 마법사(비디오 포함)
description: 이 항목에서는 기준 계획 설정 마법사를 실행하여 기준 계획을 설정하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 10/21/2019
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
ms.openlocfilehash: 453184a3fed567b3a09e5e45e7f904bcf855dd6d
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2021
ms.locfileid: "8449611"
---
# <a name="master-planning-setup-wizard"></a>기준 계획 설정 마법사

[!include [banner](../includes/banner.md)]

이 항목은 **기준 계획 설정 마법사** 를 위한 가이드를 제공합니다. 매개 변수 제안을 계산하는 방법을 설명하고 비즈니스 요구 사항에 따라 여러 회사에서 기준 계획을 설정하는 방법을 보여주는 예도 제공합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3YnSB]

[Dynamics 365 Supply Chain Management의 기준 계획 설정 마법사](https://youtu.be/c-e6n-8rZb4) 비디오(위 참조)는 YouTube에서 제공되는 [금융 및 운영 재생 목록](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)에 포함되어 있습니다.


## <a name="specific-requirements-of-your-company"></a>회사의 특정 요구 사항

마법사의 첫 번째 페이지는 회사의 특정 요구 사항에 대해 묻습니다. 이러한 질문에 대한 귀하의 답변이 정확할 필요는 없지만 법인에 대해 있을 예정인 항목 및 계획 주문의 수에 대한 대략적인 근사치를 제공할 수 있어야 합니다. 귀하의 답변은 귀하가 선택한 기준 계획뿐만 아니라 귀하의 법인에 적용되는 매개 변수를 구성하는 데 사용됩니다. 다음 섹션에서는 계산되는 매개 변수와 사용되는 공식에 대해 설명합니다.

### <a name="number-of-threads"></a>스레드 수

- **다음 항목 중 하나를 제조하는 경우:** 스레드 수 = 계획 주문 수 ÷ 1,000
- **다음 항목 중 하나를 제조하지 않는 경우:** 스레드 수 = 항목 수 ÷ 1,000

계산된 스레드 수가 사용 가능한 스레드 수의 75%를 초과하는 경우 각 고객이 사용할 수 있는 스레드 수의 75%로 제한됩니다. (사용 가능한 스레드 수는 각 고객에 대해 결정됩니다.)

자세한 내용은 [스레드 수](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads)를 참조하세요.

### <a name="bundle-size"></a>번들 크기

번들 크기는 **1** 로 설정됩니다. 이 값은 기준 계획의 성능을 향상시키는 데 도움이 되므로 종종 최상의 값입니다.

자세한 내용은 [도우미 작업 번들의 작업 수](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle)를 참조하세요.

### <a name="firming-bundle-size"></a>확정 번들 크기

- **다음 항목 중 하나를 제조하는 경우:** 확정 번들 크기는 **10** 과 번들 계산의 두 값 중 더 큰 값으로 설정됩니다.
- **다음 항목 중 하나를 제조하지 않는 경우:** 확정 번들 크기는 **50** 과 번들 계산의 두 값 중 더 큰 값으로 설정됩니다.

번들 계산 = (계획 주문 수 × (확정 타임펜스 ÷ 적용 범위 타임펜스) ÷ 스레드 수) ÷ 10

### <a name="cache-size"></a>캐시 크기

캐시 크기는 **최대값** 으로 설정됩니다. 이 값은 기준 계획의 성능을 향상시키는 데 도움이 되므로 종종 최상의 값입니다.

자세한 내용은 [작업 번들의 작업에 시간 할당](/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle)을 참조하세요.

### <a name="manufacturing-setup"></a>제조 설정

항목을 제조하는 경우, **제조 설정** 페이지는 마법사의 뒷부분에 나타납니다.

## <a name="scope-of-the-current-plan"></a>현재 계획의 범위

마법사의 **현재 계획의 범위** 페이지에서 향후 기준 계획에서 다양한 요구 사항을 고려하고 계산하는 것과 관련된 질문에 답합니다. 각 질문은 기능을 사용할지 여부와 구성 방법을 묻습니다.

예를 들어, 예측 계획 기능의 경우 마법사는 "예상 수요를 충족하기 위해 계획 주문이 제안되도록 기준 계획에서 예측 계획을 사용하시겠습니까?"라고 묻습니다.

다음 옵션을 사용할 수 있습니다.

- **아니요** – 기준 계획은 예측을 수행하기 위해 계획된 주문을 제안하지 않습니다. **기준 계획** 페이지의 **타임펜스** 탭(**기준 계획 \> 설정 \> 계획 \> 기준 계획**)에서 마법사는 **예측 계획(타임펜스)** 옵션을 **예** 로 설정하고 일수를 **0**(제로)으로 설정됩니다. 이 설정은 적용 범위 그룹에 지정된 타임펜스를 무시합니다. 일수가 **0**(영)으로 설정되어 있기 때문에 기능이 사용되지 않습니다.
- **예, 이 기준 계획에 정의된 대로** – 기준 계획이 예측 수요를 충족하기 위해 계획 주문을 제안할 일 수를 입력할 수 있는 필드가 사용 가능하게 됩니다. 마법사는 **예측 계획(타임펜스)** 옵션을 **예** 로 설정하고 일수를 **기준 계획** 페이지의 **타임펜스** 탭에 있는 **예측 계획** 에 입력한 일수로 설정합니다. 이 설정은 적용 범위 그룹에 설정된 값을 무시합니다.
- **예, 적용 범위에 정의된 대로** – 마법사가 **예측 계획(타임펜스)** 옵션을 **아니요** 로 설정합니다. 적용 범위 그룹에 지정된 타임펜스는 예측을 계획할 기간을 지정하는 데 사용됩니다.

이 페이지의 나머지 질문과 답변은 동일한 스키마를 따릅니다.

- **아니요** – **예측 계획(타임펜스)** 옵션이 **예** 로 설정되고 일수는 **0**(영)으로 설정됩니다.
- **예, 기준 계획에 정의된 대로** – **예측 계획(타임펜스)** 옵션이 **예** 로 설정됩니다. 입력한 일수가 사용되며 적용 범위 그룹에 설정된 값보다 우선 적용됩니다.
- **예, 적용 범위 그룹에 정의된 대로** – **예측 계획(타임펜스)** 옵션이 **아니요** 로 설정됩니다.

자세한 내용은 [작업 예약](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling)을 참조하세요.

## <a name="scheduling-options"></a>예약 옵션

**예약 옵션** 페이지는 마법사의 첫 페이지에 있는 "계획된 항목을 제조합니까?" 질문에 **예** 라고  답한 경우에만 나타납니다.

이 페이지의 첫 번째 질문("작업을 개별 작업으로 분할해야 합니까?")에 대한 대답은 **기준 계획** 페이지의 **일반** 탭에서 예약 방법을 결정합니다.

- **예** – 작업 예약이 사용됩니다.
- **아니요** – 작업 예약이 사용됩니다.

자세한 내용은 [작업 예약](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) 및 [작업 예약](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling)을 참조하세요.

## <a name="updates-of-demand-and-supply"></a>수요와 공급 업데이트

**수요와 공급 업데이트** 페이지의 질문은 확정, 조치 메시지 및 지연과 관련이 있습니다.

기준 계획 설정은 이전 섹션에서 설명한 것과 동일한 스키마에 따라 귀하의 답변을 기반으로 업데이트됩니다.

- **아니요** – **기준 계획** 페이지의 **타임펜스** 옵션이 **예** 로 설정되고 일수는 **0**(영)으로 설정됩니다.
- **예, 기준 계획에 정의된 대로** – **타임펜스** 옵션이 **예** 로 설정됩니다. 입력한 일수가 사용되며 적용 범위 그룹에 설정된 값보다 우선 적용됩니다.
- **예, 적용 범위 그룹에 정의된 대로** – **타임펜스** 옵션이 **아니요** 로 설정됩니다.

계산된 지연의 경우 마법사의 질문에 대한 답변은 **기준 계획** 페이지의 **계산된 지연** 탭에서 해당 매개 변수를 업데이트합니다.

## <a name="summary-of-your-changes"></a>변경 사항 요약

마법사의 마지막 페이지에는 귀하의 응답을 기반으로 권장되는 변경 사항이 표시됩니다. 여기에는 설정의 값(**현재 설정**)과 마법사가 권장하는 값(**새 구성**)이 모두 표시됩니다.

새 구성에서 매개 변수를 수정할 수도 있습니다. 매개 변수는 법인에 적용되는 매개 변수와 선택한 기준 계획에만 적용되는 매개 변수로 구분됩니다. 마법사를 사용하여 변경할 수 있는 모든 설정 매개 변수를 보려면 페이지 하단에서 **모든 매개 변수 표시** 를 선택합니다. 그런 다음 매개 변수를 변경할 수 있습니다.

마지막으로 **마침** 을 선택하면 새 구성이 적용됩니다. **취소** 를 선택하면 변경 사항이 적용되지 않습니다.

## <a name="examples"></a>예

이 섹션에서는 각 비즈니스의 필요에 따라 설정이 어떻게 변경될 수 있는지 보여주기 위해 두 개의 가상 회사의 설정에 대해 설명합니다.

### <a name="example-1-contoso-manufacturer"></a>예시 1: Contoso Manufacturer

Contoso Manufacturer는 스피커를 생산하는 제조 회사입니다. 다양한 공급업체로부터 최종 스피커에 사용되는 다양한 원자재와 부품을 구매합니다. 다음은 공급 및 제조의 특징 중 일부입니다.

- 회사에서 제조하는 최종 항목에는 BOM(자재 명세서) 구조가 있습니다.
- 모든 최종 항목 및 구성 요소는 기준 계획에 의해 계획됩니다. 수동 계획이 완료되지 않았습니다.
- 각 최종 항목의 생산을 위해 작업 경로가 정의됩니다.
- 제조 공장은 최종 항목을 생산합니다. 구성 요소를 처리하는 데 사용되는 정의된 수의 밀링 및 드릴링 머신이 있습니다. 다양한 구성 요소는 이러한 기계에 의해 처리되어야 합니다.
- 많은 공급자가 있습니다. 항목의 평균 리드 타임은 일주일입니다. 동일한 공급업체의 항목 그룹에는 7주의 리드 타임이 있습니다.

마법사에서 Contoso Manufacturer에 대해 다음 값이 입력됩니다.

- **적용 범위:**

    - **질문:** "계획 기간의 일수를 지정하시겠습니까?"
    - **답변:** "예, 적용 범위 그룹에 정의된 대로"

    항목의 리드 타임은 매우 다르기 때문에 Contoso는 미래의 같은 기간 동안 모든 항목을 계획할 필요가 없습니다. 항목에 대한 적용 범위 그룹이 생성됩니다. 리드 타임이 유사한 항목은 동일한 적용 그룹에 할당됩니다. 각 적용 그룹(즉, 적용 타임펜스)에 대한 계획 기간은 대략 리드 타임에 1주일의 여유를 더한 것입니다. 그런 다음 기준 계획은 리드 타임을 기반으로 항목이 미리 계획되도록 합니다.

    따라서 이 예에서는 두 개의 적용 범위 그룹이 생성됩니다. 한 적용 범위 그룹에는 2주의 적용 타임펜스가 있고 다른 하나는 8주의 적용 타임펜스가 있습니다.

    **예, 이 기준 계획에 정의된 대로** 가 답변으로 선택된 경우 입력한 일수는 전체 항목 중 가장 긴 리드 타임을 초과해야 합니다. 그러나 많은 항목이 지금까지 미리 계획할 필요가 없기 때문에 많은 계획 주문이 계산되지만 사용되지 않습니다. 따라서 기준 계획 런타임이 증가합니다.

- **예약:**

    - **질문:** "개별 작업으로 나누어 작업을 예약해야 합니까?"
    - **답변:** "예."

    Contoso Manufacturing은 작업 현장에서 수행될 개별 작업을 계획하고 예약해야 합니다. 따라서 작업 예약을 사용합니다.

- **용량:**

    - **질문:** "리소스의 용량을 사용하여 예약하시겠습니까?"
    - **답변:** "예, 이 기준 계획에 정의된 대로" **10일** 이 입력됩니다.

    밀링 및 드릴링 머신의 수는 제한되어 있습니다. 생산 계획은 이 제한을 고려하고 리소스의 용량에 따라 적시에 작업을 정렬해야 합니다. 즉, 예약된 작업은 리소스의 제한에 따라 다시 계획됩니다. 계획은 정의된 기간 외에 리드 타임을 사용합니다. (계획된 생산 주문은 겹칠 수 있습니다.) 항목의 생산 리드 타임이 7일이므로 기준 계획을 위한 리소스의 용량은 10일 동안 고려됩니다.

- **시퀀싱:**

    - **질문:** "제품의 시퀀스 값을 사용하여 계획 주문의 시퀀스를 지정하시겠습니까?"
    - **답변:** "예, 적용 범위 그룹에 정의된 대로"

    각 최종 항목의 생산을 위해 경로가 정의됩니다. 따라서 기준 계획은 정의된 경로에 따라 제 시간에 주문을 예약합니다.

- **분해:**

    - **질문:** "BOM의 모든 요소에 대한 주문을 계획하시겠습니까(상위 및 모든 하위 항목에 대한 계획)?"
    - **답변:** "예, 적용 범위 그룹에 정의된 대로"

    생산에 사용되는 모든 항목은 계획되어야 합니다. 항목의 리드 타임이 매우 다르기 때문에 기준 계획은 적용 범위 그룹을 사용할 때 더 나은 성능을 보입니다. 이번에도 1주일의 여유를 입력할 수 있으며, 적용 범위와 같은 시간에 분해가 가능합니다.

### <a name="example-2-contoso-retailer"></a>예시 2: Contoso Retailer

Contoso Retailer는 패션 업계의 유통 회사입니다. 기준 계획을 사용하여 예측된 판매를 기반으로 구매 주문을 해야 하는 시기를 계산합니다. 다음은 몇 가지 특징입니다.

- Contoso Retailer는 수요 예측을 사용하여 판매를 예측합니다. 구매 주문은 예측에 따라 계획됩니다.
- 상점은 보충을 위해 요청을 사용합니다.
- 본점에서 각 점포까지의 리드 타임은 전항목 약 2주입니다.

마법사에서 Contoso Retailer에 대해 다음 값이 입력됩니다.

- **수요 예측:**

    - **질문:** "예측 수요를 충족하기 위해 계획 주문이 제안되도록 기준 계획에서 예측 계획을 사용하시겠습니까?"
    - **답변:** "예, 이 기준 계획에 정의된 대로"

    Contoso는 판매를 예측하기 위해 수요 예측을 포함했습니다. 따라서 기준 계획은 예측을 수행하기 위해 계획 주문을 권장해야 합니다.

- **확정:**

    - **질문:** "기준 계획에서 계획 주문을 생산 또는 구매 주문과 같은 주문 문서로 자동 확정하기를 원하십니까?"
    - **답변:** "예, 이 기준 계획에 정의된 대로" **1일** 이 입력됩니다.

    Contoso Retailer는 계획된 구매 주문에서 직접 구매 주문을 생성하므로 계획된 구매 주문이 자동으로 확정되는 경우에 유용합니다. 회사는 매일 기준 계획을 실행하기 때문에 하루의 확정 타임펜스가 다음 날에 필요한 모든 주문을 자동으로 확정합니다.

- **승인된 요청:**

    - **질문:** "소매점을 보충하기 위해 승인된 요청의 수요를 포함하시겠습니까?"
    - **답변:** "예, 이 기준 계획에 정의된 대로" **1일** 이 입력됩니다.

    Contoso는 매장에서 승인된 요청을 사용하여 해당 매장을 보충할 계획된 구매 주문을 만듭니다. 기준 계획은 매일 실행되기 때문에 마지막 날의 구매 요청이 계획에 포함됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]