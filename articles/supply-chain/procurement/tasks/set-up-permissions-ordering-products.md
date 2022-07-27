---
title: 다른 사람을 대신하여 제품을 주문할 수 있는 권한 설정
description: 이 토픽에서는 작업자에게 다른 작업자를 대신하여 구매 요청을 준비할 수 있는 권한을 부여하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a29b7ebece8009f29f4313b380889635a87473b5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448975"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>다른 사람을 대신하여 제품을 주문할 수 있는 권한 설정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 작업자에게 다른 작업자를 대신하여 구매 요청을 준비할 수 있는 권한을 부여하는 방법에 대해 설명합니다. 즉, 구매 요청 "준비자"는 다른 "요청자"에 대한 구매 요청을 생성할 수 있습니다. 이 절차는 또한 다른 법인 또는 운영 단위에서 항목 및 서비스를 주문할 수 있는 권한을 작업자에게 부여하는 방법을 보여줍니다. 일반적으로 이러한 작업은 구매 관리자가 수행합니다. USMF 데모 회사의 데이터 또는 자체 데이터에 대해 이 절차를 사용할 수 있습니다.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>다른 작업자를 대신하여 구매 요청을 입력할 수 있는 권한 부여
1. 탐색 창에서 **모듈 > 조달 및 소싱 > 설정 > 정책 > 구매 요청 권한** 으로 이동합니다. **현재 보기** 필드가 **준비자** 기준으로 설정되어 있는지 확인하세요. 왼쪽 창의 목록은 다른 사람을 대신하여 요청을 준비할 수 있는 권한을 부여받을 수 있는 사람을 보여줍니다.  
2. (준비자에게) 권한을 부여할 사람을 선택합니다.
3. **추가** 를 선택합니다.
4. 요청자로 추가할 사람을 찾아 선택합니다.
    - 요청자는 작성자가 대신하여 요청을 생성할 수 있는 사람입니다.  
    - 작성자가 선택한 작업자를 대신하여 구매 요청을 생성할 수 있어야 하는 경우 **승인** 필드에서 **특정** 을 선택합니다. 준비자가 해당 작업자에게 보고하는 모든 작업자를 대신하여 구매 요청을 생성할 수도 있어야 하는 경우 **보고** 를 선택합니다.  
5. **적용** 필드에 날짜를 입력합니다.
6. **만료** 필드에 날짜를 입력합니다.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>선택한 작업자에 대한 구매 요청을 생성할 수 있는 권한이 있는 준비자 보기
1. **현재 보기** 필드에서 **요청자별** 을 선택합니다. 이 보기는 선택한 작업자를 대신하여 구매 요청을 생성할 수 있는 권한이 부여된 준비자 목록을 보여줍니다.  
2. 빠른 필터를 사용하여 방금 요청자로 추가한 작업자를 찾습니다.
3. 요청자를 선택합니다. 준비자 목록에는 왼쪽 창에서 선택한 요청자를 대신하여 항목을 주문할 수 있는 권한이 있는 사람이 표시됩니다.  여기에서 준비자를 추가할 수 있습니다. 또한 이 보기를 통해 요청자에게 해당 개인의 기본 법인 또는 운영 단위가 아닌 법인 및 운영 단위에서 구매 요청을 생성할 수 있는 권한을 부여할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]