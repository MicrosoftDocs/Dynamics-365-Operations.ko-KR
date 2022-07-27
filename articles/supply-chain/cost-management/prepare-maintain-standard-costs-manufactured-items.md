---
title: 제조 항목에 대한 표준 원가 유지 준비
description: 이 항목에서는 제조 품목의 원가 유지를 준비하는 단계에 대해 설명합니다.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec68e1efc261920dc8f08ed602836b1939511dfce01008c093af7916ecd71618
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446824"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>제조 항목에 대한 표준 원가 유지 준비

[!include [banner](../includes/banner.md)]

이 항목에서는 제조 품목의 원가 유지를 준비하는 단계에 대해 설명합니다. 제조 품목의 단계는 구매 품목의 단계와 약간 다릅니다.

제조 품목에 할당된 정책은 상위 제조 품목에 대한 비용 계산에 영향을 미칠 수 있습니다. 제조 품목에 대한 비용 유지를 준비하려면 다음 단계를 따르십시오.

1. 제조 품목에 품목 모델 그룹을 지정합니다. 

   품목 모델 그룹은 표준 비용이 사용될 것임을 식별합니다.

2. 제조 품목에 품목 그룹을 지정합니다. 

   품목 그룹에는 제조 품목에 적용되는 원장 계정이 포함됩니다. 표준 원가 재고 모델이 있는 제조 품목에 대한 원장 계정에는 여러 생산 차이, 원가 변경 차이 및 재고 원가 재평가가 포함됩니다.

3. 품목에 재고 UOM을 지정합니다. 

   품목의 비용은 항상 품목의 재고 측정 단위로 표시됩니다.

4. 품목이 구매 품목으로 취급되지 않는 한 제조 품목에 비용 그룹을 지정하지 마십시오.

5. 제조 품목에 BOM(자재 명세서) 계산 그룹을 지정합니다. 

   항목의 BOM 계산 그룹은 적용되는 경고 조건을 정의합니다. 이러한 방식으로 BOM 계산이 완료되면 계산 오류의 가능한 원인에 대한 경고 메시지가 생성될 수 있습니다. 예를 들어 경고 메시지는 활성 BOM 또는 경로가 존재하지 않을 때 식별할 수 있습니다. BOM 계산 그룹에는 제조 품목을 구매 품목으로 처리해야 하는 시기를 나타내는 폭발 중지 정책이 포함되어 있습니다.

6. 제조 품목에 일정 비용이 있는 경우 표준 주문 수량을 지정합니다. 

   표준 주문 수량은 일정 비용을 상각하기 위한 회계 로트 크기입니다. 일정 비용의 예로는 라우팅 작업의 설정 시간과 BOM의 일정 구성품 수량을 들 수 있습니다.

7. 제조 품목에 대한 BOM을 정의합니다. 

   제조 품목에 대해 하나 이상의 BOM 버전을 정의할 수 있습니다. 원하는 버전이 승인 및 활성으로 표시되었고 원하는 유효 날짜가 있는지 확인하세요. BOM 버전은 회사 전체 또는 사이트별로 다를 수 있습니다.

8. 제조 품목에 대한 라우팅을 정의합니다. 

   제조 품목에 대해 하나 이상의 경로 버전을 정의할 수 있습니다. 원하는 버전이 승인 및 활성으로 표시되었고 원하는 유효 날짜가 있는지 확인하세요. 경로 버전은 사이트별로 달라야 합니다.

원가 계산을 위해 라우팅 정보를 사용하려면 추가 준비 단계가 필요합니다. 예를 들어, 라우팅 작업에 지정된 비용 범주는 정확하고 완료되어야 합니다.

## <a name="related-topics"></a>관련 토픽

[제조 품목에 대한 불변 비용 상각](amortize-constant-costs-manufactured-item.md)

[생산 또는 조달할 수 있는 제품 설정](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]