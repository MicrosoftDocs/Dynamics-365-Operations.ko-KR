---
title: 급여 송장 시나리오 설정
description: 이 문서에서는 송장 결제와 관련된 다양한 시나리오를 지원하기 위해 Dynamics 365 Commerce를 구성하는 방법에 대해 설명합니다.
author: josaw1
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 78af54fec771e5012aca095d07fd772988a56029
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885378"
---
# <a name="set-up-pay-invoice-scenarios"></a>급여 송장 시나리오 설정

[!include [banner](includes/banner.md)]

Dynamics 365 Commerce의 송장 결제 기능은 다음 사항들을 지원하도록 확장되었습니다.

- 단일 POS 거래 건에서 다수의 판매 주문 송장 대금을 지급.
- 무료 문자 송장, 프로젝트 기반 송장, 대변 전표 등을 포함하는 다양한 유형의 고객 송장을 결제.

이러한 시나리오를 사용하려면 매장에 대한 기능 프로필을 아래에 설명된 대로 구성해야 합니다.

1. **Retail 및 Commerce \> 채널 설정 \> POS 설정 \> POS 프로필 \> 기능 프로필** 로 이동하여 변경하려는 해당 매장에 연결된 프로필을 선택합니다.
2. **Functions** 탭에서 필요에 따라 다음과 같은 매개 변수를 구성합니다.

    - **판매 주문 송장** - 사용자가 단일 POS 거래 건에서 하나 이상의 판매 주문 기반 송장을 결제할 수 있도록 하려면 **예** 를 선택합니다.
    - **무료 문자 송장** - 사용자가 단일 POS 거래 건에서 하나 이상의 무료 문자 기반 송장을 결제할 수 있도록 하려면 **예** 를 선택합니다.
    - **프로젝트 송장** - 사용자가 단일 POS 거래 건에서 하나 이상의 프로젝트 기반 송장을 결제할 수 있도록 하려면 **예** 를 선택합니다.
    - **판매 주문 대변 전표** - 사용자가 미결 송장에 대해 여러 건의 판매 주문 기반 대변 전표를 정산하거나 고객을 대상으로 미결 대변 전표에 대한 환불을 처리할 수 있도록 허용하려면 **예** 를 선택합니다.

> [!NOTE]
> 일부 금액의 결제 또는 정산은 아직 지원되지 않습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]