---
title: 인덱스 이자율 설정
description: 이 토픽에서는 인덱스 이자율을 설정하는 방법을 설명합니다. 조직에서 임대 지불 금액을 일련의 인덱스 이자율과 연결하는 경우 인덱스 이자율이 필요합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c9fd1ebabce628bbd7d0b0b03daaec11b2cd9d54157ba0ccbf0a7c89bdd07
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450460"
---
# <a name="set-up-index-rates"></a>인덱스 이자율 설정

[!include [banner](../includes/banner.md)]

임대료가 지수에 의존하는 경우 인덱스 이자율 유형을 시스템에 추가하고 유지할 수 있습니다. **인덱스 이자율 유형** 페이지에서 임대료를 재평가하기 위해 인덱스 이자율 재평가 프로세스는 재평가 날짜로부터 가장 최근의 인덱스 이자율을 사용합니다.

인덱스 이자율 유형과 인덱스 이자율을 추가하려면 다음 단계를 따르세요.

1. **자산 임대 \> 설정 \> 인덱스 이자율 유형** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 해당 필드에 이자율 유형과 인덱스 이자율 이름을 입력합니다.
4. 새 인덱스 이자율 값을 추가하려면 인덱스 이자율 유형을 선택한 다음 **추가** 를 선택합니다.
5. 이자율의 유효 시작 날짜를 선택하고 이자율 값을 선택합니다.

**인덱스 이자율 값 차이** 또는 **인덱스 이자율 값** 을 인덱스 이자율 방법으로 선택해야 합니다.

- 시작 날짜의 인덱스 이자율과 가장 최근의 인덱스 이자율의 차이를 기반으로 새로운 임대료를 계산하려면 **인덱스 이자율 값 차이** 방법을 선택합니다. 인덱스 이자율은 **인덱스 이자율(%)** 필드에 정의합니다.
- **인덱스 이자율 값** 방법을 선택하여 **인덱스 이자율(%)** 필드에 지정된 백분율을 사용하여 임대료를 계산합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
