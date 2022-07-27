---
title: 생산 주문 비용 추정
description: 이 문서에서는 생산 비용 추정에 대한 정보를 제공합니다. 생산 비용 추정은 계획된 생산 주문 수량으로 품목을 생산하는 데 필요한 예상 자재 및 용량 소비 비용을 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5debf62a3a0fc3ae8828473d7dd593c690e298712e5ed696077db1562796943
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446734"
---
# <a name="production-order-cost-estimation"></a>생산 주문 비용 추정

[!include [banner](../includes/banner.md)]

이 문서에서는 생산 비용 추정에 대한 정보를 제공합니다. 생산 비용 추정은 계획된 생산 주문 수량으로 품목을 생산하는 데 필요한 예상 자재 및 용량 소비 비용을 제공합니다. 

생산 주문을 생성한 후에는 생산 비용을 추정해야 합니다. 목적은 생산 프로세스에 대한 품목 및 경로 소비를 추정하는 것입니다. 이러한 추정은 후속 일정 및 생산 프로세스의 기초로 사용되기 때문입니다.

## <a name="production-cost-estimation"></a>생산 비용 추정
생산 비용 추정은 다음 정보를 기반으로 합니다.

-   생산 주문의 수량
-   자재 명세서(생산 자재 명세서)의 구성 요소
-   생산 경로의 라우팅 작업
-   구성 요소 및 작업에 적용되는 간접 비용
-   계산일 현재 활성 비용 데이터

생산 BOM에 팬텀 라인 항목이 있는 경우 계산에는 팬텀의 구성 요소 및 경로 작업이 반영됩니다. 추정 작업을 사용하여 업데이트된 정보를 반영하도록 추정 비용을 다시 계산할 수 있습니다. 예를 들어, 업데이트된 정보는 생산 주문의 수량, 생산 BOM의 구성 요소, 생산 경로의 라우팅 작업, 이러한 구성 요소및 작업에 적용되는 간접 원가 또는 재계산 날짜 현재의 활성 원가 데이터에 대한 변경일 수 있습니다. 예상 비용 계산은 또한 비용 가산 인상 방식을 기반으로 한 생산 품목의 판매 가격을 제안합니다. 예상 비용 계산은 생산 주문에 연결된 다른 생산 주문을 반영하는 참조 주문에 선택적으로 적용될 수 있습니다.

## <a name="view-the-estimated-costs"></a>예상 비용 보기
추정을 실행한 후 **가격 계산** 페이지에서 결과를 볼 수 있습니다. 추정은 다음 값을 계산합니다.

-   **생산 비용** – 생산 비용은 추정의 상위 라인입니다. 생산 주문 실행의 전체 비용과 생산의 총 판매 가격을 보여줍니다. 추정에 있는 모든 비용 라인의 합계입니다.
-   **경로 또는 리소스 비용** – 경로 또는 리소스 비용은 생산 작업에 대한 비용입니다. 여기에는 설정 시간, 실행 시간 및 오버헤드와 같은 요소 비용이 포함됩니다.
-   **재료비** – 재료비는 품목을 생산하는 데 필요한 BOM 구성 요소의 비용 및 가격입니다. 이러한 비용은 이전에 설정되어 시스템에 입력되었습니다.

## <a name="other-uses-of-cost-estimation"></a>비용 추정의 다른 용도
비용 추정은 다음 정보도 제공합니다.

-   의미있는 가격 견적
-   주문의 수익성 추정
-   원료 사용량 추정
-   이전 생산의 비용 정보 비교
-   예산 및 예측 정보
-   특정 비용을 유지하기 위해 필요한 생산 규모 추정






[!INCLUDE[footer-include](../../includes/footer-banner.md)]