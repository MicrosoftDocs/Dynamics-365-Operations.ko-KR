---
title: 휴가 구매 및 판매
description: 이 항목에서는 Dynamics 365 Human Resources에서 휴가 구매 및 판매 요청을 제출하는 방법을 설명합니다.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ddc50540ba0686f18b6e8875e40f11c378c448f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452359"
---
# <a name="buy-and-sell-leave"></a>휴가 구매 및 판매


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources에서 회사에서 설정한 휴가 구매 및 판매 정책에 따라 휴가 구매 및 판매 요청을 제출할 수 있습니다.  

## <a name="request-to-buy-leave"></a>휴가 구매 요청

1. **직원 셀프 서비스** 작업 영역의 **휴가 잔액** 타일에서 **휴가 구매 요청** 을 선택합니다. 

2. **휴가 유형** 을 추가하고 구매하려는 휴가 **잔액** 을 입력합니다. 

3. 요청을 제출할 준비가 되면 **제출** 을 선택합니다. 

잔액은 자동으로 업데이트되거나 업데이트 전에 승인 프로세스를 거칩니다. 이는 구매 정책이 구성된 방식에 따라 다릅니다.

## <a name="request-to-sell-leave"></a>휴가 판매 요청

1. **직원 셀프 서비스** 작업 영역의 **휴가 잔액** 타일에서 **휴가 판매 요청** 을 선택합니다. 

2. **휴가 유형** 을 추가하고 판매하려는 휴가 **금액** 를 입력합니다. 

3. 요청을 제출할 준비가 되면 **제출** 을 선택합니다.

잔액은 자동으로 업데이트되거나 업데이트 전에 승인 프로세스를 거칩니다. 이는 구매 정책이 구성된 방식에 따라 다릅니다.


## <a name="troubleshooting"></a>문제 해결 

휴가 구매 또는 휴가 판매 요청 워크플로가 실패하면 **EssLeaveBuySellRequestApprover** 권한이 있는 사용자는 모든 휴가 구매 및 판매 요청에 대한 메시지 로그를 검토할 수 있습니다. 이렇게 하려면 **휴가 및 휴직 > 연결 > 휴가 구매 및 판매 요청 > 메시지 로그**(왼쪽 상단)로 이동합니다. **메시지 로그** 는 트랜잭션이 처리된 방식과 관련 워크플로 기록을 사용자에게 보여줍니다.


## <a name="see-also"></a>참고 항목

[휴가 및 휴직 개요](hr-leave-and-absence-overview.md)</br>
[휴가 구매 및 판매 정책 관리](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
