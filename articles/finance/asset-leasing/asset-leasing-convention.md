---
title: 자산 임대 규칙
description: 이 토픽에서는 임대 자산에 대한 규칙에 대해 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: afc432d448f3b013dd8732120d7e8a50a9169343c705a75465e669156fd5e052
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450415"
---
# <a name="asset-leasing-conventions"></a>자산 임대 규칙

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 토픽에서는 임대 자산에 대한 규칙에 대해 설명합니다. 임대 규칙은 임대 장부의 시작 날짜를 결정하는 데 사용됩니다. 임대 규칙이 **없음** 으로 설정된 경우 시작 날짜는 임대 시작 날짜와 동일합니다(즉, **임대 시작 날짜** 필드의 값). 임대 규칙이 **한 달** 로 설정된 경우 시작 날짜는 임대 시작 날짜가 속하는 달의 1일입니다.

개시일은 부채 상각 및 자산 감가상각 일정 기간의 시작 날짜를 결정합니다. 이자 비용과 감가상각비는 해당 일정의 종료 날짜에 전기합니다. 최초 인식 및 조정 분개는 개시일에 전기됩니다.

> [!NOTE]
> 임대 규칙에 대한 기능은 기능 관리를 통해 켜야 합니다. **기능 관리** 작업 영역에서 **자산 임대에 대한 임대 규칙** 기능이라는 기능을 찾아 선택한 다음 **지금 활성화** 를 선택합니다.

임대 자산 장부에 대한 설정에 임대 규칙이 지정됩니다.

임대 규칙을 보거나 할당하려면 다음 단계를 따르세요.

1. **자산 임대 \> 설정 \> 임대 장부** 로 이동합니다.
2. **임대 규칙** 필드에서 다음 값 중 하나를 선택합니다.

    | 임대 규칙 | 설명 |
    |--------------------|-------------|
    | 없음               | 부채 상각 및 자산 감가상각 일정은 개시일이 임대 시작 날짜와 같기 때문에 임대 시작 날짜에 시작됩니다. 종료 날짜는 한 달 후입니다. 이 임대 계약은 이자가 매월 말일에 전기될 것이라고 보장하지 않습니다. |
    | 한 달 전체         | 시작 날짜가 해당 월 중 아무 때나 발생하는 임대의 경우 부채 상각 및 자산 감가상각 일정에 따라 해당 월의 1일에 비용이 발생하기 시작합니다. 이 임대 규칙은 이자가 매월 말일에 발생하도록 보장합니다. |

3. **저장** 을 선택합니다.

임대가 생성되면 각 장부의 시작 날짜는 임대에 대해 입력된 시작 날짜와 해당 장부에 대해 지정된 임대 규칙에 따라 자동으로 입력됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
