---
title: 비용 요소 차원
description: 원가 회계의 핵심 기둥 중 하나인 비용 요소 차원은 원가가 어디로 흘러가는지 분류하고 추적하는 데 사용됩니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 667fb81a2c1c8f564c09fe8fb7921c7aff75920bfa4326e82078583df61576e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450286"
---
# <a name="cost-element-dimensions"></a>비용 요소 차원

[!include [banner](../includes/banner.md)]

원가 회계의 핵심 기둥 중 하나인 비용 요소 차원은 원가가 어디로 흘러가는지 분류하고 추적하는 데 사용됩니다. 

비용 요소는 계정 차트의 비용 관련 항목에 해당합니다. 기본적으로 비용이 유입될 수 있는 비즈니스의 가장 낮은 수준에 있는 모든 유형의 요소가 될 수 있습니다. 개념으로서의 비용 요소는 원장 계정에서 모든 비용 관련 리소스에 이르기까지 다양합니다. 현재 원가 회계는 원장 계정을 지원합니다.

## <a name="two-types-of-cost-elements"></a>두 가지 유형의 비용 요소
비용 요소에는 기본 비용 요소와 보조 비용 요소의 두 가지 유형이 있습니다. 다음 표에서는 두 유형의 차이점을 설명합니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>기본 비용 요소</strong></td>
<td><strong>보조 비용 요소</strong></td>
</tr>
<tr class="even">
<td>기본 비용 요소는 재무 회계에서 원가 회계로의 원가 흐름을 나타냅니다. 비용 요소 구조는 총계정원장의 손익 계정 구조에 해당하며, 여기서 비용 요소는 주 계정에 해당할 수 있습니다. 비즈니스 요구 사항에 따라 모든 주 계정이 반드시 비용 요소로 표시되는 것은 아닙니다. 기본 비용 요소의 예는 다음과 같습니다.
<ul>
<li>판매 제품 원가(COG)</li>
<li>간접 재료비</li>
<li>인건비</li>
<li>에너지 비용</li>
</ul></td>
<td>보조 원가 요소는 이러한 비용이 원가 회계에서만 생성되고 사용되기 때문에 내부적으로 원가 흐름을 나타냅니다. 비용 출처를 추적할 수 있도록 보장하는 데 사용됩니다. 이러한 비용 요소는 비용 할당 및 간접비 계산에 사용됩니다. 보조 비용 요소의 예는 다음과 같습니다.
<ul>
<li>생산 비용</li>
<li>생산, 재료 및 마케팅 간접비</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>비용 요소 차원 및 비용 요소 차원 구성원
비용 요소는 *비용 요소 차원* 이라고 합니다. 개별 차원 값을 *비용 요소 차원 구성원* 이라고 합니다. 예를 들어, 법정 보고의 기준이 되는 미국 계정 차트 구조(COA)가 있습니다. 이 COA는 비용 요소 차원으로 사용됩니다. 기본 비용 요소인 계정은 원가 회계에서 비용 요소 차원 구성원으로 표시됩니다. 다음 스크린샷은 실제 주 계정이 비용 요소 차원 구성원인 비용 요소 차원으로 주 계정의 예를 보여줍니다. 

[![비용 요소 차원인 주 계정의 스크린샷.](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>데이터 커넥터를 통해 비용 요소 차원 구성원 가져오기
원가 회계에서 비용 요소 차원 구성원을 쉽게 설정하기 위해 사전 구축된 데이터 커넥터 또는 사용자 지정 구축을 사용하여 하나 이상의 소스 시스템에서 기본 비용 요소를 검색할 수 있습니다.

## <a name="implementation-considerations"></a>구현 고려 사항
비용 요소는 가장 낮은 수준의 비용 세부 정보를 나타내므로 비용 요소 구조를 구현할 때 관리 보고에 필요한 모든 비용 요소가 포함되어 있는지 확인해야 합니다. 비용 관리를 위해 적절한 수의 비용 요소를 찾는 것이 어려울 수 있습니다. 수천 개의 비용 요소가 있으면 각 비용 요소를 제어하기 어려울 수 있습니다. 또는 비용 요소를 그룹화하고 집계된 수준에서 비용 제어를 관리할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]