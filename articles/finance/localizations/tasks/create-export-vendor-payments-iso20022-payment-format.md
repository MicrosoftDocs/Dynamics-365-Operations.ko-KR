---
title: ISO20022 지불 형식을 사용하여 공급업체 지불 만들기 및 내보내기
description: 이 절차에서는 공급업체 지급 분개장에서 지급 라인을 생성하고 ISO2022 신용 이전 예제를 사용하여 공급업체 지급 파일을 생성하는 방법을 보여줍니다.
author: mrolecki
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c7bd5308e7589cb280244ea85e184422cbe2aa09f1cb548a81445defbd082e42
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450547"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>ISO20022 지불 형식을 사용하여 공급업체 지불 만들기 및 내보내기

[!include [banner](../../includes/banner.md)]

이 토픽에서는 공급업체 지급 분개장에서 지급 라인을 생성하고 ISO2022 신용 이전 예제를 사용하여 공급업체 지급 파일을 생성하는 방법을 설명합니다.

이것은 전자 보고 구성을 사용하는 공급업체 지불 프로세스를 설명하는 다섯 개의 절차 중 다섯 번째 절차입니다. DEMF 데모 데이터를 사용하여 이 예를 완료하십시오.

## <a name="example"></a>예:

1.    **지급 계정 > 지불 > 지불 분개장** 으로 이동합니다.
2.    **새로 만들기** 를 클릭합니다.
3.    **이름** 필드에 값을 입력하거나 선택합니다.
4.    **라인 > 지불 제안 > 지불 제안 생성** 을 클릭합니다.
5.    **포함할 레코드** 섹션을 펼칩니다.
6.    **필터** 를 클릭합니다.
7.    목록에서 **공급업체 테이블** 및 **공급업체 계정 필드** 에 대한 행을 선택합니다.
8.    **기준** 필드에서 값을 입력하거나 선택합니다. 지불할 공급업체 거래 선택 기준을 적용할 수 있습니다. 이 예에서는 DE-001을 공급업체 계정으로 사용합니다.
12.    **확인** 을 클릭합니다.
13.    **확인** 을 클릭합니다.
14.    **지불 생성** 을 클릭합니다.
15. ISO20022 지불 파일을 생성합니다.
    1.    **지불 생성** 을 클릭합니다.
    2.    **지불 방법** 필드에 값을 입력하거나 선택합니다.
    3.    **파일 이름** 필드에 값을 입력합니다. 이 예의 경우 EUR 지불로 인해 생성된 파일은 SEPA를 준수합니다. ISO20022 신용 이체 및 기타 공급업체 지불 형식을 사용하여 다른 통화로 지불할 수도 있습니다.
    4.    **은행 계좌** 필드에서 값을 입력하거나 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]