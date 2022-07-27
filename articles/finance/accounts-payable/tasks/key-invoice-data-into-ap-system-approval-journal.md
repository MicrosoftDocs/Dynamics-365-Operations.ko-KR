---
title: 승인 분개장을 사용하여 지급 계정으로 송장 데이터 입력
description: 이 항목에서는 송장 등록을 사용하여 송장을 생성한 다음 승인 분개장을 사용하여 경비 계정을 업데이트하는 방법을 설명합니다.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ce66a4b92f26bcec0849accad3878aef2b2f658
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451537"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>승인 분개장을 사용하여 지급 계정으로 송장 데이터 입력

[!include [banner](../../includes/banner.md)]

이 항목에서는 송장 등록을 사용하여 송장을 생성한 다음 승인 분개장을 사용하여 경비 계정을 업데이트하는 방법을 설명합니다.

## <a name="create-and-post-and-invoice"></a>송장 만들기 및 게시
1. 탐색 창에서 **모듈 > 지급 계정 > 송장 > 송장 등록** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 사용하려는 송장 레지스터의 이름을 선택합니다.
4. **라인** 을 선택하여 레지스터를 열고 경비 라인을 입력합니다.
5. 공급업체를 선택합니다. 예를 들어 `US-104`를 입력하거나 선택합니다.
6. **송장** 필드에 값을 입력합니다.
7. **설명** 필드에 값을 입력합니다.
8. **대변** 필드에 숫자를 입력합니다.
9. **승인자** 필드의 드롭다운 메뉴에서 승인자를 선택합니다.
10. **게시** 를 선택합니다.

## <a name="approve-an-invoice"></a>송장 승인
1. 탐색 창에서 **모듈 > 지급 계정 > 송장 > 송장 승인** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 사용하려는 송장 승인 분개장의 이름을 선택합니다.
4. **라인** 을 선택하면 승인할 송장을 선택할 수 있는 페이지가 표시됩니다.
5. **전표 찾기** 를 선택하여 승인 준비가 된 모든 송장을 표시합니다.
6. 생성한 송장을 표시한 다음 **선택** 을 클릭합니다. 위에서 선택한 전표는 선택 후 이 목록으로 이동됩니다.  
7. **확인** 을 선택합니다.
8. **계정 번호** 필드를 선택하여 송장에 경비 계정을 추가합니다.
9. 계정 번호를 입력하고 탭을 눌러 필드 밖으로 나옵니다. 예를 들어 `600120`을 입력합니다.
10. **게시** 를 선택합니다.
11. 게시된 항목을 보려면 **전표** 를 선택합니다. 승인 보류 중인 송장 계정이 취소되고 실제 경비 계정으로 대체됩니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
