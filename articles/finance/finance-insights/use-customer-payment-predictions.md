---
title: 고객 지불 예측 사용
description: 이 항목에서는 Finance Insights 평가판을 사용하는 데 필요한 전제 조건과 광범위한 단계를 안내합니다.
author: ShivamPandey-msft
ms.date: 11/03/2021
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
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: ed70e133b93c783542d4669b679fc5b6d2d20240
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2022
ms.locfileid: "8451360"
---
# <a name="use-customer-payment-predictions"></a>고객 지불 예측 사용

[!include [banner](../includes/banner.md)]

이 항목에서는 고객 지불 예측을 사용하는 방법을 설명합니다. 이 기능을 사용하기 전에 설정 단계를 완료했는지 확인하세요. 자세한 내용은 [고객 지불 예측 활성화](enable-cust-paymnt-prediction.md)를 참조하세요.

**고객 신용 및 수금 관리** 작업 영역과 **거래 지불 예측** 및 **고객 지불 예측** 의 두 가지 새로운 목록 페이지에서 고객 지불 예측을 볼 수 있습니다.

### <a name="manage-customer-credit-and-collections-workspace"></a>고객 신용 및 수금 관리 작업 영역

**고객 신용 및 수금 관리** 작업 영역에는 **거래 지불 예측** 및 **고객 지불 예측** 의 두 가지 새로운 타일이 포함됩니다.

### <a name="transaction-payment-predictions-list-page"></a>거래 지불 예측 목록 페이지

**거래 지불 예측** 목록 페이지에서 **정시**, **늦음** 및 **매우 늦음** 버킷의 미결 거래에 대한 지불 확률을 볼 수 있습니다. 그리드의 각 거래에 대해 **정시 확률** 열은 송장이 만기일 또는 그 이전에 지불될 확률을 보여줍니다. 정시 지불 확률이 50% 미만이면 **정기 지불 확률** 열의 비율 옆에 빨간색 원이 표시되어 연체 위험을 나타냅니다.

[![거래별 지불 예측 페이지.](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

페이지 오른쪽의 **관련 정보** 창에는 예측에 관한 세부 정보가 표시됩니다.

- 그리드에서 선택한 거래에 대해 **지불 예측** 빠른 탭은 **정시**, **늦음** 및 **매우 늦음** 버킷의 지불 예측에 관한 세부 정보를 표시합니다. **주요 요인** 섹션에는 예측에 영향을 준 주요 요인이 표시됩니다. 주요 요인은 선택한 거래 및/또는 해당 거래에 대한 고객의 특성입니다.
- **Customer Insights** 빠른 탭은 선택한 거래에 대한 고객의 현재 송장, 지불 및 수금 통계를 보여줍니다.
- **고객 내역** 빠른 탭은 **정시**, **늦음** 및 **매우 늦음** 버킷에 고객의 결제 내역을 표시합니다.

**주요 요인** 섹션, **Customer Insights** 및 **고객 내역** 빠른 탭의 데이터는 지불 예측을 설명하는 데 도움이 됩니다. 예측의 효율성에 대한 신뢰도를 높이는 데 도움이 될 수 있습니다.

[![관련 정보 창의 지불 예측을 위한 그래픽 표시기.](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>고객 지불 예측 목록 페이지

**고객 지불 예측** 목록 페이지는 총 미결제 잔액과 **정시**, **늦음** 및 **매우 늦음** 버킷에서 지불될 것으로 예상되는 금액을 보여줍니다.

[![고객별 지불 요청 페이지.](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

각 버킷의 지불 금액은 거래 잔액의 가중 평균 합계로 계산됩니다. 이 금액은 각 버킷의 지불 확률을 기반으로 계산됩니다.

예를 들어 고객에게 각 버킷에 다음과 같은 지불 가능성이 있는 3개의 미결 거래가 있습니다.

| 거래 | 금액 | 정시 지불 가능성 | 늦은 지불 가능성 | 매우 늦은 지불 가능성 |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10%                  | 50%               | 40%                    |
| T2          | 1,000  | 50%                  | 30%               | 20%                    |
| T3          | 10,000 | 1%                   | 4%                | 95%                    |

이 경우 각 버킷에 대해 다음과 같은 방식으로 지불이 예상됩니다.

| 버킷   | 거래 T1      | 거래 T2         | 거래 T3            | 합계 |
|-----------|---------------------|------------------------|---------------------------|-------|
| 정시   | 100 × 10 ÷ 100 = 10 | 1,000 × 50 ÷ 100 = 500 | 10,000 × 1 ÷ 100 = 100    | 610   |
| 늦음      | 100 × 50 ÷ 100 = 50 | 1,000 × 30 ÷ 100 = 300 | 10,000 × 4 ÷ 100 = 400    | 750   |
| 매우 늦음 | 100 × 40 ÷ 100 = 40 | 1,000 × 20 ÷ 100 = 200 | 10,000 × 95 ÷ 100 = 9,500 | 9,740 |

페이지 오른쪽의 **관련 정보** 섹션에는 예측에 관한 세부 정보가 표시됩니다.

- 그리드에서 선택한 거래에 대해 **지불 예측** 빠른 탭은 **정시**, **늦음** 및 **매우 늦음** 버킷의 지불 예측에 관한 세부 정보를 표시합니다.
- **Customer Insights** 빠른 탭은 선택한 거래에 대한 고객의 현재 송장, 지불 및 수금 통계를 보여줍니다.
- **고객 내역** 빠른 탭은 **정시**, **늦음** 및 **매우 늦음** 버킷에 고객의 결제 내역을 표시합니다.

**Customer Insights** 및 **고객 내역** 빠른 탭의 데이터는 지불 예측을 설명하는 데 도움이 됩니다. 예측의 효율성에 대한 신뢰도를 높이는 데 도움이 될 수 있습니다.

## <a name="improving-the-accuracy-of-payment-predictions"></a>지불 예측의 정확도 개선

**신용 및 수금 \> 설정 \> Finance Insights \> Finance Insights 매개 변수** 로 이동하여 지불 예측의 정확성을 볼 수 있습니다. **고객 지불 인사이트** 탭의 **예측 모델** 섹션은 예측 모델의 정확도를 백분율로 표시합니다.

[![지불 예측의 정확도.](./media/finance-insights-parameters-accuracy-2nd.png)](./media/finance-insights-parameters-accuracy-2nd.png)

정확도가 만족스럽지 않으면 **모델 정확도 향상** 링크를 선택하여 AI Builder 확장 환경을 엽니다. AI Builder 확장 환경에서 지불 가능성을 정확하게 예측하는 데 가장 중요하다고 생각되는 필드를 선택할 때까지 필드 선택을 선택하거나 취소할 수 있습니다. 완료되면 예측 모델을 쉽게 다시 학습시키고 변경 사항을 게시할 수 있습니다. 새로 훈련된 예측 모델은 Dynamics 365 Finance의 예측을 위해 자동으로 선택됩니다.

[![AI Builder 확장 환경.](./media/ai-builder.png)](./media/ai-builder.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
