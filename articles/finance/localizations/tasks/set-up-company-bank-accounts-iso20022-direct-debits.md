---
title: ISO20022 자동 이체를 위한 회사 은행 계좌 설정
description: 이 작업은 고객 지불 파일을 생성하는 데 필요한 회사별 은행 계좌 정보를 설정하는 과정을 안내합니다.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a0f8ac369bb6b9a7a0f21c23aaddab2601ae3f8f37e2427cbb10b5509a7a2f23
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450721"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a>ISO20022 자동 이체를 위한 회사 은행 계좌 설정

[!include [banner](../../includes/banner.md)]

이 작업은 고객 지불 파일을 생성하는 데 필요한 회사별 은행 계좌 정보를 설정하는 과정을 안내합니다. 이 절차에서는 ISO 20022 자동 이체 형식을 예로 사용합니다. 다른 형식에는 회사 ID 또는 정렬 코드와 같은 추가 설정 정보가 필요할 수 있습니다.



이 작업은 데모 데이터 회사 DEMF를 사용하여 작성되었습니다.



이것은 전자 보고 구성을 사용하는 고객 지불 프로세스를 보여주는 5개 절차 중 2번째 절차입니다.


## <a name="set-up-the-iban-and-swift-codes"></a>IBAN 및 SWIFT 코드 설정
1. 현금 및 은행 관리 > 은행 계좌로 이동합니다.
2. 빠른 필터를 사용하여 'DEMF OPER' 값으로 은행 계좌 필드를 필터링합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
    * 예를 들어, 은행 계좌 세부 정보를 열려면 'DEMF OPER'를 클릭합니다.  
4. 편집을 클릭합니다.
5. 추가 ID 섹션을 확장하거나 축소합니다.
6. IBAN 필드에 값을 입력합니다.
    * 예를 들어 'DE89370400440532013000'을 입력합니다.  
7. SWIFT 코드 필드에 값을 입력합니다.
    * 예를 들어 'DEUTDEFF'를 입력합니다.    SWIFT \ BIC는 많은 지불 형식에서 필수는 아니지만 은행 계좌에 등록하는 것이 좋습니다.  
8. 저장을 클릭합니다.

## <a name="set-up-a-bank-account-for-the-legal-entity"></a>법인의 은행 계좌 설정
1. 조직 관리 > 조직 > 법인으로 이동합니다.
2. 편집을 클릭합니다.
3. 은행 계좌 정보 섹션을 확장하거나 축소합니다.
4. 은행 계정 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
    * 예를 들어 "DEMF OPER" 은행 계좌를 선택합니다.  
6. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]