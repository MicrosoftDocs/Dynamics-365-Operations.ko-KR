---
title: 생산 실적 Power BI 콘텐츠
description: 이 항목에서는 생산 실적 Power BI 콘텐츠에 포함된 항목에 대해 설명합니다.
author: AndersGirke
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProductionPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 940e49b43ec1dba0917c67ad6ef4562351d175bcb1c0be7f98d00e73371e5346
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460825"
---
# <a name="production-performance-power-bi-content"></a>생산 실적 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 **생산 실적** Microsoft Power BI 콘텐츠에 포함된 항목에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**생산 실적** Power BI 콘텐츠는 생산 관리를 담당하는 조직의 생산 관리자 또는 개인을 위한 것입니다.

포함된 보고서를 사용하면 Power BI로 적시 실행, 품질 및 비용과 관련하여 제조 작업의 성능을 모니터링할 수 있습니다. 이 보고서는 생산 주문 및 배치 주문의 거래 데이터를 사용하며 회사 전체의 생산 메트릭에 대한 집계 보기와 제품 및 리소스별 메트릭 분석을 모두 제공합니다.

Power BI 콘텐츠는 적시에 완전히 생산을 완료할 수 있는 조직의 능력을 강조합니다. 향후 실적은 생산 계획에 따라 예측됩니다. 포괄적인 보고서는 생산으로 인한 제품 결함과 리소스 및 운영의 결함 비율에 대한 자세한 통찰력을 제공합니다.

이 Power BI 콘텐츠를 통해 생산 차이를 분석할 수도 있습니다. 생산 차이는 예상 비용과 실현 비용의 차이로 계산됩니다. 생산 차이는 생산 주문 또는 배치 주문이 **종료됨** 상태에 도달할 때 계산됩니다.

**생산 실적** Power BI 콘텐츠에는 생산 주문 및 배치 주문에서 비롯된 데이터가 포함됩니다. 보고서에는 칸반 제작과 관련된 데이터가 포함되지 않습니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**생산 실적** Power BI 콘텐츠는 **생산 실적** 페이지(**생산 관리** \> **문의 및 신고** \> **생산 실적 분석** \> **생산 실적**)에 표시됩니다. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 메트릭

**생산 실적** Power BI 콘텐츠에는 일련의 보고서 페이지가 포함됩니다. 각 페이지는 차트, 타일 및 테이블로 시각화되는 메트릭 세트로 구성됩니다.

다음 표는 포함된 시각화에 대한 개요를 제공합니다.

| 보고서 페이지                                | 차트 | 타일 |
|--------------------------------------------|--------|-------|
| 생산실적                     | <ul><li>날짜별 생산 수</li><li>제품별, 품목군별 생산수</li><li>날짜별 계획된 생산 수</li><li>정시 &amp; 전체 기준 하위 10개 제품</li></ul> | <ul><li>총 주문</li><li>정시 &amp; 전체 %</li><li>미완료 %</li><li>조기 %</li><li>늦음 %</li></ul> |
| 제품별 하자                         | <ul><li>날짜별 불량률(ppm)</li><li>제품 및 품목군별 불량률(ppm)</li><li>날짜별 생산 수량</li><li>유효율 기준 상위 10개 제품</li></ul> | <ul><li>결함률(ppm)</li><li>결함 수량</li><li>총 수량</li></ul> |
| 제품별 하자 동향                   | 생산량별 불량률(ppm) | 결함률(ppm) |
| 리소스별 결함                        | <ul><li>날짜별 결함률(ppm)</li><li>자원별, 현장별 불량률(ppm)</li><li>작업별 결함률(ppm)</li><li>결함률별 상위 10개 리소스</li></ul> | 결함 수량 |
| 리소스별 하자 동향                  | 처리된 수량별 불량률(ppm) | |
| 작업 주문 원가 계산에 대한 생산 차이 | <ul><li>일자별 및 원가군 유형별 생산차이</li><li>사이트 및 원가군 유형별 생산차이</li><li>생산 편차가 좋지 않은 상위 10개 제품</li><li>리소스별 생산 편차가 좋지 않은 상위 10개 제품</li></ul> | <ul><li>실현 비용</li><li>생산 변화</li><li>생산 변화 %</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해

다음 데이터는 **생산 실적** Power BI 콘텐츠에서 보고서 페이지에 사용됩니다. 이 데이터는 엔터티 저장소에 준비된 집계 측정값으로 표시됩니다. 엔터티 스토어는 분석에 최적화된 Microsoft SQL Server 데이터베이스입니다. 엔터티 저장소에 대해 자세히 알아보려면 [엔티티 스토어와 Power BI 통합](power-bi-integration-entity-store.md)을 참조하세요.

다음 표는 Power BI 콘텐츠의 기준으로 사용되는 주요 집계 측정값을 보여줍니다.

| 엔터티                   | 주요 집계 측정  | 재무 및 운영 앱용 데이터 소스 | 필드              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

다음 표는 주요 집계 측정값을 사용하여 콘텐츠 데이터세트에서 여러 계산된 측정값을 만드는 방법을 보여줍니다.

| 측정                  | 측정값 계산 방법 |
|--------------------------|-------------------------------|
| 생산 변화, %   | SUM('생산 편차'\[생산 편차\]) / SUM('생산 편차'\[예상 비용\]) |
| 모든 계획된 주문       | COUNTROWS('계획된 생산 주문') |
| 조기                    | COUNTROWS(FILTER('계획된 생산 주문', '계획된 생산 주문\[예정된 종료일\] \< '계획된 생산 주문'\[요구 일자\])) |
| 늦음                     | COUNTROWS(FILTER('계획된 생산 주문', '계획된 생산 주문\[예정된 종료일\] \> '계획된 생산 주문'\[요구 일자\])) |
| 정시                  | COUNTROWS(FILTER('계획된 생산 주문', '계획된 생산 주문\[예정된 종료일\] = '계획된 생산 주문'\[요구 일자\])) |
| 정시 %                | IF ( '계획된 생산 주문'\[On-time\] \<\> 0, '계획된 생산 주문'\[On-time\], IF ('계획된 생산 주문'\[모든 계획된 주문\] \<\> 0, 0, BLANK()) ) / '계획된 생산 주문'\[모든 계획된 주문\] |
| 완료됨                | COUNTROWS(FILTER('생산 주문', '생산 주문'\[Is RAF'ed\] = TRUE)) |
| 결함률(ppm)     | IF( '생산 주문'\[총 수량\] = 0, BLANK(), (SUM('생산 주문'\[결함 수량\]) / '생산 주문'\[총 수량\]) \* 1000000) |
| 지연된 생산율  | '생산 주문'\[지연 \#\] / '생산 주문'\[완료됨\] |
| 조기 및 전체          | COUNTROWS(FILTER('제작 주문', '제작 주문'\[Is in full\] = TRUE && '생산 주문'\[Is early\] = 참)) |
| 조기 \#                 | COUNTROWS(FILTER('생산 주문', '생산 주문'\[Is early\] = TRUE)) |
| 조기 %                  | IFERROR( IF('생산 주문'\[조기 \#\] \<\> 0, '생산 주문'\[조기 \#\], IF('생산 주문'\[총 주문\] = 0, BLANK(), 0)) / '생산 주문'\[총 주문\], BLANK()) |
| 완료 안 됨               | COUNTROWS(FILTER('제작 주문', '제작 주문'\[Is in full\] = FALSE && '생산 주문'\[Is RAF'ed\] = 참)) |
| 미완료 %             | IFERROR( IF('생산 주문'\[미완료\] \<\> 0, '생산 주문'\[미완료\], IF('생산 주문'\[총 주문\] = 0, BLANK(), 0)) / '생산 주문'\[총 주문\], BLANK()) |
| 지연됨               | '생산 주문'\[Is RAF'ed\] = TRUE && '생산 주문'\[지연된 값\] = 1 |
| 조기임                 | '생산 주문'\[Is RAF'ed\] = TRUE && '생산 주문'\[지연 일\] \< 0 |
| 전체임               | '생산 주문'\[양호 수량\] \>= '생산 주문'\[예정된 수량\] |
| Is RAF'ed                | '생산 주문'\[생산 상태 값\] = 5 \|\| '생산 주문'\[생산 상태 값\] = 7 |
| 지연 및 전체           | COUNTROWS(FILTER('제작 주문', '제작 주문'\[Is in full\] = TRUE && '생산 주문'\[I지연됨\] = 참)) |
| 지연 \#                  | COUNTROWS(FILTER('생산 주문', '생산 주문'\[지연됨\] = TRUE)) |
| 늦음 %                   | IFERROR( IF('생산 주문'\[지연 \#\] \<\> 0, '생산 주문'\[지연 \#\], IF('생산 주문'\[총 주문\] = 0, BLANK(), 0)) / '생산 주문'\[총 주문\], BLANK()) |
| 정시 및 전체        | COUNTROWS(FILTER('생산 주문', '생산 주문'\[만기임\] = TRUE && '생산 주문'\[지연됨\] = FALSE && '생산 주문'\[조기\] = FALSE)) |
| 정시 및 전체 %      | IFERROR( IF('생산 주문'\[정시 및 만기\] \<\> 0, '생산 주문'\[정시 및 만기\], IF('생산 주문'\[완료됨\] = 0, BLANK(), 0)) / '생산 주문'\[완료됨\], BLANK()) |
| 총 주문             | COUNTROWS('생산 주문') |
| 총 수량           | SUM('생산 주문'\[양호 수량\]) + SUM('생산 주문'\[결함 수량\]) |
| 결함률(ppm)        | IF( '트랜잭션 경로'\[처리량\] = 0, BLANK(), (SUM('트랜잭션 경로'\[불량 수량\]) / '트랜잭션 경로 지정'\[처리량\])\* 1000000) |
| 혼합 불량률(ppm) | IF( '트랜잭션 경로'\[총 혼합 수량\] = 0, BLANK(), (SUM('트랜잭션 경로'\[불량 수량\]) / '트랜잭션 경로 지정'\[총 혼합 수량\])\* 1000000) |
| 처리 수량       | SUM('트랜잭션 경로'\[좋은 수량\]) + SUM('트랜잭션 경로'\[불량 수량\]) |
| 총 혼합 수량     | SUM('생산 주문'\[좋은 수량\]) + SUM('트랜잭션 경로'\[불량 수량\]) |

다음 표는 집계 측정값을 조각화하는 필터로 사용되는 주요 차원을 보여줍니다. 따라서 더 세분화되고 심층적인 분석 통찰력을 얻을 수 있습니다.

| 엔터티                    | 특성의 예                                        |
|---------------------------|---------------------------------------------------------------|
| 완료 날짜로 보고됨 | 완료(RAF) 날짜, 월 및 연도 오프셋                 |
| 종료 날짜                | 종료 월 오프셋 및 월                                  |
| 요구 날짜          | 요구 날짜 월 오프셋 및 요구 날짜            |
| 라우팅 거래일    | 거래 월 오프셋 및 날짜 라우팅                       |
| 사이트                     | 사이트 ID, 사이트 이름, 주 및 도시                          |
| 엔터티                  | ID와 이름                                                   |
| 리소스                 | 리소스 ID, 리소스 이름, 리소스 유형 및 리소스 그룹 |
| 제품                  | 제품 번호, 제품 이름, 항목 ID 및 항목 그룹         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]