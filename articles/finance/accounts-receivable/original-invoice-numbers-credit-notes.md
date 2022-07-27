---
title: 대변표의 원본 송장에 대한 참조
description: 이 항목에서는 연관된 대변표에서 원래 송장 번호를 설정하고 인쇄하는 방법을 설명합니다.
author: ilkond
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7147c5bea5273f385b004effe0844b5f4541a881
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2021
ms.locfileid: "8451108"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>대변표의 원본 송장에 대한 참조

[!include [banner](../includes/banner.md)]


일부 국가 및 지역에서는 인쇄된 대변표에 원본 송장에 대한 참조가 포함되어야 한다는 법적 요구 사항이 있습니다. 이 항목에서는 연관된 대변표에서 원래 송장 번호를 설정하고 인쇄하는 방법을 설명합니다.

## <a name="prerequisites"></a>전제 조건

- **기능 관리** 작업 영역에서 **판매 및 프로젝트 송장 보고서에 신용 송장 레이아웃** 기능을 켭니다. 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.
- 필요한 문서의 인쇄 가능한 형식은 인쇄 관리에서 구성해야 합니다.

이 항목에서 설명하는 기능은 다음 문서에 적용됩니다.

**수취 계정**

- 자유 텍스트 대변표
- 고객 대변표

**프로젝트 관리 및 회계**

- 프로젝트 대변표

## <a name="configure-accounts-receivable-parameters"></a>수취 계정 매개 변수 구성

원본 송장에 대한 참조가 관련 대변표에 인쇄되는지를 제어하는 매개 변수를 설정하려면 다음 단계를 따릅니다.

1. **수취 계정** \> **설정** \> **수취 계정 매개 변수** 로 이동합니다.
2. **업데이트** 탭의 **송장** 빠른 탭에서 **판매 및 프로젝트 송장 보고서에 신용 송장 발부 레이아웃 적용** 옵션을 **예** 로 설정합니다.

![수취 계정 매개 변수 구성.](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>원본 송장에 대한 참조 정의

문서 유형에 따라 원본 송장에 대한 참조를 정의하려면 다음 절차를 따릅니다.

### <a name="free-text-credit-note"></a>자유 텍스트 대변표

1. **수취 계정** \> **송장** \> **모든 자유 텍스트 송장** 으로 이동합니다.
2. 새 대변표를 작성하거나 기존 대변표를 선택합니다.
3. 송장을 엽니다.
4. 작업 창의 **송장** 탭에 있는 **기능** 그룹에서 **신용 송장 발행** 을 선택합니다.
5. 원본 송장에 대한 참조를 입력하고 수정 사유를 선택합니다.

![자유 텍스트 송장에 대한 참조 정의.](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>고객 대변표

1. **수취 계정** \> **주문** \> **모든 판매 주문** 으로 이동합니다.
2. 수정해야 하는 송장 발행된 판매 주문을 선택하고 엽니다.
3. 작업 창의 **판매** 탭에 있는 **대변표** 그룹에서 **대변표** 를 선택합니다.
4. 수정 이유를 입력합니다. 원본 송장에 대한 참조가 자동으로 설정됩니다.

![판매 주문에 대한 참조 정의.](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>프로젝트 대변표

1. **프로젝트 관리 및 회계** \> **프로젝트 송장** \> **프로젝트 송장** 으로 이동합니다.
2. 수정해야 하는 프로젝트 송장을 선택하고 엽니다.
3. 작업 창의 **프로젝트 송장** 탭에 있는 **기능** 그룹에서 **대변표로 선택** 을 선택합니다.
4. **신용 송장 발생** 을 선택합니다.
5. 수정 이유를 입력합니다. 원본 송장에 대한 참조가 자동으로 설정됩니다.

![프로젝트 송장에 대한 참조 정의.](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>대변표 인쇄

자유 텍스트, 고객 및 프로젝트 대변표를 인쇄할 때 원본 송장에 대한 참조와 수정 사유가 포함됩니다.

![인쇄된 대변표.](media/credit-note-FTI.jpg)

> [!NOTE]
> 원본 송장에 대한 참조가 인쇄된다는 가정 하에 문서의 인쇄 가능한 형식이 올바르게 구성되었는지 확인하세요.

## <a name="references-to-original-invoices-in-debit-notes"></a>차변표의 원본 송장에 대한 참조

기본적으로 원본 송장에 대한 참조를 대변표에 입력할 수 있습니다. 예를 들어 원본 송장을 음수(감소) 수정하는 경우 참조를 입력할 수 있습니다.

원본 송장을 양수(증가) 수정할 때 참조를 입력하려면 **기능 관리** 작업 영역에서 **차변표의 원본 송장에 대한 참조** 기능을 활성화해야 합니다.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
