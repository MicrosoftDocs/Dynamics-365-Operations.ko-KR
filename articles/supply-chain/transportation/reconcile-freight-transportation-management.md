---
title: 운송 관리에서 화물 조정
description: 이번에는 운임 조정 절차에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a63bfd34860c6a7c34cbc526c6a621cbc9666efc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448768"
---
# <a name="reconcile-freight-in-transportation-management"></a>운송 관리에서 화물 조정

[!include [banner](../includes/banner.md)]

이번에는 운임 조정 절차에 대해 설명합니다.

운임 조정은 수동으로 수행하거나 자동으로 발생하도록 설정할 수 있습니다. 자동 운임 조정을 사용하려면 자동으로 대응되는 운임 청구서를 결정하는 기준을 정의할 수 있는 감사 마스터를 설정해야 합니다.

## <a name="the-freight-reconciliation-process"></a>운임 조정 절차

운임은 관련 운송업체와 연결된 운임 엔진에 의해 계산됩니다. 화물이 확정되면 운임 계산서가 생성되어 운임이 이체됩니다. 운임은 일반 청구 절차에 사용되는 설정에 따라 관련 소스 문서(구매 주문, 판매 주문서 및/또는 이전 주문서)에 기타 비용으로 할당됩니다. 화물 조정 절차(일치 절차라고도 함)는 운송업체에서 화물 송장이 도착하는 즉시 시작할 수 있습니다. 송장은 전자적으로나 종이로 받을 수 있습니다. 송장이 종이로 접수된 경우 운임 청구서를 템플릿으로 사용하여 전자 송장을 생성할 수 있습니다.

[![화물 조정 절차](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>수동 조정

운임을 수동으로 조정하는 경우 각 송장 라인을 송장이 발행되는 부하에 대한 운임 청구서 라인과 일치시켜야 합니다. **운임 청구서 및 송장 일치 페이지** 에서 이 일치를 수행합니다. 송장 라인의 금액이 운임 청구서 금액과 일치하지 않는 경우 차액에 대한 조정 사유를 선택해야 합니다. 조정에 대한 여러 이유가 있는 경우 일치하지 않는 금액을 여러 이유로 나눌 수 있습니다. 조정 사유에 따라 차액이 총계정원장에 전기되는 방식이 결정됩니다. 전체 송장 금액의 조정이 계상되면 승인을 위해 제출된 다음 분개가 전기됩니다. 다음 그림은 운임 송장을 생성하고 운임 조정을 수행하는 방법을 보여줍니다.

[![화물 조정 작업](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>자동 조정

자동 조정을 사용하려면 조정 일정과 사용할 송장 및 운송업체를 지정해야 합니다. 송장 라인과 운임 청구서의 일치는 감사 마스터 및 운임 청구서 유형의 설정에 따라 수행됩니다. 자동 조정을 실행한 후에는 시스템에서 일치시킬 수 없는 송장을 처리해야 합니다. 이후 지불을 위해 모든 송장을 전기하기 전에 이러한 송장을 수동으로 처리해야 합니다.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>자동 또는 수동 조정을 사용하여 운임 청구서를 운임 송장과 일치시킵니다.

*일치* 는 각 운임 송장에 해당하는 운임 청구서를 찾는 과정입니다. 이는 송장 라인을 하나씩 일치(수동 일치)하거나 사용 가능한 모든 송장을 한 번에 일치(자동 일치)하여 수행할 수 있습니다.

### <a name="auto-matching"></a>자동 일치

여러 운임 송장을 동일한 운임 청구서에 대응시킬 때 자동 대응 절차는 다음과 같이 작동합니다.

1. 일치하지 않는 모든 운임 송장은 금액순으로 가장 큰 금액이 먼저 정렬됩니다.
1. 운임 청구서에 남아 있는 양수 금액이 없을 때까지 운임 송장은 하나씩 일치됩니다.
1. 감사 마스터의 설정과 운임 송장 잔액에 따라 잔액이 설정됩니다.

### <a name="manual-matching"></a>수동 일치

양수 금액의 모든 운임 청구서는 일치에 사용할 수 있습니다. 자동 일치와 유사하게 사용자는 완전히 일치하지 않는 운임 청구서에 음수 금액의 운임 송장만 일치시킬 수 있습니다.

### <a name="example"></a>예:

금액이 1500인 운임 청구서(FB)가 있고 다음 설정으로 각 송장에 대해 하나의 송장 라인이 있는 운임 청구서에 대해 세 개의 운임 송장을 생성했다고 가정합니다.

- 원래 운임 청구서(FB): 금액 1500
- 송장 1(Inv1): 금액 1000
- 송장 2(Inv2): 금액 600
- 송장 3(Inv3): 금액 -100

#### <a name="automatic-matching-result"></a>자동 일치 결과

자동 일치는 다음 순서로 실행됩니다.

1. 금액별로 내림차순으로 모든 운임 송장을 정렬합니다. Inv1 -> Inv2 -> Inv3
1. Inv1을 FB와 일치시킵니다. Inv1에는 1000개가 있고 FB에는 500개가 남아 있으므로 상태가 *부분 일치* 로 설정됩니다.
1. Inv2을 FB와 일치시킵니다. Inv2에는 500개의 일치 품목이 있고 FB에는 0개가 남아 있으므로 상태가 *완전 일치* 로 설정됩니다.
1. FB가 이제 완전히 일치하므로 Inv3이 처리되지 않습니다.

#### <a name="manual-matching-result"></a>수동 일치 결과

수동 일치의 경우 다음 예시와 같이 일치 순서에 따라 결과가 달라집니다.

##### <a name="manual-matching-case-1"></a>수동 일치 사례 1

이 예에 대한 수동 일치를 수행하는 한 가지 방법은 다음과 같이 진행하는 것입니다.

1. FB를 Inv1과 일치시킵니다. FB에 500개의 잔액이 남아 있으므로 상태가 *부분적으로 일치* 로 설정됩니다.
1. Inv2을 FB와 일치시킵니다. Inv2에는 500개의 일치 품목이 있고 FB에는 0개가 남아 있으므로 상태가 *완전 일치* 로 설정됩니다.
1. Inv3를 수동으로 일치시키면 일치하지 않는 운임 청구서를 찾을 수 없습니다.

이 경우는 본질적으로 자동 일치와 동일합니다.

##### <a name="manual-matching-case-2"></a>수동 일치 사례 2

이 예에 대한 수동 일치를 수행하는 또 다른 방법은 다음과 같이 진행하는 것입니다.

1. Inv3을 FB와 일치시킵니다. 이제 FB의 남은 금액은 1600이며, 이는 1500에서 음수 100을 빼는 것과 같습니다. FB와 Inv3 모두 -100의 일치된 수량을 갖습니다.
1. Inv1 및 Inv 2를 FB와 차례로 일치시킵니다. FB가 완전히 일치합니다.

이 예에서 볼 수 있듯이 운임 송장을 음수 금액과 일치시키는 것은 수동으로만 수행해야 합니다. 이렇게 하면 일치 순서를 제어할 수 있기 때문에 완전히 일치하지 않은 운임 청구서에 음수 금액의 운임 송장을 항상 일치시킬 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]