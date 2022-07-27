---
title: 수입화물선취보증서 거래
description: 이 절차는 수입화물선취보증서 프로세스를 안내합니다.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 206050a2c60eaeff4776b534e3f366c6998f1756bf2734461fc10b9b83f4539a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450454"
---
# <a name="letter-of-guarantee-transaction"></a>수입화물선취보증서 거래

[!include [banner](../../includes/banner.md)]

이 절차는 수입화물선취보증서 프로세스를 안내합니다.



이 절차를 완료하기 전에 다음 작업을 완료해야 합니다.

- 수입화물선취보증서에 대한 은행 시설 및 게시 프로필을 설정합니다.

- 수입화물선취보증서에 대한 은행 시설 계약을 작성합니다.



이 절차는 USMF 데모 회사를 사용합니다.


## <a name="create-sales-order-with-letter-of-guarantee"></a>수입화물선취보증서로 판매 주문 만들기
1. 수령 가능한 계정 > 주문 > 모든 판매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 고객 계정 필드에서 값을 입력하거나 선택합니다.
4. 일반 섹션을 확장합니다.
5. 사이트 필드에 값을 입력하거나 선택합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 창고 필드 필드에 값을 입력하거나 선택합니다.
8. 목록에서 선택한 행의 링크를 클릭합니다.
9. 은행 문서 유형 필드에서 '수입화물선취보증서'를 선택합니다.
10. 확인을 클릭합니다.
11. 항목 번호 필드에서 값을 입력하거나 선택합니다.
12. 단가 필드에 숫자를 입력합니다.
13. 라인 세부 정보 섹션을 확장합니다.
14. 배송 탭을 클릭합니다.
    * 참고: 배송 날짜 제어 = 없음을 선택합니다  
15. 요청받은 배송 날짜 필드에 날짜를 입력합니다.
16. 확인된 배송 날짜 필드에 날짜를 입력합니다.

## <a name="process-letter-of-guarantee_request"></a>수입화물선취보증서 요청 처리
1. 작업 창에서 관리를 클릭합니다.
2. 수입화물선취보증서를 클릭합니다.
3. 작업 창에서 수입화물선취보증서를 클릭합니다.
4. 요청을 클릭하여 드롭 대화 상자를 엽니다.
5. 유형 필드에서 값을 입력하거나 선택합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. 값 필드에 숫자를 입력합니다.
8. 만료 날짜 필드에 날짜와 시간을 입력합니다.
9. 확인을 클릭합니다.
10. 페이지를 닫습니다.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>은행에 수입화물선취보증서 제출 처리
1. 현금 및 은행 관리 > 수입화물선취보증서 > 수입화물선취보증서로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 은행에 제출을 클릭하여 드롭 대화 상자를 엽니다.
4. 은행 계좌 필드에서 값을 입력하거나 선택합니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. 확인을 클릭합니다.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>은행에서 수입화물선취보증서 받기 처리
1. 은행에서 받기를 클릭하여 드롭 대화 상자를 엽니다.
2. 은행 번호 필드에 값을 입력합니다.
    * 계산된 마진 및 비용 필드의 값을 확인합니다.  
3. 확인을 클릭합니다.
4. 작업 섹션을 확장합니다.
    * '은행에서 받기' 기록을 확인합니다.  
5. 분개장 일괄 처리 번호 필드에 있는 링크를 따라가려면 클릭합니다.
6. 라인을 클릭합니다.
    * 분개장 항목을 확인합니다.  
7. 페이지를 닫습니다.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>수취인에게 수입화물선취보증서 제공 처리
1. 수령 가능한 계정 > 주문 > 모든 판매 주문으로 이동합니다.
2. 목록에서 선택한 행의 링크를 클릭합니다.
3. 작업 창에서 관리를 클릭합니다.
4. 수입화물선취보증서를 클릭합니다.
5. 작업 창에서 수입화물선취보증서를 클릭합니다.
6. 수취자에게 제공을 클릭하여 드롭 대화 상자를 엽니다.
7. 확인을 클릭합니다.
8. 현금 및 은행 관리 > 수입화물선취보증서 > 수입화물선취보증서로 이동합니다.
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. 수취자에게 제공을 클릭하여 드롭 대화 상자를 엽니다.
11. 확인을 클릭합니다.
12. 작업 섹션을 확장합니다.
    * '수취인에게 제공' 기록을 확인합니다.  

## <a name="process-letter-of-guarantee_increase-value"></a>수입화물선취보증서 가치 증가 처리
1. 수령 가능한 계정 > 주문 > 모든 판매 주문으로 이동합니다.
2. 목록에서 선택한 행의 링크를 클릭합니다.
3. 작업 창에서 관리를 클릭합니다.
4. 수입화물선취보증서를 클릭합니다.
5. 작업 창에서 수입화물선취보증서를 클릭합니다.
6. 가치 증가를 클릭하여 드롭 대화 상자를 엽니다.
7. 값 추가 필드에 숫자를 입력합니다.
8. 확인을 클릭합니다.
9. 현금 및 은행 관리 > 수입화물선취보증서 > 수입화물선취보증서로 이동합니다.
10. 목록에서 원하는 레코드를 찾아 선택합니다.
11. 가치 증가를 클릭하여 드롭 대화 상자를 엽니다.
12. 확인을 클릭합니다.
13. 작업 섹션을 확장합니다.
    * '값 증가' 기록을 확인합니다.  
14. 목록에서 원하는 레코드를 찾아 선택합니다.
15. 분개장 일괄 처리 번호 필드에 있는 링크를 따라가려면 클릭합니다.
16. 라인을 클릭합니다.
    * 게시된 분개장 항목을 확인합니다.  

## <a name="process-letter-of-guarantee_liquidate"></a>수입화물선취보증서 청산 처리
1. 수령 가능한 계정 > 주문 > 모든 판매 주문으로 이동합니다.
2. 목록에서 선택한 행의 링크를 클릭합니다.
3. 작업 창에서 관리를 클릭합니다.
4. 수입화물선취보증서를 클릭합니다.
5. 작업 창에서 수입화물선취보증서를 클릭합니다.
6. 청산을 클릭하여 드롭 대화 상자를 엽니다.
7. 확인을 클릭합니다.
8. 현금 및 은행 관리 > 수입화물선취보증서 > 수입화물선취보증서로 이동합니다.
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. 청산을 클릭하여 드롭 대화 상자를 엽니다.
11. 확인을 클릭합니다.
12. 작업 섹션을 확장합니다.
    * '청산' 기록을 확인합니다.  
13. 목록에서 원하는 레코드를 찾아 선택합니다.
14. 분개장 일괄 처리 번호 필드에 있는 링크를 따라가려면 클릭합니다.
15. 라인을 클릭합니다.
    * 게시된 분개장 항목을 확인합니다.  
16. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]