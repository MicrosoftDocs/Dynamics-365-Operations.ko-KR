---
title: 원장 계정 간 거래 정산
description: 이 절차는 원장 계정 간의 거래를 정산하고 원장 정산을 취소하는 방법을 보여줍니다.
author: aprilolson
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 711e2f445e043dc74cba0ee11f1ab2dc22215ff30f495e06dce1f6f3ab4a0a09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450223"
---
# <a name="settle-transactions-between-ledger-accounts"></a>원장 계정 간 거래 정산

[!include [banner](../../includes/banner.md)]

이 절차는 원장 계정 간의 거래를 정산하고 원장 정산을 취소하는 방법을 보여줍니다. 이 절차에서는 USMF 데모 데이터 회사를 사용합니다.


## <a name="settle-transaction-between-ledger-accounts"></a>원장 계정 간 트랜잭션 정산
1. 총계정원장 > 정기 작업 > 원장 정산으로 이동합니다.
2. 목록에서 정산하려는 거래를 찾습니다.
   > [!NOTE]
   > 금액 잔액은 0이어야 합니다.  
3. 포함을 클릭합니다.
4. 수락을 클릭합니다.

## <a name="cancel-a-ledger-settlement"></a>원장 정산 취소

1. 총계정원장 > 조회 및 보고서 > 시산표로 이동합니다.
2. 매개 변수를 클릭하여 드롭 대화 상자를 엽니다.
3. 업데이트를 클릭합니다.
4. 목록에서 정산한 트랜잭션이 있는 계정을 찾습니다.
5. 모든 트랜잭션을 클릭합니다.
6. 필터를 사용하여 목록에서 트랜잭션을 쉽게 찾을 수 있습니다.
7. 원장 정산을 클릭합니다.
8. 목록에서 선택한 행을 표시합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]