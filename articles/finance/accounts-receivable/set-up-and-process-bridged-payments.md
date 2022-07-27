---
title: 연결된 지불 설정 및 처리
description: 이 항목에서는 연결된 고객 지불을 설정하고 처리하는 방법을 설명합니다. 연결된 지불은 총계정원장에 두 단계로 게시되는 지불입니다.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1418e573f34fadcf0bebc7232d847ee7e9768b
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2022
ms.locfileid: "8451477"
---
# <a name="set-up-and-process-bridged-payments"></a>연결된 지불 설정 및 처리

[!include [banner](../includes/banner.md)]

연결된 지불은 총계정원장에 두 단계로 게시되는 지불입니다. 일반적으로 이 접근 방식은 지불 방법이 **은행** 으로 설정된 경우에 사용되며 거래가 은행에서 정산된 경우에만 은행 계좌로 거래를 게시해야 합니다. 그러나 원장 계정으로도 사용할 수 있습니다. 이 경우 연결 게시가 처리될 때 시스템은 한 주 계정에서 다른 주 계정으로 금액을 이동합니다.

지급 계정 또는 수취 계정 중 하나에서 연결된 지불을 만들 수 있습니다. 이 항목에서는 수취 계정에 대한 연결 게시를 구성하는 방법을 설명하지만 지금 계정 거래에 대한 단계도 비슷합니다.

## <a name="set-up-bridging-posting"></a>연결 게시 설정

연결 게시를 사용하려면 **연결 게시** 방법을 사용하도록 하나 이상의 결제 방법을 설정해야 합니다. 그런 다음 연결 계정을 선택해야 합니다.

1. **수취 계정 &gt; 지불 설정 &gt; 지불 방법** 으로 이동합니다.
2. 연결 게시를 활성화할 기존 지불 방법을 선택합니다. 또는 새 결제 방법을 만듭니다.
3. **연결 게시** 확인란을 선택합니다.
4. **연결 계정** 필드에서 은행 계좌로 입금되기 전에 지불이 게시되어야 하는 주 계정을 선택합니다.
5. 페이지를 닫습니다.

## <a name="process-and-transfer-bridging-posting"></a>연결 게시 처리 및 이전

연결 게시를 만들고 처리하려면 다음 단계를 따르세요.

1. **수취 계정 &gt; 지불 &gt; 고객 지불 분개장** 으로 이동합니다.
2. **새로 만들기** 를 선택하여 분개장을 만듭니다.
3. **이름** 필드에서 이름을 선택합니다.
4. 고객 지불 분개장에 라인을 추가하고 연결 게시를 위해 구성된 지불 방법을 선택합니다.
5. 분개장을 게시합니다. 거래는 이전 절차의 **연결 계정** 필드에서 선택한 주 계정으로 게시됩니다.

거래가 은행을 정산하고 연결 계정에서 지불 방법에 대해 지정된 지불 계정으로 지불을 이전하려면 다음 단계를 따릅니다.

1. **총계정원장 &gt; 분개장 항목 &gt; 일반 분개장** 으로 이동합니다.
2. **새로 만들기** 를 선택하여 분개장을 만듭니다.
3. **이름** 필드에서 이름을 선택합니다.
4. **라인** 을 선택하여 분개장 세부 정보를 엽니다.
5. **기능 &gt; 연결된 거래 선택** 을 선택합니다.
6. 결제가 완료된 각 결제를 표시한 다음 **수락** 을 선택합니다.
7. 분개장을 게시합니다.
