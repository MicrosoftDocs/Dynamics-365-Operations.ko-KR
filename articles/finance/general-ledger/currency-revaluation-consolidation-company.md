---
title: 통합 회사의 통화 재평가
description: 이 토픽에서는 통합 회사에서 통화를 재평가하는 방법에 대해 설명합니다.
author: roschlom
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: roschlom
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4f2d4e1340e6ed986a1a079a7e88fea3bbe6e1d6af8aee99837adbfe03c39f1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450145"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>통합 회사의 통화 재평가

[!include [banner](../includes/banner.md)]

한 회계 통화에서 다른 회계 통화로 데이터를 통합할 때 환율이 변경되더라도 통화 재평가를 실행해야 계정 잔액이 올바르게 재평가됩니다. 데이터를 원래 통합할 때 **통화 환산** 탭을 사용하여 통합 프로세스 동안 환산할 초기 환율을 선택합니다. 새 환율을 입력한 후(예: 다음 달) 계정 잔액을 재평가해야 합니다. 그러면 미실현 손익이 새로운 환율과 날짜를 기준으로 업데이트됩니다. 다음 예는 프로세스 중에 생성되는 회계 항목을 보여줍니다.

## <a name="company-setup"></a>회사 설정
-   **소스/운영 회사(USMF)** – 미국 달러(USD)가 회계 및 보고 통화로 사용됩니다.
-   **통합 회사(CON)** – 유로(EUR)가 회계 및 보고 통화로 사용됩니다.
    -   **실현 이익** – 원장 계정 801500
    -   **실현 손실** – 원장 계정 801600
    -   **미실현 이익** – 원장 계정 801600
    -   **미실현 손실** – 원장 계정 801400

## <a name="original-transactions"></a>원본 거래
### <a name="cash-receipt-transactions-in-usmf"></a>USMF의 현금 영수증 거래

| 날짜       | 원장 계정               | 통화 | 금액 |
|------------|------------------------------|----------|--------|
| 2015년 10월 11일 | 110110 – 현금                | USD      | 500    |
| 2015년 10월 11일 | 130100 – 수취 계정 | USD      | -500   |

## <a name="exchange-rates"></a>환율

| 원래 통화 | 변환 통화 | 시작 날짜 | 환율 |
|---------------|-------------|------------|---------------|
| EUR           | USD         | 2015년 10월 1일  | 200           |
| EUR           | USD         | 2015년 11월 1일  | 150           |
| EUR           | USD         | 2012년 12월 1일  | 100           |

## <a name="perform-the-consolidation-for-october-2015"></a>2015년 10월 통합 수행
### <a name="balances-in-the-consolidation-company"></a>통합 회사의 잔액

| 원장 계정 | 통화 | 금액 | 계산    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | 500 USD × 50%  |
| 130100         | EUR      | -250   | -500 USD × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a>2015년 10월 1일부터 2015년 11월 30일까지 계정에 대한 통화 재평가 수행
### <a name="balances-in-the-consolidation-company"></a>통합 회사의 잔액

| 원장 계정 | 통화 | 금액  | 계산                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333.33  | 원래 금액 500 × 66.6667%  |
| 130100         | EUR      | -333.33 | 원래 금액 -500 × 66.6667% |
| 801400         | EUR      | 83.33   | 333.33 – 250                       |
| 801600         | EUR      | -83.33  | -333.33 – (-250)                   |

보고 통화 금액에 대한 추가 거래가 표시됩니다.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a>2015년 10월 1일부터 2015년 12월 31일까지 계정에 대한 통화 재평가 수행
### <a name="balances-in-the-consolidation-company"></a>통합 회사의 잔액

| 원장 계정 | 통화 | 금액  | 계산                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500.00  | 원래 금액 500 × 1                           |
| 130100         | EUR      | -500.00 | 원래 금액 -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333.33 = 166.67 166.67 + 83.33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]