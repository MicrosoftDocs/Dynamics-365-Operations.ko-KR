---
title: 단계 이유 코드 사용
description: 이유 코드를 사용하여 서비스 수준 계약(SLA)이 취소된 이유 또는 서비스 주문이 SLA에 정의된 시간 제한을 초과한 이유를 나타냅니다.
author: kamaybac
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac825fe96ee69491953bd50c758dde42744cea85
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448594"
---
# <a name="use-stage-reason-codes"></a>단계 이유 코드 사용 

[!include [banner](../includes/banner.md)]


이유 코드를 사용하여 서비스 수준 계약(SLA)이 취소된 이유 또는 서비스 주문이 SLA에 정의된 시간 제한을 초과한 이유를 나타냅니다.

SLA가 취소되거나 시간 제한이 서비스 주문에 대한 SLA에 지정된 시간을 초과할 때 이유 코드가 필요하도록 지정할 수도 있습니다.

사유 코드가 필요하다고 지정한 경우 다음 상황에서 사유 코드를 입력해야 합니다.

  - 서비스 주문에 대한 SLA에 대한 시간 기록을 중지하는 단계로 서비스 주문이 이동하는 경우.

  - 서비스 주문이 승인된 경우.

  - 시간 기록이 수동으로 중지된 경우.

## <a name="set-up-reason-codes"></a>사유 코드 설정

1.  **서비스 관리** \> **설정** \> **서비스 주문** \> **스테이지 사유 코드** 를 클릭합니다.

2.  **단계 이유 코드** 양식에서 **새로 만들기** 를 클릭하여 새 이유 코드를 만듭니다.

3.  **단계 이유 코드** 필드에 고유한 단계 이유 코드를 입력합니다.

4.  **설명** 필드에 단계 이유 코드에 대한 설명을 입력합니다.

5.  변경 내용을 저장하려면 양식을 닫으세요.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>서비스 수준 계약이 취소될 때 이유 코드 필요

1.  **서비스 관리** \> **설정** \> **서비스 관리 매개 변수** 를 클릭합니다.

2.  **서비스 관리 매개 변수** 양식에서 **일반** 링크를 클릭한 다음 **취소 시 이유 코드** 확인란을 선택합니다.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>서비스 주문이 서비스 수준 계약에서 설정한 시간 제한을 초과하는 경우 이유 코드 필요

1.  **서비스 관리** \> **설정** \> **서비스 관리 매개 변수** 를 클릭합니다.

2.  **서비스 관리 매개 변수** 양식에서 **일반** 링크를 클릭한 다음 **시간 초과 시 이유 코드** 확인란을 선택합니다.

## <a name="see-also"></a>참고 항목

[서비스 주문에 대한 시간 기록 시작 및 중지](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]