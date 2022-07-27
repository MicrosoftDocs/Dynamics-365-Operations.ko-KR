---
title: 감가상각 계산을 위한 금액 반올림
description: 이 항목에서는 장부 설정 페이지에 있는 감가상각 반올림 필드에 관해 설명합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3df48fc7bb092b0257c4652a8c67d1d740dbcfe
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451051"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>감가상각 계산을 위한 금액 반올림

[!include [banner](../includes/banner.md)]

이 항목에서는 **장부 설정** 페이지에 있는 **감가상각 반올림** 필드에 관해 설명합니다.

감가상각 금액 반올림은 장부별로 설정됩니다. 감가상각 금액 반올림은 고정 자산의 미래 감가상각 및 가치를 보여주는 고정 자산 감가상각 프로필과 감가상각 제안에도 사용됩니다. 장부에 허용되는 가장 낮은 감가상각 금액을 입력합니다. 

반올림 설정과 관계없이 마지막 감가상각 기간의 감가상각 금액은 반올림되지 않습니다. 마지막 감가상각 기간 종료 시 고정 자산의 가치는 0(영)이거나 폐기 가치가 사용되는 경우 폐기 가치여야 합니다.

### <a name="example"></a>예

반올림하지 않은 감가상각은 2,444.44로 계산됩니다. 다음 표에서 볼 수 있듯이 제안된 금액은 반올림 설정 방법에 따라 다릅니다.

| 반올림 방법 | 감가상각액 |
|-----------------|---------------------|
| 0.1 반올림    | 2,444.40            |
| 1.00 반올림   | 2,444.00            |
| 10.00 반올림  | 2,440.00            |
| 100.00 반올림 | 2,400.00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
