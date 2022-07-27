---
title: 회사 간 거래에 대한 TDS 계산
description: 이 토픽에서는 단계적으로 회사 간 거래에 대한 원천공제세(TDS)를 계산하는 데 사용되는 프로세스에 대해 설명합니다.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: c978c84891a0c1ce5a079484eec24590283027c4
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451807"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>회사 간 거래에 대한 TDS 계산

[!include [banner](../includes/banner.md)]

이 토픽에서는 단계적으로 회사 간 거래에 대한 원천공제세(TDS)를 계산하는 데 사용되는 프로세스에 대해 설명합니다.

회사 간 구매 주문 또는 판매 주문이 생성되면 고객 또는 공급업체에 대해 정의된 기본 TDS 그룹이 TDS 금액을 계산하는 데 사용됩니다. TDS 금액은 송장이 전기된 후 회수 가능 또는 지급 계정으로 전기됩니다.

회사 간 판매 주문 또는 구매 주문은 최초 구매 오더 또는 판매 오더에 대해 자동으로 생성됩니다. 기본 TDS 그룹은 회사 간 주문에 표시되므로 TDS를 계산할 수 있습니다. TDS 그룹을 변경할 수 있습니다. 자동으로 생성된 회사 간 주문의 순 송장 금액이 최초 주문의 순 송장 금액과 일치하는 경우에만 송장을 전기할 수 있습니다. (순액은 TDS 차감 후 송장 금액입니다.)

예를 들어, 50,000에 대한 판매 송장이 생성되고 **10%** TDS 그룹이 여기에 첨부됩니다. 전기된 송장 금액은 45,000이고 판매 송장에 대해 전기된 TDS 금액은 5,000입니다. 회사 간 판매 주문에 대해 구매 주문이 자동으로 생성되고 **10%** TDS 그룹이 여기에 연결됩니다. TDS 그룹을 **15%** 로 변경하면 자동으로 생성된 회사 간 판매 주문의 순 송장 금액이 최초 판매 주문의 순 송장 금액과 일치하지 않기 때문에 송장을 전기할 수 없습니다.

회사 간 송장에 대해 생성된 지불 분개가 자동으로 전기됩니다. 해당 지불 분개는 순 지불 금액이 원래 지불 분개의 순 지불 금액과 일치하는 경우에만 전기될 수 있습니다.
