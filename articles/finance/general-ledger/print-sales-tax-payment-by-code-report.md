---
title: 코드별 판매세 결제 보고서 인쇄
description: 이 항목에서는 회계 또는 세금 코드 통화로 코드별 판매 세금 결제 보고서를 인쇄하는 데 필요한 설정 및 작업에 대한 정보를 제공합니다.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7c863308d2efc442ad16973407fe1cb72fb68cf89204c20f4468a3c98f4740c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450799"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>코드별 판매세 결제 보고서 인쇄 

[!include [banner](../includes/banner.md)]

**코드별 판매세 결제** 보고서를 인쇄하려면 **세금** \> **문의 및 보고서** \> **판매세 보고** \> **코드별 판매세 결제** 로 이동합니다. 기본적으로 **판매세 보고 코드** 페이지에 설정된 모든 신고 코드에 대한 신고 금액은 법인의 회계 통화로 생성됩니다.

또한 이 보고서를 생성하여 **판매세 코드** 페이지에서 판매세 코드에 할당된 모든 보고 코드에 대해 판매세 코드 통화로 판매세 납부 금액을 표시할 수 있습니다.

## <a name="turn-on-the-feature"></a>기능 켜기

**기능 관리** 작업 공간에서 **판매세 코드 통화의 코드별 판매세 결제 보고서 생성** 기능을 켭니다.

## <a name="run-the-report"></a>보고서 실행

1. **세금** \> **문의 및 신고** \> **판매세 보고** \> **코드별 판매세 결제** 로 이동합니다.
2. **보고 통화** 필드에서 다음 값 중 하나를 선택합니다.

    - **회계 통화** – 회계 통화로 보고서 금액을 인쇄합니다.
    - **판매세 코드 통화** – 판매세 코드의 통화로 보고서 금액을 인쇄합니다.

    ![코드별 판매세 대화 상자](media/Sales-tax-payment-by-code.png)

다음 그림은 생성된 보고서의 예를 보여 줍니다. 보고서에 따르면 보고 코드가 할당된 판매세 코드에 대해 **판매세 통화** 필드가 **EUR** 로 설정된 경우 보고 코드 **101** 은 **EUR** 통화를 가집니다.

![코드별 판매세 결제 보고서의 예.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]