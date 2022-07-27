---
title: ISO20022 자동 이체를 위한 고객 및 고객 은행 계좌 설정
description: 이 작업은 ISO20022 자동 이체와 같은 고객 지불 파일을 생성하는 데 필요한 고객 은행 계좌 및 고객 자동 이체 위임장을 설정하는 과정을 안내합니다.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595e89faa1e24ca937d399994e15ce53e3f5308b1c6fd7f43e4e831e70c15ad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450352"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>ISO20022 자동 이체를 위한 고객 및 고객 은행 계좌 설정

[!include [banner](../../includes/banner.md)]

이 작업은 ISO20022 자동 이체와 같은 고객 지불 파일을 생성하는 데 필요한 고객 은행 계좌 및 고객 자동 이체 위임장을 설정하는 과정을 안내합니다. 설정된 고객 지불 형식에 따라 이 절차에서 다루지 않은 추가 정보가 고객 또는 고객 은행 계좌에 필요할 수 있습니다. 

이 작업은 법인 기본 주소가 독일인 데모 데이터 회사 DEMF를 사용하여 생성되었습니다.



이것은 전자 보고 구성을 사용하는 고객 지불 프로세스를 보여주는 5개 절차 중 4번째 절차입니다.


## <a name="set-up-a-customer-bank-account"></a>고객 은행 계좌 설정
1. 수취 계정 > 고객 > 모든 고객으로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 'DE-010'인 계정 필드를 필터링합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 작업 창에서 고객을 클릭합니다.
5. 은행 계좌를 클릭합니다.
6. 새로 만들기를 클릭합니다.
7. 은행 계좌 필드에 값을 입력합니다.
8. 이름 필드에 값을 입력합니다.
    * 예를 들어 'EUR bank'를 입력합니다.  
9. 은행 그룹 필드에 값을 입력하거나 선택합니다.
10. IBAN 필드에 값을 입력합니다.
    * 예를 들어 'DE36200400000628808808'을 입력합니다.  
11. SWIFT 코드 필드에 값을 입력합니다.
    * 예를 들어 'COBADEFFXXX'를 입력합니다.  SWIFT \ BIC는 많은 지불 형식에서 필수는 아니지만 은행 계좌에 등록하는 것이 좋습니다.  
12. 저장을 클릭합니다.
13. 페이지를 닫습니다.
14. 편집을 클릭합니다.
15. 지불 기본 섹션을 확장합니다.
16. 은행 계좌 필드에서 값을 입력하거나 선택합니다.

## <a name="add-a-direct-debit-mandate"></a>자동 이체 위임장 추가
1. 자동 이체 위임장 섹션을 확장합니다.
2. 추가를 클릭합니다.
3. 채권자 은행 계좌 필드에서 값을 입력하거나 선택합니다.
    * 예를 들어 DEMF OPER을 선택합니다.  
4. 서명 날짜 필드에 날짜를 입력합니다.
5. 예를 클릭하여 날짜 업데이트를 확인합니다.
6. 서명 위치 필드에 값을 입력하거나 선택합니다.
7. 예상 지불 횟수 필드에 숫자를 입력합니다.
8. 확인을 클릭합니다.
9. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]