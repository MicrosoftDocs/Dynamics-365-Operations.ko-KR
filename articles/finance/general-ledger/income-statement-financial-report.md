---
title: 손익 계산서 재무 보고서
description: 이 문서에서는 손익 계산서에 대한 기본 보고서에 관해 설명합니다. 또한 이 보고서와 연결된 구성 요소에 관해 설명합니다.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 118c7207f6efc252c0265d6c8f7b949c0e178203bf8523585aa2bfc53a69a6a2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450493"
---
# <a name="income-statement-financial-report"></a>손익 계산서 재무 보고서

[!include [banner](../includes/banner.md)]

이 문서에서는 손익 계산서에 대한 기본 보고서에 관해 설명합니다. 또한 이 보고서와 연결된 구성 요소에 관해 설명합니다. 

## <a name="default-income-statement-report"></a>기본 손익 계산 보고서

| 기본 보고서             | 용도                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| 손익 계산서 – 기본값 | 조직의 현재 기간 및 연도 누계 수익성을 보여줍니다. |

## <a name="building-blocks"></a>구성 요소
손익 계산서 재무 보고서는 다음 구성 요소를 사용합니다.

| 기본 보고서             | 행 정의                     | 열 정의          |
|----------------------------|------------------------------------|----------------------------|
| 손익 계산서 - 기본값 | 요약 손익 계산서 - 기본값 | 정기 및 YTD - 기본값 |

### <a name="row-definition"></a>행 정의

행 정의인 요약 손익 계산서 – 기본값에는 기존 손익 계산서의 각 부분에 대한 섹션이 포함되어 있습니다. 주 계정 범주 차원은 이 행 정의를 작성하는 데 사용됩니다. 따라서 누구나 수정하지 않고도 보고서를 생성할 수 있습니다.

### <a name="column-definition"></a>열 정의

열 정의에는 다양한 수준의 세부 정보 및 재무 데이터를 제공하는 다양한 유형의 열이 포함되어 있습니다.

-   **정기 및 YTD – 기본 열 유형:**
    -   **DESC** – 행 정의의 설명
    -   **FD** – 당기 재무 데이터
    -   **FD** – 연간 누계 재무 데이터



## <a name="additional-resources"></a>추가 리소스

[Financial Reporting 개요](financial-reporting-getting-started.md)

[재무 보고서 보기](view-financial-reports.md)

[Dynamics Financial Reporting 블로그](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]