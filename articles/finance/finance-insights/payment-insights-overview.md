---
title: 고객 지불 예측
description: 이 항목에서는 고객의 일반적인 지불 관행을 더 잘 이해하는 데 도움이 되는 지불 예측 기능에 관해 설명합니다. 이 기능은 또한 수금 프로세스를 다른 때보다 일찍 시작해야 하는 상황을 식별하는 데 도움이 될 수 있습니다.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 04897e3a7765264ab2e664422caa928c49b9cc61
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451372"
---
# <a name="customer-payment-predictions"></a>고객 지불 예측

[!include [banner](../includes/banner.md)]

이 항목에서는 고객의 일반적인 지불 관행을 더 잘 이해하는 데 도움이 되는 지불 예측 기능에 관해 설명합니다. 이 기능은 또한 수금 프로세스를 다른 때보다 일찍 시작해야 하는 상황을 식별하는 데 도움이 될 수 있습니다.

## <a name="overview"></a>개요

조직에서 고객이 언제 송장 대금을 지불할지 예측하기는 어렵습니다. 이러한 통찰력 부족으로 인해 다음과 같은 문제가 발생할 수 있습니다.

- 현금 흐름 예측의 정확도 하락
- 너무 늦게 시작되는 수금 프로세스
- 지불 불이행으로 이어질 수 있는 고객에게 주문 출시

고객 지불 예측은 조직에서 고객 송장이 지불될 시기를 예측하는 데 도움이 됩니다. 따라서 정시 지불 가능성을 높이는 데 도움이 되는 수금 전략을 만들 수 있습니다.

## <a name="predictions"></a>예측

지불 예측을 통해 조직은 늦게 지불될 가능성이 있는 송장을 식별하여 비즈니스 프로세스를 개선할 수 있습니다. 조직은 해당 정보를 사용하여 정시 지불 가능성을 높이는 조치를 취할 수 있습니다.

고객 지불 예측 기능은 기계 학습 모델을 사용하여 고객이 미결제 송장 대금을 지불할 시기를 더 정확하게 예측합니다. 이 기계 학습 모델에는 과거 송장, 지불 및 고객 데이터가 포함됩니다.

이 기능은 각 미결 송장에 대해 세 가지 지불 가능성을 지정합니다.

- 정시에 지불될 확률
- 늦게 지불될 확률
- 매우 늦게 지불될 확률

이 기능은 또한 예상 지불에 대한 집계 보기를 제공합니다.

[![지불 예측의 집계 보기.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

각 송장에 정시 지불 가능성이 지정됩니다. 정시 지불 가능성이 50% 미만인 송장에는 수금원의 주의가 필요할 수 있음을 나타내기 위해 빨간색 원으로 태그가 지정됩니다.

[![지불 가능성 목록](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

고객 지불 예측 기능은 예측을 설명하는 컨텍스트 정보도 제공합니다. 이 정보에는 예측에 영향을 미친 주요 요인, 고객과의 현재 비즈니스 상태 및 고객의 과거 지불 행동에 대한 세부 정보가 포함됩니다.

많은 기업에서 수금 프로세스는 사후 대응 활동이었습니다. 즉, 송장 만기가 될 때까지 수금 프로세스가 시작되지 않습니다. 조직은 고객 지불 예측으로 더욱 능동적으로 수금에 대처할 수 있습니다. 더는 수금 프로세스를 시작하기 위해 거래 만기가 될 때까지 기다릴 필요가 없습니다. 대신 지불 예측 기능을 사용하여 사전 수금으로 정시에 지불될 가능성을 높일 수 있는지를 결정할 수 있습니다.

## <a name="methodology"></a>방법론

과거에는 일반적으로 인공 지능(AI) 솔루션을 개발하고 배포하기가 어려웠습니다. 이 프로세스에는 사용 가능한 AI 솔루션을 공식화, 개발, 배포 및 유지 관리하기 위해 시간이 지남에 따라 작업하는 데이터 과학자, 주제 전문가(SME) 및 엔지니어가 포함된 팀이 필요했습니다. 고객 지불 예측을 통해 Microsoft Dynamics 365 Finance에서 AI 솔루션을 쉽게 배포하고 사용할 수 있습니다. Microsoft는 Microsoft AI Builder를 기반으로 구축된 AI 솔루션을 사전 패키징하고 있습니다. 따라서 사용자는 한 번의 마우스 클릭으로 AI 솔루션을 배포하고 지능형 예측의 이점을 활용할 수 있습니다. 예측의 정확도가 만족스럽지 않으면 고급 사용자가 다시 한번 마우스 클릭으로 AI Builder 확장 환경으로 들어가서 예측을 생성하는 데 사용되는 필드를 선택하거나 선택 취소할 수 있습니다. 준비되면 모델을 "학습"하고 변경 사항을 게시할 수 있습니다. 새로 훈련된 모델은 Dynamics 365 Finance에서 예측을 생성하기 위해 자동으로 선택됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
