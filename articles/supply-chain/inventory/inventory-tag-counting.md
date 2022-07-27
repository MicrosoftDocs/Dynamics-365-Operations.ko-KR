---
title: 재고 태그 계산
description: 이 토픽에서는 창고의 실제 내용을 현재고와 비교하는 데 사용하는 태그 계산에 대한 정보를 제공합니다.
author: yufeihuang
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64315b8c5f0be1dbd19239a8b07746e90aebb0d4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448006"
---
# <a name="inventory-tag-counting"></a>재고 태그 계산

[!include [banner](../includes/banner.md)]

이 토픽에서는 창고의 실제 내용을 현재고와 비교하는 데 사용하는 태그 계산에 대한 정보를 제공합니다.

**태그 계산** 페이지에서 라인을 생성하여 1에서 500까지의 숫자와 같이 각 재고 항목에 태그 번호를 배치합니다. 계산하는 동안 해당 태그에 품목 번호와 수량을 입력합니다. 그런 다음 이 태그를 태그 계산 분개장에 입력하기 위한 기준으로 사용할 수 있습니다. 태그 계산 분개장을 게시하면 **계산** 페이지에 새로운 계산 분개장이 생성됩니다. 새 분개장은 생성한 분개장 라인을 계산하는 태그를 기반으로 합니다. 특정 재고 규모로 항목에 태그를 계산하려면 태그 계산 분개장을 생성할 때 표시되는 **디스플레이 규모** 페이지에서 규모를 선택합니다. 예를 들어, 특정 창고의 항목을 계산하려면 **창고** 확인란을 선택합니다. **재고 및 창고 관리 매개 변수** 페이지에서 **계산 중 항목 잠금** 슬라이더를 선택하면 계산 중에 항목을 물리적으로 업데이트할 수 없습니다. 그러나 태그 계산 분개장의 항목은 계산 중에 잠기지 않습니다. 태그 실사 라인이 전기되고 실사 분개장으로 이전될 때까지는 재고 거래가 생성되지 않습니다. 태그가 임의로 입력되고 누락된 태그를 식별하려면 **태그** 열 머리글을 클릭하여 태그별로 행을 정렬합니다.

## <a name="additional-resources"></a>추가 리소스

[순환 재고](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]