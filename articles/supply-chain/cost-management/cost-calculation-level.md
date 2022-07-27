---
title: 비용 계산 수준
description: 이 항목에서는 비용 계산 수준이라는 BOM(자재 명세서) 수준에 대해 설명합니다. 이 BOM 수준은 계산에서 생산 및 배치 주문을 제외합니다.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e08d11c8e9d98e56c5ef076cbab7bb68bedea62a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449377"
---
# <a name="cost-calculation-level"></a>비용 계산 수준

[!include [banner](../includes/banner.md)]

이름이 **비용 계산 수준** 인 명명된 재료 명세서(BOM) 레벨은 계산에서 생산 주문 및 배치 주문을 제외합니다. 시스템은 원가계산 버전에서 원가계산을 실행할 때 이 레벨을 사용합니다. 재계산 및 재고 마감과 같은 프로세스에서 시스템은 대신 **원가 계산 수준** BOM 수준을 사용합니다.

다음의 간단한 시나리오는 **비용 계산 수준** BOM 수준과 **원가 계산 수준** BOM 수준 간의 차이를 보여줍니다.

A, B, C의 세 가지 제품이 있습니다. 제품 C는 제품 B의 구성품이고 제품 B는 제품 A의 구성품입니다.

- **원가 계산 수준** 은 다음 BOM 레벨을 지정합니다.

    - **제품 A:** 0
    - **제품 B:** 1
    - **제품 C:** 2

- **비용 계산 수준** 은 다음 BOM 레벨을 지정합니다.

    - **제품 A:** 0
    - **제품 B:** 1
    - **제품 C:** 2

그런 다음 제품 C에 대한 생산 오더가 생성되고 제품 A가 생산 오더 BOM에 추가됩니다. 주문이 예상되면 BOM 수준이 다음과 같은 방식으로 업데이트됩니다.

- **원가 계산 수준** 은 다음 BOM 레벨을 지정합니다.

    - **제품 B:** 1
    - **제품 C:** 2
    - **제품 A:** 3

- **비용 계산 수준** 은 다음 BOM 레벨을 지정합니다.

    - **제품 A:** 0
    - **제품 B:** 1
    - **제품 C:** 2

이 동작은 생산 오더 BOM에 대한 변경이 후속 비용 계산에 영향을 미치지 않도록 합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]