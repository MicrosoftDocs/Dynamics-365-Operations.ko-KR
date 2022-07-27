---
title: 원장 할당 저널 처리
description: 이 항목에서는 Dynamics 365 Finance에서 할당 요청을 처리하는 방법을 설명합니다.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d37b1a9869cc130786d0e8fde68184e04c881bad1f64c86943174213025db82
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450679"
---
# <a name="process-ledger-allocation-journal"></a>원장 할당 저널 처리

[!include [banner](../../includes/banner.md)]

이 항목에서는 할당 요청을 처리하는 방법을 설명합니다. 프로세스 할당 요청 페이지를 사용하여 총계정원장에 게시하기 전에 검토 및 승인하거나 총계정원장에 직접 게시할 수 있는 할당 저널을 생성합니다. 할당 저널을 만들려면 활성 원장 할당 규칙이 하나 이상 있어야 합니다. 이 작업에는 USMF 데모 회사를 사용합니다.

1. 탐색 창에서 **모듈 > 총계정원장 > 할당 > 할당 요청 처리** 로 이동합니다.
2. **규칙** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다.
3. **현재 날짜** 필드에 날짜를 입력합니다.

    - 원장이 규칙의 데이터 원본인 경우 **현재 날짜** 가 매우 중요합니다. 이 날짜는 할당을 위해 포함할 원장 잔액을 제어합니다.  
    - **제로 소스** 필드에서 **중지** 를 선택합니다. 그러면 할당 프로세스가 중지되고 소스 금액이 0으로 선택되었다는 메시지가 표시됩니다.  

4. **제안 옵션** 필드에서 **제안만** 을 선택합니다. 할당을 총계정원장에 게시하기 전에 할당 저널에서 결과를 검토하고 선택적으로 승인하려면 **제안만** 을 선택합니다.  
5. GL 게시 날짜 필드에 날짜를 입력합니다.
6. **확인** 을 선택합니다.
7. 탐색 창에서 **모듈 > 총계정원장 > 할당 > 할당 저널** 로 이동합니다.
8. **라인** 을 선택합니다.
9. **게시** 를 선택합니다.
10. **게시** 를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]