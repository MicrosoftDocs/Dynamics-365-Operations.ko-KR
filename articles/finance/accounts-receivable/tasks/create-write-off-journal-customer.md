---
title: 고객에 대한 채무 인하 분개장 만들기
description: 이 작업 가이드는 채무 인하에 대한 매개 변수를 설정한 다음 수금 페이지, 고객 송장 열기 페이지 및 고객 페이지에서 거래를 채무 인하하는 방법을 설명합니다.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e810badf9b43a3b0e57390b05247113021e26b6a0242cf29022274307c5fd56
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450781"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>고객에 대한 채무 인하 분개장 만들기

[!include [banner](../../includes/banner.md)]

이 작업 가이드는 채무 인하에 대한 매개 변수를 설정한 다음 수금 페이지, 고객 송장 열기 페이지 및 고객 페이지에서 거래를 채무 인하하는 방법을 설명합니다. 이 작업에는 USMF 데모 회사를 사용합니다.


## <a name="set-up-the-write-off-parameters"></a>채무 인하 매개 변수 설정
1. **탐색 창 > 모듈 > 신용 및 수금 > 설정 > 수취 계정 매개 변수** 로 이동합니다.
2. **수금** 탭을 클릭합니다.
3. **채무 인하** 섹션을 펼치거나 접습니다.
    - **채무 인하 분개장** 는 생성한 채무 인하 거래를 보관할 일반 분개장입니다.  
    - 모든 채무 인하에 이유 코드를 첨부할 수 있습니다. 채무 인하 시 이 기본값을 재정의할 수 있습니다.  
    - 채무 인하의 원래 거래에서 판매세를 분리하려면 **별도 판매세** 를 예로 설정합니다.  
4. 페이지를 닫습니다.
5. **신용 및 수집 > 설정 > 고객 전기 프로필** 로 이동합니다. 채무 인하 계정은 일반 분개장의 비용 계정 또는 적립금 조정으로 사용됩니다.
6. 페이지를 닫습니다.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>에이징 잔액 페이지에서 고객 잔액을 채무 인하하십시오
1. **신용 및 수금 > 수금 > 에이징 잔액** 으로 이동합니다.
2. 채무 인하하려는 고객의 행을 표시하십시오. 예를 들어, Birch Company가 있는 선을 표시하십시오.
3. **작업 창** 에서 **수금** 을 클릭합니다.
4. **채무 인하** 를 클릭합니다.
5. **확인** 을 클릭합니다.
6. 페이지를 닫습니다.
7. **탐색 창 > 모듈 > 총계정원장 > 분개장 기입 > 일반 분개장** 으로 이동합니다.
8. 채무 인하가 포함된 분개장의 분개장 배치 번호를 선택합니다. 고객 잔액을 취소하기 위해 하나의 라인이 생성됩니다. 채무 인하 계정에 채무 인하를 전기하기 위해 하나 이상의 라인이 생성됩니다.  
9. 페이지를 닫습니다.
10. 페이지를 닫습니다.

## <a name="write-off-transactions-from-the-collections-form"></a>수금 양식에서 거래를 채무 인하합니다.
1. **신용 및 수금 > 수금 > 에이징 잔액** 으로 이동합니다.
2. 채무 인하하려는 거래가 있는 고객의 이름을 선택합니다. 예를 들어 Cave Wholesales(US-004)를 선택합니다.
3. 첫 번째 거래의 행을 표시하십시오.
4. 두 번째 거래의 행을 표시하십시오.
5. **채무 인하** 를 클릭합니다.
6. **이유 설명** 필드에 '불량 부채'를 입력합니다.
7. **확인** 을 클릭합니다.
8. 페이지를 닫습니다.
9. 페이지를 닫습니다.
10. **총계정원장 > 분개장 항목 > 일반 분개장** 으로 이동합니다.
11. 채무 인하가 포함된 분개장의 분개장 배치 번호를 선택합니다. 고객 잔액을 취소하기 위해 하나의 라인이 생성됩니다. 채무 인하 계정에 채무 인하를 전기하기 위해 하나 이상의 라인이 생성됩니다.  
12. 페이지를 닫습니다.
13. 페이지를 닫습니다.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>미결 고객 송장 페이지에서 송장 채무 인하
1. **탐색 창 > 모듈 > 수취 계정 > 송장 > 미결 고객 송장** 으로 이동합니다.
2. 송장에 대한 라인을 표시합니다. 예를 들어, CIV-000667에 대한 행을 표시하십시오.
3. **작업 창** 에서 **송장** 을 클릭합니다.
4. **채무 인하** 를 클릭합니다.
5. **확인** 을 클릭합니다.
6. 페이지를 닫습니다.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>고객 페이지에서 고객 잔액을 채무 인하하십시오
1. **수취 계정 > 고객 > 모든 고객** 으로 이동합니다.
2. 고객 계정을 선택합니다. 예를 들어 US-001(Contoso Retail San Diego)를 선택합니다.
3. **작업 창** 에서 **수금** 을 클릭합니다.
4. **채무 인하** 를 클릭합니다.
5. **확인** 을 클릭합니다.
6. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]