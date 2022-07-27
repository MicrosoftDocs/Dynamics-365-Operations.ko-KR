---
title: 송장 저널에 공급업체 송장 기록
description: 이 작업 가이드에서는 구매 주문과 관련이 없는 공급업체 송장을 기록하는 방법을 설명합니다.
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9742d8ab3e84b8f9443c7f44a5ffbabdc90a62dc19e523acd0b3b2ffa0c75880
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450217"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>송장 저널에 공급업체 송장 기록

[!include [banner](../../includes/banner.md)]

이 작업 가이드에서는 구매 주문과 관련이 없는 공급업체 송장을 기록하는 방법을 설명합니다. 이러한 유형의 송장의 예로는 공급 또는 서비스에 대한 비용이 있습니다.  이 레코딩은 USMF 데모 회사를 사용합니다.

1. **탐색 창 > 모듈 > 지급 계정 > 작업 영역 > 공급업체 송장 항목** 으로 이동합니다.
2. **작업 창** 에서 **새 송장 저널** 을 클릭합니다.
3. **새로 만들기** 를 클릭합니다.
4. **이름** 필드에 저널 이름을 입력하거나 드롭다운 단추를 눌러 조회를 엽니다.
5. **설명** 필드에 값을 입력합니다.
6. **작업 창** 에서 **라인** 을 클릭합니다. **날짜** 필드에 총계정원장을 업데이트할 게시 날짜를 입력합니다.  
7. **계정** 필드에서 **공급업체 계정** 을 지정합니다.
8. **송장** 필드에 송장 번호를 입력합니다.
9. **설명** 필드에 값을 입력합니다.
10. **대변** 필드에 숫자를 입력합니다.
11. **상쇄 계정** 필드에 계정 번호를 입력하거나 드롭다운 버튼을 클릭하여 조회를 엽니다.
    * **판매세 그룹** 이 공급업체 계정의 기본값이 됩니다.  
    * **품목 판매세 그룹** 은 **상쇄 계정** 필드에 지정된 주 계정에서 기본값이 됩니다.  
    * **기한** 은 결제 조건에 따라 계산됩니다.  
    * **현금 할인** 은 공급업체 계정에서 기본값으로 설정됩니다.
12. 공급업체 송장 저널 워크플로를 실행한 경우 **워크플로 > 제출** 을 클릭합니다.
    * 제출이 승인되면 트랜잭션 게시일이 원장 게시 보류 또는 마감 기간 내에 있는 경우 다음 공개 기간의 첫 날로 날짜가 앞당겨집니다.
12. **게시** 를 클릭합니다.
13. 페이지를 닫습니다



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]