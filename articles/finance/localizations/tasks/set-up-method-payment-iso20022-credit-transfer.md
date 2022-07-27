---
title: ISO20022 계좌 이체를 위한 지불 방법 설정
description: 이 절차는 파일을 생성하기 위해 전자 보고를 사용하여 ISO20022 신용 이전 또는 기타 결제 유형에 대한 공급업체 결제 방법을 설정하는 방법을 보여 줍니다.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f87cc0dfa47295f047ef97732f60733c362ca4066d9070418322b34934e3ce3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450796"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>ISO20022 계좌 이체를 위한 지불 방법 설정

[!include [banner](../../includes/banner.md)]

이 절차는 파일을 생성하기 위해 전자 보고를 사용하여 ISO20022 신용 이전 또는 기타 결제 유형에 대한 공급업체 결제 방법을 설정하는 방법을 보여 줍니다. 

이 작업을 완료하기 전에 형식 구성을 내보내고 지급 계정을 설정해야 합니다.

이 작업은 DEMF 데모 데이터 회사를 사용하여 생성되었습니다.

이것은 전자 보고 구성을 사용하는 공급업체 지불 프로세스를 설명하는 다섯 개의 절차 중 세 번째 절차입니다. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.

1. 지급 계정 > 결제 설정 > 결제 방법으로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 'SEPA CT' 값을 사용하여 결제 방법 필드를 필터링합니다.
3. 편집을 클릭합니다.
4. 기간 필드에서 '총계'를 선택합니다.
5. 결제 유형 필드에서 '전자 결제'를 선택합니다.
6. 파일 형식 섹션을 확장합니다.
7. 일반 전자 보고 필드에서 예를 선택합니다.
8. 내보내기 형식 구성 필드에 값을 입력하거나 선택합니다.
    * 목록에서 ISO20022 DE(신용 전송) 값을 선택합니다. 목록이 비어 있으면 공급업체 결제 내보내기 형식 구성을 가져오지 않고 활성 상태로 유지합니다.  
9. 계정 유형 필드에서 '은행'을 선택합니다.
10. 결제 계정 필드에서 'DEMF OPER' 값을 지정합니다.
11. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]