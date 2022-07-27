---
title: 임대 부채의 단기 부분 재분류
description: 이 항목에서는 임기 부채의 일부를 단기 부채로 재분류하기 위해 월별 저널을 생성하는 방법에 대해 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 21cf81ce84d91d88a800cd250fca8fd5a9c876e66f506cd366b8d61ed480ea7e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450196"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>임대 부채의 단기 부분 재분류

[!include [banner](../includes/banner.md)]

이 항목에서는 임기 부채의 일부를 단기 부채로 재분류하기 위해 월별 저널을 생성하는 방법에 대해 설명합니다. 배치 프로세스에서 선택한 일정이 **단기 임대 책임 재분류** 일 경우 저널 항목이 생성됩니다. 이 항목은 해당 월의 마지막 날에 임기 부채의 현재 부분을 게시하는 데 사용됩니다. 동시에 다음 달 1일을 기준으로 반전 입력이 게시됩니다.

임대 부채의 단기 부분은 부채 상각 일정에 표시됩니다. 저널 항목이 게시되면 **부채 재분류 저널 생성** 열을 사용할 수 있으며 저널 ID도 예약에 입력됩니다.

단기 부채 재분류 저널 항목을 만들고 게시하려면 다음 단계를 따르십시오.

1. **자산 임대 \> 정기 \> 배치 저널 생성** 으로 이동합니다.
2. **배치 저널 생성** 대화 상자의 **예약 선택** 필드에서 **단기 임대 부채 재분류** 를 선택합니다.
3. **임대 그룹** 필드에서 임대 그룹을 선택합니다. 또는 **장부 ID** 필드에서 장부 ID를 선택합니다.
4. **게시** 매개 변수를 켭니다. 또는 항목을 생성하지만 게시하지 않는 경우 이 매개 변수를 사용하지 않도록 설정합니다.
5. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
