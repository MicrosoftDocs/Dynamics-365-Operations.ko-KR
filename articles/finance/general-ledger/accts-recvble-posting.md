---
title: 수취 계정 게시
description: 이 토픽에서는 수취 계정에서 전기를 구성하는 방법을 설명하고 전기 구성의 예를 제공합니다.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e664c42461e4f2995cac9a747d85d0f2a0fdf85
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2022
ms.locfileid: "8451498"
---
# <a name="accounts-receivable-posting"></a>수취 계정 게시

[!include [banner](../includes/banner.md)]

**수취 계정** 모듈의 기본 전기 프로필은 고객 전기 프로필입니다. 이 전기 프로필은 고객 잔액이 총계정원장에 전기될 때 사용되는 요약 계정을 결정합니다. 요약 계정은 기본 계정입니다. 수취 계정 거래 계정이라고도 합니다.

자세한 내용은 [고객 게시 프로필](../accounts-receivable/customer-posting-profiles.md)을 참조하십시오.

고객 게시 프로필 외에 여러 게시 구성을 수취 계정에서 사용할 수 있습니다. 다음 섹션에서는 이러한 기타 게시 구성에 대한 자세한 정보를 제공합니다.

## <a name="posting-accounts-for-methods-of-payment"></a>지불 방법에 대한 계정 게시

지급 방법은 지급이 총계정원장에 전기되는 방법을 정의합니다. 또한 지불 결과의 동작을 제어합니다. 일반적으로 조직에서 수행하는 각 지불 유형(예: 현금, 수표, 신용 카드, 우편환 및 전신 송금)에 대해 하나의 지불 방법이 수락됩니다.

**일반** 빠른 탭의 **전기** 섹션에 있는 필드는 지불이 총계정원장에 전기되는 방법을 제어합니다. 먼저 **계정 유형** 필드에서 값을 선택해야 합니다. 선택한 계정 유형은 **지불 계정** 필드의 동작을 제어합니다. **계좌 유형** 필드에서 **은행** 을 선택한 다음 **지불 계좌** 필드에서 은행 계좌를 선택하는 것이 좋습니다. 이 접근 방식의 이점은 시스템이 조정 및 기타 현금 관련 프로세스를 지원하는 은행 보조원장에 지불을 전기한다는 것입니다. 다음 표는 **현금 및 은행 관리** 모듈을 사용하는 경우 전기 프로필 구성의 예를 보여줍니다.

| 전기 유형 | 계정 유형 | 주 계정 이름 예 | 계정 유형 | 차변/대변? | 정리 계정 | 설명 |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| 은행 | 은행 | Bank of Contoso | 자산에 연결된 은행 계좌 | 입금 | 아니요 | 각 지불 방법에 대해 **지불 계정** 필드에 기본 계정을 입력합니다. |

현금 및 은행 관리를 사용하지 않으려는 경우 **계정 유형** 필드에서 **원장** 을 선택한 다음 **지불 계정** 필드에서 기본 계정을 선택해야 합니다. 다음 표는 현금 및 은행 관리를 사용하지 않는 경우 전기 프로필 구성의 예를 보여줍니다.

| 전기 유형 | 계정 유형 | 주 계정 이름 예 | 계정 유형 | 차변/대변? | 정리 계정 | 설명 |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| 원장 | 원장 | 100100: Bank of Contoso | 자산 | 입금 | 아니요 | 각 지불 방법에 대해 **지불 계정** 필드에 기본 계정을 입력합니다. |

## <a name="bridging-accounts"></a>브리징 계정

브리징 전기는 지불이 전기될 때 사용되는 2단계 프로세스입니다. 예를 들어 잔액이 없는 은행 계좌와 함께 사용할 수 있는 선택적 기능입니다. 보다 원활하고 시기적절한 은행 조정 프로세스를 보장하는 데 도움이 될 수 있습니다. 첫 번째 단계에서 지불은 임시 계정(브리징 계정)에 게시됩니다. 두 번째 단계에서는 지급이 은행에서 정산되면 전기된 항목이 취소되어 은행 계좌로 전기됩니다. 다음 표는 브리징 게시를 위한 게시 프로필 구성의 예를 보여줍니다.

| 전기 유형 | 주 계정 예 | 주 계정 이름 예 | 계정 유형 | 차변/대변? | 정리 계정 | 설명 |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| 원장 분개장 | 130725 | 미결제 현금 | 부채 | 출금 | 예 | 각 지불 방법에 대해 **브리징 계정** 필드에 기본 계정을 입력합니다. |

자세한 내용은 [브리지 결제 설정 및 처리](../accounts-receivable/set-up-and-process-bridged-payments.md)를 참조하세요.

## <a name="posting-accounts-for-customer-cash-discounts"></a>고객 현금 할인 계정 전기

조직이 빠른 지불의 대가로 고객에게 현금 할인을 제공하는 경우 현금 할인 코드를 구성하고 할인을 총계정원장에 전기하는 방법을 지정해야 합니다. 고객 현금 할인을 게시하는 데 사용되는 기본 계정을 지정하기 위해 몇 가지 옵션을 사용할 수 있습니다.

자세한 내용은 [현금 할인](../cash-bank-management/cash-discounts.md)을 참조하세요.

## <a name="posting-accounts-for-payment-fees"></a>지불 수수료 계정 게시

지불 수수료를 사용하면 일련의 조건이 적용될 때 고객 지불에 수수료를 자동으로 추가할 수 있습니다. 지불 수수료는 고객에게 청구할 수 있거나 비용으로 귀하의 은행 계좌에 전기할 수 있습니다. 여기 예시들이 있습니다 :

- 고객이 신용 카드를 사용하여 결제하는 경우 고객에게 총 결제 금액의 3%를 청구합니다.
- 귀하의 은행은 귀하가 처리하는 각 전신 송금에 대해 $1.00를 청구하며 전신 송금 수수료는 비용으로 처리됩니다.

고객 지불 수수료를 구성할 때 **청구** 필드를 **고객** 으로 설정하면 **기본 계정** 필드를 사용할 수 없게 되고 시스템은 고객 게시 프로필을 사용하여 수수료를 게시합니다. **청구** 필드를 **원장** 으로 설정하는 경우 **주 계정** 필드를 결제 수수료가 전기될 기본 계정으로 설정해야 합니다. 일반적으로 이 주 계정은 비용 계정이 됩니다. 다음 표는 지불 수수료 게시를 위한 게시 프로필 구성의 예를 보여줍니다.

| 전기 유형 | 주 계정 예 | 주 계정 이름 예 | 계정 유형 | 차변/대변? | 정리 계정 | 설명 |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| 원장 분개장 | 618190 | 은행 수수료 비용 | 경비 | 출금 | 아니요 |  **청구** 필드에서 **원장** 이 선택되면 지불 수수료의 **주 계정** 필드에서 이 계정을 선택합니다. |

자세한 내용은 [고객 지불 수수료 설정](../accounts-receivable/tasks/establish-customer-payment-fees.md)을 참조하세요.

## <a name="posting-accounts-for-charges-codes"></a>요금 코드에 대한 계정 게시

품목 외에 판매 금액을 추적해야 하는 경우 요금 코드를 사용할 수 있습니다. 예를 들어, 운임 및 취급 수수료를 고객에게 청구하거나 내부적으로 일부 운임 및 취급 수수료를 지출할 수 있습니다. 이러한 금액을 비용 계정에 전기할지 또는 항목 비용에 추가할지 여부를 지정할 수 있습니다.

수취 계정 및 지급 계정에 대한 요금 코드를 생성할 수 있습니다. 요금 코드를 구성할 때 전기를 정의해야 합니다. 전기는 차변 계정과 대변 계정을 모두 통제합니다. 생성하는 각 요금 코드에서 사용되는 전기 유형을 선택할 수 있습니다. 다음 표는 수취 계정에 대한 요금 코드의 일반적인 예를 보여줍니다.

| 전기 유형 | 주 계정 예 | 주 계정 이름 예 | 계정 유형 | 차변/대변? | 정리 계정 | 설명 |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| 지불 수수료 | 411400 | 수익 – 수수료 | 수익 | 입금 | 아니요 | **자금 부족의 예:** 차변 고객/판매자 및 대변 원장 계정 |
| 주문, 화물 | 403500 | 수익 – 화물 | 수익 | 입금 | 아니요 | **고객에게 청구되는 운임의 예:** 차변 고객/공급업체 및 대변 원장 계정 |
| 할인\* | 403200 | 할인 | 수익 | 출금 | 아니요 | **고객 리베이트의 예:** 차변 원장 계정 및 대변 고객/판매자 |

\*리베이트 예의 경우 전기는 구매 주문 헤더 또는 라인에 요금 코드가 추가된 경우에만 사용됩니다. Microsoft Dynamics 365 Supply Chain Management에서 사용할 수 있는 고급 리베이트 기능은 리베이트에 대한 더 많은 제어 및 자동화를 제공합니다. 자세한 내용은 [고객 리베이트](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md)를 참조하세요.

앞의 표는 요금 코드에 사용할 수 있는 전기 유형의 세 가지 일반적인 예를 보여줍니다. 지침 및 샘플로 사용해야 합니다. 사용할 수 있는 모든 가능한 조합 또는 게시 유형의 포괄적인 목록을 제공하지는 않습니다.

자세한 내용은 [청구 코드 생성](../accounts-receivable/create-charges-codes.md)을 참조하세요.

## <a name="posting-accounts-for-commissions"></a>커미션 계정 게시

주어진 판매 주문에 대해 영업 사원 또는 영업 사원 그룹에 대한 커미션을 계산하도록 시스템을 선택적으로 구성할 수 있습니다. 이 기능을 활성화하는 경우 수수료를 계산하는 데 사용되는 전기 계정을 구성해야 합니다. 이 구성은 **판매 및 마케팅** 모듈의 **커미션 게시** 페이지에서 수행됩니다.

자세한 내용은 [판매 수수료 규칙 설정](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md)을 참조하세요.
