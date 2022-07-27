---
title: 특정 날짜 및 시간에 작업 주문 예약
description: 이 토픽에서는 자산 관리에서 특정 날짜 및 시간에 작업 주문을 예약하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/19/2019
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
ms.openlocfilehash: d1264ea034789c9ce052b1da9a74a10dd910fac1a1c762d29bd06ca2063478d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447322"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>특정 날짜 및 시간에 작업 주문 예약

[!include [banner](../../includes/banner.md)]

 

작업 주문을 특정 날짜 *및* 시간에 예약해야 하는 경우 자산 관리의 표준 예약 프로세스를 재정의하고 작업 주문에 대한 특정 일정을 생성할 수 있습니다.

1. **자산 관리** > **공통** > **작업 주문** > **모든 작업 주문** 또는 **활성 작업 주문** 을 클릭합니다.

2. 작업 주문 목록에서 **작업 주문** 열의 작업 주문 ID를 클릭합니다.

3. **편집** 을 클릭합니다.

4. **작업 주문 헤더** 빠른 탭에서 **예상 시작** 및 **예상 종료** 필드에 시작 및 종료 날짜와 시간을 삽입합니다.

    ![그림 1.](media/05-work-order-scheduling.png)

5. **일반** 탭에서 **일정** 을 클릭하여 표준 일정 프로세스를 사용하거나 **디스패치** 를 클릭하여 특정 작업자에게 작업 주문을 할당합니다.

6. 작업 주문이 예상 기간에 예약되도록 기존 용량 예약을 무시하려면 **작업 주문 예약** 대화 상자 > **유한 용량** 섹션에서 아래 그림과 같이 선택합니다. 즉, 작업 주문은 예상 시작 시간에 시작해야 하므로 예약 프로세스는 기존 용량 예약을 무시합니다.

    ![그림 2.](media/06-work-order-scheduling.png)

7. **확인** 을 클릭하여 예약을 시작합니다.

8. 예약 프로세스로 인해 이중 예약이 발생하면 화면에 메시지가 표시되고 관련 작업 주문을 조정할 수 있습니다.

>[!NOTE]
>작업 주문에 대해 유지 관리 작업자를 예약하려면 해당 유지 관리 작업자가 예상 시작 날짜 및 시간에 사용할 수 있어야 합니다. 작업자 가용성은 [작업자 캘린더](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md)에서 설정됩니다. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]