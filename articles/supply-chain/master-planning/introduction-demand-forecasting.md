---
title: 수요 예측 개요
description: 수요 예측은 고객 주문에 대한 디커플링 지점에서 판매 주문 및 종속 수요로부터의 독립 수요를 예측하는 데 사용됩니다. 향상된 수요 예측 감소 규칙은 대량 맞춤화를 위한 이상적인 솔루션을 제공합니다.
author: ChristianRytt
ms.date: 07/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "72004"
- intro-internal
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34a8cd4b17a5a75a5e817e6a1f982d75eefbb717
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449689"
---
# <a name="demand-forecasting-overview"></a>수요 예측 개요

[!include [banner](../includes/banner.md)]

수요 예측은 고객 주문에 대한 디커플링 지점에서 판매 주문 및 종속 수요로부터의 독립 수요를 예측하는 데 사용됩니다. 향상된 수요 예측 감소 규칙은 대량 맞춤화를 위한 이상적인 솔루션을 제공합니다.

기준 예측을 생성하기 위해 기록 트랜잭션 요약이 Azure에서 호스팅되는 Microsoft Azure Machine Learning으로 전달됩니다. 이 서비스는 사용자 간에 공유되지 않으므로 산업별 요구 사항을 충족하도록 쉽게 사용자 지정할 수 있습니다. Supply Chain Management를 사용하여 예측을 시각화하고, 예측을 조정하고, 예측 정확도에 대한 핵심 성과 지표(KPI)를 볼 수 있습니다.

> [!NOTE]
> 기계 학습을 통한 예측 생성에는 Microsoft Azure Machine Learning Studio(클래식)가 필요합니다. 2021년 12월 1일부터 새로운 Machine Learning Studio(클래식) 리소스를 생성할 수 없습니다. 그러나 2024년 8월 31일까지 기존 Machine Learning 스튜디오(클래식) 리소스를 계속 사용할 수 있습니다. 업데이트된 정보는 [Azure Machine Learning Studio](/azure/machine-learning/overview-what-is-machine-learning-studio#ml-studio-classic-vs-azure-machine-learning-studio)를 참조하세요.
> 
> Dynamics 365 Supply Chain Management 버전 10.0.23 이상은 새로운 Azure Machine Learning Studio를 지원합니다.

## <a name="key-features-of-demand-forecasting"></a>수요 예측의 주요 기능

다음은 수요 예측의 주요 기능 중 일부입니다.

- 과거 데이터를 기반으로 하는 통계적 기준선 예측을 생성합니다.
- 예측 차원의 동적 집합을 사용합니다.
- 수요 추세, 신뢰 구간 및 예측 조정을 시각화합니다.
- 계획 프로세스에 사용할 조정된 예측을 승인합니다.
- 이상치를 제거합니다.
- 예측 정확도 측정값을 생성합니다.

## <a name="major-themes-in-demand-forecasting"></a>수요 예측의 주요 테마

수요 예측에는 세 가지 주요 테마가 구현됩니다.

- **모듈성** – 수요 예측은 모듈식이며 구성하기 쉽습니다. **무역** &gt; **재고 예측** &gt; **수요 예측** 에서 구성 키를 변경하여 기능을 켜고 끌 수 있습니다..
- **Microsoft Stack 재사용** - Microsoft Cortana Analytics Suite의 일부인 Machine Learning을 사용하면 알고리즘 R 또는 Python 프로그래밍 언어와 간단한 드래그 앤-앤- 드롭 인터페이스.
  - 수요 예측 실험을 다운로드하고, 비즈니스 요구 사항에 맞게 변경하고, Azure에 웹 서비스로 게시하고, 수요 예측을 생성하는 데 사용할 수 있습니다. 엔터프라이즈 수준 사용자로 프로덕션 계획자를 위한 Supply Chain Management 구독을 구입한 경우 실험을 다운로드할 수 있습니다.
  - [Cortana Analytics 갤러리](https://gallery.cortanaanalytics.com/)에서 현재 사용 가능한 수요 예측 실험을 다운로드할 수 있습니다. 수요 예측 실험은 Supply Chain Management와 자동으로 통합되지만 고객과 파트너는 [Cortana Analytics 갤러리](https://gallery.cortanaanalytics.com/)에서 다운로드한 실험 통합을 처리해야 합니다. 따라서 [Cortana Analytics 갤러리](https://gallery.cortanaanalytics.com/)의 실험은 금융 및 운영 수요 예측 실험만큼 사용하기 간단하지 않습니다. 금융 및 운영 API(응용 프로그래밍 인터페이스)를 사용하도록 실험 코드를 수정해야 합니다.
  - Microsoft Azure Machine Learning Studio(클래식)에서 고유한 실험을 만들고 Azure에 서비스로 게시하고 수요 예측을 생성하는 데 사용할 수 있습니다.
  - 고성능이 필요하지 않거나 많은 양의 데이터를 처리할 필요가 없다면 머신 러닝 프리 티어를 사용할 수 있습니다. 특히 구현 및 테스트 단계에서는 항상 이 계층에서 시작하는 것이 좋습니다. 더 높은 성능과 추가 스토리지가 필요한 경우 기계 학습 표준 계층을 사용할 수 있습니다. 이 계층에는 Azure 구독이 필요하며 추가 비용이 필요합니다. Machine Learning 가격 책정에 대한 자세한 내용은 [Machine Learning Studio 가격 책정](https://aka.ms/machine-learning-price-info)을 참조하세요.
- **모든 분리 지점에서 감소 예측** – 이 기능을 기반으로 하는 수요 예측을 통해 모든 분리 지점에서 종속 및 독립 수요를 모두 예측할 수 있습니다.

## <a name="basic-flow-in-demand-forecasting"></a>수요 예측의 기본 흐름

다음 다이어그램은 수요 예측의 기본 흐름을 보여줍니다.

[![수요 예측 도입도.](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

수요 예측 생성은 Supply Chain Management에서 시작됩니다. Supply Chain Management 트랜잭션 데이터베이스의 과거 트랜잭션 데이터가 수집되어 준비 테이블을 채웁니다. 이 스테이징 테이블은 나중에 Machine Learning 서비스에 제공됩니다. 최소한의 사용자 지정을 수행하여 다양한 데이터 원본을 준비 테이블에 연결할 수 있습니다. 데이터 원본에는 Microsoft Excel 파일, CSV(쉼표로 구분된 값) 파일, Microsoft Dynamics AX 2009 및 Microsoft Dynamics AX 2012의 데이터가 포함될 수 있습니다. 따라서 여러 시스템에 분산된 과거 데이터를 고려한 수요 예측을 생성할 수 있습니다. 그러나 항목 이름 및 측정 단위와 같은 마스터 데이터는 다양한 데이터 원본에서 동일해야 합니다.

수요 예측 기계 학습 실험을 사용하는 경우 기본 예측을 계산하기 위해 5가지 시계열 예측 방법 중에서 가장 적합한 것을 찾습니다. 이러한 예측 방법에 대한 매개 변수는 Supply Chain Management에서 관리됩니다.

예측, 기록 데이터 및 이전 반복에서 수요 예측에 대한 변경 사항은 Supply Chain Management에서 사용할 수 있습니다.

Supply Chain Management를 사용하여 베이스라인 예측을 시각화하고 수정할 수 있습니다. 예측을 계획에 사용하려면 먼저 수동 조정을 승인해야 합니다.

## <a name="limitations"></a>제한 사항

수요 예측은 제조 산업의 고객이 예측 프로세스를 생성하는 데 도움이 되는 도구입니다. 수요예측 솔루션의 핵심 기능을 제공하며 쉽게 확장할 수 있도록 설계되었습니다. 수요 예측은 상업, 도매, 창고 보관, 운송 또는 기타 전문 서비스와 같은 산업 분야의 고객에게 가장 적합하지 않을 수 있습니다.

### <a name="demand-forecast-variant-conversion-limitation"></a>수요 예측 변형 전환 제한

재고 UOM이 수요 예측 UOM과 다른 경우 수요 예측을 생성할 때 변형당 UOM(측정 단위) 변환이 완전히 지원되지 않습니다.

예측 생성(**재고 UOM > 수요 예측 UOM**)은 제품 UOM 변환을 사용합니다. 수요 예측 생성에 대한 히스토리 데이터를 로드할 때 변형 레벨에 정의된 변환이 있더라도 재고 UOM에서 수요 예측 UOM으로 변환할 때 항상 제품 레벨 UOM 변환이 사용됩니다.

예측 승인의 첫 번째 부분(**수요 예측 UOM > 재고 UOM**)은 제품 UOM 변환을 사용합니다. 예측 승인의 두 번째 부분(**재고 UOM > 판매 UOM**)은 변형 UOM 변환을 사용합니다. 생성된 수요 예측이 승인되면 수요 예측 UOM에서 재고 UOM으로의 변환은 제품 레벨 UOM 변환을 사용하여 수행됩니다. 동시에 재고 단위와 판매 UOM 간의 변환은 변형 레벨 정의 변환을 따릅니다.

수요 예측 UOM에는 특별한 의미가 없어도 됩니다. "수요 예측 단위"로 정의할 수 있습니다. 각 제품에 대해 재고 UOM과 1:1이 되도록 변환을 정의할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[수요 예측 설정](demand-forecasting-setup.md)

[통계 기준선 예측 생성](generate-statistical-baseline-forecast.md)

[기준선 예측을 수동으로 조정](manual-adjustments-baseline-forecast.md)

[조정된 예측 승인](authorize-adjusted-forecast.md)

[예측 정확도 모니터링](monitor-forecast-accuracy.md)

[수요 예측을 계산할 때 과거 거래 데이터에서 이상치 제거](remove-historical-outliers-calculating-demand-forecast.md)

[수요 예측 기능 확장](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
