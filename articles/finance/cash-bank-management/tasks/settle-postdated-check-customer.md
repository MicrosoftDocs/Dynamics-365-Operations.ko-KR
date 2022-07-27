---
title: 고객의 후일 수표 정산
description: 은행에서 수표를 정산한 후에 기한이 지난 수표를 결제할 수 있습니다.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab591fc3ac529e65c15ee083377954a83363edd528861aff9bc449bfc10c7735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450772"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>고객의 후일 수표 정산

[!include [banner](../../includes/banner.md)]

은행에서 수표를 정산한 후에 기한이 지난 수표를 결제할 수 있습니다. 이 금융 트랜잭션은 또한 날짜가 지난 수표에 대한 브리지 계정 트랜잭션도 지웁니다. 

이 작업을 시작하기 전에 다음을 완료해야 합니다.

1) 후일 수표 설정

2) 고객에 대한 소급 수표 등록 및 게시 



이 작업 가이드의 역할은 재무입니다.



이 절차는 USMF 데모 회사를 사용합니다.

1. 크레딧 및 수금 > 조회 및 보고서 > 결제 > 고객 기한이 지난 수표로 이동합니다.
2. 정산을 클릭합니다.
3. 정산을 클릭하여 항목을 지웁니다.
    * 수표 거래에 대한 고객 계정을 정산합니다.  
4. 페이지를 닫습니다
5. 총계정원장 > 분개장 항목 > 일반 분개장으로 이동합니다.
6. 표시 필드에서 옵션을 선택합니다.
7. 사용자가 만든 것만 표시 확인란을 선택하거나 선택 취소합니다.
8. 목록에서 원하는 레코드를 찾아 선택합니다.
9. 라인을 클릭합니다.
10. 바우처를 클릭합니다.
11. 페이지를 닫습니다



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]