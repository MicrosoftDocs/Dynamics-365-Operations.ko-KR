---
title: 고객 지불 방법 설정
description: 이 항목에서는 고객 지불을 위한 지불 방법을 만드는 방법을 설명합니다.
author: ShivamPandey-msft
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0dd9fb37c733730360c78b702c62adadfdc6bd476ba4c436da08c86a9ad7ff55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450652"
---
# <a name="establish-customer-method-of-payment"></a>고객 지불 방법 설정

[!include [banner](../../includes/banner.md)]

이 항목에서는 고객 지불을 위한 지불 방법을 만드는 방법을 설명합니다. 이 작업에는 USMF 데모 회사를 사용합니다.

1. 탐색 창에서 **모듈 > 수취 계정 > 지불 설정 > 지불 방법** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **지불 방법** 필드에서 지불 방법의 ID를 입력합니다. 지불 방법 ID는 송장 및 결제에 표시되므로 어떤 유형의 결제가 기록되고 어떤 은행 계좌에 사용되는지 이해할 수 있도록 충분히 설명이 가능합니다.  
4. **설명** 필드에 설명을 입력합니다.
5. 지불을 게시하는 데 필요한 지불 상태를 선택합니다. 고객 지불을 생성할 때 지불 상태가 여기에서 정의한 지불 상태와 일치할 때만 게시할 수 있습니다.  
6. 송장에 대한 고객 지불을 생성하는 방법을 선택합니다. 이 옵션은 지불 제안을 실행할 때만 사용됩니다. 지불 제안은 고객이 자동 이체하고 고객의 은행 계좌에서 자금을 인출할 때 사용할 수 있습니다.  
7. 지불 유형을 선택합니다. 지불 유형은 지불에 대해 일부 유효성 검사를 수행할지 결정하는 데 도움이 됩니다.  
8. 지불이 게시될 계정 유형을 선택합니다. 일반적으로 이 옵션에는 은행이 선택됩니다.  
9. 이 지불이 기록될 은행 계좌를 선택합니다.
10. 은행에서 사용하는 지불 유형을 식별할 은행 거래 유형을 입력합니다. 은행 거래 유형은 은행 조정 프로세스 중에 사용되며 더 쉽게 조정할 수 있게 해줍니다.  
11. 이 지불을 브리징 계정에 일시적으로 게시할지 선택합니다. 은행 계좌를 정산하기 위해 지불 유동 시간을 시도하려면 브리징 기능을 사용하세요. 지불은 은행을 정산할 때까지 원장 계정에 일시적으로 게시되며, 이때 지불은 여기에서 정의한 은행 계좌로 이동합니다.  
12. 브리징 게시에 사용된 주 계정을 입력합니다. 브리징을 사용하는 경우 지불이 일시적으로 게시되는 주 계정입니다.  
13. **파일 형식** 탭에서 전자 지불 설정을 정의합니다.
14. **지불 관리** 탭에서 필수 필드를 정의합니다. 예를 들어 이 지불 방법으로 모든 지불을 예치해야 하는 경우 이 탭에서 해당 옵션을 선택할 수 있습니다.  
15. **지불 특성** 탭에서 이 지불 방법에 사용할 지불 특성을 정의합니다.
16. **저장** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]