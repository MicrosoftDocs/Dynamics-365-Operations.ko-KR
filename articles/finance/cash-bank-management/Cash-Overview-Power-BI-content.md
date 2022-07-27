---
title: 현금 개요 Power BI 콘텐츠
description: 이 토픽에서는 현금 개요 Power BI 콘텐츠에 대해 설명합니다. 콘텐츠에 포함된 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.
author: saraschi2
ms.date: 07/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3f7e0c792df8519f3bcb2ade2e29cc4c5c8e4730
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451471"
---
# <a name="cash-overview-power-bi-content"></a>현금 개요 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 토픽에서는 **현금 개요** Microsoft Power BI 콘텐츠에 대해 설명합니다. 콘텐츠에 포함된 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**현금 개요** Power BI 콘텐츠는 조직에서 현금을 담당하는 개인을 위해 만들어졌습니다. **현금 개요** Power BI 콘텐츠는 현금 흐름에 대한 가시성을 제공합니다. 또한 더 나은 결정을 내리는 데 도움이 되는 예측을 제공하여 현금 흐름의 건전성을 개선할 수 있습니다. 법인, 통화 및 은행 계좌별로 현금을 분석하여 잉여금과 부족금을 더 잘 이해할 수 있습니다.

## <a name="setup-needed-to-view-power-bi-content"></a>Power BI 콘텐츠를 보려면 설정이 필요합니다

**현금 개요** 및 **은행 관리** Power BI 시각적 개체에 데이터를 표시하려면 다음 설정을 완료해야 합니다.

1. **시스템 관리 > 설정 > 시스템 매개 변수** 로 이동하여 **시스템 통화** 및 **시스템 환율** 을 설정합니다.
2. **총계정원장 > 일정 > 회계 일정** 으로 이동하여 활성 기간에 지정된 회계 일정 날짜를 검증합니다.
3. **총계정원장 > 설정 > 원장** 으로 이동하여 **회계 통화** 및 **환율 유형** 을 설정합니다.
4. 거래 통화와 회계 통화, 회계 통화와 시스템 통화, 회계 통화와 은행 통화 간의 환율을 정의합니다. 이렇게 하려면 **총계정원장 > 통화 > 통화 환율** 로 이동합니다.
5. 현금 흐름 예측을 구성하고 실행합니다. 현금 흐름 예측을 설정하는 방법에 대한 자세한 내용은 [현금 흐름 예측](./cash-flow-forecasting.md)을 참조하십시오. 
6. **시스템 관리 > 설정 > 엔터티 스토어** 로 이동하여 **LedgerCovLiquidityMeasurement** 집계 측정값을 새로 고칩니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스

**현금 개요** Power BI 콘텐츠의 보고서는 **현금 개요** 및 **은행 관리** 작업 영역에 표시됩니다.

데이터가 포함된 현금 흐름 예측 보고서를 보려면 먼저 현금 및 은행 관리 영역에서 **현금 흐름 예측 계산** 기능을 사용하여 예측 계산 프로세스를 실행해야 합니다. 예측에 포함된 각 회사에 대해 완료해야 합니다.  그런 다음 **엔터티 스토어** 페이지에서 LedgerCovLiquidityMeasurement 집계 측정값을 새로 고쳐야 합니다.  

데모용으로 데모 데이터 모듈의 **데이터 생성** 페이지를 사용하여 현금 흐름 예측 데모 데이터를 추가할 수 있습니다.  이 스크립트는 현금 흐름 예측 테이블에 데이터를 삽입하여 보고서에 필요한 정보를 빠르게 채웁니다.  이 모듈은 환경에 배포된 데모 데이터 제품군 모델이 있는 경우에만 사용할 수 있습니다. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서

다음 표는 **현금 개요** Power BI 콘텐츠의 각 보고서 페이지에 있는 메트릭에 대한 세부 정보를 제공합니다.

| 보고서                                | 콘텐츠 |
|---------------------------------------|----------|
| 현금 개요 – 모든 회사         | <ul><li>시스템 통화의 유입 및 유출</li><li>예측 통화 잔액</li><li>시스템 통화의 총 은행 잔고</li><li>법인별 잔액</li><li>은행 계좌 통화로 표시된 오늘의 실제 잔액 대 예상 잔액</li></ul> |
| 현금 개요 – 현재 회사       | <ul><li>회계 통화의 유입 및 유출</li><li>예측 통화 잔액</li><li>회계 통화의 총 은행 잔고</li><li>은행 계좌 통화로 표시된 오늘의 실제 잔액 대 예상 잔액</li></ul> |
| 현금 흐름 예측 – 모든 회사    | <ul><li>시스템 통화의 유입 및 유출</li><li>일일 예측 요약</li><li>예측 세부정보</li></ul> |
| 현금 흐름 예측 – 통화 회사 | <ul><li>회계 통화의 유입 및 유출</li><li>일일 예측 요약</li><li>예측 세부정보</li></ul> |
| 통화 예측                     | <ul><li>예측 통화 잔액</li><li>일일 통화 요약</li><li>예측 세부정보</li></ul> |
| 은행 잔고                         | <ul><li>시스템 통화의 총 은행 잔고</li><li>법인별 잔액</li><li>은행 계좌 통화로 표시된 오늘의 실제 잔액 대 예상 잔액</li><li>은행 계좌별 잔고</li><li>통화별 잔액</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해

다음 표는 **현금 개요** Power BI 콘텐츠의 기반이 되는 엔터티를 보여줍니다.

| 엔터티                                                                          | 콘텐츠 |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | 보고서를 필터링할 회사 |
| LedgerCovLiquidityMeasurement\_Date                                             | 보고서를 필터링할 날짜 |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | 실제 은행 잔고와 마지막으로 예측된 은행 잔고 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | 예측 거래 내역 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | 각 기업의 회계 통화를 이용하여 현금의 유입, 유출 및 잔액을 요약 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | 모든 회사의 시스템 통화를 사용하여 현금 유입, 유출 및 잔액을 요약 |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | 거래 통화를 사용하여 순거래 금액 및 통화 잔액을 요약 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]