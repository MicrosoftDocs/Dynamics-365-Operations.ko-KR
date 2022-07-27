---
title: 기준선 예측을 수동으로 조정
description: 이 토픽에서는 기준선 예측을 수동으로 조정하고 예측 세부 정보를 보는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d00061efa551c9fe2ad9d0e441bba44e70b071c
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450031"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>기준선 예측을 수동으로 조정

[!include [banner](../includes/banner.md)]

이 토픽에서는 기준선 예측을 수동으로 조정하고 예측 세부 정보를 보는 방법에 대해 설명합니다. 

수동 조정을 수행하기 전에 다양한 페이지의 몇 가지 개념을 이해하는 것이 중요합니다.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>조정된 수요 예측 페이지의 그리드
**조정된 수요 예측** 페이지에는 다음 구조의 그리드가 포함됩니다.

-   첫 번째 열에는 예측이 생성된 항목, 항목 할당 키, 회사 등이 표시됩니다. 페이지의 부제목은 그리드에 표시되는 현재 예측 차원에 대한 설명을 제공합니다. 예를 들어, 페이지의 부제가 **회사 / 사이트 / 항목 할당 키** 이고 그리드의 행 헤더 중 하나가 **USMF / 1 / D\_Alloc** 인 경우 해당 행은 USMF 회사, 사이트 1 및 **D\_Alloc** 항목 할당 키에 대한 예측을 표시합니다.
-   후속 열은 예측이 생성된 예측 버킷을 나타냅니다. 각 열 헤더는 열에 표시되는 예측 버킷의 첫 번째 날짜입니다.
-   셀의 값은 특정 예측 버킷에 대한 한 항목, 항목 할당 키 등에 대한 예측을 나타냅니다.

## <a name="forecast-aggregation-and-de-aggregation"></a>예측 집계 및 집계 해제
페이지의 부제목은 예측 집계 수준을 보여줍니다. 

예를 들어 페이지의 부제목이 **회사/사이트/할당키/품목번호/색상/크기/구성/스타일** 인 경우 예측 집계가 없으며 예측은 항목 및 해당 차원의 수준에서 표시됩니다. 집계를 변경하려면 애플리케이션 메뉴에서 열 수 있는 **예측 차원 변경** 페이지를 사용합니다. 

예측을 수정하려면 사용 가능한 셀을 클릭하고 조정된 예측 값을 입력합니다. 편집된 셀은 표시되는 예측이 수요 예측 서비스에서 생성된 예측이 아니라 수동으로 조정되었음을 나타내기 위해 즉시 굵게 표시됩니다. 

페이지에 더 많은 집계 데이터를 표시하도록 집계를 변경하는 경우 **수요 예측** 라인 페이지를 사용하여 집계된 예측을 구성하는 개별 예측 라인을 볼 수 있습니다. 

예를 들어, 항목 수준에서 예측을 생성했지만 판촉 또는 기타 유사한 이벤트로 인해 이 항목에 대한 수요가 모든 사이트에서 증가할 것임을 알고 있습니다. 이 경우 **예측 차원 변경** 페이지에서 집계를 **회사/항목 할당 키/항목** 으로 설정할 수 있습니다 **조정된 수요 예측** 그리드의 모든 사이트에서 항목에 대한 글로벌 예측을 조정할 수 있습니다. 모든 사이트에서 변경 사항의 효과를 보려면 **수요 예측 라인** 페이지를 엽니다. 이 페이지에서 각 사이트의 항목, 조정된 예측 수량 및 원래 예측 수량에 대한 한 줄을 볼 수 있습니다. 

집계 레벨에서 예측 수량을 조정하면 시스템은 가중 할당을 사용하여 집계를 생성하는 라인 간에 변경 사항을 분배합니다. 

**총 수량** 값 또는 집계 해제 그리드의 **수량** 셀을 수정하여 **수요 예측 라인** 페이지에서 수동으로 조정할 수도 있습니다.

## <a name="viewing-details-of-the-forecast"></a>예측 세부 정보 보기
**수요 예측 세부 정보** 페이지를 열어 예측에 대한 자세한 정보를 볼 수 있습니다. 

**수요 예측 상세 내역** 페이지는 다음 정보를 그래픽 및 표 형식으로 표시합니다.

-   예측 예측의 기반이 되는 과거 수요입니다.
-   기준 계획에서 사용하는 현재 예측입니다.
-   새 수요 예측 값 및 수동으로 조정된 금액입니다.
-   예측된 값에 대한 신뢰 구간입니다.
-   예측을 생성하는 데 사용된 예측 모델입니다. 집계된 데이터를 보고 있는 경우 모든 집계된 시계열에 사용된 모든 메서드 목록이 표시됩니다.
-   MAPE(내부 모델 정확도)입니다. 예측 정확도에 대한 자세한 내용은 [예측 정확도 모니터링](monitor-forecast-accuracy.md)을 참조하세요.

**메모:**

- *수요 예측 세부 정보에서 예측 모델 선택* 기능은 포함할 예측 모델을 선택할 수 있는 **수요 예측 세부 정보** 페이지에 설정을 추가합니다. Supply Chain Management 버전 10.0.21부터 이 기능은 기본적으로 켜져 있습니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *수요 예측 세부 정보 기능에 대한 예측 모델 선택* 을 검색하여 이 기능을 켜거나 끌 수 있습니다.
- 페이지의 **예측** 섹션에 나타나는 신뢰 구간은 신뢰 구간 상한과 신뢰 구간 하한 간의 차이를 나타냅니다. 상한 및 하한 값을 보려면 **과거 수요 및 예측 그래픽** 섹션의 차트 위로 마우스를 가져갑니다.
- 수요 예측 Microsoft Azure Machine Learning을 사용하는 경우 생성된 예측이 가져야 하는 신뢰 수준 백분율을 지정할 수 있습니다. 신뢰 구간은 수요 예측에 대한 좋은 추정치로 작용하는 값 범위로 구성됩니다. 95% 신뢰 수준 백분율은 수요 예측이 신뢰 구간 범위를 벗어날 위험이 5%임을 나타냅니다.

**예측** 섹션의 **예측** 행에 있는 값을 수정하여 **수요 예측 세부 정보** 페이지에서 예측을 수동으로 조정할 수도 있습니다.

## <a name="additional-resources"></a>추가 리소스

[예측 정확도 모니터링](monitor-forecast-accuracy.md)

[통계 기준선 예측 생성](generate-statistical-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]