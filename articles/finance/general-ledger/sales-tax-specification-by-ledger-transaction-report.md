---
title: 원장 거래별 판매세 명세 보고서
description: 이 항목에서는 판매세가 계산되는 원장 거래에 대한 정보를 보고 인쇄하기 위해 원장 거래별 판매세 명세 보고서를 사용하는 방법을 설명합니다.
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: f835f06c190f1d174fbde6b68f189b0484a7b39610bc2edc0676a3e2fa320268
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450199"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>원장 거래별 판매세 명세 보고서
[!include [banner](../includes/banner.md)]

이 항목에서는 판매세가 계산되는 원장 거래에 대한 정보를 보고 인쇄하기 위해 **원장 거래별 판매세 명세** 보고서를 사용하는 방법을 설명합니다.

## <a name="tax-accounts-vs-non-tax-accounts"></a>과세 계정과 비과세 계정

**원장 거래별 판매세 명세** 보고서는 과세 계정과 비과세 계정의 세금 거래를 모두 보여줍니다. 이러한 계정은 다음과 같이 분류됩니다.

- **과세 계정** – 세금 거래가 게시될 때 과세 계정으로 간주되는 계정이며 **판매세** 분개장 라인의 주 계정은 판매세 납부 계정 또는 판매세 수취 계정과 같은 세금 계정입니다.
- **비세금 계정** – 세금 거래가 게시될 때 비과세 계정으로 간주되는 계정이며 원래 거래의 주 계정은 수익 계정이나 경비 계정과 같은 비과세 계정입니다.

과세 계정의 경우 보고서의 **기준**, **판매세 수취** 및 **판매세 지급** 열에 **0**(영)이 표시됩니다. 비과세 계정의 경우 해당 열에 금액이 표시됩니다.

## <a name="filtering-the-data-on-the-report"></a>보고서의 데이터 필터링

이 보고서를 생성하면 다음 기본 필드가 제공됩니다. 이러한 필드를 사용하여 보고서에 표시될 데이터를 필터링할 수 있습니다.

| 필드                      | 설명 |
|----------------------------|-------------|
| 날짜                       | **시작** 및 **종료** 섹션의 필드를 사용하여 세금 거래의 날짜 범위를 정의합니다. |
| 주 계정               | **시작** 및 **종료** 섹션의 필드를 사용하여 주 계정의 날짜 범위를 정의합니다. |
| 판매세 코드             | **시작** 및 **종료** 섹션의 필드를 사용하여 판매세 코드의 날짜 범위를 정의합니다. |
| 그룹화                   | 보고서를 원장 계정 또는 판매세 코드별로 그룹화할지를 선택합니다. |
| 판매세 코드별 소계 | 판매세 코드별로 소계를 표시하려면 이 옵션을 **예** 로 설정합니다. |
| 합계만                | 합계만 표시하려면 이 옵션을 **예** 로 설정합니다. |
| 주 계정만         | 주 계정만 보고서에 포함하려면 이 옵션을 **예** 로 설정합니다. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>보고서에 비과세 계정만 표시

보고서에 비과세 계정만 표시하려면 다음 그림에 표시된 것처럼 별표(\*)와 같은 필터를 설정합니다.

![비과세 계정을 보여주는 보고서.](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]