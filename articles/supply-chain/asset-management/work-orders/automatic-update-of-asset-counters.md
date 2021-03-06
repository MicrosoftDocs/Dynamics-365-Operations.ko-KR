---
title: 자산 카운터 자동 업데이트
description: 이 항목에서는 자산 관리의 자산 카운터 자동 업데이트에 대해 설명합니다.
author: johanhoffmann
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a3814a575fbe4379b59723f269d83379a253ede71962c0c82b5f4cc55d36e6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446851"
---
# <a name="automatic-update-of-asset-counters"></a>자산 카운터 자동 업데이트

[!include [banner](../../includes/banner.md)]

자산 카운터의 수동 등록에 대한 자세한 내용은 [자산 카운터의 수동 업데이트](../work-orders/manual-update-of-asset-counters.md)를 참조하세요. 자산 카운터를 설정하는 방법에 대한 정보는 [카운터](../setup-for-objects/counters.md)를 참조하세요.

카운터 값은 생산 시간 또는 생산 수량(즉, 생산된 수량)을 기반으로 생산 등록에서 자동으로 업데이트될 수도 있습니다. 이 업데이트는 **자산 카운터 업데이트** 페이지에서 수행됩니다. **시작 날짜** 매개 변수를 설정하여 하나 이상의 자산을 업데이트할 수 있습니다. 이 매개 변수는 생산 등록 시작 날짜(생산 시간 또는 생산 수량)를 지정합니다. 즉, 카운터 값을 업데이트해야 하는 날짜를 지정합니다.

리소스와 관련된 모든 자산 *및* 생산 시간 또는 생산 수량에 따라 업데이트되도록 설정된 자산 카운터가 있는 모든 자산은 자동 업데이트에 포함됩니다. 새 카운터 값이 생성됩니다.

생산 수량을 기반으로 하는 카운터의 경우 실사에는 등록된 양호 수량과 오류 수량 모두가 포함됩니다. 생산 수량 등록에 사용되는 단위가 카운터에 사용되는 단위와 다른 경우 카운터 단위에 해당하도록 수량을 변환합니다.

위에서 언급했듯이 자동 카운터는 생산 등록에서 업데이트할 수 있습니다. 따라서 카운터를 자동으로 업데이트하려는 자산은 리소스(머신)와 관련되어야 합니다. 생산 수량 또는 생산 시간이 자원에 등록되면 관련 자산 카운터를 업데이트할 수 있습니다.

1. **자산 관리** > **정기** > **자산** > **자산 카운터 업데이트** 를 선택합니다.

2. **시작 날짜** 필드에서 자동 업데이트의 시작 날짜를 선택합니다.

    >[!NOTE]
    >이 필드의 날짜는 **거래 경로 지정**(**생산 관리** > **문의 및 신고** > **생산** > **거래 경로 지정** > **실제 날짜** 필드)의 "진행 중인 작업" 날짜입니다.

3. **포함할 레코드** 빠른 탭에서는 자동 업데이트를 위해 특정 자산, 자산 유형 또는 리소스를 선택할 수 있습니다. **필터** 를 선택하고 관련 항목을 선택합니다.

4. **백그라운드 실행** 빠른 탭에서 필요에 따라 자동 업데이트를 일괄 작업으로 설정할 수 있습니다.

    아래 그림은 **자산 카운터 업데이트** 대화의 예를 보여줍니다.

    ![그림 1.](media/12-work-orders.png)

5. **확인** 을 선택합니다. 

자동 자산 카운터 업데이트가 완료된 후 **자산 카운터** 페이지에서 자산과 관련된 카운터 등록을 볼 수 있습니다. **자산 관리** > **공통** > **자산** > **모든 자산** 을 선택하고 자산을 선택한 다음 작업 창의 **자산** 탭에 있는 **예방** 그룹에서 **카운터** 를 선택합니다.

**자산 집계 가치** 페이지에서 모든 자산의 모든 카운터 유형에 대해 이루어진 최신 등록에 대한 개요를 얻을 수 있습니다. **자산 관리** > **문의** > **자산** > **자산 집계 가치** 를 선택합니다. 이 페이지는 **자산 카운터** 페이지와 유사하지만 등록을 추가하거나 편집할 수 없습니다. 개요용입니다.

아래 그림은 **자산 집계 가치** 페이지의 예를 보여줍니다.

![그림 2.](media/13-work-orders.png)

다음 요점을 확인하세요.

- 자동으로 업데이트되는 카운터 유형에 대해 수동 카운터 값 등록을 계속 생성할 수 있습니다. 자세한 내용은 [자산 카운터의 수동 업데이트](../work-orders/manual-update-of-asset-counters.md)를 참조하세요.

- 다른 카운터와 관련된 카운터를 설정할 수 있습니다. 이 경우 카운터가 업데이트되면 관련 카운터도 동시에 자동으로 업데이트됩니다. 관련 카운터를 설정하는 방법에 대한 정보는 [카운터](../setup-for-objects/counters.md)를 참조하세요.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]