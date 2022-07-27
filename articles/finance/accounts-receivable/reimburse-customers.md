---
title: 고객에게 상환
description: 이 문서에서는 고객 그룹에 대한 상환 트랜잭션을 생성하는 방법을 설명합니다. 고객이 크레딧 잔액을 가지고 있으면 잔액을 고객에게 변제할 수 있습니다.
author: JodiChristiansen
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c313c03c6f3504f132a836eb6a67207e5f3c5636d43124c5f16d13992b9b604
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450760"
---
# <a name="reimburse-customers"></a>고객에게 상환

[!include [banner](../includes/banner.md)]

이 문서에서는 고객 그룹에 대한 상환 트랜잭션을 생성하는 방법을 설명합니다. 고객이 크레딧 잔액을 가지고 있으면 잔액을 고객에게 변제할 수 있습니다. 

다음 테이블은 시작하기 전에 갖추어야 할 전제 조건을 보여줍니다.

| 전제 조건                                                            | 설명 |
|-------------------------------------------------------------------------|-------------|
| 법인에 대한 최소 상환 금액을 지정합니다.          | **지급 계정 매개 변수** 페이지의 **일반** 영역의 **최소 상환** 필드에 고객의 초과 결제에 대해 상환할 수 있는 최소 금액을 입력합니다. |
| 선택 사항: 각 고객에게 상환할 수 있는 공급업체 계정을 추가합니다. | **고객** 페이지의 **기타 세부 정보** FastTab의 **공급업체 계정** 필드에서 고객에 대한 공급업체 계정을 선택합니다. |

상환 트랜잭션을 생성하면 크레딧 잔액 금액에 대한 공급업체 송장이 생성됩니다. 상환 프로세스는 고객 계정에 대한 크레딧 잔액을 제거하고 고객에 해당하는 공급업체 계정에 대한 만기 잔액을 생성합니다.

1. 수취 계정에서 **상환** 프로세스(**수취 계정 \> 정기 작업 \> 상환**)를 실행합니다.
2. 원장 수치에 관계없이 모든 트랜잭션을 그룹화하려면 **고객 요약** 옵션을 **예** 로 설정합니다. 유사한 원장 크기를 가진 트랜잭션만 그룹화하려면 이 옵션을 **아니요** 로 설정합니다.
3. 미결제 차변 금액이 있는 고객을 선택하려면 **미결제 차변 트랜잭션 고객 포함** 을 선택합니다.
4. 특정 고객 계정에 상환하려면 **포함할 레코드** FastTab에서 **필터** 를 선택한 다음 쿼리에서 고객 계정을 지정합니다.

    크레딧 금액은 고객의 공급업체 계정으로 이체되고 통상적인 지급으로 처리됩니다. 고객이 벤더 계정을 가지고 있지 않으면 고객에 대한 일회성 공급업체 계정이 자동으로 생성됩니다.

5. 생성된 상환 트랜잭션을 보려면 **상환** 보고서(**수취 계정 \> 조회 및 보고서 \> 상환 보고서**)를 사용합니다.
6. 지급 계정에서 상환 프로세스로 생성된 공급업체 송장에 대한 결제를 생성합니다. 공급업체에 결제하는 자세한 방법은 [공급업체 결제 개요](../accounts-payable/Vendor-payments-workspace.md)를 참조하십시오.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]