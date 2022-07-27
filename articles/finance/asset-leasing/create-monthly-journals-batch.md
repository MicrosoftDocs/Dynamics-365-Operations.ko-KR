---
title: 월별 분개장 항목 일괄 처리 만들기
description: 이 항목에서는 월별 임대 비용이 기록될 때 효율성을 높이는 데 도움이 되도록 일괄 처리로 분개장 항목을 만드는 방법에 대해 설명합니다.
author: moaamer
ms.date: 08/10/2021
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
ms.openlocfilehash: 22e2892a6866123ecf0e72511bdce19fe12895df
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "8450901"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>월별 분개장 항목 일괄 처리 만들기

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


이 항목에서는 월별 임대 비용이 기록될 때 효율성을 높이는 데 도움이 되도록 일괄 처리로 분개장 항목을 만드는 방법에 대해 설명합니다. 일괄 처리를 사용하여 여러 일정에서 분개 항목을 만들 수 있습니다. 이러한 분개에는 임대 지불, 부채 상각, 사용권(ROU) 자산 상각 및 집행 비용 지출이 포함될 수 있습니다. 일괄 처리를 사용하여 동시에 여러 임대의 초기 인식을 수행하거나 동시에 여러 임대에 대한 전환 조정을 생성할 수도 있습니다.

일괄 작업을 설정하거나 여러 임대에 대한 지불 송장, 감가상각 또는 이자를 처리하려면 **자산 임대 \> 정기 \> 배치 분개장 생성** 으로 이동하십시오. 표시되는 대화 상자에서 분개장을 생성할 일정을 선택할 수 있습니다. 특정 엔터티, 임대 그룹 또는 임대 장부에 대해 일괄 처리 프로세스를 실행해야 하는지 여부도 지정할 수 있습니다.

> [!NOTE]
> 부채 상각 일정, 지불, 감가상각 및 비용과 같은 후속 거래는 해당 임대에 대한 최초 인식이 전기된 후에만 전기됩니다.
>
> 분개장 항목이 생성되지만 **실행** 명령을 선택할 때까지 전기되지 않습니다.

임대 개시일 이외의 날짜에 최초 인식 분개를 전기하려면 **최초 인식 전기일 지정** 을 선택합니다. 올바른 전기 날짜를 지정할 수 있는 **날짜** 필드가 나타납니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
