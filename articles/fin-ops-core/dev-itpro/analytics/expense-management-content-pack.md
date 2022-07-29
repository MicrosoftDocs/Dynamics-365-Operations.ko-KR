---
title: 비용 관리 Power BI 콘텐츠
description: 이 항목에서는 비용 관리 Power BI 콘텐츠 팩에 포함된 항목에 대해 설명합니다.
author: panolte
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 178a65c44abd0c9c068d4da1f2684a60062da595247560de4cb81d97ab7b6521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460668"
---
# <a name="expense-management-power-bi-content"></a>비용 관리 Power BI 콘텐츠

[!include [banner](../includes/banner.md)]

이 항목에서는 비용 관리 Power BI 콘텐츠에 포함된 항목에 대해 설명합니다. 

## <a name="overview"></a>개요
두 개의 Power BI 콘텐츠 팩은 버전 8.1 이상에서 비용 관리와 함께 사용할 수 있습니다. 
- 경비 보고서를 제출하는 직원을 위해 설계된 개인 대시보드가 있습니다. 

  대시보드는 개인에게 미제출 및 제출 금액, 지출 거래 기록에 대한 기록 및 통찰력에 대한 주요 정보를 제공하도록 맞춤화되었습니다. 개인 대시보드는 사용자에게 가장 중요한 정보가 포함된 단일 페이지입니다.

- 지급 계정 사무원 및 관리자를 위해 설계된 관리 대시보드가 있습니다. 대시보드는 전체 직원 비용을 추적하고 보고하는 데 적합합니다. 미제출 비용, 마일리지 및 평균 비용 보고서 금액과 같은 주요 비용 메트릭을 제공합니다. 거래 데이터를 사용하고 모든 회사의 비용 관리에 대한 집계 보기를 제공합니다. 또한 재무 차원 데이터를 추가할 수 있는 옵션과 함께 직원별 분석도 제공합니다. 관리 비용 분석 콘텐츠에는 다음이 포함됩니다. 
  - 비용 금액에 대한 주요 메트릭과 초안, 진행 중 및 완료된 비용 보고서에 대한 통찰력이 있는 개요 페이지입니다. 
  - 시간, 비용 유형 및 통계 그룹별로 직원에 대한 개별 세부 정보를 검토하는 직원 통계 페이지입니다. 
  - 시간 경과에 따라 여러 직원을 비교하는 직원 비교 페이지입니다. 

모든 금액은 회사 통화로 표시됩니다. 모든 회사에 대한 데이터가 표시되지만 필요한 경우 회사 필터를 추가할 수 있습니다. 

## <a name="accessing-the-power-bi-content"></a>Power BI 콘텐츠에 액세스
Microsoft Dynamics Lifecycle Services(LCS)의 공유 자산 라이브러리에서 Expense Admin Dashboard.pbix 및 Expense Personal Dashboard.pbix Power BI 콘텐츠를 찾을 수 있습니다. 콘텐츠를 다운로드하고 조직에서 구현하는 방법에 대한 자세한 내용은 [Microsoft 및 파트너의 LCS Power BI 콘텐츠](/archive/blogs/dynamicsaxbi/power-bi-content-from-microsoft-and-your-partners)를 참조하세요.
콘텐츠는 비용 관리 작업 영역에서 포함된 Power Bi 콘텐츠로 사용할 수 있습니다. 모든 경비 소유자는 자신을 위한 개인 경비에 액세스할 수 있으며, 지급 계정 사무원과 관리자만 관리자 콘텐츠에 액세스하여 모든 사용자의 경비 데이터를 볼 수 있습니다.

## <a name="refreshing-the-power-bi-content"></a>Power BI 콘텐츠 새로 고침
비용 관리 Power BI 콘텐츠를 사용하려면 TrvBiExpenseMeasurement 측정값과 BudgetActivityMeasure가 엔터티 저장소에서 새로 고쳐져야 합니다. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Power BI 콘텐츠에 포함된 메트릭
콘텐츠에는 일련의 보고서 페이지가 포함됩니다. 각 페이지는 차트, 타일 및 테이블로 시각화되는 메트릭 세트로 구성됩니다. 다음 표는 Power BI 콘텐츠의 시각화에 대한 개요를 제공합니다.

**개인 비용 분석**

| 보고서 페이지 | 시각화                             |
|-------------|-------------------------------------------|
| 내 비용 | 마일리지 금액                         |
|             | 진행 중인 경비 보고서                |
|             | 번호 미제출 비용               |
|             | 지불해야 하는 개인 비용              |
|             | 미제출 금액                        |
|             | 제출 금액                          |
|             | 상환 대기 금액             |
|             | 금액 및 상태가 포함된 경비 보고서   |
|             | 제출했지만 승인되지 않은 경비 보고서  |
|             | 비용 유형별 비용                     |
|             | 가맹점 비용                      |
|             | 처리 비용별 비용            |
|             | 프로젝트별 비용                       |
|             | 시간 경과에 따른 총 거래 금액        |

**관리 비용 분석**

| 보고서 페이지         | 시각화                           |           
|---------------------|-----------------------------------------|
| 비용 개요    | 초안 비용 금액                   |
|                     | 초안 비용 라인 수           |
|                     | 비용 라인 초안                     |
|                     | 경비 보고서 정책 위반        |
|                     | 미결제 금액                      |
|                     | 제출했지만 승인되지 않은 경비       |
|                     | 승인된 비용                       |
|                     | 총 경비 금액                    |
|                     | 경비 보고서 요약                |
|                     | 비용 유형별 비용                   |
|                     | 가맹점 비용                    |
|                     | 직원 비용                   |
|                     | 비용과 프로젝트                     |
| 직원 비교 | 경비 금액                         |
|                     | 직원별 시간 경과에 따른 비용 금액   |
| 직원 통계 | 비용 유형별 비용 보고서            |
|                     | 개인 경비                       |
|                     | 통계 그룹별 지출 보고서     |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]