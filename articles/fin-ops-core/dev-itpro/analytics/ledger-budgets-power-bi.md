---
title: 실제 대 예산 Power BI 콘텐츠
description: 이 항목에서는 실제 대 예산 Power BI 콘텐츠에 대해 설명합니다. 보고서에 액세스하는 방법을 설명하고 데이터 모델에 대한 정보를 제공합니다.
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 7a5628dc67c721bf616803d6a31047cee09d8a434d43c0175dd8639815b7c9a6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460657"
---
# <a name="actual-vs-budget-power-bi-content"></a>실제 대 예산 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 **실제 대 예산** Microsoft Power BI 콘텐츠에 대해 설명합니다. Power BI 보고서에 액세스하는 방법을 설명하고 콘텐츠를 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="overview"></a>개요

**실제 대 예산** Power BI 콘텐츠는 조직에서 실제 대 예산 성과를 모니터링하는 책임이 있는 개인을 위해 만들어졌습니다. **실제 대 예산** Power BI 콘텐츠는 예산 변동에 대한 가시성을 제공합니다. 현재 연도의 예산을 계정 범주, 예산 코드, 주 계정, 주 계정 설명 또는 회계 기간별로 분석하여 변동의 원인을 더 잘 이해할 수 있습니다.

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
**실제 대 예산** Power BI 콘텐츠에 보고서는 **원장 예산 및 예측** 및 **CFO** 작업 공간에 표시됩니다.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 보고서
다음 표는 **실제 대 예산** Power BI 콘텐츠의 각 보고서 페이지에 있는 메트릭에 대한 세부 정보를 제공합니다.

| 보고서                      | 메트릭                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| 지출 - 실제 대 예산 | <ul><li>올해 총 지출</li><li>올해 예산 총 지출</li></ul>  |
| 수익 - 실제 대 예산  | <ul><li>올해 총 수익</li><li>올해 예산 총 수익</li><ul>     |
| 경비                     | <ul><li>올해 총 지출</li><li>예산에 따른 지출 목표</li><ul> |
| 수익                     | <ul><li>올해 총 수익</li><li>예산에 따른 수익 목표</li><ul>   |
| 순이익                  | <ul><li>올해 순이익</li><li>예산에 따른 순이익 목표</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해

| 엔터티                    | 콘텐츠                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| 총계정원장 활동 | 총계정원장의 거래 금액                                       |
| 예산 활동         | 예산대장 거래금액                                      |
| 주 계정             | 보고서를 필터링할 기본 계정                                               |
| 회계 캘린더          | 보고서를 필터링할 회계 달력                                            |
| 원장                   | 보고서를 현재 원장으로 필터링하는 데 사용할 수 있는 원장              |
| 예산 코드              | 보고서를 필터링할 예산 코드                                                |
| 법인            | 보고서를 현재 법인으로 필터링하는 데 사용할 수 있는 법인 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]