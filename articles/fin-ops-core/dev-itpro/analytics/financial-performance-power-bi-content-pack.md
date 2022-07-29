---
title: 재무 성과 PowerBI.com 솔루션
description: 이 항목에서는 재무 성과 PowerBI.com 솔루션에 대해 설명합니다.
author: kweekley
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ca8338473b2efd91b6570e140ee1def3fa93df14dcf57273f601efb7f548d08
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460670"
---
# <a name="financial-performance-powerbicom-solution"></a>재무 성과 PowerBI.com 솔루션

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 이 PowerBI.com 솔루션은 [재무 및 운영에 대해 제거되거나 더 이상 사용되지 않는 기능](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource)에 설명된 대로 더 이상 사용되지 않습니다.

이 항목에서는 **재무 성과** PowerBI.com 솔루션에 대해 설명합니다. 포함된 대시보드 및 보고서를 설명하고 솔루션을 구축하는 데 사용된 데이터 모델 및 엔터티에 대한 정보를 제공합니다.

## <a name="main-account-setup"></a>즈 계정 설정
조직에서는 부채와 수익 금액이 보고서에 양수로 표시되기를 원하기 때문에 기본 계정 설정이 중요합니다. 이러한 기본 계정이 양수 금액으로 표시되려면 기본 계정 유형을 **채무** 또는 **수익** 으로 설정해야 합니다. 이러한 계정 유형을 사용하는 경우 Power BI를 통한 보고서가 부호를 반대로 하고 금액을 양수로 표시합니다.

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>PowerBI.com 솔루션에 포함된 대시보드 및 보고서
대시보드에는 기본 보고서를 기반으로 하는 요약된 데이터 타일이 포함되어 있습니다. 각 타일에는 조직의 모든 회사에 대한 현재 연도에 대한 요약 정보가 포함되어 있습니다. 다음은 타일 중 일부입니다.

- 현금
- 올해 총 수익
- 올해 총 지출
- 올해 순이익
- 빠른 비율
- 올해 계정 범주별 총 지출
- 현재 비율
- 총 자산 대비 부채
- 실제 수익과 예상 수익
- 올해 청구 수익
- 올해 영업 비용 비율
- 올해 이익률
- 실제 대 예산 비용 – 모든 회사

각 타일은 지원 보고서로 뒷받침됩니다. 이러한 보고서에는 추가 정보를 제공하는 차트와 테이블이 모두 포함되어 있습니다. 다음 테이블에서는 보고서를 설명합니다.

| 보고서                      | 보고서에 포함된 정보 |
|-----------------------------|--------------------------------------|
| 현금 분석               | 법인별 현금, 분기별 현금, 총현금, 계좌별 현금<blockquote>[!NOTE] 분기별 현금 정보에는 1분기 총계의 기초 잔액이 포함되지 않습니다. 각 분기에 게시된 신규 거래의 총계를 보여줍니다.</blockquote> |
| 유동비율 분석      | 법인별 유동비율, 분기별 유동비율, 유동자산 및 유동부채 잔액 |
| 빠른 비율 분석        | 법인별 빠른 비율, 분기별 빠른 비율, 현금, 수취 계정 및 유동부채 잔액 |
| 판매 제품 비용 분석 | 법인별 매출원가(COGS), 올해 및 작년 분기별 매출원가, 법인별 매출원가, 총 매출원가 및 매출비중 원가율 |
| 운전 자본 분석    | 법인별 운전자본, 분기별 운전자본, 유동자산, 유동부채, 총 운전자본 |
| 자산 및 부채 분석     | 법인별 총자산 및 부채수익률, 총자산 대비 부채 및 분기별 총자산수익률, 자산, 부채 |
| 이익률 분석      | 법인별 실제 및 예산 이익률, 분기별 이익 표시, 이익률 비율 및 이익률 |
| 순이익 분석         | 법인별 실·예산 순이익, 올해·전년 순이익, 순이익 대비 지출 비율 |
| 수익 분석           | 법인별 이자 및 세금 전 실제 및 예산 수입(EBIT), 올해 및 작년 EBIT, 수익 대비 비용 비율, 수익 대비 실제 및 예산 비용 |
| 수익 분석            | 총수입, 법인별 실제 및 예산총수입, 금년도 및 작년 총수입, 법인별 수입예산차이, 이번 기간 및 지난 기간의 총수입 |
| 비용 분석            | 총비용, 법인별 실제예산총비용, 분기별 실제예산총비용, 계정항목별 총비용, 운영비 비율 |
| 청구 수익 분석     | 매출채권총액, 법인별 매출채권총액, 분기별 매출채권총액, 매출채권 잔액<blockquote>[!NOTE] 이 정보에는 매출 채권 원장 계정에 대한 기초 잔액이 포함되지 않습니다. 수취 계정에 게시된 신규 거래의 총계를 보여줍니다.</blockquote> |

이러한 모든 보고서의 차트와 타일을 필터링하여 대시보드에 고정할 수 있습니다. Power BI에서 필터링 및 고정 방법에 대한 자세한 내용은 [대시보드 생성 및 구성](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards)을 참조하세요.

## <a name="understanding-the-data-model-and-entities"></a>데이터 모델 및 엔터티 이해
다음 엔티티는 **재무 성과** PowerBI.com 솔루션의 기초로 사용되었습니다.

**데이터 항목 집계**

- **GeneralLedgerActivities** – 이 엔터티는 계정 범주별로 총계정원장 잔액을 집계합니다.
- **BudgetActivities** – 이 엔터티는 계정 범주별로 예산 잔액을 집계합니다.

**데이터 엔터티**

- FiscalCalendars
- MainAccounts
- LegalEntities
- 원장
- ChartofAccounts

이러한 엔터티는 데이터 모델에서 계산된 측정값을 만드는 데 사용되었습니다. 계산된 측정값은 콘텐츠에 사용되는 핵심 성과 지표(KPI) 및 보고서를 계산하는 데 사용됩니다. 기본적으로 콘텐츠는 지난 3년 및 향후 1년 동안의 데이터를 가져옵니다. 보고서 및 대시보드에 추가 계산을 포함하려면 [Microsoft Excel 통합 문서](/dynamics/s-e/)를 수정할 수 있습니다. 이 통합 문서는 콘텐츠를 만드는 데 사용된 기본 데이터 모델입니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]