---
title: 매출 및 수익성 실적 Power BI 콘텐츠
description: 이 항목에서는 Sales 및 수익성 실적 Power BI 콘텐츠에 포함된 항목에 대해 설명합니다.
author: ShylaThompson
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesProfitabilityPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9ec9ef5f4abf898100c670b1ca1cc845d6ebeeea36f21cdda3a9b7d3f1027d4e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460727"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>매출 및 수익성 실적 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 **Sales 및 수익성 실적** Microsoft Power BI 콘텐츠에 포함된 항목에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용되는 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**매출 및 수익성 실적** Power BI 콘텐츠는 판매 관리자가 수익, 총 이익 및 이익 마진의 주요 판매 메트릭을 모니터링할 수 있도록 만들어졌습니다. 판매 거래 데이터를 사용하고 회사 전체의 판매 수치에 대한 집계 보기와 고객 및 제품에 대한 판매 실적 분석을 모두 제공합니다.

보고서는 시간 경과에 따른 수익 및 이익 성장의 변화를 강조합니다. 따라서 보고서를 사용하여 개별 고객 및 제품에 대한 긍정적 및 부정적 추세에 대해 관리자에게 경고할 수 있습니다. 또한 차트는 서로 다른 제품 범주 및 고객 그룹의 수익과 수익성을 서로 비교합니다. 따라서 카테고리 및 지역 관리자는 후발주자와 리더를 식별할 수 있습니다. 마지막으로 포괄적인 보고서는 개별 고객의 수익 대 이윤을 표시합니다. 따라서 계정 관리자는 판매 및 마케팅 활동을 각 고객의 프로필에 맞게 조정하는 데 사용할 수 있는 데이터 기반 기반을 가지고 있습니다.

**매출 및 수익성 실적** 콘텐츠 영업 관리자는 다음과 같은 방법으로 영업 실적을 분석할 수 있습니다.

- 수익, 연간 누계(고객 그룹 및 개별 고객, 판매 범주, 개별 제품 및 지역별)
- 전년 대비 매출 변화(고객 지역 및 판매 카테고리별)

수익성은 다음과 같은 방식으로 분석할 수 있습니다.

- 총 이익 및 이익 마진(고객 그룹 및 제품 판매 범주별)
- 전년 대비 총 이익 변화
- 고객 수익성(매출 대 총 마진 기준)

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**매출 및 수익성 실적** Power BI 내용은 **매출 및 수익성 실적** 페이지(**영업 및 마케팅** \> **문의 및 신고** \> **영업 실적 분석** \> **매출 및 수익성 실적**)에 표시됩니다.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 메트릭
**매출 및 수익성 실적** Power BI 콘텐츠에는 측정항목 집합으로 구성된 보고서가 포함됩니다. 이러한 메트릭은 차트, 타일 및 테이블로 시각화됩니다. 다음 표는 콘텐츠의 시각화에 대한 개요를 제공합니다.

| 보고서 페이지            | 차트                                     | 타일                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| 고객별 수익    | 매출 기준 상위 10명의 고객                | 총 수익                                           |
|                        | 고객 그룹별 총 수익            | 전년 동기 매출 성장                                      |
|                        | 고객 그룹별 평균 고객 수익 | 매상 총이익                                            |
|                        | 고객 그룹별 매출 및 총이익   |                                                         |
| 제품별 수익     | 판매 카테고리별 매출 및 총 이익   | 총 제품 \#                                    |
|                        | 수익 기준 상위 10개 제품                 | 활성 제품 총 수 및 총 비율 |
|                        | 판매 카테고리별 총 수익            | 수익의 80%를 차지하는 제품 수           |
| 기간별 수익\*    | 월별 수익                           | 전년 동기 매출 성장                                      |
|                        | 후행 수익 차이, YOY             | 전년 동기 매출 성장 %                                    |
|                        | 고객 지역별 총 판매 차이    |                                                         |
| 위치별 수익    | 도시별 판매 수익                      |                                                         |
|                        | 전년 동기 매출 성장 %                       |                                                         |
|                        | 지역별 판매 수익                    |                                                         |
| 고객 수익성 | 고객별 매상 총이익과 수익   | 총 이익, 총 마진, YOY 매출 성장          |
| 수익성 분석 | 월별 매출 및 총 이익          |                                                         |
|                        | 매상 총이익별 고객 상위 15           |                                                         |
|                        | 월별 총 이익, YOY                 |                                                         |

\* 올해와 작년의 매출과 판매 카테고리별 성장.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
다음 데이터는 **영업 및 수익성 실적** Power BI 콘텐츠에서 보고서 페이지를 작성하는 데 사용됩니다. 이 데이터는 엔터티 저장소에 준비된 집계 측정값으로 표시됩니다. 엔터티 스토어는 분석에 최적화된 Microsoft SQL Server 데이터베이스입니다. 자세한 내용은 [엔터티 스토어와 Power BI 통합](power-bi-integration-entity-store.md)을 참조하세요.

이 콘텐츠의 집계 측정은 Microsoft Dynamics AX 2012 및 Microsoft Dynamics AX 2012 R3의 영업 큐브에서 사용할 수 있었던 집계 측정의 하위 집합입니다. 엔터티 저장소에서 큐브의 집계 측정을 준비하려면 배포 가능하게 만들어야 합니다. 자세한 내용은 [Dynamics에서 엔터티 스토어와 Power BI 통합](/archive/blogs/dynamicsaxbi/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update) 블로그 게시물에서 엔터티 저장소의 집계 측정 스테이징 절차를 참조하세요.

인보이스 라인 엔터티에 대한 다음 주요 집계 지표는 콘텐츠의 기준으로 사용됩니다.

| 엔터티        | 주요 집계 측정                   | Dynamics 365용 데이터 원본 | 필드                                        | 설명                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| 송장 라인 | 수익                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | 회계 통화 금액.            |
|               | 판매 제품 원가                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | 비용 금액과 조정의 합계입니다.    |
|               | 커미션 라인 금액 – 회계 통화 | CustInvoiceTrans             | SUM(CommissAmountMST)                        | 커미션 금액(회계 통화). |

다음 표는 인보이스 라인 엔터티의 주요 집계 측정값을 사용하여 콘텐츠 데이터세트에서 여러 계산된 측정값을 만드는 방법을 보여줍니다.

| 측정           | 계산                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| 총 이익      | SUM(수익 – COGS – 수수료 – 판매세(고객 송장 라인 금액에 포함))          |
| 매상 총이익      | SUM(총 수익 / (수익 – 판매세(고객 송장 라인 금액에 포함)))             |
| 작년 매출 | 작년 수익 = CALCULATE(SUM('송장 라인'\[수익\]), SAMEPERIODLASTYEAR(날짜\[날짜\]) |

다음 표는 Sales Cube의 집계 측정값을 조각화하는 필터로 사용되는 주요 차원을 보여줍니다. 따라서 더 세분화되고 심층적인 분석 통찰력을 얻을 수 있습니다.

| 엔터티           | 특성의 예                               |
|------------------|------------------------------------------------------|
| 고객        | 고객 그룹, 고객 지역, 주소, 업종 |
| 제품         | 제품 번호, 제품 이름, 항목 그룹 이름       |
| 판매 범주 | 판매 범주 이름                                 |
| 법인   | 법인명                                   |
| 날짜            | 날짜                                                |

기본적으로 콘텐츠에는 현재 연도의 데이터가 표시됩니다. 그러나 보고서 필터 섹션에서 날짜 필터를 변경할 수 있습니다. 회사 필터를 변경할 수도 있습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]