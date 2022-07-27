---
title: 고객 지불 인사이트(미리 보기)
description: 이 항목에서는 개별 고객의 일반적인 지불 방식에 관한 이해를 높이는 데 도움이 되는 지불 인사이트 기능에 관해 설명합니다. 이 기능은 다른 경우보다 일찍 수금 프로세스를 시작하는 것을 정당화하는 상황을 식별하는 데 도움이 될 수 있습니다.
author: ShivamPandey-msft
ms.date: 11/06/2019
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
ms.openlocfilehash: d359e3ceef0fb7213d52aeb265da2e75120ae223
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451420"
---
# <a name="customer-payment-insights-preview"></a>고객 지불 인사이트(미리 보기)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 항목에서는 개별 고객의 일반적인 지불 방식에 관한 이해를 높이는 데 도움이 되는 지불 인사이트 기능에 관해 설명합니다. 이 기능은 다른 경우보다 일찍 수금 프로세스를 시작하는 것을 정당화하는 상황을 식별하는 데 도움이 될 수 있습니다. 

## <a name="overview"></a>개요

고객이 언제 송장 대금을 지불할지 예측하기는 어렵습니다. 이러한 통찰력 부족은 현금 흐름 예측의 정확도 저하, 너무 늦게 시작되는 수금 프로세스, 지불 불이행으로 이어질 수 있는 고객에게 주문 출시 등으로 이어집니다. 고객 지불 인사이트(미리 보기)는 조직에서 고객 송장이 지불될 시기를 예측하는 데 도움이 됩니다. 이 정보는 조직이 정시 지불 가능성을 높이는 수금 전략을 수립하는 데 도움이 될 수 있습니다. 

## <a name="predictions"></a>예측

지불 예측을 통해 조직은 늦게 지불될 가능성이 있는 송장을 쉽게 식별하고 제시간에 지불받을 가능성을 높이는 적절한 조치를 취할 수 있도록 지원하여 비즈니스 프로세스를 개선할 수 있습니다.

고객 지불 인사이트(미리 보기)는 과거 송장, 지불 및 고객 데이터를 활용하는 기계 학습 모델을 사용하여 고객이 미결제 송장을 지불할 시기를 보다 정확하게 예측합니다.

고객 지불 인사이트(미리 보기)는 각 미결제 송장에 대해 세 가지 지불 가능성을 예측할 수 있습니다.

-   정시에 결제될 확률 
-   늦게 결제될 확률
-   매우 늦게 결제될 확률

고객 지불 인사이트(미리 보기)는 예상 지불에 대한 집계 보기도 제공하여 조직이 정시, 늦음 및 매우 늦음 세 가지 범주 중 하나에서 고객에게 기대할 수 있는 총 지불 금액을 이해하는 데 도움이 됩니다.

[![지불 예측의 집계 보기.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

또한 각 송장에 정시 지불 가능성이 지정됩니다. 정시 지불할 확률이 50% 미만인 경우 송장에 수금 주의가 필요할 수 있음을 나타내는 빨간색 원으로 태그가 지정됩니다. 

[![지불 가능성 목록](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

고객 지불 인사이트(미리 보기)는 예측에 영향을 미친 주요 요인, 고객과의 현재 비즈니스 상태, 과거 고객 지불 행동에 대한 세부 정보 등 예측을 설명하는 컨텍스트 정보도 제공합니다. 많은 기업에서 수금 프로세스는 사후 대응 활동이었으며 송장 기한이 될 때까지 수금 프로세스가 시작되지 않습니다. 

고객 지불 인사이트(미리 보기)를 사용하면 조직에서 수금에 대해 보다 능동적으로 대처할 수 있습니다. 더는 수금 프로세스를 시작하기 위해 거래 만기가 될 때까지 기다릴 필요가 없습니다. 대신 지불 예측 기능을 사용하여 사전 수금으로 정시에 지불될 가능성을 높일 수 있는지를 결정할 수 있습니다. 지불 예측은 또한 기업이 수금 프로세스를 일찍 시작하는 것을 정당화하는 데 필요한 정보를 제공합니다.

## <a name="methodology"></a>방법론

AI 솔루션을 개발하고 배포하는 일은 어렵습니다. 사용 가능한 AI 솔루션을 공식화, 개발, 배포 및 유지 관리하려면 데이터 과학자, 주제 전문가 및 엔지니어로 구성된 팀이 오랜 기간 작업해야 합니다. Microsoft는 Finance에서 AI 솔루션을 쉽게 배포하고 사용할 수 있도록 했습니다. Microsoft AI Builder를 기반으로 Finance에 AI 솔루션을 사전 패키징하고 있습니다. 최종 사용자는 한 번의 버튼 클릭으로 AI 솔루션을 배포하고 지능형 예측의 이점을 활용할 수 있습니다. 조직이 예측의 정확성에 만족하지 않는 경우 고급 사용자는 다시 한번 클릭하여 AI Builder 확장 환경으로 들어가서 예측을 생성하는 데 사용되는 필드를 선택하거나 선택 취소할 수 있습니다. 준비되면 변경 사항을 학습 및 게시할 수 있으며 새로 학습된 모델은 재무 예측을 위해 자동으로 선택됩니다.

## <a name="how-to-get-customer-payment-insights-preview"></a>고객 지불 인사이트를 사용하는 방법(미리 보기)

고객 결제 인사이트(미리 보기)에 관심이 있는 경우 [고객 결제 인사이트(미리 보기)](mailto:fiap@microsoft.com)로 이메일을 보내주세요.

## <a name="privacy-notice"></a>개인정보취급방침

미리 보기는 (1) Dynamics 365 Finance and Operations 서비스보다 개인 정보 보호 및 보안 조치를 덜 활용할 수 있으며 (2) 이 서비스에는 서비스 수준 약정에 포함되지 않고 (3) 법적 또는 규정 준수 요구 사항이 적용되는 개인 데이터 또는 기타 데이터를 처리하는 데 사용해서는 안 되며 (4) 지원이 제한됩니다.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]