---
title: 분할 후 잔액 감소 감가상각
description: 이 항목에서는 잔액 감소 방법을 사용하여 자산을 분할한 후 고정 자산의 감가상각을 계산하는 데 사용되는 방법에 대해 설명합니다.
author: moaamer
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8e59ff1ef2b06a7203c1023bade7f06019479f3929dfbd582860f102c46b49f0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450397"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>분할 후 잔액 감소 감가상각

[!include [banner](../includes/banner.md)]

이 항목에서는 잔액 감소 방법을 사용하여 다른 자산으로 자산을 분할한 후 고정 자산의 감가상각을 계산하는 데 사용되는 방법에 대해 설명합니다. 자산 장부에 구성된 감가상각 연도는 회계 연도입니다. 자세한 내용은 [잔액 감소 감가상각](reduce-balance-depreciation.md) 및 [고정 자산 분할](tasks/split-fixed-asset.md)을 참조하십시오.

자산을 취득한 기간보다 늦은 회계 기간에 고정 자산을 분할할 경우 감소된 잔액 감가상각에는 해당 자산의 전년도 순 장부가액(NBV)이 고려됩니다. 자산을 분할한 트랜잭션에서 발생한 취득 및 감가상각 조정 트랜잭션도 고려됩니다. 이 방식은 자산이 한 회계연도에 취득되어 이후 회계연도에 분할되었다고 가정합니다. 분할 후 원래 자산에 대해 감가상각해야 하는 금액은 자산이 분할되기 전의 자산의 NBV와 분할에 대해 게시된 취득 및 감가상각 조정 트랜잭션을 반영합니다.

예를 들어 다음과 같은 조건이 적용됩니다.

- 회계 기간은 6월 30일부터 7월 1일까지입니다.
- 잔액 감소 비율은 18%이며, 2019년 6월에 자산을 10,000달러에 인수합니다.
- 첫 회계연도의 감가상각은 18,000달러, 월 감가상각은 150달러이며, 이후 2019년 11월까지 감가상각은 738.75달러입니다.
- 2019년 11월에 자산의 80%가 다른 고정 자산으로 분할됩니다.

[![분할 후 잔액 감소 감가상각.](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

원래 자산의 감가상각 금액은 $1,822.25입니다. 이 금액은 분할 트랜잭션이 게시되기 전의 NBV(9,111.25달러), 분할 트랜잭션을 게시하는 동안 발생하는 취득 조정(-8,000달러), 분할 트랜잭션 동안 발생하는 감가상각 조정(711달러)과 같습니다. 따라서 2년 차의 감가상각은 (1,822.25 × 18%) ÷ 12 = 27.33달러입니다.

첫 해에 새로운 고정 자산의 감가상각은 (8,000 × 18%) ÷ 12 = 120달러입니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]