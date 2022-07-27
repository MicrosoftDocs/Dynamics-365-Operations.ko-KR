---
title: 파견 작업 주문
description: 이 토픽에서는 자산 관리에서 작업 주문을 발송하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 87f67f4db143fabbfae926e30e7e5d97ac6af0f6fa5469218e4ab3605aa44dcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447301"
---
# <a name="dispatch-work-order"></a>파견 작업 주문

[!include [banner](../../includes/banner.md)]

 

**파견** 기능을 사용하여 한 작업자에게 하나의 작업 주문 또는 작업 주문 작업을 예약할 수 있습니다.

1. **자산 관리** > **공통** > **작업 주문** > **모든 작업 주문** 또는 **활성 작업 주문** 을 클릭합니다.

2. 목록에서 작업 주문을 선택합니다.

3. **일반** 탭에서 **파견** 을 클릭합니다.

4. **작업 주문 예약** 대화 상자의 작업자 필드에서 **작업자** 를 선택합니다.

5. 예상 근무 시간이 예상 근무 시간과 다를 경우 **일정 시간** 필드에 예상 근무 시간을 입력할 수 있습니다.

6. **예약된 시작** 필드에서 필요한 경우 시작 날짜와 시간을 편집할 수 있습니다.

7. 예약 프로세스가 다른 작업에 이미 예액된 리소스에 대한 용량 제한을 준수해야 하는 경우 **자산**, **도구** 및 **작업자** 토글 단추가 **예** 로 설정되어 있는지 확인하세요. 일정 프로세스에 대한 자세한 정보를 보려는 경우 **Verbose** 토글 단추에서 **예** 를 선택하세요. 즉, 작업 주문에서 계산된 점수에 대한 자세한 정보가 정보 기록에 표시됩니다.

8. **일정 무시** 토글 단추에서 **예** 를 선택하여 달력에서 휴무일을 무시합니다(자산, 작업자 및 도구에 적용됨). 예약과 관련하여 작업 주문에서 선택되었을 수 있는 제한을 무시하려면 **예약 실행 무시** 토글 단추에서 **예** 를 선택합니다. 

    예약된 실행 설정에 대한 자세한 내용은 [예약된 실행](../setup-for-work-orders/scheduled-execution.md) 섹션을 참조하세요.

9. **확인** 을 클릭합니다. 작업 주문 수명 주기 상태는 **자산 관리** > **설정** > **작업 주문** > **수명 주기 모델** 에 지정된 **예약됨** 수명 주기 상태로 자동 업데이트됩니다.

아래 그림은 **작업 주문 예약** 대화 상자에서 디스패치 선택의 예를 보여줍니다.

![자료 1.](media/04-work-order-scheduling.png)

[!NOTE]
작업 주문의 일정을 삭제하려면 **모든 작업 주문** 에서 작업 주문을 선택한 다음 **일반** 탭에서 **일정 삭제** 를 클릭합니다. 일정을 삭제하는 경우 작업 주문 수명 주기 상태를 수동으로 업데이트해야 합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]