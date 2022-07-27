---
title: ISO20022 계좌 이체를 위한 회사 은행 계좌 설정
description: 이 절차는 지불 파일 생성에 필요한 회사별 은행 계좌 정보를 설정하는 방법을 보여줍니다.
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
ms.openlocfilehash: a3b3b5ce9d7e24b2b7d3f76e4d770968df897b546df507ba9e3bde5aeac91715
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450883"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a>ISO20022 계좌 이체를 위한 회사 은행 계좌 설정

[!include [banner](../../includes/banner.md)]

이 절차는 지불 파일 생성에 필요한 회사별 은행 계좌 정보를 설정하는 방법을 보여줍니다. ISO 20022 계좌 이체 형식을 생성하는 데 필요한 정보를 설정했지만 형식에 따라 회사 ID 또는 정렬 코드와 같은 다른 정보가 필요할 수 있습니다. 

이 절차를 만드는 데 사용된 데모 데이터 회사는 DEMF입니다.

이것은 전자 보고 구성을 사용하는 공급업체 지불 프로세스를 설명하는 5개 절차 중 2번째 절차입니다. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="set-up-iban-and-swift-code"></a>IBAN 및 SWIFT 코드 설정
1. 현금 및 은행 관리 > 은행 계좌로 이동합니다.
2. 빠른 필터를 사용하여 'DEMF OPER' 값으로 은행 계좌 필드를 필터링합니다.
3. DEMF OPER를 클릭하여 은행 계좌 세부 정보를 엽니다.
4. 편집을 클릭합니다.
5. 추가 ID 섹션을 확장합니다.
6. IBAN 필드에 'DE89370400440532013000'을 입력합니다.
7. SWIFT 코드 필드에 'DEUTDEFF'를 입력합니다.
    * SWIFT\BIC는 많은 지불 형식에 필요하지 않지만 은행 계좌에 등록하는 것이 좋습니다.  
8. 저장을 클릭합니다.

## <a name="set-up-bank-account-for-the-legal-entity"></a>법인의 은행 계좌 설정
1. 조직 관리 > 조직 > 법인으로 이동합니다.
2. 편집을 클릭합니다.
3. 은행 계좌 정보 섹션을 확장합니다.
4. 은행 계좌 필드에서 값을 입력하거나 선택합니다.
5. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]