---
title: 유지 관리 일정 비용
description: 이 토픽에서는 자산 관리의 유지 관리 일정 비용에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 267452bf5ec8cafebb5927045e8708a41603ec16f48626b7fd351d13fdb2fab7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446947"
---
# <a name="maintenance-schedule-cost"></a>유지 관리 일정 비용

[!include [banner](../../includes/banner.md)]

 

자산 관리에서 유지 관리 일정 라인에 대한 예산 비용을 계산할 수 있습니다. 이것은 예상 비용의 개요를 얻으려는 경우에 유용합니다(예: 다음 해에 계획된 예방 유지 관리 작업과 관련된 비용). 계산은 "유지 관리 계획" 및 "유지 관리 라운드" 및 "유지 관리 요청" 유형의 기존 유지 관리 일정 라인을 기반으로 합니다.

1. **자산 관리** > **문의** > **자산** > **유지 관리 일정 비용** 을 클릭합니다.

2. **유지 관리 일정 비용** 대화 상자에서 재무 차원으로 그룹화된 비용을 보려면 **재무 차원 집합** 을 선택할 수 있습니다.

>[!NOTE]
>재무 차원 집합은 **총계정원장** >  **회계 계통도** >  **차원** >  **재무 차원 집합** 에서 설정됩니다.

3. **수준** 필드를 사용하여 기능 위치와 관련하여 유지 관리 일정 라인이 얼마나 상세하게 표시되기를 원하는지 나타낼 수 있습니다. 예를 들어, 필드에 숫자 "1"을 삽입하고 다중 레벨 기능 위치 구조가 있는 경우 기능 위치에 대한 모든 유지 관리 일정 라인이 최상위 레벨에 표시되므로 라인의 시간은 다음과 같이 표시될 수 있으며, 하위 수준에 위치한 기능적 위치에서 추가됩니다. **레벨** 필드에 숫자 "0"을 입력하면 관련된 모든 기능적 위치 수준의 모든 유지 관리 일정 라인을 보여주는 자세한 결과를 볼 수 있습니다.

4. 특정 자산에 대한 계산을 수행하려면 **포함할 레코드** 빠른 탭에서 **필터** 를 클릭하고 관련 자산을 선택합니다. 필요한 경우 비용 계산에 대한 **예상 시작** 날짜를 지정하거나 비용 계산에 대해 다른 **상태** 를 선택할 수도 있습니다.

5. **확인** 을 클릭하여 비용 계산을 시작합니다.

6. **유지 관리 일정 비용** 탭 > **그룹화 기준...** 작업 창 그룹에서 관련 단추를 클릭하여 비용 계산에 필요한 세부 수준을 표시합니다. 선택한 작업 창 그룹 단추가 강조 표시됩니다. 단추를 클릭하여 활성화하거나 비활성화합니다.

7. 비용을 새로 계산하려면 **비용 계산** 단추를 클릭합니다.

아래 그림은 유지 관리 일정 비용 계산 결과를 보여줍니다.

![자료 1.](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]