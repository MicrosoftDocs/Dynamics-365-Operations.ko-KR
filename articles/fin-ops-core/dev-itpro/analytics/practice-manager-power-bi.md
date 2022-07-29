---
title: 실무 담당자 Power BI 콘텐츠
description: 이 항목에서는 실무 관리자 Power BI 콘텐츠에 포함된 항목에 대해 설명합니다.
author: kfend
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjManagementWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 4acef3c595f25fa0be16945a9f41611832cfcea9
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2021
ms.locfileid: "8460827"
---
# <a name="practice-manager-power-bi-content"></a>실무 담당자 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 **실무 관리자** Microsoft Power BI 콘텐츠에 포함된 항목에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용되는 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**실무 관리자** Power BI 콘텐츠는 실무 관리자와 프로젝트 관리자를 위해 만들어졌습니다. 조직에서 작업 중인 프로젝트와 관련된 주요 메트릭을 제공합니다. 대시보드는 프로젝트 및 관련 고객에 대한 개요를 제공합니다. 보고서 수준 필터를 사용하여 특정 법인에 대해 보고할 수 있습니다. 이 Power BI 콘텐츠는 프로젝트 회계 집계 측정값에서 데이터를 가져옵니다.

**실무 관리자** Power BI 콘텐츠에는 5개의 보고서 페이지가 포함되어 있습니다. 하나는 개요 페이지이고 다른 하나는 프로젝트 비용, 수익, 획득 가치 관리 및 다양한 차원에 걸쳐 분류된 시간 측정항목에 대한 세부 정보를 제공하는 네 페이지입니다.

콘텐츠의 모든 금액은 시스템 통화로 표시됩니다. **시스템 매개 변수** 페이지에서 시스템 통화를 설정할 수 있습니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스

**실무 담당자** Power BI 내용은 **프로젝트 관리** 작업 공간에 표시됩니다.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서

다음 표는 **실무 관리자** Power BI 콘텐츠의 각 보고서 페이지에 있는 메트릭에 대한 세부 정보를 제공합니다.

| 보고서 페이지       | 메트릭 |
|-------------------|---------|
| 프로젝트 개요 | <ul><li>만든 프로젝트</li><li>예상 프로젝트</li><li>진행 중인 프로젝트</li><li>고객별 실제 수익</li><li>프로젝트별 예산 매상 총이익</li><li>획득가치 관리 개요</li></ul> |
| 비용              | <ul><li>월별 실제 대 예산 비용</li><li>연도별 실제 대 예산 비용</li><li>카테고리별 실제 대 예산 비용</li><li>거래 유형별 실제 비용</li></ul> |
| 수익           | <ul><li>월별 실제 수익</li><li>우편번호별 실제 수익</li><li>카테고리별 실제 대 예산 수익</li><li>고객 업계별 실제 수익</li></ul> |
| EVM               | 프로젝트별 비용 및 일정 성과 지표 |
| 시간             | <ul><li>실제 청구 가능 활용 시간 대 실제 청구 가능 배분 시간 대 예산 시간</li><li>프로젝트별 실제 청구 가능 활용 시간 대 실제 청구 가능 배분 시간</li><li>리소스별 실제 청구 가능 활용 시간 대 실제 청구 가능 배분 시간</li><li>프로젝트별 실제 청구 가능 시간 비율</li><li>리소스별 실제 청구 가능 시간 비율</li></ul> |

이러한 모든 보고서의 차트와 타일을 필터링하여 대시보드에 고정할 수 있습니다. Power BI에서 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/)을 참조하세요. 기본 데이터 내보내기 기능을 사용하여 시각화에 요약된 기본 데이터를 내보낼 수도 있습니다.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해

다음 데이터는 **실무 담당자** Power BI 콘텐츠에서 보고서 페이지를 작성하는 데 사용됩니다. 이 데이터는 엔터티 저장소에 준비된 집계 측정값으로 표시됩니다. 엔터티 스토어는 분석에 최적화된 Microsoft SQL Server 데이터베이스입니다. 자세한 내용은 [엔터티 스토어와 Power BI 통합](power-bi-integration-entity-store.md)을 참조하세요.

다음 섹션에서는 각 엔터티에서 사용되는 집계 측정값에 대해 설명합니다.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>엔터티: ProjectAccountingCube\_ActualHourUtilization
**데이터 원본:** ProjEmplTrans

| 주요 집계 측정      | 필드                              | 설명 |
|--------------------------------|------------------------------------|-------------|
| 실제 청구 가능 사용 시간 | 합계(ActualUtilizationBillableRate) | 실제 청구 가능 사용 시간 합계. |
| 실제 청구 가능 부담 시간   | Sum(ActualBurdenBillableRate)      | 실제 부담률의 합계입니다. |

### <a name="entity-projectaccountingcube_actuals"></a>엔터티: ProjectAccountingCube\_Actuals
**데이터 소스:** ProjTransPosting

| 주요 집계 측정 | 필드              | 설명 |
|---------------------------|--------------------|-------------|
| 실제 수익            | 합계(실제 수익) | 모든 거래에 대해 게시된 총 수익입니다. |
| 실제 비용               | 합계(실제비용)    | 모든 거래 유형에 대해 게시된 총 비용입니다. |

### <a name="entity-projectaccountingcube_customer"></a>엔터티: ProjectAccountingCube\_Customer
**데이터 원본:** CustTable

| 주요 집계 측정 | 필드                                             | 설명 |
|---------------------------|---------------------------------------------------|-------------|
| 프로젝트 수        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | 사용 가능한 프로젝트 수입니다. |

### <a name="entity-projectaccountingcube_forecasts"></a>엔터티: ProjectAccountingCube\_Forecasts
**데이터 원본:** ProjTransBudget

| 주요 집계 측정 | 필드                  | 설명 |
|---------------------------|------------------------|-------------|
| 예산 비용               | Sum(BudgetCost)        | 모든 거래 유형에 대한 총 예측 비용입니다. |
| 예산 수익            | Sum(BudgetRevenue)     | 예측 발생/송장 수익의 합계입니다. |
| 예산 매상 총이익       | Sum(BudgetGrossMargin) | 총 예측 수익 합계와 총 예측 비용 합계 간의 차이입니다. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>엔터티: ProjectAccountingCube\_ProjectPlanCostsView
**데이터 원본:** 프로젝트

| 주요 집계 측정 | 필드                    | 설명 |
|---------------------------|--------------------------|-------------|
| 계획 비용              | Sum(SumOfTotalCostPrice) | 계획된 작업이 있는 모든 프로젝트 트랜잭션 유형에 대한 견적의 총 비용 가격입니다. |

### <a name="entity-projectaccountingcube_projects"></a>엔터티: ProjectAccountingCube\_Projects
**데이터 원본:** 프로젝트

| 주요 집계 측정    | 필드 | 설명 |
|------------------------------|-------|-------------|
| 비용 성과 색인       | ProjectAccountingCube\_Projects\[Earned value\] ÷ ProjectAccountingCube\_Projects\[완료된 작업의 총 실제 비용\] | 총 획득 가치를 총 실제 비용으로 나눈 계산입니다. |
| 공정 성과 색인   | ProjectAccountingCube\_Projects\[Earned value\] ÷ ProjectAccountingCube\_Projects\[완료된 작업의 총 계획 비용\] | 총 획득 가치를 총 계획 비용으로 나눈 계산입니다. |
| 작업 완료율 | 작업 완료율 = ProjectAccountingCube\_Projects\[완료된 작업의 총 실제 비용\] ÷ (ProjectAccountingCube\_Projects\[완료된 작업의 총 실제 비용\] + ProjectAccountingCube\_Projects\[프로젝트의 총 계획 비용\] – ProjectAccountingCube\_Projects\[완료된 작업의 총 계획 비용\]) | 완료된 작업의 총 실제 비용과 프로젝트의 계획된 비용을 기반으로 한 완료된 작업의 총 백분율입니다. |
| 실제 청구 가능 시간 비율  | ProjectAccountingCube\_Projects\[프로젝트 총 실제 청구 가능 활용 시간\] ÷ (ProjectAccountingCube\_Projects\[프로젝트 총 실제 청구 가능 활용 시간\] + ProjectAccountingCube\_Projects\[프로젝트 총 실제 청구 가능 배분 시간\]) | 사용 시간 및 부담 시간을 기준으로 한 총 실제 청구 가능 시간입니다. |
| 획득한 가치                 | ProjectAccountingCube\_Projects\[프로젝트의 총 계획 비용\] × ProjectAccountingCube\_Projects\[작업 완료율\] | 총 계획 비용에 완료된 작업의 백분율을 곱한 값입니다. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>엔터티: ProjectAccountingCube\_TotalEstimatedCosts 
**데이터 원본:** ProjTable

| 주요 집계 측정       | 필드               | 설명 |
|---------------------------------|---------------------|-------------|
| 완료된 활동 계획 비용 | Sum(TotalCostPrice) | 완료된 작업이 있는 모든 프로젝트 트랜잭션 유형에 대한 견적의 총 비용 가격입니다. |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
