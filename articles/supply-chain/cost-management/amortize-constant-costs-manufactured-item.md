---
title: 제조 품목에 대한 불변 비용 상각
description: 제조 품목의 일정 비용은 작업 설정 시간과 일정 수량 또는 일정 스크랩 양이 있는 구성품을 반영합니다.
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: d9c539d525639ace6a139716e0644214364a060a2957ac97586cfad617e56ec0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446749"
---
# <a name="amortize-constant-costs-for-a-manufactured-item"></a>제조 품목에 대한 불변 비용 상각

[!include [banner](../includes/banner.md)]

제조 품목의 일정 비용은 작업 설정 시간과 일정 수량 또는 일정 스크랩 양이 있는 구성품을 반영합니다. 

원가 계산 로트 크기의 개념은 이러한 일정 비용을 제조 품목의 계산된 비용으로 상각하는 데 사용됩니다. 이 개념에는 여러 동의어가 있으며 그 중 하나는 회계 로트 크기입니다. 고정 비용 상각의 개념에는 여러 동의어가 있으며 그 중 하나는 비례 고정 비용입니다.

제조 품목에 대한 원가계산 로트 크기의 수량은 BOM(자재 명세서) 계산에 사용됩니다. 수량은 다음과 같이 BOM 계산을 시작하고 수행하는 방법에 따라 다릅니다.

-   항목 BOM 계산의 기본 계산 수량 - 재고에 대한 항목의 표준 주문 수량은 원가 계산 로트 크기로 작동하지만 기본 값은 항목의 주문 수량 배수를 반영하기 위해 더 큰 수량일 수 있습니다. 항목의 표준 주문 수량 및 배수는 기본 주문 설정 또는 사이트별 주문 설정 내에서 정의할 수 있습니다.
-   항목의 BOM 계산에서 지정된 계산 수량 - 지정된 계산 수량은 항목의 원가계산 로트 크기로 사용됩니다. 계산 수량은 처음에 항목의 표준 주문 수량을 사용하지만 기본값을 수동으로 무시할 수 있습니다. 지정된 계산 수량은 지정된 품목 및 BOM 라인 유형 생산이 있는 제조 구성품에 대한 원가계산 로트 크기를 나타냅니다. 부품이 정확한 수량으로 생산될 것으로 가정하기 때문입니다. 품목의 BOM 라인 유형이 있는 기타 제조 구성요소의 원가계산 로트 크기는 표준 주문 수량을 반영합니다.
-   품목의 BOM 계산에서 지정된 주문 생산 계산 수량 - BOM 계산에서 주문 생산 전개 모드를 사용할 때 지정된 계산 수량은 품목의 원가 계산 로트 크기 및 제조된 구성품으로 작동합니다. 제조된 부품은 BOM 라인 유형의 생산이 있는 제조 부품과 마찬가지로 정확한 수량으로 생산될 것이라고 가정합니다.
-   주문별 BOM 계산에서 지정된 계산 수량 − 판매 주문, 판매 견적 또는 서비스 주문의 라인 항목에 대해 주문별 BOM 계산을 수행할 수 있습니다. 지정된 계산 수량은 원래 라인 항목의 수량을 사용하지만 기본 수량을 재정의할 수 있습니다. 주문별 BOM 계산에서 주문 생산 또는 다중 레벨 분해 모드를 사용할지 여부를 선택할 수 있습니다.

제조 품목의 상각 불변 비용의 계산된 금액을 비용이라고 합니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]