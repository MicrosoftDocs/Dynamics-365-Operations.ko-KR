---
title: 고객 지불 조건 설정
description: 이 절차는 현금 할인 및 기한 설정을 정의합니다.
author: aprilolson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12c26cfedca3f3b0eec1a3b068184522f87ff8d103a41b81a0775bf5a35d0e03
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450694"
---
# <a name="establish-customer-payment-terms"></a>고객 지불 조건 설정

[!include [banner](../../includes/banner.md)]

이 절차는 현금 할인 및 기한 설정을 정의합니다. 이 작업에는 USMF 데모 회사를 사용합니다.

1. **탐색 창 > 모듈 > 수취 계정 > 결제 > 지불 설정 > 지불일** 로 이동합니다. **지불 조건** 설정은 **수취 계정** 및 **지급 계정** 에 대해 공유됩니다. 모듈에서 정의하면 다른 모듈에서도 사용할 수 있습니다. 이 작업 가이드의 경우 **수취 계정** 아래의 모든 지불 조건을 설정합니다.
2. **새로 만들기** 를 클릭합니다. 지불 조건에 특정 요일(월요일, 화요일 등) 또는 특정 날짜(5일, 10일 등)가 필요한 경우 지불일을 지정합니다. 
3. **지불일** 필드에 ID를 입력합니다.
4. **설명** 필드에 지불일에 대한 설명을 입력합니다.
5. **주/월** 필드에 '주' 또는 '월'을 선택합니다. 요일(예: 월요일)을 입력하려면 주를 선택합니다. 해당 월의 날짜(예: 10일)를 입력하려면 월을 선택합니다. 이 예에서는 월을 선택합니다. 
6. **날짜** 필드에 날짜를 입력합니다. 날짜는 '10일'이 아닌 '10'과 같은 숫자로 입력해야 합니다. 
7. **저장** 을 클릭합니다.
8. 페이지를 닫습니다.
9. **탐색 창 > 모듈 > 수취 계정 > 결제 > 지불 설정 > 지불 조건** 으로 이동합니다.
10. **새로 만들기** 를 클릭합니다. 지불 조건은 기한을 계산하는 방법을 정의합니다. 현금 할인일 설정은 별도의 페이지에서 정의됩니다. 
11. **지불 조건 필드** 에 ID를 입력합니다.
12. **설명** 필드에 설명을 입력합니다.
13. COD, 순 기간, 이번 달 등과 같은 **지불 방법** 을 선택합니다. 지불 방법은 지불액을 계산하는 방법의 시작을 정의하는 데 사용됩니다. 예를 들어 기한이 항상 송장 날짜 이후의 설정된 개월 또는 일수인 경우 순 기간이 사용됩니다. COD는 송장 지불이 필요할 때 사용할 수 있기 때문에 기한이 계산되지 않습니다. 이 작업 가이드에서는 '이번 달'을 선택합니다.  
14. 계산에 특정 요일이나 날짜가 포함된 경우 **지불일** 을 선택합니다. 지불 조건에 따라 월 또는 일 단위로 수량을 입력할 수 있습니다. 또는 **지불 일정** 이나 **결제일** 을 사용하여 지불 방법의 끝에 '추가'할 수 있습니다. 기한이 항상 다음 달 10일인 경우 **지급일** 10일을 선택합니다. 
15. **저장** 을 클릭합니다.
16. 페이지를 닫습니다.
17. **수취 계정 > 지불 설정 > 현금 할인** 으로 이동합니다.
18. **새로 만들기** 를 클릭합니다. 이 페이지는 현금 할인 날짜를 계산하는 방법을 정의하는 데 사용됩니다. 
19. **현금 할인** 필드에 ID를 입력합니다.
20. **설명** 필드에 설명을 입력합니다.
21. 단계적 현금 할인이 제공되는 경우 이 새로운 현금 할인 다음의 해당하는 **다음 할인 코드** 를 선택합니다.
22. **일** 필드에 현금 할인 날짜를 계산하는 데 사용된 일수를 입력합니다. **순 기간** 원칙을 선택한 경우 일수가 송장 날짜에 추가되어 현금 할인 날짜가 계산됩니다.  
23. **할인율** 필드에 현금 할인율을 입력합니다.
24. **고객 할인을 위한 주 계정** 에 고객 송장에 대해 현금 할인이 게시될 주 계정을 입력합니다.
25. **할인 상쇄 계정** 필드에서 옵션을 선택합니다. '송장 라인의 계정'을 선택하면 현금 할인이 공급업체 송장 라인의 동일한 자산/비용 주 계정에 게시됩니다. '공급업체 송장에 주 계정 사용'을 선택하면 현금 할인이 '공급업체 송장의 주 계정'에서 정의한 주 계정에 게시됩니다. 이 예에서는 '공급업체 송장에 주 계정 사용'을 선택합니다. 
26. **공급업체 할인을 위한 주 계정** 필드에 공급업체 송장에 대해 현금 할인이 게시될 주 계정을 입력합니다.
27. **저장** 을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]