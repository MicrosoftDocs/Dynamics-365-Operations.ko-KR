---
title: 계수 감가상각
description: 이 문서에서는 계수 감가상각 방법에 대한 개요를 제공합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aab5ab518f2806e1b27f352e354dc9280fd27def
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451060"
---
# <a name="factor-depreciation"></a>계수 감가상각

[!include [banner](../includes/banner.md)]

이 문서에서는 계수 감가상각 방법에 대한 개요를 제공합니다.

계수는 자산을 감가상각하는 데 사용되는 백분율입니다. 고정 자산 감가상각 프로필을 설정하고 **감가상각 프로필** 페이지의 **방법** 필드에서 **계수** 를 선택하면 누진, 역진 또는 정액 감가상각을 설정할 수 있습니다.

-   누진 감가상각에서는 감가상각액이 감가상각 기간마다 증가합니다.
-   역진 감가상각에서는 감가상각액이 감가상각 기간마다 감소합니다.
-   정액 감가상각에서는 감가상각이 기간마다 동일합니다.

다음에 나오는 규칙과 예는 각 감가상각 유형별로 계수를 설정하는 방법을 보여줍니다. 

> [!NOTE] 
> **방법** 필드에서 **계수** 를 선택하면 **계수** 필드와 **간격** 필드가 표시됩니다.

## <a name="progressive-depreciation"></a>누진 감가상각
**계수** 필드의 값이 **50** 을 초과합니다.

### <a name="example"></a>예

취득 가격은 100,000, 계수는 70, 서비스 수명은 10년이고 감가상각은 1월 1일에 시작됩니다. 감가상각액과 순 장부가액은 서비스 수명의 최초 6년 동안만 표시됩니다.

| 년 | 기간      | 감가상각액 | 순 장부가액 금액 |
|------|-------------|---------------------|-----------------------|
| 1    | 12월 31일 | 307.69              | 99,692.31             |
| 2    | 12월 31일 | 1,447.21            | 98,245.10             |
| 3    | 12월 31일 | 3,104.50            | 95,140.60             |
| 4    | 12월 31일 | 5,150.21            | 89,990.39             |
| 5    | 12월 31일 | 7,522.95            | 82,467.44             |
| 6    | 12월 31일 | 10,184.06           | 72,283.38             |

## <a name="digressive-depreciation"></a>역진 감가상각
**계수** 필드의 값이 **50** 미만입니다.

### <a name="example"></a>예

취득 가격은 100,000, 계수는 20, 서비스 수명은 10년이고 감가상각은 1월 1일에 시작됩니다. 감가상각액과 순 장부가액은 서비스 수명의 최초 6년 동안만 표시됩니다.

| 년 | 기간      | 감가상각액 | 순 장부가액 금액 |
|------|-------------|---------------------|-----------------------|
| 1    | 12월 31일 | 56,080.43           | 43,919.57             |
| 2    | 12월 31일 | 10,665.70           | 33,253.87             |
| 3    | 12월 31일 | 7,156.22            | 26,097.65             |
| 4    | 12월 31일 | 5,538.06            | 20,559.59             |
| 5    | 12월 31일 | 4,579.89            | 15,979.70             |
| 6    | 12월 31일 | 3,937.36            | 12,042.34             |

## <a name="straight-line-depreciation"></a>정액 감가상각
**계수** 필드의 값이 **50** 과 같습니다. 이 경우 감가상각은 기간별로 동일하며 [정액 서비스 수명 감가상각](straight-line-service-life-depreciation.md)에서 설명한 것처럼 다른 필드에 지정한 값의 의미를 고려해야 합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
