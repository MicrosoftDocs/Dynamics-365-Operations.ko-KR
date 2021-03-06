---
title: 자동 결산 및 우선 순위 지정
description: 이 토픽에서는 수취 계정 매개 변수 페이지에서 자동 결산을 선택한 경우 거래가 결산되는 방법에 대해 설명합니다. 또한 자동 결산을 지불 우선 순위와 조합하여 사용하는 방법에 대해서도 설명합니다.
author: ShivamPandey-msft
ms.date: 01/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ba8a2f3b6a731e3371ca5245d5a9177b4cd0c226768c39c0cf7f6cb27526058
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450241"
---
# <a name="automatic-settlement-and-prioritization"></a>자동 결산 및 우선 순위 지정

[!include [banner](../includes/banner.md)]

이 토픽에서는 수취 계정 매개 변수 페이지에서 자동 결산을 선택한 경우 거래가 결산되는 방법에 대해 설명합니다. 또한 자동 결산을 지불 우선 순위와 조합하여 사용하는 방법에 대해서도 설명합니다.

송장 및 기타 거래로 지불을 결산할 때 두 가지 옵션이 있습니다. 결산할 거래를 수동으로 선택하거나 시스템에서 자동 결산 기능을 사용하여 거래를 자동으로 선택할 수 있습니다. **결산 우선 순위** 옵션을 사용하여 자동 결산 처리 방식을 사용자 지정할 수도 있습니다. 이러한 모든 옵션은 **수취 계정 매개 변수** 페이지에 정의된 결산 매개 변수의 일부입니다. 자동 결산 방식에 따라 거래가 자동으로 결산되는 방식이 다를 수 있습니다. 다음 방법을 사용할 수 있습니다.

-   사용자 정의 결산 우선 순위
-   기본 자동 결산

다음 섹션에서는 각 방법에 대한 거래가 결산되는 방법을 설명합니다.

## <a name="example-transactions"></a>거래 예시
이 문서 뒷부분의 결산 예시는 다음 거래를 기반으로 합니다. 모든 거래는 고객 2050에 대한 것입니다.

| 거래   | 날짜        | 금액 | 현금 할인 기간 | 현금 할인 날짜 | 코멘트                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 송장 1     | 8월 15일   | 100.00 | 2%14, 순액 30        | 8월 29일          |                                                                                                                                                                                               |
| 송장 2     | 9월 1일 | 250.00 | 2%14, 순액 30        | 9월 15일       |                                                                                                                                                                                               |
| 송장 3     | 10월 15일  | 500.00 | 2% 14/순액 30        | 10월 29일         |                                                                                                                                                                                               |
| 이자 계산서 | 10월 15일  | 7.00   |                     |                    | 이 이자 계산서는 송장 1 및 송장 2에 대한 것입니다. 금액은 30일 이상 연체된 금액에 대해 2%의 이자로 계산됩니다. 예를 들어 0.02 × (100.00 + 250.00) = 7.00입니다. |

## <a name="user-defined-settlement-priority"></a>사용자 정의 결산 우선 순위
**수취 계정 매개 변수** 페이지에서 **자동 결산 우선 순위 사용** 을 **예** 로 설정한 경우, **결산 우선 순위** 페이지에서 정의한 결산 우선 순위는 자동 결산을 위한 거래를 선택할 때 사용됩니다. 이 예에서는 다음 결산 우선 순위가 정의됩니다.

1.  거래 유형
    -   지불 수수료
    -   수집 서신
    -   이자 계산서
    -   송장

2.  거래 날짜, 오름차순
3.  바우처

10월 25일에 700.00에 대한 지불을 전기하면 다음 순서로 거래에 지불이 결산됩니다.

| 바우처       | 날짜       | 송장 | 트랜잭션 통화 금액 | 결산할 금액 | 잔액 | 통화 |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| 이자 계산서 | 2015년 10월 15일 |         | 7.00                           | 7.00             | 0.00    | USD      |
| 송장 1     | 2015년 8월 15일  | 10001   | 100.00                         | 100.00           | 0.00    | USD      |
| 송장 2     | 2015년 9월 1일   | 10002   | 250.00                         | 250.00           | 0.00    | USD      |
| 송장 3     | 2015년 10월 15일 |         | 500.00                         | 343.00           | 157.00  | USD      |

## <a name="default-automatic-settlement"></a>기본 자동 결산
사용자가 정의한 결산 우선 순위가 없을 경우 기한을 기준으로 자동으로 결산할 거래를 선택합니다. 결산된 거래는 결산된 거래와 동일한 통화를 사용해야 합니다. 10월 25일에 700.00에 대한 지불을 전기하면 다음 거래가 결산 대상으로 선택됩니다.

| 바우처       | 날짜       | 송장 | 트랜잭션 통화 금액 | 결산할 금액 | 잔액 | 통화 |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| 송장 1     | 2015년 8월 15일  | 10001   | 100.00                         | 100.00           | 0.00    | USD      |
| 송장 2     | 2015년 9월 1일   | 10002   | 250.00                         | 250.00           | 0.00    | USD      |
| 송장 3     | 2015년 10월 15일 |         | 500.00                         | 350.00           | 150.00  | USD      |
| 이자 계산서 | 2015년 10월 15일 |         | 7.00                           | 0.00             | 7.00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]