---
title: 예약된 작업 주문에 대한 용량 부하 계산
description: 이 항목에서는 자산 관리에서 예약된 작업 주문의 용량 부하를 계산하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: ff244e51151a1cc0485cae25873566fa97253171516d48449fed75f070146431
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447169"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>예약된 작업 주문에 대한 용량 부하 계산

[!include [banner](../../includes/banner.md)]

 

예약된 작업 주문에 대한 용량 부하를 계산하여 특정 기간 동안 리소스에 대한 작업 부하의 개요를 얻을 수 있습니다. 유지 관리 작업자, 작업자 그룹, 도구 및 자산과 같은 리소스에 대해 계산할 수 있습니다.

1. **자산 관리** > **문의** > **일정** > **용량 부하** 를 클릭합니다.

2. **용량 부하 계산** 대화 > **표시** 필드에서 계산할 하중 유형을 선택합니다. **용량**, **예약됨** 또는 **나머지**.

3. 0이 포함된 결과를 표시하지 않으려면 **0 건너뛰기** 토글 버튼에서 **예** 를 선택합니다.

4. 관련 토글 버튼에서 **예** 를 선택하여 용량 부하를 계산할 리소스 유형을 선택합니다. **작업자**, **유지 관리 작업자 그룹**, **도구** 및 **자산**.

5. **시작 날짜** 필드에서 계산의 시작 날짜를 선택합니다.

6. **간격 유형** 필드에서 계산 간격을 선택합니다. **일**, **주**, **월** 또는 **분기**.

7. **주기 빈도** 필드에 계산하려는 간격 수를 입력합니다. 예를 들어 간격 유형으로 **일** 을 선택하고 이 필드에 숫자 "5"를 입력하면 시작 날짜로부터 5일이 계산됩니다.

8. **확인** 을 클릭하여 비용 계산을 시작합니다.

아래 그림은 **예약됨** 부하 유형에 대해 3주 동안 계산한 결과를 보여줍니다.

![그림 1.](media/08-work-order-scheduling.png)

[!NOTE]
계산에 대해 부하 유형으로 **용량** 또는 **나머지** 를 선택하는 경우 선택한 기간에 리소스에 대한 예약이 없는 경우 동일한 결과가 표시됩니다.

예약된 작업 주문이 아닌 유지 관리 일정 라인의 용량 부하를 계산하는 방법에 대한 자세한 내용은 [용량 부하 계산](../capacity-planning/calculate-capacity-load.md)을 참조하세요.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]