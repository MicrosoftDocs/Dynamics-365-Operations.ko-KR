---
title: 신용 전표에서 원본 송장 참조(공급업체 송장)
description: 이 항목에서는 신용 전표를 만들 때 원본 송장에 대한 참조를 생성하는 방법을 설명합니다.
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6114ffb4d3b9e942887cbfa10c6039b0d73af7e1
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8450994"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>신용 전표에서 원본 송장 참조(공급업체 송장)

[!include [banner](../includes/banner.md)]

이 항목에서는 신용 전표를 만들 때 원본 송장에 대한 참조를 생성하는 방법을 설명합니다.

## <a name="prerequisites"></a>전제 조건

**기능 관리** 작업 영역에서 **공급업체 송장을 위한 신용 송장 발행 사용** 기능을 활성화합니다. 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요.

이 항목에서 설명하는 기능은 다음 비즈니스 문서에 적용됩니다.

**지급 계정:**

- 구매 주문
- 송장 분개장
- 송장 등록

**총계정원장:**

- 일반 분개장

## <a name="define-a-reference-to-an-original-invoice"></a>원본 송장에 대한 참조 정의

다음 절차를 사용하여 지정된 업무 문서 유형의 원본 송장에 대한 참조를 정의합니다.

### <a name="vendor-credit-note-purchase-order"></a>공급업체 신용 전표(구매 주문)

1. **지급 계정** \> **구매 주문** \> **모든 구매 주문** 으로 이동합니다.
2. 새 구매 주문을 생성하거나 기존 구매 주문을 사용하여 신용 전표를 만듭니다.
3. 작업 창의 **송장** 탭에 있는 **도입** 그룹에서 **신용 송장 발행** 을 선택합니다.
4. 수정 사유와 원본 송장에 대한 참조를 입력합니다.

### <a name="vendor-credit-note-ledger-journals"></a>공급업체 신용 전표(원장 분개장)

1. 다음 단계 중 하나를 따르십시오.

    - **지급 계정** \> **송장 분개장** 으로 이동합니다.
    - **지급 계정** \> **송장 등록** 으로 이동합니다.
    - **총계정원장** \> **분개장 항목** \> **일반 분개장** 으로 이동합니다.

2. 신규 분개장 및 신규 분개장 라인을 만듭니다.
3. 작업 창에서 **기능** \> **신용 송장 발행** 을 선택합니다.
4. 수정 사유와 원본 송장에 대한 참조를 입력합니다.

> [!NOTE]
> **계정 유형** 필드가 **공급업체** 로 설정된 경우 일반 분개장에서 **신용 송장 발행** 명령을 볼 수 있습니다.
