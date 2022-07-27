---
title: 수요 예측 설정
description: 이 항목에서는 수요 예측을 준비하기 위해 수행해야 하는 설정 작업에 대해 설명합니다.
author: ChristianRytt
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f53171361b655ab4ae05894d098203df0af8d60
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449608"
---
# <a name="demand-forecasting-setup"></a>수요 예측 설정

[!include [banner](../includes/banner.md)]

이번에는 수요 예측을 설정하는 방법에 대해 설명합니다.  

## <a name="item-allocation-keys"></a>항목 할당 키

항목 할당 키는 항목 그룹을 설정합니다. 항목이 항목 할당 키의 일부인 경우에만 항목 및 해당 차원에 대한 수요 예측이 계산됩니다. 이 규칙은 수요 예측을 더 빨리 생성할 수 있도록 많은 수의 항목을 그룹화하도록 시행됩니다. 예측은 기록 데이터만을 기반으로 생성됩니다.

항목 할당 키가 예측 생성 중에 사용되는 경우 항목 및 해당 차원은 하나의 항목 할당 키에만 속해야 합니다.

항목 할당 키를 만들고 여기에 SKU(재고 관리 단위)를 추가하려면 다음 단계를 따르세요.

1. **기준 계획 \> 설정 \> 수요 예측 \> 항목 할당 키** 로 이동합니다.
1. 목록 창에서 항목 할당 키를 선택하거나 작업 창에서 **새로 만들기** 를 선택하여 새 키를 만듭니다. 새 키 또는 선택한 키의 헤더에서 다음 필드를 설정합니다.

    - **항목 할당 키** – 키의 고유 이름을 입력합니다.
    - **이름** – 키를 설명하는 이름을 입력합니다.

1. 다음 단계 중 하나에 따라 선택한 항목 할당 키에 항목을 추가하거나 항목을 제거하세요.

    - **항목 할당** 빠른 탭에서 도구 모음의 **새로 만들기** 및 **삭제** 단추를 사용하여 필요에 따라 항목을 추가하거나 제거합니다. 각 행에 대해 품목 번호를 선택한 다음 필요에 따라 다른 열에 차원 값을 할당합니다. 도구 모음에서 **차원 표시** 를 선택하여 그리드에 표시되는 차원 열 집합을 변경합니다. (**백분율** 열의 값은 수요 예측이 생성될 때 무시됩니다.)
    - 키에 많은 수의 항목을 추가하려면 작업 창에서 **항목 할당** 을 선택하여 여러 항목을 찾아 선택한 키에 할당할 수 있는 페이지를 엽니다.

> [!IMPORTANT]
> 각 항목 할당 키에 관련 항목만 포함하도록 주의하세요. Microsoft Azure Machine Learning을 사용할 때 불필요한 항목으로 인해 비용이 증가할 수 있습니다.

## <a name="intercompany-planning-groups"></a>회사 간 계획 그룹

수요 예측은 회사 간 예측을 생성할 수 있습니다. Dynamics 365 Supply Chain Management에서 함께 계획된 회사는 동일한 회사 간 계획 그룹으로 그룹화됩니다. 수요 예측을 위해 고려해야 하는 항목 할당 키를 회사별로 지정하려면 항목 할당 키를 내부 거래 계획 그룹 구성원과 연결합니다.

> [!IMPORTANT]
> 계획 최적화는 현재 회사 간 계획 그룹을 지원하지 않습니다. 계획 최적화를 사용하는 본지사 계획을 수행하려면 모든 관련 회사에 대한 기준 계획을 포함하는 기준 계획 배치 작업을 설정합니다.

회사 간 계획 그룹을 설정하려면 다음 단계를 따르세요.

1. **기준 계획 \> 설정 \> 회사 간 계획 그룹** 으로 이동합니다.
1. 목록 창에서 계획 그룹을 선택하거나 작업 창에서 **새로 만들기** 를 선택하여 새 그룹을 만듭니다. 새 키 또는 선택한 그룹의 헤더에서 다음 필드를 설정합니다.

    - **이름** – 계획 그룹의 고유한 이름을 입력합니다.
    - **설명** – 계획 그룹에 대한 간단한 설명을 입력합니다.

1. **회사간 계획 그룹 구성원** 빠른 탭에서 도구 모음의 단추를 사용하여 그룹에 속해야 하는 각 회사(법인)에 대한 행을 추가합니다. 각 행에 대해 다음 필드를 설정합니다.

    - **법인** – 선택한 그룹의 구성원인 회사(법인)의 이름을 선택합니다.
    - **예약 순번** – 다른 회사와 비교하여 회사가 처리해야 하는 순서를 지정합니다. 낮은 값이 먼저 처리됩니다. 이 순서는 한 회사에 대한 수요가 다른 회사에 영향을 미칠 때 중요할 수 있습니다. 이 경우 수요를 공급하는 업체가 가장 마지막에 처리되어야 합니다.
    - **기준 계획** – 현재 회사에 대해 트리거할 마스터 플랜을 선택합니다.
    - **정적 계획에 자동 복사** – 계획 결과를 정적 계획에 복사하려면 이 확인란을 선택합니다.
    - **동적 계획에 자동 복사** – 계획 결과를 동적 계획에 복사하려면 이 확인란을 선택합니다.

1. 기본적으로 내부 거래 계획 그룹 구성원에게 할당된 항목 할당 키가 없으면 모든 회사의 모든 항목 할당 키에 할당된 모든 항목에 대해 수요 예측이 계산됩니다. 회사 및 항목 할당 키에 대한 추가 필터링 옵션은 **통계 기준선 예측 생성** 대화 상자(**기준 계획 \> 예측 \> 수요 예측 \> 통계 기준선 예측** 생성)에서 사용할 수 있습니다. 선택한 내부 거래 계획 그룹의 회사에 항목 할당 키를 할당하려면 회사를 선택한 다음 **회사 간 트랜잭션 계획 그룹 구성원** 빠른 탭의 도구 모음에서 **항목 할당 키** 를 선택합니다.

> [!IMPORTANT]
> 각 회사 간 계획 그룹에 관련 항목 할당 키만 포함하도록 주의하세요. Azure Machine Learning을 사용할 때 불필요한 항목으로 인해 비용이 증가할 수 있습니다.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>수요 예측 매개 변수 설정

**수요 예측 매개 변수** 페이지를 사용하여 시스템에서 수요 예측이 작동하는 방식을 제어하는 여러 옵션을 설정합니다.

### <a name="open-the-demand-forecasting-parameters-page"></a>수요 예측 매개 변수 페이지 열기

수요 예측 매개 변수를 설정하려면 **기준 계획 \> 설정 \> 수요 예측 \> 수요 예측 매개 변수** 로 이동합니다. 수요 예측은 회사 전체에서 실행되기 때문에 설정은 전역입니다. 즉, 모든 법인(회사)에 적용됩니다.

### <a name="general-settings"></a>일반 설정

**수요 예측 매개 변수** 페이지의 **일반** 탭을 사용하여 수요 예측에 대한 일반 설정을 정의합니다.

#### <a name="demand-forecast-unit"></a>수요 예측 단위

수요 예측은 예측을 수량으로 생성합니다. 따라서 수량을 표현해야 하는 측정 단위는 **수요 예측 단위** 필드에 지정되어야 합니다. 이 필드는 각 제품의 일반적인 재고 단위에 관계없이 모든 수요 예측에 사용할 단위를 정의합니다. 일관된 예측 단위를 사용하면 집계 및 백분율 분포가 의미가 있는지 확인하는 데 도움이 됩니다. 집계 및 백분율 분포에 대한 자세한 내용은 [기준선 예측 수동 조정](manual-adjustments-baseline-forecast.md)을 참조하세요.

수요 예측에 포함된 SKU에 사용되는 모든 측정 단위에 대해 여기에서 선택하는 측정 단위 및 일반 예측 측정 단위에 대한 변환 규칙이 있는지 확인하세요. 예측을 생성할 때 측정 단위 변환이 없는 항목 목록이 기록됩니다. 따라서 설정을 쉽게 수정할 수 있습니다. 측정 단위 및 단위 변환 방법에 대한 자세한 내용은 [측정 단위 관리](../pim/tasks/manage-unit-measure.md)를 참조하세요.

#### <a name="transaction-types"></a>트랜잭션 유형

**트랜잭션 유형** 빠른 탭의 필드를 사용하여 통계 기준선 예측이 생성될 때 사용되는 트랜잭션 유형을 선택하세요.

수요 예측은 종속 수요와 독립 수요를 모두 예측하는 데 사용할 수 있습니다. 예를 들어 **판매 주문** 옵션만 *예* 로 설정되어 있고 수요 예측에 고려되는 모든 항목이 판매되는 항목인 경우 시스템은 독립 수요를 계산합니다. 그러나 중요한 하위 구성 요소는 항목 할당 키에 추가되고 수요 예측에 포함될 수 있습니다. 이 경우 **생산 라인** 옵션이 *예* 로 설정되어 있으면 종속 예측이 계산됩니다.

**항목 할당 키** 탭을 사용하여 하나 이상의 특정 항목 할당 키에 대한 트랜잭션 유형을 재정의할 수 있습니다. 해당 탭은 유사한 필드를 제공합니다.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>기준선 예측 생성 방법 선택

**예측 생성 전략** 필드를 사용하여 기준선 예측을 생성하는 데 사용되는 방법을 선택할 수 있습니다. 세 가지 방법을 사용할 수 있습니다.

- *과거 수요 복사* – 과거 데이터를 복사하여 예측을 생성합니다.
- *Azure Machine Learning Service* – Azure Machine Learning Service를 사용하는 예측 모델을 사용합니다. Azure Machine Learning Service는 Azure용 현재 기계 학습 솔루션입니다. 따라서 예측 모델을 사용하고자 하는 경우 사용을 권장합니다.
- *Azure Machine Learning* – Azure Machine Learning Studio(클래식)를 사용하는 예측 모델을 사용합니다. Azure Machine Learning Studio(클래식)는 더 이상 사용되지 않으며 곧 Azure에서 제거됩니다. 따라서 수요 예측을 처음 설정하는 경우 *Azure Machine Learning Service* 를 선택하는 것이 좋습니다. 현재 Azure Machine Learning Studio(클래식)를 사용 중인 경우 최대한 빨리 Azure Machine Learning Service로 전환할 계획을 세워야 합니다.

**항목 할당 키** 탭을 사용하여 하나 이상의 특정 항목 할당 키에 대한 예측 생성 방법을 대체할 수 있습니다. 해당 탭은 유사한 필드를 제공합니다.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>전역적으로 기본 예측 알고리즘 매개 변수 재정의

기본 예측 알고리즘 매개 변수 및 값은 **수요 예측 매개 변수** 페이지(**기준 계획 \> 설정 \> 수요 예측 \> 수요 예측 매개 변수**)에서 지정됩니다. 그러나 **수요 예측 매개 변수** 페이지의 **일반** 탭에 있는 **예측 알고리즘 매개 변수** 빠른 탭을 사용하여 전역적으로 이를 대체할 수 있습니다. (**수요 예측 매개 변수** 페이지의 **항목 할당 키** 탭을 사용하여 특정 할당 키에 대해 이를 대체할 수도 있습니다.)

도구 모음의 **추가** 및 **제거** 단추를 사용하여 필요한 매개 변수 재정의 컬렉션을 설정합니다. 목록의 각 매개 변수에 대해 **이름** 필드에서 값을 선택한 다음 **값** 필드에 적절한 값을 입력합니다. 여기에 나열되지 않은 모든 매개 변수는 **수요 예측 매개 변수** 페이지의 설정에서 값을 가져옵니다. 표준 매개 변수 집합을 사용하고 이에 대한 값을 선택하는 방법에 대한 자세한 내용은 [수요 예측 모델의 기본 매개 변수 및 값](#model-parameters) 섹션을 참조하세요.

### <a name="set-forecast-dimensions"></a>예측 차원 설정

예측 차원은 예측이 정의된 세부 정보 수준을 나타냅니다. 회사, 사이트 및 항목 할당 키는 필수 예측 차원입니다. 또한 창고, 재고 상태, 고객 그룹, 고객 계정, 국가/지역, 주 및/또는 항목 수준과 모든 항목 차원 수준에서 예측을 생성할 수 있습니다. **수요 예측 매개 변수** 페이지의 **예측 차원** 탭을 사용하여 수요 예측이 생성될 때 사용되는 예측 차원 집합을 선택합니다.

언제든지 수요 예측에 사용되는 차원 목록에 예측 차원을 추가할 수 있습니다. 목록에서 예측 차원을 제거할 수도 있습니다. 그러나 예측 차원을 추가하거나 제거하면 수동 조정이 손실됩니다.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>특정 항목 할당 키에 대한 재정의 설정

수요 예측 관점에서 모든 항목이 동일한 방식으로 작동하는 것은 아닙니다. 따라서 **일반** 탭에 정의된 대부분의 설정에 대해 할당 키 관련 재정의를 설정할 수 있습니다. 예외는 수요 예측 단위입니다. 특정 항목 할당 키에 대한 재정의를 설정하려면 다음 단계를 따르십시오.

1. **수요 예측 매개 변수** 페이지의 **항목 할당 키** 탭에서 도구 모음 단추를 사용하여 왼쪽 그리드에 항목 할당 키를 추가하거나 필요에 따라 제거합니다. 그런 다음 재정의를 설정할 할당 키를 선택합니다.
1. **트랜잭션 유형** 빠른 탭에서 선택한 할당 키에 속하는 제품에 대한 통계적 기준선 예측을 생성하는 데 사용할 트랜잭션 유형을 활성화합니다. 설정은 **일반** 탭에서 작동하는 것처럼 작동하지만 선택한 항목 할당 키에만 적용됩니다. 여기의 모든 설정(*예* 값 및 *아니요* 값 모두)은 **일반** 탭의 모든 **트랜잭션 유형** 설정보다 우선합니다.
1. **예측 알고리즘 매개 변수** 빠른 탭에서 선택한 할당 키에 속하는 제품에 대한 예측 생성 전략 및 예측 알고리즘 매개 변수 재정의를 선택합니다. 이러한 설정은 **일반** 탭에서 작동하는 것처럼 작동하지만 선택한 항목 할당 키에만 적용됩니다. 도구 모음의 **추가** 및 **제거** 단추를 사용하여 필요한 매개 변수 재정의 컬렉션을 정의합니다. 목록의 각 매개 변수에 대해 **이름** 필드에서 값을 선택한 다음 **값** 필드에 적절한 값을 입력합니다. 표준 매개 변수 집합을 사용하고 이에 대한 값을 선택하는 방법에 대한 자세한 내용은 [수요 예측 모델의 기본 매개 변수 및 값](#model-parameters) 섹션을 참조하세요.

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Azure Machine Learning Service에 대한 연결 설정

**Azure Machine Learning Service** 탭을 사용하여 Azure Machine Learning Service에 대한 연결을 설정합니다. 이 솔루션은 기준선 예측을 생성하기 위한 옵션 중 하나입니다. 이 탭의 이러한 설정은 **예측 생성 전략** 필드가 *Azure Machine Learning Service* 로 설정된 경우에만 적용됩니다.

Azure Machine Learning Service를 설정한 다음 여기의 설정을 사용하여 연결하는 방법에 대한 자세한 내용은 [Azure Machine Learning Service 설정](#setup-amls) 섹션을 참조하세요.

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Azure Machine Learning Studio(클래식)에 대한 연결 설정

> [!IMPORTANT]
> Azure Machine Learning Studio(클래식)는 더 이상 사용되지 않습니다. 따라서 Azure에서 더 이상 새 작업 영역을 만들 수 없습니다. 유사한 기능 등을 제공하는 Azure Machine Learning Service로 대체되었습니다. 아직 Azure Machine Learning을 사용하지 않는 경우 Azure Machine Learning 서비스를 사용하기 시작해야 합니다. Azure Machine Learning Studio(클래식)용으로 만든 작업 영역이 이미 있는 경우 Azure에서 기능이 완전히 제거될 때까지 계속 사용할 수 있습니다. 그러나 가능한 한 빨리 Azure Machine Learning Service로 업데이트하는 것이 좋습니다. 애플리케이션은 Azure Machine Learning Studio(클래식)가 더 이상 사용되지 않는다는 경고를 계속 표시하지만 예측 결과는 영향을 받지 않습니다. 새로운 Azure Machine Learning Service 및 설정 방법에 대한 자세한 내용은 [Azure Machine Learning Service 설정](#setup-amls) 섹션을 참조하세요.
>
> 이전 Azure Machine Learning Studio(클래식) 작업 영역을 계속 사용할 수 있는 한 Supply Chain Management에서 새 기계 학습 솔루션과 이전 기계 학습 솔루션을 자유롭게 전환할 수 있습니다.

사용 가능한 Azure Machine Learning Studio(클래식) 작업 영역이 이미 있는 경우 이를 사용하여 Supply Chain Management에 연결하여 예측을 생성할 수 있습니다. **수요 예측 매개 변수** 페이지의 **Azure Machine Learning** 탭을 사용하여 이 연결을 설정할 수 있습니다. (이 탭의 설정은 **예측 생성 전략** 필드가 *Azure Machine Learning* 으로 설정된 경우에만 적용됩니다.) Azure Machine Learning Studio(클래식) 작업 영역에 대해 다음 세부 정보를 입력합니다.

- 웹 서비스 API(응용 프로그래밍 인터페이스) 키
- 웹 서비스 엔드포인트 URL
- Azure 스토리지 계정 이름
- Azure 스토리지 계정 키

> [!NOTE]
> Azure 스토리지 계정 이름과 키는 사용자 지정 스토리지 계정을 사용하는 경우에만 필요합니다. 온-프레미스 버전을 배포하는 경우 Machine Learning이 기록 데이터에 액세스할 수 있도록 Azure에 사용자 지정 스토리지 계정이 있어야 합니다.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>수요 예측 모델의 기본 매개 변수 및 값

기계 학습을 사용하여 예측 계획 모델을 생성할 때 *예측 알고리즘 매개 변수* 에 대한 값을 설정하여 기계 학습 옵션을 제어합니다. 이러한 값은 Supply Chain Management에서 Azure Machine Learning으로 전송됩니다. **예측 알고리즘 매개 변수** 페이지를 사용하여 제공해야 하는 값 유형과 각 값에 포함해야 하는 값을 제어합니다.

수요 예측 모델에 사용되는 기본 매개 변수 및 값을 설정하려면 **기준 계획 \> 설정 \> 수요 예측 \> 예측 알고리즘 매개 변수** 로 이동합니다. 표준 매개 변수 세트가 제공됩니다. 각 매개 변수에 대해 다음 필드를 설정합니다.

- **이름** – Azure에서 사용하는 매개 변수의 이름입니다. 일반적으로 Azure Machine Learning에서 실험을 사용자 지정하지 않은 경우 이 이름을 변경하면 안 됩니다.
- **설명** – 매개 변수의 공통 이름입니다. 이 이름은 시스템의 다른 위치에서 매개 변수를 식별하는 데 사용됩니다(예: **수요 예측 매개 변수** 페이지).
- **값** – 매개 변수의 기본값. 입력해야 하는 값은 편집 중인 매개 변수에 따라 다릅니다. 
- **설명** – 매개 변수 및 사용 방법에 대해 간략하게 설명합니다. 이 설명에는 일반적으로 **값** 필드의 유효한 값에 대한 조언이 포함됩니다.

다음 매개 변수가 기본적으로 제공됩니다. (이 표준 목록으로 되돌려야 하는 경우 작업 창에서 **복원** 을 선택합니다.)

- **신뢰도 수준 백분율** – 신뢰도 구간은 수요 예측에 대한 좋은 추정치로 작용하는 값 범위로 구성됩니다. 95% 신뢰 수준 백분율은 미래 수요가 신뢰 구간 범위를 벗어날 위험이 5%임을 나타냅니다.
- **강제 계절성** – 모델이 특정 유형의 계절성을 사용하도록 강제할지 여부를 지정합니다. 이 매개 변수는 ARIMA 및 ETS에만 적용됩니다. 옵션: *AUTO(기본값)*, *NONE*, *ADDITIVE*, *MULTIPLICATIVE*.
- **예측 모델** – 사용할 예측 모델을 지정합니다. 옵션: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *ALL*. 가장 적합한 모델을 선택하려면 *ALL* 을 사용합니다.
- **최대 예측값** – 예측에 사용할 최대값을 지정합니다. 형식: +1E[n] 또는 숫자 상수.
- **최소 예측값** – 예측에 사용할 최소값을 지정합니다. 형식: -1E[n] 또는 숫자 상수.
- **누락된 값 대체** – 기록 데이터의 간격을 채우는 방법을 지정합니다. 옵션: *(숫자 값)*, *MEAN*, *PREVIOUS*, *INTERPOLATE LINEAR*, *INTERPOLATE POLYNOMIAL*.
- **누락된 값 대체 범위** – 값 대체가 각 개별 세분성 속성의 날짜 범위에만 적용되는지 또는 전체 데이터 세트에 적용되는지 지정합니다. 기록 데이터의 공백을 채울 때 시스템이 사용하는 날짜 범위를 설정하는 데 다음 옵션을 사용할 수 있습니다.

    - *GLOBAL* – 시스템은 모든 세분성 속성의 전체 날짜 범위를 사용합니다.
    - *HISTORY_DATE_RANGE* – 시스템은 **통계 기준선 예측 생성** 대화 상자의 **과거 기간** 섹션에 있는 **시작 날짜** 및 **종료 날짜** 필드로 정의된 특정 날짜 범위를 사용합니다.
    - *GRANULARITY_ATTRIBUTE* – 시스템은 현재 처리된 세분성 속성의 날짜 범위를 사용합니다.

    > [!NOTE]
    > 세분성 속성은 예측이 수행되는 예측 차원의 조합입니다. **수요 예측 매개 변수** 페이지에서 예측 차원을 정의할 수 있습니다.

- **계절성 힌트** – 계절 데이터의 경우 예측 정확도를 개선하기 위해 예측 모델에 힌트를 제공합니다. 형식: 수요 패턴이 반복되는 버킷 수를 나타내는 정수입니다. 예를 들어, 6개월마다 반복되는 데이터의 경우 *6* 을 입력합니다.
- **테스트 세트 크기 백분율** – 예측 정확도 계산을 위한 테스트 세트로 사용할 과거 데이터의 백분율입니다.

**기준 계획 \> 설정 \> 수요 예측 \> 수요 예측 매개 변수** 로 이동하여 이러한 매개 변수의 값을 대체할 수 있습니다. **수요 예측 매개 변수** 페이지에서 다음과 같은 방법으로 매개 변수를 재정의할 수 있습니다.

- **일반** 탭을 사용하여 매개 변수를 전역적으로 재정의합니다.
- **항목 할당 키** 탭을 사용하여 특정 항목 할당 키에 대한 매개 변수를 재정의합니다. 특정 항목 할당 키에 대해 재정의된 매개 변수는 해당 항목 할당 키와 연결된 항목의 예측에만 영향을 줍니다.

> [!NOTE]
> **예측 알고리즘 매개 변수** 페이지에서 작업 창의 단추를 사용하여 목록에 매개 변수를 추가하거나 목록에서 매개 변수를 제거할 수 있습니다. 그러나 일반적으로 Azure Machine Learning에서 실험을 사용자 지정하지 않은 경우 이 접근 방식을 사용하면 안 됩니다.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Azure Machine Learning Service에 대한 연결 설정

Supply Chain Management는 자체 Azure 구독에서 설정하고 실행해야 하는 Azure Machine Learning Service를 사용하여 수요 예측을 계산합니다. 이 섹션에서는 Azure에서 Azure Machine Learning Service를 설정한 다음 Supply Chain Management 환경에 연결하는 방법을 설명합니다.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>기능 관리에서 Azure Machine Learning Service 활성화

수요 예측에 Azure Machine Learning Service를 사용하려면 먼저 Supply Chain Management에서 기능을 켜서 통합을 활성화해야 합니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 설정을 사용하여 기능의 상태를 확인하고 켤 수 있습니다. **기능 관리** 작업 영역에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈:** *기준 계획*
- **기능 이름:** *수요 예측을 위한 Azure Machine Learning Service*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Azure에서 Machine Learning 설정

Azure에서 기계 학습을 사용하여 예측을 처리할 수 있도록 하려면 이 용도로 Azure Machine Learning 작업 영역을 설정해야 합니다. 두 가지 옵션이 있습니다.

- Microsoft에서 제공하는 스크립트를 실행하여 작업 공간을 설정하려면, [옵션 1: 기계 학습 작업 영역을 자동으로 설정하는 스크립트 실행](#ml-workspace-script) 섹션의 지침을 따른 다음 [Supply Chain Management에서 Azure 기계 학습 서비스 연결 매개 변수 설정](#demand-forecast-parameters) 섹션으로 건너뜁니다.
- 작업 영역을 수동으로 설정하려면 [옵션 2: Machine Learning 작업 영역 수동 설정](#ml-workspace-manual) 섹션의 지침을 따른 다음 [Supply Chain Management에서 Azure Machine Learning Service 연결 매개 변수 설정](#demand-forecast-parameters) 섹션으로 건너뜁니다. 이 옵션은 시간이 더 걸리지만 더 많은 제어를 제공합니다.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>옵션 1: Machine Learning 작업 공간을 자동으로 설정하는 스크립트 실행

이 섹션에서는 Microsoft에서 제공하는 자동화된 스크립트를 사용하여 Machine Learning 작업 영역을 설정하는 방법을 설명합니다. 원하는 경우 [옵션 2: Machine Learning 작업 영역 수동 설정](#ml-workspace-manual) 섹션의 지침에 따라 모든 리소스를 수동으로 설정할 수 있습니다. 두 옵션을 모두 완료할 필요는 없습니다.

1. GitHub에서 Azure Machine Learning 리포지토리(리포지토리)를 사용하여 [Dynamics 365 Supply Chain Management 수요 예측용 템플릿](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service)을 열고 다음 파일을 다운로드합니다.

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. PowerShell 창을 열고 이전 단계에서 다운로드한 **quick_setup.ps1** 스크립트를 실행합니다. 화면의 지시를 따릅니다. 스크립트는 필요한 작업 영역, 스토리지, 기본 데이터 저장소 및 컴퓨팅 리소스를 설정합니다. 그러나 이 절차의 나머지 단계에 따라 필요한 파이프라인을 생성해야 합니다. (파이프라인은 Supply Chain Management에서 예측 스크립트를 시작하는 방법을 제공합니다.)
1. Azure Machine Learning Studio에서 1단계에서 다운로드한 **sampleInput.csv** 파일을 *demplan-azureml* 이라는 컨테이너에 업로드합니다. (quick_setup.ps1 스크립트가 이 컨테이너를 생성했습니다.) 이 파일은 파이프라인을 게시하고 테스트 예측을 생성하는 데 필요합니다. 지침은 [블록 Blob 업로드](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob)를 참조하세요.
1. Azure Machine Learning Studio의 탐색기에서 **노트북** 을 선택합니다.
1. **Files** 구조에서 다음 위치를 찾으십시오: **Users/\[현재 사용자\]/src.**
1. 1단계에서 다운로드한 나머지 4개의 파일을 이전 단계에서 찾은 위치에 업로드합니다.
1. 방금 업로드한 **api_trigger.py** 파일을 선택하고 실행합니다. API를 통해 트리거될 수 있는 파이프라인을 생성합니다.
1. 이제 작업 영역이 설정되었습니다. [Supply Chain Management에서 Azure Machine Learning Service 연결 매개 변수 설정](#demand-forecast-parameters) 섹션으로 건너뛰세요.

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>옵션 2: Machine Learning 작업 영역 수동 설정

이 섹션에서는 Machine Learning 작업 영역을 수동으로 설정하는 방법을 설명합니다. [옵션 1: Machine Learning 작업 영역 설정을 위한 스크립트 실행](#ml-workspace-script) 섹션에 설명된 대로 자동화된 설정 스크립트를 실행하지 않기로 결정한 경우에만 이 섹션의 절차를 완료해야 합니다.

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>1단계: 새 작업 영역 만들기

다음 절차를 사용하여 새 기계 학습 작업 영역을 만듭니다.

1. Azure Portal에 로그인합니다.
1. **Machine learning** 서비스를 엽니다.
1. 도구 모음에서 **만들기** 를 선택하여 **만들기** 마법사를 엽니다.
1. 화면의 지시에 따라 마법사를 완료합니다. 작업할 때 다음 사항에 유의하세요.

    - 이 목록의 다른 지점에서 다른 설정을 권장하지 않는 한 기본 설정을 사용합니다.
    - Supply Chain Management 인스턴스가 배포된 지역과 일치하는 지역을 선택해야 합니다. 그렇지 않으면 일부 데이터가 지역 경계를 통과할 수 있습니다. 자세한 내용은 이 항목 뒷부분의 [개인 정보 보호 고지](#privacy)를 참조하세요.
    - 리소스 그룹, 스토리지 계정, 컨테이너 레지스트리, Azure 키 자격 증명 모음 및 네트워킹 리소스와 같은 전용 리소스를 사용합니다.
    - 마법사의 **Azure Machine Learning Service 연결 매개 변수 설정** 페이지에서 스토리지 계정 이름을 제공해야 합니다. 수요 예측 전용 계정을 사용하세요. 수요 예측 입력 및 출력 데이터는 이 스토리지 계정에 저장됩니다.

자세한 내용은 [작업 영역 만들기](/azure/machine-learning/quickstart-create-resources#create-the-workspace)를 참조하세요.

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>2단계: 스토리지 구성

다음 절차에 따라 스토리지를 설정하세요.

1. GitHub에서 [Azure Machine Learning 리포지토리를 사용하여 Dynamics 365 Supply Chain Management 수요 예측용 템플릿](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service)을 열고 **sampleInput.csv** 파일을 다운로드합니다.
1. [1단계: 새 작업 영역 만들기](#create-workspace) 섹션에서 만든 스토리지 계정을 엽니다.
1. [컨테이너 만들기](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)의 지침에 따라 *demplan-azureml* 이라는 컨테이너를 만듭니다.
1. 1단계에서 다운로드한 **sampleInput.csv** 파일을 방금 생성한 컨테이너에 업로드합니다. 이 파일은 파이프라인을 게시하고 테스트 예측을 생성하는 데 필요합니다. 지침은 [블록 Blob 업로드](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob)를 참조하세요.

##### <a name="step-3-configure-a-default-datastore"></a>3단계: 기본 데이터 저장소 구성

다음 절차에 따라 기본 데이터 저장소를 설정하세요.

1. Azure Machine Learning Studio의 탐색기에서 **데이터 저장소** 를 선택합니다.
1. [2단계: 스토리지 구성](#config-storage) 섹션에서 만든 *demplan-azureml* Blob 저장소 컨테이너를 가리키는 *Azure Blob Storage* 유형의 새 데이터 저장소를 만듭니다. (새 데이터 저장소의 인증 유형이 *계정 키* 인 경우 생성된 스토리지 계정에 대한 계정 키를 제공하세요. 지침은 [스토리지 계정 액세스 키 관리](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal)를 참조하세요.)
1. 세부 정보를 열고 **기본 데이터 저장소로 설정** 을 선택하여 새 데이터 저장소를 기본 데이터 저장소로 만듭니다.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>4단계: 컴퓨팅 리소스 구성

다음 절차에 따라 Azure Machine Learning Studio에서 컴퓨팅 리소스를 설정하여 예측 생성 스크립트를 실행합니다.

1. [1단계: 새 작업 영역 만들기](#create-workspace) 섹션에서 만든 기계 학습 작업 영역에 대한 세부 정보 페이지를 엽니다. **Studio 웹 URL** 값을 찾아 링크를 선택하여 엽니다.
1. 탐색 창에서 **계산** 을 선택합니다.
1. **컴퓨팅 인스턴스** 탭에서 **새로 만들기** 를 선택하여 새 컴퓨팅 인스턴스를 만드는 데 도움이 되는 마법사를 엽니다. 화면의 지시를 따릅니다. 컴퓨팅 인스턴스는 수요 예측 파이프라인을 생성하는 데 사용됩니다(파이프라인 게시 후 삭제할 수 있음). 기본 설정을 사용합니다.
1. **컴퓨팅 클러스터** 탭에서 **새로 만들기** 를 선택하여 새 컴퓨팅 클러스터를 만드는 데 도움이 되는 마법사를 엽니다. 화면의 지시를 따릅니다. 컴퓨팅 클러스터는 수요 예측을 생성하는 데 사용됩니다. 설정은 성능과 실행의 최대 병렬화 수준에 영향을 줍니다. 다음 필드를 설정하되 다른 모든 필드에는 기본 설정을 사용하세요.

    - **이름** – *e2ecpucluster* 를 입력합니다.
    - **가상 머신 크기** – 수요 예측을 위한 입력으로 사용할 데이터의 양에 따라 이 설정을 조정합니다. 노드 수는 수요 예측 생성을 트리거하는 데 하나의 노드가 필요하고 예측을 생성하는 데 사용할 수 있는 최대 노드 수가 10이기 때문에 노드 수는 11을 초과해서는 안 됩니다. ([5단계: 파이프라인 생성](#create-pipelines) 섹션의 parameters.py 파일에서도 노드 수를 설정합니다.) 각 노드에는 예측 스크립트를 병렬로 실행하는 여러 작업자 프로세스가 있습니다. 작업의 총 작업자 프로세스 수는 *노드에 있는 코어 수* × *노드 수* 입니다. 예를 들어, 컴퓨팅 클러스터의 유형이 *Standard\_D4*(코어 8개)이고 노드가 최대 11개이고 parameters.py 파일에서 `nodes_count` 값이 *10* 으로 설정되어 있는 경우 효과적인 병렬 처리 수준은 80입니다.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>5단계: 파이프라인 생성

파이프라인은 Supply Chain Management에서 예측 스크립트를 시작하는 방법을 제공합니다. 다음 절차에 따라 필요한 파이프라인을 생성하세요.

1. GitHub에서 Azure Machine Learning 리포지토리(리포지토리)를 사용하여 [Dynamics 365 Supply Chain Management 수요 예측용 템플릿](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service)을 열고 다음 파일을 다운로드합니다.

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Azure Machine Learning Studio의 탐색기에서 **노트북** 을 선택합니다.
1. **Files** 구조에서 다음 위치를 찾으십시오: **Users/\[현재 사용자\]/src.**
1. 1단계에서 다운로드한 4개의 파일을 이전 단계에서 찾은 위치에 업로드합니다.
1. Azure에서 방금 업로드한 **parameters.py** 파일을 열고 검토합니다. `nodes_count` 값이 [4단계: 컴퓨팅 리소스 구성](#config-compute-resources) 섹션에서 컴퓨팅 클러스터에 대해 구성한 값보다 하나 작은지 확인합니다. `nodes_count` 값이 컴퓨팅 클러스터의 노드 수보다 크거나 같으면 파이프라인 실행이 시작될 수 있습니다. 그러나 필요한 리소스를 기다리는 동안 응답을 중지합니다. 노드 수에 대한 자세한 내용은 [4단계: 컴퓨팅 리소스 구성](#config-compute-resources) 섹션을 참조하세요.
1. 방금 업로드한 **api_trigger.py** 파일을 선택하고 실행합니다. API를 통해 트리거될 수 있는 파이프라인을 생성합니다.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>새 Active Directory 애플리케이션 설정

서비스 주체를 사용하여 수요 예측 전용 리소스로 인증하려면 Active Directory 애플리케이션이 필요합니다. 따라서 애플리케이션에는 예측을 생성하는 데 필요한 가장 낮은 수준의 권한이 있어야 합니다.

1. Azure Portal에 로그인합니다.
1. 테넌트의 Azure AD(Azure Active Directory)에 새 애플리케이션을 등록합니다. 지침은 [포털을 사용하여 리소스에 액세스할 수 있는 Azure AD 애플리케이션 및 서비스 주체 만들기](/azure/active-directory/develop/howto-create-service-principal-portal)를 참조하세요.
1. 마법사를 완료하면 화면의 지시를 따릅니다. 기본 설정을 사용합니다.
1. [Azure에서 기계 학습 설정](#ml-workspace) 섹션에서 만든 다음 리소스에 대한 액세스 권한을 새 Active Directory 애플리케이션에 부여합니다. 지침은 [Azure Portal을 사용하여 Azure 역할 할당](/azure/role-based-access-control/role-assignments-portal?tabs=current)을 참조하세요. 이 단계를 통해 시스템은 예측 데이터를 가져오고 내보내고 Supply Chain Management에서 기계 학습 파이프라인 실행을 트리거할 수 있습니다.

    - Machine Learning 작업 영역에 대한 기여자 역할
    - 전용 스토리지 계정에 대한 기여자 역할
    - 전용 스토리지 계정에 대한 Blob Storage 데이터 기여자 역할

1. 생성한 애플리케이션의 **인증서 및 비밀** 섹션에서 애플리케이션에 대한 비밀을 생성합니다. 지침은 [클라이언트 암호 추가](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)를 참조하세요.
1. 애플리케이션 ID와 해당 암호를 기록해 둡니다. 나중에 Supply Chain Management에서 **수요 예측 매개 변수** 페이지를 설정할 때 이 애플리케이션의 세부 사항이 필요합니다.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Supply Chain Management에서 Azure Machine Learning Service 연결 매개 변수 설정

다음 절차를 사용하여 Supply Chain Management 환경을 Azure에서 방금 설정한 기계 학습 서비스에 연결합니다.

1. Supply Chain Management에 로그인합니다.
1. **기준 계획 \> 설정 \> 수요 예측 \> 수요 예측 매개 변수** 로 이동합니다.
1. **일반** 탭에서 **예측 생성 전략** 필드가 *Azure Machine Learning Servic* e로 설정되어 있는지 확인합니다.
1. **항목 할당 키** 탭에서 수요 예측에 *Azure Machine Learning Service* 를 사용해야 하는 각 할당 키에 대해 **예측 생성 전략** 필드가 Azure Machine Learning Service로 설정되어 있는지 확인합니다.
1. **Azure Machine Learning Service** 탭에서 다음 필드를 설정합니다.

    - **테넌트 ID** – Azure 테넌트의 ID를 입력합니다. Supply Chain Management는 이 ID를 사용하여 Azure Machine Learning Service에 인증합니다. Azure Portal의 Azure AD **개요** 페이지에서 테넌트 ID를 찾을 수 있습니다.
    - **서비스 주체 애플리케이션 ID** – [Active Directory 애플리케이션](#aad-app) 섹션에서 생성한 애플리케이션의 애플리케이션 ID를 입력합니다. 이 값은 Azure Machine Learning Service에 대한 API 요청을 승인하는 데 사용됩니다.
    - **서비스 주체 암호** – [Active Directory 애플리케이션](#aad-app) 섹션에서 생성한 애플리케이션에 대한 서비스 주체 애플리케이션 비밀을 입력합니다. 이 값은 Azure Storage 및 Azure Machine Language 작업 영역에 대해 승인된 작업을 수행하기 위해 만든 보안 주체에 대한 액세스 토큰을 얻는 데 사용됩니다.
    - **스토리지 계정 이름** – Azure 작업 영역에서 설정 마법사를 실행할 때 지정한 Azure 스토리지 계정 이름을 입력합니다. (자세한 내용은 [Azure에서 기계 학습 설정](#ml-workspace) 섹션을 참조하세요.)
    - **파이프라인 엔드포인트 주소** – Azure Machine Learning Service에 대한 파이프라인 REST 엔드포인트의 URL을 입력합니다. [Azure에서 기계 학습을 설정](#ml-workspace)할 때 마지막 단계로 이 파이프라인을 만들었습니다. 파이프라인 URL을 가져오려면 Azure Portal에 로그인하고 탐색에서 **파이프라인** 을 선택합니다. **파이프라인** 탭에서 이름이 **TriggerDemandForecastGeneration** 인 파이프라인 엔드포인트를 선택합니다. 그런 다음 표시된 REST 엔드포인트를 복사합니다.

    ![수요 예측 매개 변수 페이지의 Azure Machine Learning Service 탭에 있는 매개 변수.](media/azure-ml-service-parameters.png "수요 예측 매개 변수 페이지의 Azure Machine Learning Service 탭에 있는 매개 변수")

## <a name="privacy-notice"></a><a name="privacy"></a>개인정보보호 통지

*Azure Machine Learning Service* 를 예측 생성 전략으로 선택하면 Supply Chain Management에서 집계된 수량, 제품 이름 및 제품 치수, 배송 및 수령 위치, 고객 식별자, 예측 매개 변수와 같은 과거 수요에 대한 고객 데이터를 자동으로 보냅니다. 미래 수요를 예측할 목적으로 기계 학습 작업 영역과 연결된 스토리지 계정이 있는 지리적 지역으로 이동합니다. Azure Machine Learning Service는 Supply Chain Management가 배포된 지역과 다른 지역에 있을 수 있습니다. 일부 사용자는 **수요 예측 매개 변수** 페이지에서 예측 생성 전략을 선택하여 이 기능의 활성화 여부를 제어할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [수요 예측 개요](introduction-demand-forecasting.md)
- [통계 기준선 예측 생성](generate-statistical-baseline-forecast.md)
- [기준선 예측을 수동으로 조정](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
