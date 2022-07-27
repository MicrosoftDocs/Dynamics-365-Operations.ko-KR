---
title: 공급업체에 대한 후일 수표 정산
description: 은행이 수표가 연체되고 은행이 수표로 결제한 후 수표 트랜잭션을 청산할 때 공급업체에게 발행된 기한이 지난 수표를 정산합니다.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b7755c3c3d092692dde6582a8d4ba74f00b10a95ba82a2782e3dad34d28e7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450277"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>공급업체에 대한 후일 수표 정산

[!include [banner](../../includes/banner.md)]

은행이 수표가 연체되고 은행이 수표로 결제한 후 수표 트랜잭션을 청산할 때 공급업체에게 발행된 기한이 지난 수표를 정산합니다. 

이 절차를 시작하기 전에 다음 절차를 완료하십시오.

1) 후일 수표 설정

2) 공급업체에 대한 소급 수표 등록 및 게시



이 절차의 역할은 재무입니다. 이 절차는 USMF 데모 회사를 사용합니다.

1. 지급 계정 > 결제 > 공급업체 후일 수표로 이동합니다.
2. 정산을 클릭합니다.
3. 정산을 클릭하여 항목을 지웁니다.
    * 수표 거래에 대한 공급업체 계정을 정산합니다.  
4. 페이지를 닫습니다
5. 총계정원장 > 분개장 항목 > 일반 분개장으로 이동합니다.
6. 표시 필드에서 '모두'를 선택합니다.
7. 사용자가 만든 것만 표시 확인란을 선택하거나 선택 취소합니다.
8. 목록에서 선택한 행을 표시합니다.
9. 라인을 클릭합니다.
10. 바우처를 클릭합니다.
11. 페이지를 닫습니다



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]