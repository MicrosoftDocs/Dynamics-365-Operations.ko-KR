---
title: ISO20022 계좌 이체를 위한 공급업체 및 공급업체 은행 계좌 설정
description: 이 절차는 ISO20022 신용 이체 또는 기타 공급업체 지불 파일 생성에 필요한 공급업체 및 공급업체별 은행 계좌 정보를 설정하는 방법을 보여줍니다.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a901591f9f3d1a892c29f92e59dc96c1f172143cae6bec571da33b4a50d274
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450220"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>ISO20022 계좌 이체를 위한 공급업체 및 공급업체 은행 계좌 설정

[!include [banner](../../includes/banner.md)]

이 절차는 ISO20022 신용 이체 또는 기타 공급업체 지불 파일 생성에 필요한 공급업체 및 공급업체별 은행 계좌 정보를 설정하는 방법을 보여줍니다. 

이 절차를 만드는 데 사용된 데모 데이터 회사는 DEMF입니다.
이것은 전자 보고 구성을 사용하는 공급업체 지불 프로세스를 설명하는 다섯 개의 절차 중 네 번째 절차입니다. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="set-up-bank-details"></a>은행 세부 정보 설정
1. 지급 계정 > 공급업체 > 모든 공급업체로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 'DE-001' 값을 사용하여 공급업체 계정 필드를 필터링합니다.
3. 공급업체 세부 정보를 열려면 DE-001을 클릭합니다.
4. 작업 창에서 공급업체를 클릭합니다.
5. 은행 계좌를 클릭합니다.
6. 편집을 클릭합니다.
    * 사용 가능한 은행 계좌가 없으면 새로 만들어야 합니다.  
7. SWIFT 코드 필드에 'COBADEFFXXX'를 입력합니다.
8. IBAN 필드에 'DE36200400000628808808'을 입력합니다.
9. 페이지를 닫습니다

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>공급업체에 대한 결제 방법 설정
1. 편집을 클릭합니다.
2. 결제 섹션을 펼치거나 접습니다.
3. 결제 방법 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
4. 목록에서 SEPA CT 행의 링크를 클릭합니다.
5. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]