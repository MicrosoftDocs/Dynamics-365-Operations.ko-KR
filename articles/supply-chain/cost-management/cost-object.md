---
title: 원가 개체
description: '이 문서에서는 원가 개체에 대한 정보를 제공하고 원가 및 수량이 누적되는 방법을 설명합니다. 원가 개체는 원가와 수량이 누적되는 개체입니다. 원가 개체 엔터티는 제품 또는 제품 변형(예: 스타일 및 색상 변형)일 수 있습니다.'
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d27e2dcfd8f70c8d4b0f2ae1254f3c4fce63bb4d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448489"
---
# <a name="cost-objects"></a>원가 개체

[!include [banner](../includes/banner.md)]

이 문서에서는 원가 개체에 대한 정보를 제공하고 원가 및 수량이 누적되는 방법을 설명합니다. 원가 개체는 원가와 수량이 누적되는 개체입니다. 원가 개체 엔터티는 제품 또는 제품 변형(예: 스타일 및 색상 변형)일 수 있습니다.  

## <a name="cost-objects"></a>원가 개체

**원가 개체** 페이지에는 제품에 등록된 모든 원가 개체가 나열됩니다. 비용 개체는 다음 소스의 데이터로 정의됩니다.

-   제품
-   제품 크기 그룹
-   재고 규모 그룹
-   추적 규모 그룹

**메모:** 비용 개체는 **직접 재료** 유형의 비용 요소만 나타냅니다. 원가 개체와 인벤토리 개체는 재무 인벤토리에 대해 선택한 인벤토리 차원에 따라 원가 개체가 정의되는 방식이 다릅니다. 예를 들어 항목의 구성은 다음과 같습니다.

-   **대지:** 총실사 = 예, 재무 재고 = 예
-   **창고:** 총실사 = 예, 재무 재고 = 아니요
-   **배치 번호:** 총실사 = 예, 재무 재고 = 아니요

다음 표는 원가 개체와 재고 개체를 보여줍니다.

| 개체 유형      | 품목 번호 | 사이트 | 창고 | 배치 번호 |
|------------------|-------------|------|-----------|-----------|
| 원가 개체      | x           | x    |           |           |
| 인벤토리 개체 | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>비용 및 수량의 누적
-   **값** 필드의 값은 다음 값의 합계입니다.
    -   실제 비용 금액
    -   금융 비용 금액
    -   조정
-   **수량** 필드의 값은 다음 값의 합계입니다.
    -   수령함
    -   공제
    -   기장된 수량
-   **평균 단가** 필드는 계산된 필드입니다. 값은 **값** 값을 **수량** 값으로 나누어서 계산됩니다.

**메모:** **물리적 값 포함** 매개 변수는 이전 계산에 영향을 주지 않습니다.

## <a name="additional-resources"></a>추가 리소스

[제품 크기 그룹](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[재고 규모 그룹](/dynamicsax-2012//storage-dimension-groups-form)

[추적 규모 그룹](/dynamicsax-2012//tracking-dimension-groups-form)

[새로운 기능 또는 변경된 기능](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[비용 항목](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]