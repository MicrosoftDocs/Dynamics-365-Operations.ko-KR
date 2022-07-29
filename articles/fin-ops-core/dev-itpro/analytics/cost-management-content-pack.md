---
title: 비용 관리 Power BI 콘텐츠
description: 이번에는 비용 관리 Power BI 콘텐츠에 포함된 내용을 설명합니다.
author: ShylaThompson
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fbdc6addc820aadc1f5469cb059a62724cfe905
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "8460977"
---
# <a name="cost-management-power-bi-content"></a>비용 관리 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>개요

**비용 관리** Microsoft Power BI 콘텐츠는 재고 또는 WIP(진행 중인 작업)의 상태에 대해 책임이 있거나 관심이 있는 조직의 재고 회계사 또는 개인, 또는 표준 비용 차이 분석을 담당하거나 분석하는 데 관심이 있는 개인을 대상으로 합니다.

이 Power BI 콘텐츠는 인벤토리의 성과를 모니터링하고 비용 흐름을 시각화하는 데 도움이 되는 분류된 형식을 제공합니다. 회전율, 재고 보유 일수, 정확성 및 선호하는 집계 수준(회사, 항목, 항목 그룹 또는 사이트)에서 'ABC 분류'와 같은 관리 통찰력을 얻을 수 있습니다. 제공되는 정보는 재무제표에 대한 상세한 보완 자료로도 사용될 수 있습니다.

Power BI 콘텐츠는 **CostObjectStatementCache** 테이블을 기본 데이터 소스로 포함하는 **CostObjectStatementCacheMonthly** 집계 측정값을 기반으로 합니다. 이 테이블은 데이터 세트 캐시 프레임워크에서 관리합니다. 기본적으로 테이블은 24시간마다 업데이트되지만 데이터 세트 캐시 구성에서 업데이트 빈도를 변경하거나 수동 업데이트를 활성화할 수 있습니다. **비용 관** 리 작업 영역 또는 **비용 분석** 작업 영역에서 수동 업데이트를 실행할 수 있습니다.

**CostObjectStatementCache** 테이블을 업데이트할 때마다 Power BI 시각화의 데이터가 업데이트되기 전에 **CostObjectStatementCacheMonthly** 집계 측정을 업데이트해야 합니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스

**비용 관리** Power BI 콘텐츠는 **비용 관리** 및 **비용 분석** 작업 공간에 표시됩니다.

**비용 관리** 작업 공간에는 다음 탭이 있습니다.

- **개요** – 이 탭은 애플리케이션 데이터를 보여줍니다.
- **인벤토리 계정 상태** – 이 탭에는 Power BI 콘텐츠가 표시됩니다.
- **제조 회계 상태** – 이 탭에는 Power BI 내용이 표시됩니다.

**비용 분석** 작업 공간에는 다음 탭이 있습니다.

- **개요** – 이 탭은 애플리케이션 데이터를 보여줍니다.
- **재고 회계 분석** – 이 탭은 Power BI 내용을 보여줍니다.
- **제조 회계 분석** – 이 탭은 Power BI 내용을 보여줍니다.
- **표준 비용 차이 분석** – 이 탭에는 Power BI 내용이 표시됩니다.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서 페이지

**비용 관리** Power BI 콘텐츠에는 메트릭 집합으로 구성된 보고서 페이지 집합이 포함됩니다. 이러한 메트릭은 차트, 타일 및 테이블로 시각화됩니다. 

다음 표는 **비용 관리** Power BI 콘텐츠의 시각화 개요를 제공합니다.

### <a name="inventory-accounting-status"></a>재고 회계 상태

| 보고서 페이지                               | 가상화                                   |
|-------------------------------------------|-------------------------------------------------|
| 인벤토리 개요                        | 기초 잔액                               |
|                                           | 순 변화                                      |
|                                           | 순 변화율 %                                    |
|                                           | 종료 잔액                                  |
|                                           | 인벤토리 정확도                              |
|                                           | 재고회전율                        |
|                                           | 현재고 일수                          |
|                                           | 기간 내 활성 제품                        |
|                                           | 기간의 활성 원가 개체                   |
|                                           | 항목 그룹별 잔액                           |
|                                           | 사이트별 잔액                                 |
|                                           | 카테고리별 명세서                           |
|                                           | 분기별 순 변화                           |
| 사이트 및 항목 그룹별 재고 개요 | 사이트별 인벤토리 정확도                      |
|                                           | 사이트별 재고회전율                |
|                                           | 지점별 재고 기말 잔액                |
|                                           | 항목 그룹별 재고 정확도                |
|                                           | 항목군별 재고회전율          |
|                                           | 지점 및 항목 그룹별 재고 기말 잔액 |
| 재고 명세서                       | 재고 명세서                             |
| 사이트별 재고 명세서               | 사이트별 재고 명세서                     |
| 제품 계층별 재고 명세서  | 재고 명세서                             |
| 제품 계층별 재고 명세서  | 사이트별 재고 명세서                     |

### <a name="manufacturing-accounting-status"></a>제조회계현황

| 보고서 페이지                | 가상화                       |
|----------------------------|-------------------------------------|
| WIP 개요 YTD           | 기초 잔액                   |
|                            | 순 변화                          |
|                            | 순 변화율 %                        |
|                            | 종료 잔액                      |
|                            | WIP 회전율                  |
|                            | WIP 현재고 일수                    |
|                            | 기간의 활성 원가 개체        |
|                            | 리소스 그룹별 순 변경        |
|                            | 사이트별 잔액                     |
|                            | 카테고리별 명세서               |
|                            | 분기별 순 변화               |
| WIP 명세서              | 기초 잔액                   |
|                            | 종료 잔액                      |
|                            | 범주별 WIP 명세서           |
| 사이트별 WIP 명세서      | 기초 잔액                   |
|                            | 종료 잔액                      |
|                            | 카테고리 및 사이트별 WIP 명세서  |
| 계층별 WIP 문 | 기초 잔액                   |
|                            | 종료 잔액                      |
|                            | 범주 계층별 WIP 명세서 |

### <a name="inventory-accounting-analysis"></a>재고 회계 분석

| 보고서 페이지        | 가상화                                                                |
|--------------------|------------------------------------------------------------------------------|
| 인벤토리 세부정보  | 잔액 기준 상위 10개 리소스                                           |
|                    | 순 변경 증가에 따른 상위 10개 리소스                                      |
|                    | 순 변경 감소 기준 상위 10개 리소스                                      |
|                    | 재고 회전율 기준 상위 10개 자원                                 |
|                    | 낮은 재고 회전율 및 임계값 이상의 기말 잔액에 의한 자원 |
|                    | 낮은 정확도로 상위 10개 리소스                                             |
| ABC 분류 | 재고 기말 잔액                                                     |
|                    | 소모된 재료                                                            |
|                    | 판매(원가)                                                                  |
| 재고 동향   | 재고 기말 잔액                                                     |
|                    | 재고 순 변동                                                         |
|                    | 재고회전율                                                     |
|                    | 인벤토리 정확도                                                           |

### <a name="manufacturing-accounting-analysis"></a>제조회계분석

| 보고서 페이지 | 가상화      |
|-------------|--------------------|
| WIP 동향  | WIP 기말 잔액 |
|             | WIP 순 변경     |
|             | WIP 회전율 |

### <a name="std-cost-variance-analysis"></a>표준 비용 차이 분석

| 보고서 페이지                             | 가상화                                        |
|-----------------------------------------|------------------------------------------------------|
| 구매 가격 차이(표준 비용) YTD | 조달 잔액                                     |
|                                         | 구매 가격 차이                              |
|                                         | 구매 가격 편차 비율                        |
|                                         | 항목 그룹별 차이                               |
|                                         | 사이트별 차이                                     |
|                                         | 분기별 구매가                            |
|                                         | 분기별 및 항목군별 구매금액             |
|                                         | 불리한 구매가 비율로 상위 10 자원 |
|                                         | 유리한 구매 가격 비율로 상위 10 자원   |
| 생산 차이(표준 비용) YTD     | 제조원가                                    |
|                                         | 생산 편차                                  |
|                                         | 생산 편차 비율                            |
|                                         | 항목 그룹별 차이                               |
|                                         | 사이트별 차이                                     |
|                                         | 분기별 생산량 편차                       |
|                                         | 분기별 및 차이 유형별 생산 차이     |
|                                         | 불리한 생산 편차에 따른 상위 10개 자원  |
|                                         | 유리한 생산 편차에 따른 상위 10개 자원    |

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해

애플리케이션의 데이터는 **비용 관리** Power BI 콘텐츠의 보고서 페이지를 채우는 데 사용됩니다. 이 데이터는 분석에 최적화된 Microsoft SQL Server 데이터베이스인 엔터티 저장소에 준비된 집계 측정값으로 표시됩니다. 자세한 내용은 [엔터티 스토어와 Power BI 통합](power-bi-integration-entity-store.md)을 참조하세요.

다음 개체의 주요 집계 측정값이 Power BI 콘텐츠의 기초로 사용됩니다.

| 개체                          | 주요 집계 측정 | 재무 및 운영을 위한 데이터 소스 | 필드               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | 금액                     | CostObjectStatementCache               | 금액              |
| CostObjectStatementCacheMonthly | 수량                   | CostObjectStatementCache               | 수량                 |
| 비용재고회계KPI목표  | 연간 재고 회전율        | 비용재고회계KPI목표         | 연간 재고 회전율 |
| 비용재고회계KPI목표  | 인벤토리 정확도          | 비용재고회계KPI목표         | 인벤토리 정확도   |

다음 표는 Power BI 콘텐츠에서 계산된 주요 측정값을 보여줍니다.

| 측정                            | 계산 |
|------------------------------------|-------------|
| 기초 잔액                  | 기초 잔액 = \[종료 잔액\]-\[순 변경\] |
| 기초 잔액 수량             | 기초 잔액 수량 = \[기말 잔액 수량\]-\[순 변경 수량\] |
| 종료 잔액                     | 기말 잔액 = (CALCULATE(SUM(\[금액\]), FILTER(ALL(FiscalCalendar), FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| 기말 잔액 수량                | 기말 잔액 수량 = (CALCULATE(SUM(\[금액\]), FILTER(ALL(FiscalCalendar), FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| 순 변화                         | 순 변화 = SUM(\[AMOUNT\]) |
| 순 변경 수량                    | 순 변경 수량 = SUM(\[QTY\]) |
| 수량별 재고회전율 | 수량별 재고회전율 = if(OR(\[재고평균잔고\] \<= 0, \[Inventory sold or consumed issues\] \>= 0), 0, ABS(\[매출 또는 소비된 재고\])/\[재고평균잔고\]) |
| 재고 평균 잔액          | 재고 평균 잔액 = ((\[기말 잔액\] + \[초기 잔액\]) / 2) |
| 현재고 일수             | 보유 재고 일수 = 365 / CostObjectStatementEntries\[금액별 재고 회전율\] |
| 인벤토리 정확도                 | 수량별 재고 정확도 = IF(\[기말 잔액\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0, \[기말 잔액\] \< 0), 0, 1), MAX(0, (\[기말 잔액\] - ABS(\[재고 실사 금액\]))/\[기말 잔액\])) |

다음 주요 차원은 필터로 사용되어 집계 측정값을 조각화하므로 더 세분화되고 심층적인 분석 통찰력을 얻을 수 있습니다.


| 엔터티                                                  | 속성의 예                          |
|---------------------------------------------------------|-------------------------------------------------|
| 제품                                                | 제품번호, 제품명, 단위, 항목군 |
| 범주 계층 구조(비용 관리 역할에 할당됨) | 카테고리 계층, 카테고리 레벨              |
| 법인                                          | 법인 이름                              |
| 회계 달력                                        | 회계 달력, 연도, 분기, 기간, 월   |
| 사이트                                                    | 아이디, 이름, 주소, 주, 국가               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
