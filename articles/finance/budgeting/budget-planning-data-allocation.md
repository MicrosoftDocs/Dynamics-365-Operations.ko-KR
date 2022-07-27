---
title: 예산 계획 데이터 할당
description: 이 토픽에서는 Microsoft Dynamics 365 Finance에서 사용할 수 있는 할당 방법과 사용 방법에 대해 설명합니다.
author: panolte
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6011c4c005a26720fd57caca0075483404f41b4
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451018"
---
# <a name="budget-planning-data-allocation"></a>예산 계획 데이터 할당

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Finance에서 사용할 수 있는 할당 방법과 사용 방법에 대해 설명합니다.  

예상 금액을 정확하게 나타내기 위해 여러 가지 방법으로 예산 계획의 데이터를 배포할 수 있습니다.

## <a name="allocation-methods"></a>할당 방법
세 가지 할당 방법(기간에 걸쳐 할당, 차원에 할당 및 원장 할당 규칙 사용)은 동일한 예산 계획의 라인을 기반으로 하는 예산 계획 라인을 생성할 수 있습니다. 세 가지 다른 방법(예산 계획에서 집계, 배포 및 복사)을 사용하여 다른 예산 계획에서 예산 계획 라인을 생성할 수 있습니다. 6가지 할당 방법 모두에 대해 대상 시나리오를 지정합니다. 대상 시나리오는 원본 시나리오와 같거나 원본 시나리오와 다를 수 있습니다. 또한 새 라인을 예산 계획에 추가할지 아니면 예산 계획의 현재 라인을 대체할지 여부를 지정할 수 있습니다.

> [!NOTE] 
> 이전에 상위 계획에서 수행된 배포 또는 기타 수정에 사용된 시나리오와 다른 집계에는 고유한 시나리오를 사용해야 합니다.  

[![기간 할당 방법에 걸쳐 할당.](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**기간에 걸쳐 할당** – 기간 할당 범주는 대상 시나리오의 기간에 걸쳐 원본 예산 계획 시나리오의 예산 계획 라인을 할당하는 데 사용됩니다. 원본 금액은 기간 할당 범주에 정의된 퍼센트 및 일자를 기준으로 대상 시나리오의 여러 라인에 지정됩니다.         

[![차원 할당 방법에 할당.](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**차원에 할당** – 예산 계획 라인은 선택한 예산 할당 기간에 정의된 백분율 및 재무 차원을 기반으로 원본 예산 계획 시나리오에서 대상 시나리오의 하나 이상의 라인에 할당됩니다.           

![차트 집계.](./media/aggregatechart-300x230.png)
**집계** – 예산 계획 라인은 연관된(하위) 예산 계획의 원본 예산 계획 시나리오에서 상위 예산 계획의 대상 시나리오로 집계됩니다. 이 방법을 사용하면 조직의 하위 수준에서 준비된 예산 금액을 상위 수준에서 통합할 수 있습니다.          

[![차트 분배.](./media/distributechart-300x230.png)](./media/distributechart.png)
**분배** – 예산 계획 라인은 연결된 계획 조직 단위의 재무 차원을 기반으로 상위 예산 계획의 원본 예산 계획 시나리오에서 연결된(하위) 예산 계획의 대상 시나리오로 분배됩니다. 이 방법을 사용하면 조직의 상위 수준에서 준비된 예산 금액을 보다 현지화된 검토를 위해 분산할 수 있습니다.           

[![원장 할당 규칙.](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**원장 할당 규칙 사용** – 예산 계획 라인은 선택한 원장 할당 규칙에 따라 원본 예산 계획 시나리오에서 대상 시나리오로 분배됩니다. 

[![예산 계획에서 복사.](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**예산 계획에서 복사** – 분배 할당 방식과 마찬가지로 관련 예산 계획의 라인을 기반으로 대상에 예산 계획 라인이 생성됩니다. 그러나 이 방법의 경우 원본 예산 계획이 상위일 필요는 없지만 예산 계획 계층에서 더 높은 수준에 있을 수 있습니다. 이 할당 방법은 통합 금액이 원래 훨씬 더 높은 수준에서 예산 책정된 경우에 유용하며 상위 수준 승인을 받기 전에 자세한 검토 및 조정을 위해 조직의 하위 수준으로 이전되어야 합니다.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>예산 계획에서 할당 방법 사용
예산 계획 페이지에서 할당을 수행하려면 할당할 라인을 선택한 다음 **예산 할당** 을 클릭합니다.

[![예산 할당 버튼.](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

다음으로 할당 방법을 선택합니다. 그러면 선택한 방법에 따라 나머지 필드가 설정됩니다. 이러한 필드에는 예산 계획 데이터의 원본 및 대상, 대량 조정을 단순화하기 위해 대상 금액이 생성될 때 지정된 요소로 원본을 곱할 수 있는 옵션이 포함됩니다. **계획에 추가** 옵션을 설정할 수도 있습니다. 기존 예산 계획 라인을 바꾸려면 **아니요** 를 선택하고, 기존 예산 계획 라인을 유지하고 할당된 금액에 대해 새 라인을 추가하려면 **예** 를 선택합니다.

## <a name="automating-allocations-during-a-workflow"></a>워크플로 중 할당 자동화
한 가지 강력한 기능을 사용하면 예산 계획 워크플로의 일부로 할당을 자동으로 수행할 수 있습니다. 예산 계획이 워크플로를 통해 이동함에 따라 자동화된 작업은 지정된 예산 계획 단계에서 할당을 호출할 수 있습니다. 

자동 할당을 설정하려면 먼저 **예산 계획 구성** 페이지에서 할당 일정을 생성해야 합니다. 할당 일정은 자동 할당이 실행될 때 사용할 할당 방법과 다양한 할당 옵션의 값을 정의합니다(설명은 이전 섹션 참조). 

다음으로 **예산 계획 구성** 페이지에서 단계 할당을 만듭니다. 단계 할당은 예산 계획 워크플로 및 단계에 할당 일정을 할당합니다. 

마지막으로 원하는 워크플로 단계에서 예산 계획 단계 할당을 위한 자동화된 작업을 추가합니다. 다음 예에서는 두 개의 예산 계획 단계 할당(빨간색 윤곽선)이 워크플로에 삽입되었습니다.

[![예산 계획 단계 할당.](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
