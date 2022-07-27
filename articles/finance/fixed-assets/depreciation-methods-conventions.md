---
title: 감가상각 방법 및 규칙
description: 이 문서에서는 Microsoft Dynamics 365 Finance에서 지원하는 감가상각 규칙 및 감가상각 방법을 설명합니다.
author: moaamer
ms.date: 12/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f0f3b8be86225fd68df9b099e5c8e13a220a213
ms.sourcegitcommit: a5861c2fef4071e130208ad20e26cb3a42a45cf1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2021
ms.locfileid: "8451312"
---
# <a name="depreciation-methods-and-conventions"></a>감가상각 방법 및 규칙

[!include [banner](../includes/banner.md)]

이 문서에서는 지원되는 감가상각 규칙과 감가상각 방법에 대한 개요를 설명합니다.

다양한 감가상각 방법 및 규칙을 선택할 수 있습니다. 이 방법의 목적은 고정 자산의 감가상각 가치를 회계 기간에 배분하는 것입니다. 고정 자산의 감가상각 가능 가치는 폐기 가치가 있는 경우 이를 뺀 취득 가격입니다. 

감가상각 규칙을 사용하는 경우 자산의 마지막 감가상각 실행 날짜를 수정하여 일부 감가상각을 건너뛸 경우 지난 해의 감가상각이 예상보다 크거나 적을 수 있습니다. 감가상각은 마지막 감가상각 날짜 변경의 영향을 받는 감가상각 기간의 수에 따라 조정됩니다.

예를 들어 반년 감가상각 규칙을 3년 넘게 사용하면 감가상각은 일반적으로 3년 반에 넘게 발생합니다. 3년 반 동안 마지막 감가상각 실행 날짜를 변경하면 마지막 감가상각 연도의 영향을 받는 기간 수가 변경됩니다. 날짜를 3개월 이동하면 보통 6개월의 감가상각이 발생하는 마지막 연도에 9개월의 감가상각이 발생합니다.

다음 감가상각 규칙 중에서 선택할 수 있습니다.


-   반년
-   한 달 전체
-   분기 중반
-   월 중간(매월 1일)
-   월 중간(매월 15일)
-   반년(연초)
-   반년(내년)

다음 감가상각 방법 중에서 선택할 수 있습니다.
-   직선 서비스 수명
-   잔액 감소
-   수동
-   계수
-   소비
-   남은 직선 수명
-   200% 잔액 감소
-   175% 잔액 감소
-   150% 잔액 감소
-   125% 잔액 감소





## <a name="additional-resources"></a>추가 리소스

[고정 자산 감가상각](fixed-asset-depreciation.md)

[직선 서비스 수명 감가상각](Straight-line-service-life-depreciation.md)

[잔액 감소 감가상각](reduce-balance-depreciation.md)

[수동 감가상각](manual-depreciation.md)

[계수 감가상각](factor-depreciation.md)

[소비 감가상각](consumption-depreciation.md)

[남은 직선 수명 감가상각](straight-line-life-remaining-depreciation.md)

[125% 잔액 감소 감가상각](125-percent-reducing-balance-depreciation.md)

[150% 잔액 감소 감가상각](150-percent-reducing-balance-depreciation.md)

[175% 잔액 감소 감가상각](175-percent-reducing-balance-depreciation.md)

[200% 잔액 감소 감가상각](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
