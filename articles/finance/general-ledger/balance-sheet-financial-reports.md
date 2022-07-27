---
title: 대차 대조표 재무 보고서
description: 이 문서에서는 대차 대조표에 대한 기본 보고서에 대해 설명합니다. 또한 이러한 보고서와 연결된 구성 요소에 대해 설명합니다.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0fae7ccb216ced0cbcbdb69980b3bae754a4980ecaf9314893368ae89459fa0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450343"
---
# <a name="balance-sheet-financial-reports"></a>대차 대조표 재무 보고서

[!include [banner](../includes/banner.md)]

이 문서에서는 대차 대조표에 대한 기본 보고서에 대해 설명합니다. 또한 이러한 보고서와 연결된 구성 요소에 대해 설명합니다. 

## <a name="default-balance-sheet-reports"></a>기본 대차 대조표 보고서

두 가지 기본 대차 대조표 보고서가 있습니다. 한 보고서에서는 섹션이 쌓여 있습니다. 다른 보고서에서는 섹션이 나란히 있습니다.

| 기본 보고서                       | 용도                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| 대차 대조표 – 기본값              | 해당 연도에 대한 조직의 재무 상태에 대한 보기를 제공합니다.                                                                 |
| 대차 대조표 나란히 – 기본값 | 해당 연도에 대한 조직의 재무 상태에 대한 보기를 제공합니다. 자산과 부채, 자본은 나란히 있습니다. |

## <a name="building-blocks"></a>구성 요소
대차 대조표 재무 보고서는 다음 구성 요소를 사용합니다.

| 기본 보고서                       | 행 정의                       | 열 정의             |
|--------------------------------------|--------------------------------------|-------------------------------|
| 대차 대조표 - 기본값              | 대차 대조표 - 기본값              | YTD 및 차이 - 기본값    |
| 대차 대조표 나란히 – 기본값 | 대차 대조표 나란히 – 기본값 | 연간 누계 열 - 기본값 |

### <a name="row-definition"></a>행 정의

두 대차 대조표 보고서의 행 정의에는 기존 대차 대조표의 각 부분에 대한 섹션이 포함되어 있습니다. 병렬 보고서에는 열 나누기가 포함되어 있으므로 부채와 자기 자본이 자산 옆에 표시됩니다. 주 계정 범주 차원은 두 행 정의를 모두 작성하는 데 사용됩니다. 따라서 누구나 수정하지 않고도 보고서를 생성할 수 있습니다.

### <a name="column-definition"></a>열 정의

열 정의에는 다양한 수준의 세부 정보 및 재무 데이터를 제공하는 다양한 유형의 열이 포함되어 있습니다.

-   **YTD 및 차이 – 기본 열 유형:**
    -   **DESC** – 행 정의의 설명
    -   **FD** – 현재 연도의 연간 누계 재무 데이터
    -   **FD** – 작년의 연간 누계 재무 데이터
    -   **CALC** – 올해에서 작년을 뺀 차이

<!-- -->

-   **연간 누계 열 – 기본값**
    -   **DESC** – 행 정의의 설명
    -   **FD** – 현재 연도의 연간 누계 재무 데이터



## <a name="additional-resources"></a>추가 리소스

[Financial Reporting 개요](financial-reporting-getting-started.md)

[재무 보고 보기](view-financial-reports.md)

[Dynamics Financial Reporting 블로그](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]