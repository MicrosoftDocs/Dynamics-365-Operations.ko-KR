---
title: Global Inventory Accounting 원장
description: 이 토픽에서는 통화, 달력, 규칙 및 법인과의 연관의 조합으로 정의되는 Global Inventory Accounting 원장에 대해 설명합니다.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0130aef7212256a11ca9d27ffdd4af7a0aa6d98c
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2021
ms.locfileid: "8449491"
---
# <a name="global-inventory-accounting-ledger"></a>Global Inventory Accounting 원장

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Global Inventory Accounting에는 자체 원장 세트가 있습니다. 재고 관련 거래가 관련 법인에 대해 처리될 때마다 시스템은 필요에 따라 여러 Global Inventory Accounting 원장에서 해당 거래를 설명할 수 있습니다

원장은 출금 및 입금 측정값의 등록부입니다. 이러한 측정값은 비용 요소와 보조원장 계정을 사용하여 분류됩니다. Global Inventory Accounting 원장은 통화, 달력, 규칙 및 법인과의 연결의 조합으로 정의됩니다.

Global Inventory Accounting 원장을 설정하려면 **Global Inventory Accounting \> 설정 \> Global Inventory Accounting 원장** 으로 이동합니다. 각 원장에 대해 다음 필드를 설정합니다.

- **이름** – 원장의 이름을 입력합니다.
- **설명** - 원장의 설명을 입력합니다.
- **회계 달력** – 원장에 대한 회계 달력을 지정합니다.
- **통화 및 환율 유형** – 이 빠른 탭의 필드를 사용하여 원장이 사용하는 회계 통화와 환율 유형을 선택합니다. 선택한 통화는 법인이 사용하는 통화와 다를 수 있습니다. Global Inventory Accounting에서 사용자는 필요한 만큼 원가계산 원장을 정의할 수 있습니다. Global Inventory Accounting은 여러 통화 및 여러 평가로 재고 회계를 지원합니다. 다음 필드를 설정합니다.

    - **통화** – 재고 관련 값이 유지되는 원가계산 통화를 선택합니다. 이러한 값에는 재고 가치, 판매 제품 원가, 미착 재고 및 모든 종류의 차이가 포함됩니다.
    - **환율 유형** – 시스템이 거래 통화의 거래 금액과 품목의 표준 원가를 원가 계산 통화로 변환하는 데 사용해야 하는 환율을 선택합니다.

- **규칙 이름** – 규칙을 지정합니다. 규칙은 이 원장에서 비용을 계산하는 방법을 설정하는 정책 모음입니다.
- **법인** – 원장은 선택한 법인에 전기된 문서를 회계 처리합니다.
- **프라이밍** – 원장이 생성되기 전에 생성된 재고 트랜잭션을 원장의 통화 및 규칙에 따라 처리할지 여부를 선택합니다. 다음 값 중 하나를 선택합니다.

    - **활성화됨** – 원장은 원장이 생성되기 전에 생성된 트랜잭션을 처리해야 합니다.
    - **비활성화됨** – 원장은 원장이 생성된 이후에 생성된 트랜잭션만 처리해야 합니다.

    > [!IMPORTANT]
    > 새 문서를 입력한 후에는 돌아와서 이 필드를 설정할 수 **없습니다**.

- **상태** – 시스템은 새로 생성된 원장의 상태를 자동으로 *준비* 로 설정합니다.
