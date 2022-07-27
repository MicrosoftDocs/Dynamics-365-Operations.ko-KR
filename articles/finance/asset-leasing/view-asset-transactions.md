---
title: 부채, 자산 및 경비 거래 보기
description: 이 항목에서는 임대 자산에 대한 거래를 보는 방법을 설명합니다. 이러한 거래에는 게시된 임대 부채 거래와 경비 거래가 포함됩니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 58a57b2a1237b41c99e44cf40c57d80257fc9b5b77188586aab6735a8a3f4984
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450685"
---
# <a name="view-liability-asset-and-expense-transactions"></a>부채, 자산 및 경비 거래 보기

[!include [banner](../includes/banner.md)]

이 항목에서는 임대 자산에 대한 거래를 보는 방법을 설명합니다. 이러한 거래에는 게시된 임대 부채 거래와 경비 거래가 포함됩니다. 부채 및 사용권(ROU) 자산의 장부 가치는 여러 보고서에 사용됩니다. 조정 가치를 계산하는 데도 사용됩니다.

## <a name="liability-transactions"></a>부채 거래

임대 부채 거래를 보려면 **임대 요약** 페이지에서 임대를 선택한 다음 **장부** 를 선택하여 임대 레코드에 첨부된 장부를 엽니다. 최초 인식, 송장 또는 이자 분개장이 게시된 후 **부채 거래** 를 선택합니다.

**부채 거래** 페이지에는 임대 부채를 늘리거나 줄이는 거래가 표시됩니다. 이 페이지의 음수 금액은 표준 애플리케이션의 신용 거래를 나타냅니다. 모든 이자 적립은 음수 값으로 표시되며 총 임대 부채를 증가시킵니다. 모든 임대 조정은 임대 장부의 성격과 영향에 따라 양수 또는 음수 값으로 표시됩니다. 선택한 임대에 대한 임대 부채의 현재 순 총 잔액은 페이지 왼쪽 하단에 표시됩니다.

## <a name="asset-transactions"></a>자산 거래

임대 자산 거래를 보려면 **임대 요약** 페이지에서 임대를 선택한 다음 **장부** 를 선택하여 임대 레코드에 첨부된 임대 장부를 엽니다. 그런 다음 **자산 거래** 를 선택합니다.

**자산 거래** 페이지는 임대 자산과 누적 감가상각 계정을 증감하는 거래를 보여줍니다. **채무 거래** 페이지와 같이 출금은 양수 값으로 표시되고 입금은 음수 값으로 표시됩니다. 게시된 초기 인식과 다음 누적 감가상각은 페이지 왼쪽 하단에 자산 잔액으로 표시됩니다. 

## <a name="expenses-transactions"></a>경비 거래

임대 경비 거래를 보려면 **임대 요약** 페이지에서 임대를 선택한 다음 **장부** 를 선택하여 임대 레코드에 첨부된 임대 장부를 엽니다. 그런 다음 **경비 거래** 를 선택합니다.

**경비 거래** 페이지에는 이자 비용, 감가상각 경비, 집행 비용 등 임대에 대해 게시된 모든 경비가 표시됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
