---
title: ISO20022 자동 이체를 위한 지불 방법 설정
description: 이 절차에서는 전자 보고를 사용하여 ISO20022 자동 이체 또는 기타 결제 유형에 대한 고객 결제 방법을 설정하는 방법을 보여줍니다.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 127d5402abfedcce124b39b76a6c1036a6c818a7c1318aaeabdb0688b50f738e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450868"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>ISO20022 자동 이체를 위한 지불 방법 설정

[!include [banner](../../includes/banner.md)]

이 절차에서는 전자 보고를 사용하여 ISO20022 자동 이체 또는 기타 결제 유형에 대한 고객 결제 방법을 설정하는 방법을 보여줍니다. 



이 작업을 완료하기 전에 내보내기 형식 구성 및 지불 계정을 설정해야 합니다.



이 절차는 데모 데이터 회사 DEMF를 사용하여 생성되었습니다.



이는 전자 보고 구성을 사용하여 고객 결제 프로세스를 시연하는 다섯 가지 절차 중 세 번째 절차입니다.

1. 수취 계정 > 결제 설정 > 결제 방법으로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어, 'ELECTRONIC'의 값을 사용하여 결제 방법 필드를 필터링합니다.
3. 편집을 클릭합니다.
4. 결제 계정 필드에서 'DEMF OPER' 값을 지정합니다.
5. 파일 형식 섹션을 확장합니다.
6. 일반 전자 보고 필드에서 예를 선택합니다.
7. 내보내기 형식 구성 필드에 값을 입력하거나 선택합니다.
    * 목록에서 ISO20022 직접 차변(DE)을 선택합니다.  목록이 비어 있으면 고객 지불 내보내기 형식 구성을 가져와서 활성화하지 않은 것입니다.  
8. 위임 필요 필드에서 예를 선택합니다.
    * SEPA 자동 이체와 같이 결제 메시지에 위임 정보를 포함해야 하는 고객 결제 형식에 대해 위임 필요 매개 변수를 선택합니다.  
9. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]