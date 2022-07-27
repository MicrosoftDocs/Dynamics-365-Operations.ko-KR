---
title: Finance insights 홈페이지
description: Finance insights는 구성 및 확장할 수 있는 모델을 제공하여 회사의 현금 흐름을 정확하고 지능적으로 예측하고, 미지급 채권을 지불받을 시기를 예측하며, 예산 책정 프로세스를 가속할 수 있는 예산 제안서를 작성하는 데 도움이 됩니다. 이러한 모든 기능은 지능형 기계 학습 모델에 기반을 둡니다.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05b0de8b0104238a33f006234d4a0e8ba9fcdb2a
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8451519"
---
# <a name="finance-insights-home-page"></a>Finance insights 홈페이지

[!include [banner](../includes/banner.md)]

Finance insights는 구성 및 확장할 수 있는 솔루션을 제공하여 회사의 현금 흐름을 지능적으로 예측하고, 미지급 채권을 지불받을 시기를 예측하며, 예산 책정 프로세스를 가속할 수 있는 예산 제안서를 작성하는 데 도움이 됩니다. 이러한 기능은 지능형 기계 학습 템플릿을 사용하여 귀하가 제공한 데이터(부서 소비자 보고서 정보와 같은 타사 데이터 포함)를 사용하여 모델을 구축합니다. 이러한 지능형 기능은 의사 결정을 위한 정보를 제공하고 현재 및 예상되는 비즈니스 과제에 효과적으로 대응하기 위한 조치를 취하는 데 도움이 됩니다. 귀하는 Finance insights와 함께 사용되거나 그로부터 출력되는 모든 데이터에 대한 책임이 있습니다.

> [!NOTE]
> Finance insights는 미국, 캐나다, 영국, 유럽, 아시아 태평양, 일본, 호주 및 뉴질랜드에서 배포할 수 있습니다. Microsoft는 더 많은 지역에 대한 지원을 점진적으로 추가하고 있습니다.

## <a name="prerequisites"></a>전제 조건

이 섹션에는 Finance insights를 사용하기 위한 요구 사항이 나열되어 있습니다. 가능한 경우 추가 정보 출처에 대한 링크가 제공됩니다.

### <a name="system-requirements"></a>시스템 요구 사항

Finance insights 프리뷰에는 계층 2 환경(멀티박스)이 필요합니다. 환경에 대한 배경 정보는 [환경 계획](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)을 참조하세요.

### <a name="version-requirements"></a>버전 요구 사항

이 항목은 Microsoft Dynamics 365 Finance 버전 10.0.21 이상에 적용됩니다.

### <a name="license-requirements"></a>라이선스 요구 사항

Finance insights는 AI Builder 크레딧을 사용하여 재무 예측을 생성합니다. 이에 필요한 모든 라이선스는 테넌트 라이선스에 포함되어 있습니다. 각 Dynamics 365 Finance 테넌트에게 매월 20,000 AI Builder 크레딧이 제공됩니다. 업무상 추가 크레딧이 필요한 경우 AI Builder에서 직접 구매할 수 있습니다.

### <a name="historical-data-requirements"></a>과거 데이터 요구 사항

고객 지불 예측 기능에 사용되는 기계 학습 모델을 올바르게 학습시키려면 최소 1년 치의 고객 송장이 필요합니다. 현금 흐름 예측에는 3년 치의 과거 데이터가 권장됩니다. 지능형 예산 제안에는 3년 치의 과거 예산 및/또는 실제 데이터가 권장됩니다.

## <a name="configure-finance-insights"></a>Finance insights 구성

Finance insights를 사용하려면 먼저 구성 단계를 완료해야 합니다. Finance insights를 구성하는 방법에 대한 자세한 내용은 [Finance insights의 구성](configure-for-fin-insites.md)을 참조하세요.

## <a name="create-a-data-integrator-project"></a>데이터 통합자 프로젝트 만들기

기계 학습 모델이 생성하는 데이터가 Dynamics 365 Finance로 전달될 수 있도록 데이터 통합자 프로젝트를 만들어야 합니다. 해당 프로젝트를 만드는 단계는 [데이터 통합자 프로젝트 만들기](create-data-integrate-project.md)를 참조하세요.

## <a name="enable-finance-insights-capabilities"></a>Finance insights 기능 활성화

구성 단계를 완료하고 데모 데이터를 설정한 다음에는 고객 지불 예측, 현금 흐름 예측 및 예산 제안과 같이 사용할 각 기능을 켜고 설정해야 합니다.

### <a name="enable-customer-payment-predictions"></a>고객 지불 예측 활성화
데모 데이터를 사용하여 고객 지불 예측을 테스트하는 경우 AI 모델을 성공적으로 생성하기 위해 추가 데모 데이터를 가져와야 할 수 있습니다. 

고객 지불 예측을 활성화하려면 조직의 데이터를 사용하여 고객이 미결제 송장을 지불할 가능성이 큰 시기와 특정 송장을 지불할 가능성이 있는 시기를 예측하는 기계 학습 모델을 구축하기 위한 일련의 단계를 완료해야 합니다. 자세한 내용과 완료해야 하는 특정 단계는 [고객 지불 예측 활성화](enable-cust-paymnt-prediction.md)를 참조하세요. 

### <a name="enable-cash-flow-forecasting"></a>현금 흐름 예측 활성화
현금 흐름 예측을 활성화하려면 조직의 데이터를 사용하여 현금 흐름을 예측하는 기계 학습 모델을 구축하기 위한 일련의 단계를 완료해야 합니다. 자세한 내용과 완료해야 하는 특정 단계는 [현금 흐름 예측 활성화](enable-cash-flow-forecasting.md)를 참조하세요.

### <a name="enable-budget-proposals"></a>예산 제안 활성화

예산 제안 기능은 조직의 과거 데이터와 함께 기계 학습 모델을 사용하여 예산 제안을 생성합니다. 생성된 제안은 수동 프로세스보다 더 효과적이고 효율적인 예산 프로세스를 시작하는 데 도움이 될 수 있습니다. 이 기능을 활성화하는 구체적인 단계는 [예산 제안 활성화](enable-budget-proposal.md)를 참조하세요. 

## <a name="using-finance-insights-features"></a>Finance insights 기능 사용

### <a name="using-customer-payment-predictions"></a>고객 지불 예측 사용

- 고객 지불 예측으로 사전에 수집 활동을 시작하는 데 필요한 정보를 제공하는 방법을 알아보려면 [고객 지불 예측 사용](use-customer-payment-predictions.md)을 참조하세요.
- 기능 사용을 시작한 후 예측 모델의 효율성을 평가하는 데 도움이 되는 정보는 [초기 고객 지불 예측 모델 평가](evaluate-payment-prediction.md)를 참조하세요.
- 예측을 생성하는 데 사용되는 데이터를 조정하여 효율성을 개선하는 데 도움이 되는 정보는 [예측 모델 개선](improve-model.md)을 참조하세요.
- AI 예측 모델의 결과에 대한 자세한 내용은 [기계 학습 모델의 결과](confusion-matrix.md)를 참조하세요.

### <a name="using-cash-flow-forecasts"></a>현금 흐름 예측 사용

현금 흐름 예측 기능을 사용하면 현금 유동성을 더 정확하게 추정할 수 있습니다. 지능형 현금 흐름 예측은 Dynamics 365 Finance의 기존 현금 흐름 예측 기능을 바탕으로 구축됩니다. 기존 기능을 검토하려면 [현금 흐름 예측](../cash-bank-management/cash-flow-forecasting.md)을 참조하세요.

- 현금 흐름 예측의 새로운 기능에 대해 자세히 알아보려면 [현금 흐름 예측](cash-flow-forecast-intro.md)을 참조하세요.
- 현금 흐름 예측에 포함할 외부 데이터 가져오기에 대한 자세한 내용은 [현금 흐름 예측에 외부 데이터 사용](external-data-in-cash-flow.md)을 참조하세요. 
- 단기 현금 흐름을 예측하기 위해 AI 모델을 사용하는 방법에 대한 정보는 [현금 유동성](cash-position.md)을 참조하세요.
- 현금 흐름 유동성 및 현금 흐름 예측을 스냅샷으로 저장하고 스냅샷을 실제와 비교하는 방법에 대한 내용은 [스냅샷 개요](payment-snapshots.md)를 참조하세요.

### <a name="using-budget-proposal"></a>예산 제안 사용

예산 편성 가속에 관한 내용은 [예산 제안](budget-proposals.md)을 참조하세요. 

## <a name="feedback-and-support"></a>피드백 및 지원

피드백 제공에 관심이 있거나 지원이 필요한 경우 [Finance Insights](mailto:fiap@microsoft.com)로 이메일을 보내주세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
