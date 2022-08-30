---
title: 다수의 고객 주문 및 송장에서 항목 반품
description: 이 문서에서는 Dynamics 365 Commerce의 여러 고객 주문 및 송장에서 반품을 실행하는 기능에 대해 설명합니다.
author: josaw1
ms.date: 08/27/2020
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
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 65ef700db5a81c49a962fd388af54e7811c088d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890325"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>다수의 고객 주문 및 송장에서 항목 반품

[!include [banner](includes/banner.md)]


반품은 여러 주문과 송장에 걸쳐 진행할 수 있습니다. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>다수의 고객 주문 및 송장에 대한 반품을 지원하도록 Commerce를 구성

1. **Commerce 매개 변수 \> 고객 주문** 으로 이동합니다.
1. **다수의 주문에 대해 반품 실행** 매개 변수를 켭니다. 

## <a name="process-returns"></a>반품 처리

매개 변수가 켜져 있고 변경 사항이 매장에 동기화되면 매장의 계산원이 반품할 고객에 대해 여러 건의 판매 주문을 선택할 수 있습니다.

주문을 선택하면 해당 주문에 대한 모든 송장에서 반품 가능한 모든 제품의 목록이 표시됩니다. 계산원은 반품할 제품을 선택할 수 있습니다. 선택한 모든 제품에 대해 단일 반품 주문이 생성됩니다.
