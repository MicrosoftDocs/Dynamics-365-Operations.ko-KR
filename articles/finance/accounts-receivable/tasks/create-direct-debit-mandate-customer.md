---
title: 고객에 대한 자동이체 위임장 생성
description: 이 작업 가이드는 자동이체 위임장을 생성하고 송장에 사용하는 방법을 보여줍니다.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51fea2b9a0f25b078abc3ca83ee02c585eaf465128bebba0234ffadb030ef42a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450418"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>고객에 대한 자동이체 위임장 생성

[!include [banner](../../includes/banner.md)]

이 작업 가이드는 자동이체 위임장을 생성하고 송장에 사용하는 방법을 보여줍니다.


## <a name="create-a-bank-account"></a>은행 계좌를 만들기
1. **탐색 창** 에서 **모듈 > 수취 계정 > 고객 > 모든 고객** 으로 이동합니다.
2. 목록에서 레코드를 선택합니다. 예를 들어 US-001을 선택합니다
3. 작업 창에서 **고객** 을 클릭합니다.
4. **은행 계좌** 를 클릭합니다.
5. **새로 만들기** 를 클릭합니다.
6. **은행 계좌** 필드에 값을 입력합니다.
7. **이름** 필드에 값을 입력합니다.
8. **IBAN** 필드에 값을 입력합니다.
9. **통화** 필드에 값을 입력합니다.
10. **저장** 을 클릭합니다.
11. 페이지를 닫습니다.
12. **탐색 창** 에서 **모듈 > 현금 및 은행 관리 > 은행 계좌 > 은행 계좌** 로 이동합니다.
13. 목록에서 원하는 레코드를 찾아 선택합니다.
14. 목록에서 선택한 행의 링크를 클릭합니다.
15. **편집** 을 클릭합니다.
16. **추가 신원 확인** 빠른 탭을 확장합니다.
17. **자동이체 ID** 필드에 값을 입력합니다.
18. **IBAN** 필드에 값을 입력합니다.
19. 페이지를 닫습니다.
20. 페이지를 닫습니다.

## <a name="define-the-electronic-payment-method"></a>전자 지불 방법 정의
1. **탐색 창** 에서 **모듈 > 수취 계정 > 지불 설정 > 지불 방법** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **지불 방법** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **지불 유형** 필드에 '전자 지불'을 입력합니다. 자동이체 위임 지불 방법의 결제 유형은 전자 결제여야 합니다.
6. **위임 필요** 필드에서 예를 선택합니다.
7. 페이지를 닫습니다.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>고객에게 자동이체 위임장을 추가합니다.
1. **탐색 창** 에서 **모듈 > 수취 계정 > 고객 > 모든 고객** 으로 이동합니다.
2. 목록에서 레코드를 선택합니다. 예를 들어 US-001을 선택합니다
3. **편집** 을 클릭합니다.
4. **지불 기본값** 빠른 탭을 확장합니다.
5. **지불 방법** 필드에 값을 입력하거나 선택합니다.
6. **지불 기본값** 빠른 탭을 확장합니다.
7. **자동이체 위임장** 빠른 탭을 확장합니다.
8. **추가** 를 클릭합니다.
9. **은행 계좌** 필드에서 값을 입력하거나 선택합니다.
10. **채권자 은행 계좌** 필드에서 값을 입력하거나 선택합니다.
11. **지불 빈도** 필드에 이 위임에 대해 처리할 것으로 예상되는 지불 횟수를 입력합니다.
12. **확인** 을 클릭합니다.
13. **인쇄** 를 클릭합니다.
14. **위임 보고서** 를 클릭합니다.
15. 페이지를 닫습니다.
16. **편집** 을 클릭합니다.
17. **서명 날짜** 필드에 날짜를 입력합니다.
18. **예** 를 클릭합니다.
19. 위임장에 서명한 위치를 입력합니다.
20. **확인** 을 클릭합니다.
21. 페이지를 닫습니다.

## <a name="create-a-free-text-invoice-with-mandate"></a>위임이 있는 자유 텍스트 송장 만들기
1. **탐색 창** 에서 **모듈 > 수취 계정 > 송장 > 모든 자유 텍스트 송장** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. 위임장을 추가한 고객을 선택합니다.
4. **자동이체 위임장 ID** 필드에 값을 입력하거나 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]