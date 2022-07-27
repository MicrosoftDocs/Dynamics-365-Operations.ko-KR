---
title: 자동 이체 위임장이 있는 고객을 위한 지불 만들기
description: 이 절차는 자동이체가 구성되어 있고 지불할 송장이 있는 고객을 위해 ISO20022 자동이체 지불 파일을 생성하는 방법을 보여줍니다.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ecc28cb11b8c34a438bb47b1cfa9a37e17297e421020b32030261af95b86a49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450601"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>자동 이체 위임장이 있는 고객을 위한 지불 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 자동이체가 구성되어 있고 지불할 송장이 있는 고객을 위해 ISO20022 자동이체 지불 파일을 생성하는 방법을 보여줍니다. 송장 생성 및 전기는 선택 사항입니다. 송장을 지불받는 대신 지불 파일을 생성하기 전에 분개장에서 위임장을 선택하여 고객 선지급 시나리오를 지원할 수 있습니다.



이 절차를 만드는 데 사용된 데모 데이터 회사는 DEMF입니다.



이것은 전자 보고 구성을 사용하는 고객 지불 프로세스를 보여주는 5가지 절차 중 다섯 번째 절차입니다. 이 작업을 완료하기 전에 이전 작업을 완료해야 합니다. 먼저 고객 지불 전자 보고 구성을 가져와서 지불 방법을 구성하고 회사 및 고객 정보를 설정해야 합니다. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>자동이체 정보가 포함된 자유 텍스트 송장 전기
1. 수취 계정 > 송장 > 모든 무료 텍스트 송장으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 고객 계정 필드에서 값을 입력하거나 선택합니다.
    * 예를 들어 DE-010을 선택합니다  
4. 지불 방법 필드에 값을 입력하거나 선택합니다.
    * 예: 전자를 선택합니다.  
5. 자동이체 위임장 ID 필드에 값을 입력하거나 선택합니다.
6. 라인 추가를 클릭합니다.
7. 설명 필드에 값을 입력합니다.
8. 주 계정 필드에서 원하는 값을 지정합니다.
9. 단가 필드에 숫자를 입력합니다.
10. 게시를 클릭합니다.
11. '확인'을 클릭합니다.

## <a name="create-a-payment"></a>지불 만들기
1. 수취 계정 > 지불 > 지불 분개장으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력하거나 선택합니다.
4. 라인을 클릭합니다.
5. 지불 제안을 클릭합니다.
6. 지불 제안 생성을 클릭합니다.
7. 포함할 레코드 섹션을 펼칩니다.
8. 필터를 클릭합니다.
9. 목록에서 고객 거래 테이블의 행과 지불 방법 필드를 선택합니다.
    * 지불할 고객 거래를 선택하는 기준을 적용할 수 있습니다. 이 예에서는 전자를 지불 방법으로 사용하여 거래를 필터링합니다.  
10. 기준 필드에서 값을 입력하거나 선택합니다.
11. '확인'을 클릭합니다.
12. '확인'을 클릭합니다.
13. 지불 생성을 클릭합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]