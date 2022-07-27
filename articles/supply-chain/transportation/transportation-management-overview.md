---
title: 운송 관리 개요
description: 이 토픽에서는 Supply Chain Management의 운송 관리 기능에 대한 개요를 제공합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "30251"
- intro-internal
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68082a736fd45c6701324a1492087c1b16bf0566
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449740"
---
# <a name="transportation-management-overview"></a>운송 관리 개요

[!include [banner](../includes/banner.md)]

이 토픽에서는 Supply Chain Management의 운송 관리 기능에 대한 개요를 제공합니다.

운송 관리를 통해 회사 운송을 사용할 수 있으며 인바운드 및 아웃바운드 주문에 대한 공급업체 및 라우팅 솔루션을 식별할 수도 있습니다. 예를 들어 배송에 대해 가장 빠른 경로 또는 가장 저렴한 요금을 식별할 수 있습니다. 다음 표에서는 운송 관리를 사용하기 위한 주요 시나리오를 설명합니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>시나리오</th>
<th>운송 관리가 도움이 되는 방법</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>운송 활동을 위해 외부 물류 제공업체를 이용합니다.</td>
<td>인바운드 및/또는 아웃바운드 운송에 운송 관리를 사용합니다.</td>
</tr>
<tr class="even">
<td>자체 보유 차량으로 배송/픽업이 가능하며 배송비는 고객 부담입니다.</td>
<td>아웃바운드 프로세스의 경우 운송 관리를 사용하여 운송 비용을 결정하고 고객에게 전달할 수 있습니다. 그러나 운송업체 송장 조정 프로세스는 필요하지 않습니다.</td>
</tr>
<tr class="odd">
<td>자체 보유 차량은 배송/픽업이 가능하지만, 제품 가격에 운송비가 포함되어 있어 배송료는 고객에게 전가되지 않습니다.</td>
<td>많은 운송 관리 기능이 필요하지 않습니다. 그러나 운송 관리를 사용하여 운송 요금을 결정하고 그에 따라 판매 가격을 조정할 수 있습니다.</td>
</tr>
<tr class="even">
<td>물류 서비스는 동일한 회사의 다른 법인에서 제공합니다.</td>
<td><ul>
<li>다른 법인을 다른 운송업체처럼 취급하여 운송 관리를 사용할 수 있습니다. 법인 간의 경제적 거래를 자동화할 수 없습니다. 따라서 이러한 거래를 수동으로 처리해야 합니다(예: 구매 주문 생성).</li>
<li>물류 서비스를 제공하는 법인에서 운송 관리를 사용하여 운송 요금을 결정할 수 있습니다.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a>Supply Chain Management의 운송 계획
운송 관리에서 운송 계획은 주문을 기반으로 하거나 해당 주문을 기반으로 생성된 배송을 기반으로 할 수 있습니다. 선적은 항상 특정 시점에 존재하지만 운송 계획에는 필요하지 않습니다. 이전 주문은 아웃바운드 시나리오의 일부이며 판매 주문과 함께 계획할 수 있습니다. 

![도면을 로드합니다.](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>인바운드 운송
공급업체로부터 품목을 주문하고 품목을 창고로 배송해야 하는 경우 품목 운송을 직접 준비할 수 있습니다. Supply Chain Management를 사용하여 인바운드 로드의 운송 및 입고를 계획할 수 있습니다. 다음 그림은 인바운드 화물에 대한 운송 계획을 위한 비즈니스 프로세스 흐름을 보여줍니다. 

![인바운드 화물 운송을 위한 비즈니스 프로세스 흐름입니다.](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>아웃바운드 운송
회사 창고에서 고객에게 특정 품목을 배송하기 위해 아웃바운드 로드를 계획하고 처리할 수 있습니다. Supply Chain Management를 사용하여 아웃바운드 로드의 운송 및 배송을 계획할 수 있습니다. 다음 그림은 배송을 위한 아웃바운드 로드를 계획하고 처리하기 위한 비즈니스 프로세스 흐름을 보여줍니다. 

![아웃바운드 로드 계획 및 처리.](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>부하 구축
Supply Chain Management는 볼륨 기반 부하 구축 전략이라는 부하 구축 전략을 제공합니다. 이 전략을 사용하면 하중 템플릿에서 높이와 무게에 대해 지정된 최대값을 사용하거나 새 값을 입력하여 설정을 무시할 수 있습니다. 이 전략을 사용하려면 **로드 빌드 워크벤치** 페이지의 **설정** 빠른 탭에 있는 **로드 빌드 전략** 필드에서 선택하세요. 또한 AOT(애플리케이션 개체 트리)에서 새 클래스를 생성하여 고유한 로드 구축 전략을 추가할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]