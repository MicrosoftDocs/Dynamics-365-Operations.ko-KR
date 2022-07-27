---
title: 초기 고객 지불 예측 모델 평가
description: 이 항목에서는 고객 지불 예측 모델을 이해하고 그 효과를 평가하기 위해 수행할 수 있는 단계를 설명합니다.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 874c6e938681537a0420eece6835a4c2124e11fc
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451366"
---
# <a name="evaluate-the-initial-customer-payment-prediction-model"></a>초기 고객 지불 예측 모델 평가

[!include [banner](../includes/banner.md)]

이 항목에서는 Finance Insights를 켠 다음 첫 번째 모델을 생성하고 훈련한 후 예측 모델을 평가하는 방법을 설명합니다. 이 항목에서는 고객 지불 예측 모델을 다룹니다. 이 항목에서는 고객 지불 예측 모델을 이해하고 그 효과를 평가하기 위해 수행할 수 있는 단계를 설명합니다.

## <a name="getting-details-about-the-model"></a>모델에 대한 세부 정보 얻기

Microsoft Dynamics 365 Finance의 **Finance Insights 매개 변수** 페이지에서 정확도 점수 옆에 **모델 정확도 개선** 링크가 표시됩니다.

[![모델 정확도 개선 링크.](./media/prediction-model.png)](./media/prediction-model.png)

이 링크는 현재 모델에 대해 자세히 알아보고 개선 단계를 수행할 수 있는 AI Builder를 연결합니다. 다음 그림은 열린 페이지를 보여줍니다.

[![AI Builder.](./media/what-to-predict.png)](./media/what-to-predict.png)

열리는 페이지에는 다음 정보가 표시됩니다.

- **성능** 섹션에서 모델 성능 등급은 모델 품질에 대한 관점을 제공합니다. 이 등급에 대한 자세한 내용은 AI Builder 설명서의 [예측 모델 성능](/ai-builder/prediction-performance)을 참조하세요.
- **가장 영향력 있는 데이터** 섹션은 다양한 입력 유형의 데이터가 모델에 얼마나 중요한지 보여줍니다. 이 목록과 해당 비율을 평가하여 귀하가 비즈니스 및 시장에 대해 아는 내용과 정보가 일치하는지 확인할 수 있습니다.

    [![예측 모델에 대한 성능 및 가장 영향력 있는 데이터 섹션.](./media/models.png)](./media/models.png)

- 등급 및 기타 고려 사항에 대해 자세히 알아보려면 **성능** 섹션에서 **세부 정보 보기** 를 선택합니다. 다음 그림의 세부 정보는 모델이 권장되는 것보다 적은 정보를 사용함을 보여줍니다. 따라서 시스템에서 경고 메시지를 생성했습니다.

    [![모델의 성능에 대한 경고.](./media/details.png)](./media/details.png)

## <a name="digging-deeper"></a>심층 분석

정확도는 모델 평가를 위한 좋은 출발점이고 성능 등급은 관점을 제공하지만 AI Builder는 평가를 위한 더 자세한 메트릭을 제공합니다. 세부 정보를 다운로드하려면 **성능** 섹션에서 **모델 사용** 버튼 옆에 있는 줄임표 버튼(**...**)을 선택한 다음 **자세한 메트릭 다운로드** 를 선택합니다.

[![자세한 메트릭 다운로드 명령.](./media/performance.png)](./media/performance.png)

다음 그림은 데이터를 다운로드할 수 있는 형식을 보여줍니다.

[![다운로드한 데이터의 형식.](./media/data-format.png)](./media/data-format.png)

결과를 더 깊게 분석하기 위한 좋은 출발점은 "혼동 행렬" 메트릭을 검토하는 것입니다. 예를 들어 다음은 이전 그림에서 이 메트릭에 대해 표시된 데이터입니다.

`{"name": "Confusion Matrix", "value": {"schema_type": "confusion_matrix", "schema_version": "1.0.0", "data": {"class_labels": ["0", "1", "2"], "matrix": [[71, 9, 21], [5, 0, 27], [2, 0, 45]]}}, "type": "dictionaryNumericalList", "isGlobalScore": false}`

다음과 같은 방법으로 이 데이터를 확장할 수 있습니다.

| &nbsp;                   | 정시 예상 | 연체 예상 | 심한 연체 예상 |
|--------------------------|-------------------|----------------|---------------------|
| 실제 정시 지불   | **71**            | 0              | 21                  |
| 실제 연체      | 5                 | **0**          | 27                  |
| 실제 심한 연체 | 2                 | 0              | **45**              |

혼동 행렬은 훈련 과정에서 무작위로 선택된 테스트 데이터 집합의 결과를 보여줍니다. 이러한 마감된 송장은 모델을 훈련하는 데 사용되지 않았기 때문에 모델을 테스트하는 데 좋은 사례입니다. 또한 청구서의 실제 상태를 알기 때문에 모델의 성능도 볼 수 있습니다.

먼저 가장 일반적인 실제 값을 찾아야 합니다. 이 값은 전체 데이터 세트와 완벽하게 일치하지 않을 수 있지만 합리적인 근사치입니다. 이 경우 **실제 정시 지불** 은 총 171개의 송장 중 92개에 대해 수행되었으며 가장 일반적인 실제 값입니다. 따라서 모델에 맞는 좋은 기준선입니다. 모든 송장이 정시에 처리될 것이라고 예측했다면 171번 중 92번(즉, 54%)이 맞았을 것입니다.

데이터 세트가 얼마나 균형을 이루고 있는지 이해하는 것이 중요합니다. 이 경우 171건의 송장 중 92건이 정시 지불되었고, 32건은 연체되었고, 47건은 심하게 연체되었습니다. 각 분류에 중요한 결과가 있기 때문에 이러한 값은 합리적으로 균형 잡힌 데이터 세트를 나타냅니다. 상태 중 하나에 결과가 매우 적은 상황에는 기계 학습 모델에 어려움이 있을 수 있습니다.

모델의 정확도는 테스트 데이터 세트에 대한 올바른 예측의 수를 나타냅니다. 이러한 올바른 예측은 앞의 예에서 굵게 표시된 값입니다. 이 경우 값은 계산된 정확도 67.8%를 생성합니다(= \[71 + 0 + 45\] ÷ 171). 이 값은 기준선 예상인 54%보다 14% 향상을 나타내며 모델 품질의 한 지표입니다.

혼동 행렬을 더 자세히 살펴보면 모델이 정시 지불과 심한 연체 송장 지불을 잘 예측한다는 것을 알 수 있습니다. 그러나 실제로 연체된(그러나 심한 연체가 아닌) 32개의 송장은 사실 모두 잘못되었습니다. 이러한 결과는 모델에 대한 추가적인 탐색과 개선이 필요함을 의미합니다.

F1 매크로 점수는 정확도보다 모델의 성능을 더 잘 나타내는 숫자입니다. 이 점수는 각 분류 상태(정시, 연체, 심한 연체)의 결과를 고려합니다. 예를 들어 다음은 이전 그림에서 "F1 매크로" 메트릭에 대해 표시된 데이터입니다.

`{"name": "F1 Macro", "value": 0.4927170868347339, "type": "percentage", "isGlobalScore": false}`

이 경우 F1 매크로 점수 약 49.3%은 전체 정확도 점수가 합리적으로 높지만 모델이 각 상태에서 효과적인 예측하지 못한다는 것을 나타냅니다.

## <a name="improving-the-model"></a>모델 개선

첫 번째 모델의 결과를 더 잘 이해한 후에는 특성 열을 추가 또는 제거하거나 정확한 예측을 지원하지 않는 데이터 세트 부분을 필터링하여 모델을 개선할 수 있습니다. AI Builder를 닫고 Dynamics 365 Finance의 **모델 개선** 링크를 사용하여 AI Builder 프로세스를 다시 시작합니다. 게시된 모델에 영향을 주지 않고 다양한 특성을 실험할 수 있습니다. 게시된 모델은 **게시** 를 선택한 경우에만 영향을 받습니다. Dynamics 365 Finance 인스턴스에 단일 모델이 사용된다는 점을 기억하세요. 따라서 새 모델을 게시하기 전에 신중하게 검토해야 합니다.

## <a name="for-more-information"></a>자세한 내용

예측 모델을 평가하는 방법에 대한 자세한 내용은 [기계 학습 모델의 결과](/confusion-matrix.md)를 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
