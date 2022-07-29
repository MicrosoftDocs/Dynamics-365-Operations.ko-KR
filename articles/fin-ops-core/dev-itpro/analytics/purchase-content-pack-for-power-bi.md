---
title: 구매 지출 분석 Power BI 콘텐츠
description: 이 항목에서는 구매 지출 분석 Power BI 콘텐츠에 포함된 항목에 대해 설명합니다.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a40d4f39a7119def9ed0393d4ced2be1f7e801a5c1c3f984b002e5224299915a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460824"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>구매 지출 분석 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 **구매 지출 분석** Microsoft Power BI 콘텐츠에 포함된 항목에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용되는 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**구매 지출 분석** Power BI 콘텐츠는 구매 관리자와 예산을 담당하는 관리자가 구매 지출을 추적할 수 있도록 설계되었습니다. 관리자는 다음과 같은 방법으로 구매 지출을 분석할 수 있습니다.

- 연간 누계 구매(공급업체 그룹 및 개별 공급업체, 조달 범주 및 개별 제품, 공급업체 위치별)
- 전년 대비 구매 변화(벤더 그룹 및 구매 카테고리별)

콘텐츠는 구매 거래 데이터를 사용하고 전사적 구매 수치의 집계 보기와 공급업체 및 제품별 구매 지출 기록을 모두 제공합니다. 보고서는 시간 경과에 따른 구매 지출의 변화를 강조 표시합니다. 따라서 보고서를 사용하여 개별 공급업체 및 제품에 대한 긍정적 및 부정적 지출 추세에 대해 관리자에게 경고할 수 있습니다. 또한 차트는 다양한 조달 범주 및 공급업체 그룹에 대한 구매 지출을 보여줍니다. 따라서 범주 및 지역 관리자는 차트를 사용하여 지출 행동의 변화를 식별할 수 있습니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**구매 지출 분석** Power BI 콘텐츠는 **구매 및 지출 분석** 페이지(**조달 및 소싱** \> **문의 및 신고** \> **구매 실적 분석** \> **구매 및 지출 분석**)에 표시됩니다.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 메트릭
**구매 지출 분석** Power BI 콘텐츠에는 측정항목 집합으로 구성된 보고서가 포함됩니다. 이러한 메트릭은 차트, 타일 및 테이블로 시각화됩니다. 

다음 섹션에서는 시각화에 대한 개요를 제공합니다.

### <a name="purchase-by-vendor-report-page"></a>공급업체별 구매 보고서 페이지
**차트**
- 구매 기준 상위 10개 공급업체(누적 막대 차트)
- 공급업체 그룹/국가/이름별 총 구매액(파이 차트)
- 공급업체 그룹/국가/이름별 구매액(열 차트)
- 공급업체 그룹/국가/이름별 평균 구매액(열 차트)

**타일**
- 총 구매
- YOY 구매 성장
- 공급업체 총 수
- 활성 공급업체의 총 수

**예**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>제품별 구매 보고서 페이지

**차트**
- 구매 카테고리/제품명(칼럼 차트)별 구매
- 구매 카테고리/제품명(파이 차트)별 총 구매
- 구매 기준 상위 10개 제품(누적 막대 차트)

**타일**
- 총 제품 수</li>
- 총 제품 수 중 총 활성 제품 비율
- 구매의 80%를 차지하는 제품 수

**예**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>기간별 구매 보고서 페이지
이 페이지는 올해와 작년의 구매와 구매 카테고리별 성장을 보여줍니다.

**차트** 
- 월/일별 구매(칼럼 차트)
- 누적 구매 YOY 변동(폭포 차트)
- 총 구매 YOY 성장(칼럼 차트)
- 조달 명세서(매트릭스)

**타일**
- YOY 구매 성장
- YOY 구매 성장 %

**예**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>공급업체 위치별 구매 보고서 페이지

**차트**
- 도시별 구매
- 연도별 구매 성장 %
- 국가별 구매

**예**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>시간별 구매 지출 분석 보고서 페이지

**차트** 
- 현재 연도별 월/일 구매(선 차트)
- 현재 및 작년 구매(선 및 세로 막대형 차트)

**예**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>공급업체별 구매 지출 분석 보고서 페이지

**차트** 
- 상위 10개 공급업체 구매 구매 비율(퍼널)
- 전년 대비 지출이 증가한 상위 10개 공급업체
- 전년 대비 지출이 감소한 상위 10개 공급업체

**예** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>데이터 모델 및 엔터티
다음 데이터는 **구매 비용 분석** Power BI 콘텐츠에서 보고서 페이지를 작성하는 데 사용됩니다. 이 데이터는 엔터티 저장소에 준비된 집계 측정값으로 표시됩니다. 엔터티 스토어는 분석에 최적화된 Microsoft SQL Server 데이터베이스입니다. 자세한 내용은 [엔터티 스토어와 Power BI 통합](power-bi-integration-entity-store.md)을 참조하세요.

이 콘텐츠의 집계 측정은 Microsoft Dynamics AX 2012 및 Microsoft Dynamics AX 2012 R3의 구매 큐브에서 사용할 수 있었던 집계 측정의 하위 집합입니다. 엔터티 저장소에서 큐브의 집계 측정을 준비하려면 배포 가능하게 만들어야 합니다. 자세한 내용은 [엔터티 스토어와 Power BI 통합](power-bi-integration-entity-store.md)에서 엔터티 저장소의 집계 측정 스테이징 절차를 참조하세요. 다음 주요 집계 측정값은 송장 라인 엔터티에서 직접 사용할 수 있으며 콘텐츠의 기초로 사용됩니다.

| 엔터티        | 주요 집계 측정 | 데이터 원본                                 | 필드              | 설명                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| 송장 라인 | 구매                   | VendInvoiceTrans                            | SUM(LineAmountMST) | 회계 통화 금액. |

다음 표는 송장 라인 엔터티에서 계산된 콘텐츠의 주요 측정값을 보여줍니다.

| 측정               | 계산                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| 올해 구매 | 현재 연도 구매 = SUM('송장 라인'\[구입\])                                            |
| 작년에 구매    | 작년 구매 = CALCULATE(SUM('송장 라인'\[구입\]), SAMEPERIODLASTYEAR(날짜\[날짜\])) |
| YOY 구매 성장   | YOY 구매 증가율 = \[올해 구매\] – \[작년에 구매\]                            |

콘텐츠의 다음 키 차원은 집계 측정값을 조각화하는 필터로 사용되는 주요 차원을 보여줍니다. 따라서 더 세분화되고 심층적인 분석 통찰력을 얻을 수 있습니다.

| 엔터티                 | 특성의 예                                |
|------------------------|-------------------------------------------------------|
| 공급업체                | 공급업체 그룹, 공급업체 국가 또는 지역, 공급업체 이름 |
| 제품               | 제품 번호, 제품 이름, 항목 그룹 이름        |
| 조달 범주 | 조달 범주, 조달 범주 이름      |
| 법인         | 법인명                                     |
| 날짜                  | 날짜, 연도 오프셋                                    |

기본적으로 콘텐츠에는 현재 연도의 데이터가 표시됩니다. 그러나 보고서 필터 섹션에서 날짜 필터를 변경할 수 있습니다. 회사 필터를 변경할 수도 있습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]