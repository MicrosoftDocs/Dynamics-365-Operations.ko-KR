---
title: 구독 워크플로 개요
description: 이 토픽에서는 구독 워크플로에 대한 개요를 제공합니다.
author: kamaybac
ms.date: 05/07/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd1484563e9650b9ddae543e3440eec2a3ed075c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449680"
---
# <a name="subscription-workflow-overview"></a>구독 워크플로 개요 

[!include [banner](../includes/banner.md)]


귀하는 조명 장비 유지 관리를 위한 구독을 제공하는 조명 회사의 구독 관리자입니다. 고객이 조명 장비 유지 관리를 위한 연간 구독을 구매하기 위해 회사에 문의합니다.

## <a name="setting-up-subscriptions"></a>구독 설정

구독을 설정하려면 먼저 새 서비스 계약에 대한 구독 그룹을 생성하거나 구독 그룹이 존재하는지 확인해야 합니다. 구독 그룹이 있는 경우 매년 고객에게 송장을 보내고 해당 연도의 매월 판매 수익을 발생하도록 설정해야 합니다. 구독 설정 방법에 대한 자세한 내용은 [구독 그룹 설정](set-up-subscription-groups.md)을 참조하세요.

구독 그룹이 생성된 후 구독을 생성할 수 있습니다. 서비스 구독을 만드는 방법에 대한 자세한 내용은 [구독 그룹에서 서비스 구독 만들기](create-service-subscriptions-from-subscription-group.md)를 참조하세요.

## <a name="create-and-modify-subscription-transactions"></a>구독 트랜잭션을 생성 및 수정합니다.

구독을 설정한 후 첫 번째 송장 발행 기간인 1년 동안 구독료 거래를 생성합니다. 트랜잭션은 **정기** 유형입니다. 따라서 시작 날짜 및 종료 날짜가 **기간 유형** 양식에서 이전에 생성된 기간에 해당하는 구독 트랜잭션만 생성할 수 있습니다. 수수료 거래에 대한 자세한 내용은 [구독료 거래 생성](create-subscription-fee-transactions.md)을 참조하세요.

고객을 위한 구독을 설정한 후 고객이 서비스 제안에 대한 모든 정가에서 10% 할인을 협상했다는 것을 기억합니다. 따라서 생성한 거래 수수료의 가격을 줄여야 합니다.

오후에 고객 담당자가 전화를 걸어 조명 장비에 대한 서비스 계약을 여전히 원하지만 올해 말에 새로운 조명 장비를 도입할 계획이라고 말합니다. 따라서 2013년 10월까지만 유지 관리 보장이 필요합니다. 고객의 구독 개월 수를 줄이려면 **감소일** 유형의 구독료 트랜잭션을 새로 생성합니다. 일수를 줄이는 방법에 대한 자세한 내용은 [구독료 일수 줄이기](reduce-the-days-on-subscription-fees.md)를 참조하세요.

## <a name="invoice-and-accrue-subscription-transactions"></a>구독 거래 송장 및 발생

이제 구독 설정이 완료되었으며 고객에게 청구할 준비가 되었습니다. 구독 송장 작성 방법에 대한 자세한 내용은 [구독 거래 송장](invoice-subscription-transactions.md)을 참조하세요.

이틀 후 고객이 전화를 걸어 구독 송장이 유로가 아닌 미국 달러로 청구되어야 한다고 말합니다. 따라서 신용 메모를 만들고 올바른 통화로 새 구독 거래도 만듭니다. 구독 거래에 크레딧을 적용하는 방법에 대한 자세한 내용은 [구독 거래 크레딧](credit-subscription-transactions.md)을 참조하세요.

매월 말에 손익 계정 및 WIP 계정에 대한 고객의 구독에서 한 달의 수익이 발생할 수 있습니다. 구독 수익 발생 방법에 대한 자세한 내용은 [구독 수익 발생](accrue-subscription-revenue.md)을 참조하세요.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]