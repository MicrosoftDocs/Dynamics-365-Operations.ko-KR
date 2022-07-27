---
title: 분개에서 지연 세금 계산 활성화
description: 이 항목에서는 분개 라인 수가 매우 많을 때 세금 계산 성능을 향상시키는 데 도움이 되도록 지연 세금 계산 기능을 설정하는 방법에 대해 설명합니다.
author: ericwang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 8394c83245865fd7fa02ddf80ada0532d1d4368e10e0a3248d0f8163f8e2224d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450439"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>분개에서 지연 세금 계산 활성화
[!include [banner](../includes/banner.md)]


이 항목에서는 분개에 대한 판매세 계산을 지연하는 방법에 대해 설명합니다. 이 기능은 분개 라인이 많은 경우 세금 계산 성능을 향상시키는 데 도움이 됩니다.

기본적으로 분개 라인의 판매세 금액은 세금 관련 필드가 업데이트될 때마다 계산됩니다. 이러한 필드에는 판매세 그룹 및 품목 판매세 그룹에 대한 필드가 포함됩니다. 분개 라인을 갱신하면 모든 분개 라인에 대해 세액이 다시 계산됩니다. 이 동작은 사용자가 실시간으로 계산된 세액을 보는 데 도움이 되지만 분개 라인 수가 매우 많을 경우 성능에 영향을 줄 수도 있습니다.

지연 세금 계산 기능을 사용하면 분개에 대한 세금 계산을 지연할 수 있으므로 성과 문제를 해결하는 데 도움이 됩니다. 이 기능을 설정하면 사용자가 **판매세** 를 선택하거나 분개장을 게시할 때만 세금 금액이 계산됩니다.

세 가지 수준에서 판매세 계산을 연기할 수 있습니다.

- 법인
- 분개장 이름
- 분개장 헤더

시스템은 분개장 헤더에 대한 설정에 우선순위를 부여합니다. 기본적으로 이 설정은 분개장 이름에서 가져옵니다. 기본적으로 분개장 이름 설정은 분개장 이름이 작성될 때 **일반 원장 매개변수** 페이지의 설정에서 가져옵니다. 다음 섹션에서는 법인, 분개 이름 및 분개장 헤더에 대해 지연 세금 계산을 설정하는 방법에 대해 설명합니다.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>법인 수준에서 지연 세금 계산 켜기

1. **총계정원장 \> 원장 설정 \> 총계정원장 매개 변수** 으로 이동합니다.
2. **판매세** 탭의 **일반** 빠른 탭에서 **지연세 계산** 옵션을 **예** 로 설정합니다.

![총계정원장 매개 변수 이미지.](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>분개장 이름 수준에서 지연 세금 계산 켜기

1. **총계정원장 \> 분개장 설정 \> 분개장 이름** 으로 이동합니다.
2. **일반** 빠른 탭의 **판매 세금** 섹션에서 **지연 세금 계산** 옵션을 **예** 로 설정합니다.

![분개장 이름 이미지.](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>분개장 헤더 수준에서 지연 세금 계산 켜기

1. **총계정원장 \> 분개장 항목 \> 일반 분개장** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 분개장 이름을 선택합니다.
4. **설정** 탭에서 **지연 세금 계산** 옵션을 **예** 로 설정합니다.

![일반 분개장 페이지 이미지.](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]