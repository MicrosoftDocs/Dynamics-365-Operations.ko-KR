---
title: 발생 개요
description: 이 문서에서는 적치휴가에 대해 설명하고 이를 설정하고 트랜잭션을 생성하는 방법에 대한 정보를 제공합니다.
author: aprilolson
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14131"
- intro-internal
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc3234c1a64155e1d0ad53cb7008d91847f7af7d
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451447"
---
# <a name="accruals-overview"></a>발생 개요

[!include [banner](../includes/banner.md)]

이 문서에서는 적치휴가에 대해 설명하고 이를 설정하고 트랜잭션을 생성하는 방법에 대한 정보를 제공합니다.

발생액은 발생주의 회계에서 지급을 받을 때가 아니라 수익이 발생한 기간에 인식된 수익을 추적하고 지급 시점이 아닌 발생 시점에 인식된 비용(원가)을 추적하는 데 사용됩니다.

## <a name="accrual-schemes"></a>발생 스키마
발생 계획은 이연 수익과 비용을 설정하는 데 사용되며 동일한 발생 계획은 수익과 비용 모두에 사용할 수 있습니다. 원장 발생은 분개 라인의 원가 또는 수익을 재분배하여 원가와 수익이 적절한 기간에 인식되도록 합니다. **발생 계획** 페이지에서 발생 계획이 적용될 때 사용할 차변 및 대변 계정을 지정합니다.

-   **차변** – 정의한 기본 계정은 분개 전표 라인의 차변 기본 계정을 대체합니다. 이 계정은 원장 발생 거래를 기반으로 한 연기 취소에도 사용됩니다.
-   **대변** – 정의한 기본 계정은 분개 전표 라인의 대변 기본 계정을 대체합니다. 이 계정은 원장 발생 거래를 기반으로 한 연기 취소에도 사용됩니다.

사용할 계정을 결정한 후 발생 거래가 생성될 때 전표 번호가 생성되는 방식을 지정할 수 있습니다. 또한 트랜잭션이 발생하는 빈도, 트랜잭션이 생성되는 횟수 및 트랜잭션이 게시되는 시기를 지정할 수 있습니다. 발생 계획이 생성된 후 원장 발생 기능을 사용하여 일부 분개에서 이를 사용할 수 있습니다.

## <a name="ledger-accruals"></a>원장 발생
분개장을 입력할 때 **기능** 메뉴에서 **원장 발생** 을 클릭할 수 있습니다. 그런 다음, 발생 계획을 선택하면 발생 계획에 의해 결정된 대로 해당 기간에 걸쳐 분산될 분개의 기준 금액을 볼 수 있습니다. 예를 들어, 1월에 전체 직원 보험을 지불하고 금액이 12,000인 경우 매월 해당 비용을 인식해야 합니다. 시작 날짜를 선택할 수 있습니다. 발생 금액이 계정을 기반으로 하는지 또는 상계 계정을 기반으로 하는지 여부를 지정할 수도 있습니다. 선택한 후 **트랜잭션** 을 클릭하여 적치휴가 계획에 따라 생성된 모든 트랜잭션을 봅니다. 예를 들어 1년 동안 보험 비용으로 12,000을 분산하면 매월 1,000이 표시됩니다. 저널 게시 후 **바우처 거래** 조회 페이지를 통해 거래내역을 조회할 수 있습니다. 발생 계획을 적용할 수 없는 경우(예: 판매 주문 송장 또는 구매 주문 송장이 관련된 경우) 선지급 금액을 대변에 기입하고 비용 금액을 차변에 기입할 수 있습니다. 그런 다음 적치휴가 계획을 적용할 때 **상계** 를 선택할 수 있습니다.


자세한 내용은 [발생 계획 생성](tasks/create-accrual-schemes.md) 및 [원장 발생 거래 생성](tasks/create-ledger-accrual-transactions.md)을 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]