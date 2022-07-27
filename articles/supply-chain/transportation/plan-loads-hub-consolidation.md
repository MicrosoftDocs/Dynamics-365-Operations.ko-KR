---
title: 허브 통합 개요를 사용하여 로드 계획
description: 이 문서에서는 다른 창고에서 동일한 고객에게 상품을 배송할 때 또는 동일한 창고에 있는 여러 공급업체로부터 상품을 받을 때 허브에서 발송물을 통합하는 기능에 대해 설명합니다.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "92273"
- intro-internal
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd47a5745719873cc491d93b9a98a7fde609fe38
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449755"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>허브 통합 개요를 사용하여 로드 계획

[!include [banner](../includes/banner.md)]

이 문서에서는 다른 창고에서 동일한 고객에게 상품을 배송할 때 또는 동일한 창고에 있는 여러 공급업체로부터 상품을 받을 때 허브에서 발송물을 통합하는 기능에 대해 설명합니다.

여러 창고에서 동일한 고객에게 상품을 배송하거나 여러 공급업체에서 동일한 창고로 상품을 배송할 때 허브에서 배송을 통합하는 것이 유용할 수 있습니다.

## <a name="building-loads"></a>부하 구축
허브 통합을 사용하려면 먼저 **운송 관리 매개 변수** 페이지에서 **운송 중 계획** 옵션을 활성화해야 합니다. 통합이 발생할 허브도 생성해야 합니다. 다음 다이어그램은 허브 통합의 예를 보여줍니다. 이 경우 다른 창고의 판매 주문이 동일한 고객에게 전달됩니다. 기본 로드는 **적재 계획 워크벤치** 페이지를 사용하여 일반적인 방식으로 판매 주문을 기반으로 생성됩니다. 고객에게 배송되기 전에 허브에 두 개의 로드를 통합하려면 **적재 계획 워크벤치** 페이지의 **운송** 필드에서 **허브 통합** 을 선택합니다. 각 로드에 대해 올바른 허브를 선택하면 로드가 "하차" 대상으로 허브를 갖게 됩니다. 또한 **적재 계획 워크벤치** 페이지의 **수요와 공급** 섹션에 두 개의 "운송 요청 라인"이 있습니다. 그런 다음 이 두 라인을 새 로드에 추가할 수 있습니다. 이 새 로드에는 판매 주문 라인이 모두 있으며 허브가 "픽업" 주소로, 고객 A가 "하차" 대상으로 지정됩니다. 그런 다음 3개의 로드가 다른 로드와 마찬가지로 평가되고 라우팅될 준비가 됩니다. 각 화물에 대해 시스템이 제안하는 운송업체를 선택할 수 있습니다. [![허브 통합.](./media/hubconsol.jpg)](./media/hubconsol.jpg) 동일한 방법을 사용하여 여러 이전 주문에 대한 로드를 통합할 수도 있습니다. 이 경우 앞의 다이어그램에서 고객 A는 창고입니다. 또는 로드가 다른 공급업체에서 동일한 창고로 배달되는 여러 구매 주문에 대한 로드를 통합할 수 있습니다. 둘 이상의 통합 허브를 가질 수 있으며 다른 창고에서 오는 더 많은 로드를 위해 여러 허브에서 통합할 수 있습니다. 기본 로드를 구축하고 허브 통합 옵션을 사용한 후 통합 운송 요청 라인을 사용하여 새 로드를 구축합니다. 그런 다음 로드를 평가하고 라우팅합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]