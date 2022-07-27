---
title: 팬텀 항목
description: 이 항목에서는 Dynamics 365 Supply Chain Management에서 BOM(자재 명세서)의 라인과 공식에 팬텀 라인 유형을 사용하는 방법에 대해 자세히 설명합니다.
author: johanhoffmann
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 8e1b241c826e89909590ae16c8458bc49df995bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448558"
---
# <a name="phantom-items"></a>팬텀 항목

[!include [banner](../includes/banner.md)]

이 항목에서는 BOM(자재 명세서)의 라인과 공식에 팬텀 라인 유형을 사용하는 방법에 대해 자세히 설명합니다.

다음 그림에서 (a)는 제품 H와 부품 F 및 G에 대한 BOM이고, (b)는 제품 H와 부품 F에 대한 경로 시트입니다.

![두 수준에서 BOM 구조의 예.](media/product-H-part-F.png)

이 그림은 두 수준에서 BOM 구조의 예를 보여줍니다. 완제품 H는 기계조립용 제품을 나타냅니다. 기계 조립은 두 개의 재료(A 및 B)가 있는 전기 장치(F)와 두 개의 재료(C 및 D)가 있는 포장 재료 그룹(G)의 두 부분으로 구성됩니다. 다른 재료(E)는 기계의 전체 조립 중에 사용됩니다.

![제품 H에 대한 엔지니어링 BOM.](media/product-H-part-B.png)

앞의 그림은 제품 H에 대한 엔지니어링 BOM을 나타냅니다. 이 구조는 전체 기계 조립의 부품 및 구성요소에 대한 좋은 개요를 제공합니다. 그러나 제품 설계자는 이러한 방식으로 BOM을 표시하는 것을 선호할 수 있지만 이 구조는 기계가 작업 현장에서 구축되는 방식을 올바르게 나타내지 않을 수 있습니다.

예를 들어, 앞의 그림에서 엔지니어링 BOM은 전기 장치 F가 별도의 작업 주문에서 별도의 부품으로 조립되었음을 나타냅니다. 그러나 작업 현장에서는 별도의 작업 지시가 아닌 전체 기계 조립의 일부로 전기 장치를 조립하는 것이 더 최적이라고 판단될 수 있습니다.

또한 이 엔지니어링 BOM은 부품 G가 별도의 부품임을 나타냅니다. 그러나 이 구조에서 파트 G는 물리적인 부분이 아니라 포장재의 집합체를 나타냅니다.

따라서 엔지니어링 BOM은 제품 설계 및 해당 설계 유지 관리에 큰 가치를 제공하지만 제품의 제조 실행 프로세스를 지원하는 가장 논리적인 방법은 아닐 수 있습니다. 대조적으로, 제조 BOM은 제품을 구축하는 가장 좋은 방법을 나타냅니다.

다음 그림은 이전 엔지니어링 BOM이 제조 BOM으로 전환되는 방법을 보여줍니다. 이 그림에서 (a)는 제품 H에 대한 BOM이고 b는 제품 H에 대한 경로 시트입니다.

이 구조에서는 부품 F와 G의 개념이 없고 이러한 부품을 구성하는 재료가 다음 BOM 수준으로 상승되었음을 알 수 있습니다.

두 개의 작업 시트가 있는 엔지니어링 BOM과 달리 제조 BOM에는 하나의 작업 시트만 있습니다. 부품 G에 연결된 포장 작업도 높아져 이제 제품 H에 대한 작업 시트의 일부입니다. 전기 장치의 조립이 첫 번째 작업입니다. 이 순서는 이 장치가 다음 작업인 기계 조립에 사용되기 때문에 의미가 있습니다. 마지막 작업은 두 개의 포장재(C 및 D)를 소모하는 포장 작업입니다.

엔지니어링 BOM과 제조 BOM 간의 전환은 팬텀 BOM 라인 유형을 통해 활성화됩니다. "팬텀"이라는 용어에서 알 수 있듯이 두 BOM 유형 간의 전환 중에 부품 F와 G가 사라졌습니다. 이 예에서 팬텀 라인 유형은 엔지니어링 BOM의 부품 F 및 G에 대한 BOM 라인에 적용됩니다. 생산 또는 배치 주문이 생성되면 엔지니어링 BOM이 생산 또는 배치 주문에 복사됩니다. 그런 다음 주문이 예상되면 앞의 그림과 같이 엔지니어링 BOM에서 제조 BOM으로 전환됩니다. 두 번째 그림의 작업 시트에서 포장재 C와 D가 작업에 입력됩니다.

## <a name="multilevel-phantom-bom-structures"></a>다단계 팬텀 BOM 구조

팬텀 라인 유형은 다음 그림과 같이 다단계 BOM 구조에서 사용할 수 있습니다. 이 그림에서 (a)는 제품 G에 대한 BOM이고 (b)는 부품 E, F 및 제품 G에 대한 경로 시트입니다.

![다중 레벨 BOM 구조에 사용되는 팬텀 라인 유형입니다.](media/product-G-route-sheet-G.png)

다음 그림은 부품 E 및 F에 대한 BOM 라인이 선 유형이 팬텀이 되도록 구성된 경우 결과 제조 BOM 및 경로 시트를 보여줍니다. 이 그림에서 (a)는 제품 G의 BOM이고 (b)는 제품 G의 경로 시트입니다.

![제품 G.](media/product-G.png)

## <a name="phantom-and-route-network"></a>팬텀 및 경로 네트워크

팬텀 BOM은 경로 네트워크가 있는 BOM에도 사용할 수 있습니다. 경로 네트워크에서 하나 이상의 작업이 병렬로 실행됩니다. 다음 그림은 다중 레벨 BOM에서 사용되는 경로 네트워크의 예를 보여줍니다. 이 그림에서 (a)는 제품 G 및 부품 F에 대한 BOM이고 (b)는 경로 네트워크가 있는 제품 G 및 부품 F에 대한 경로 시트입니다.

![다중 레벨 BOM에서 사용되는 경로 네트워크의 예.](media/product-G-part-F.png)

다음 그림에서 (a)는 제품 G 및 부품 F에 대한 BOM이고 (b)는 제품 G 및 부품 F에 대한 경로 시트입니다.

![제품 G 및 부품 F에 대한 BOM 및 제품 G 및 부품 F에 대한 경로 시트.](media/product-G-part-F-with-route-sheet.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]