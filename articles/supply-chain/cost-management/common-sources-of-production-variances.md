---
title: 생산 편차의 일반적인 원인
description: 이 문서에서는 각 유형의 생산 편차에 대한 다양한 일반적인 원인에 대해 설명합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce352db56fe41264562fd11260f9fa91931babeeb62d352327a588fb622492d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447166"
---
# <a name="common-sources-of-production-variances"></a>생산 편차의 일반적인 원인

[!include [banner](../includes/banner.md)]

이 문서에서는 각 유형의 생산 편차에 대한 다양한 일반적인 원인에 대해 설명합니다. 

다음은 몇 가지 일반적인 **로트 크기** 변수의 소스입니다.

-   생산 오더의 양호한 수량은 표준 원가 계산에 사용된 계산 수량과 다릅니다. 수량은 일정 비용을 상각하기 위한 기초를 제공합니다.
-   생산 오더의 일정 비용 값은 표준 비용 계산에 사용되는 일정 비용과 다릅니다. 생산 오더의 일정 비용은 여러 가지 이유로 다를 수 있습니다. 예를 들어, 불변 비용은 다음 요소를 반영할 수 있습니다.
    -   생산 BOM(자재 명세서) 또는 경로에 대한 수동 변경
    -   생산 오더 생성 시 다른 BOM 버전 또는 경로 버전 선택
    -   품목에 지정된 BOM 버전 또는 경로 버전에 대한 계획된 엔지니어링 변경

다음은 몇 가지 일반적인 **생산 가격** 변수의 소스입니다.

-   보고된 라우팅 작업 소비에 대한 비용 범주(및 비용 범주 가격)는 표준 비용 계산에 사용되는 비용 범주와 다릅니다.
-   비용 범주의 활성 비용 가격은 표준 비용 계산에 사용되는 비용 범주 가격과 다릅니다.

다음은 몇 가지 일반적인 **생산 수량** 변수의 소스입니다.

-   중요한 구성 요소를 초과 발행하거나 과소 발행합니다.
-   라우팅 작업 시간을 초과 보고하거나 과소 보고합니다.
-   주문 수량에 비해 상위 품목의 양호한 수량을 초과 입고 또는 적게 입고했습니다. 그러나 생산 오더의 오더 수량을 기준으로 구성품을 출고하고 작업을 완전히 보고합니다.

다음은 몇 가지 일반적인 **생산 대체** 변수의 소스입니다.

-   생산 BOM에 없는 자재 구성요소를 출고합니다.
-   생산 BOM에 구성요소를 수동으로 추가하고 해당 구성요소를 소비된 것으로 보고합니다.
-   항목을 소비된 것으로 보고하지만 생산 BOM에 수동으로 추가하지 않습니다.
-   생산 라우트에 작업을 수동으로 추가하고 해당 작업을 소비된 것으로 보고합니다.
-   생산 오더를 생성할 때 표준 원가 계산에 사용되는 BOM 버전과 다른 BOM 버전을 선택합니다.
-   생산 오더를 생성할 때 표준 원가 계산에 사용되는 라우트 버전과 다른 라우트 버전을 선택합니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]