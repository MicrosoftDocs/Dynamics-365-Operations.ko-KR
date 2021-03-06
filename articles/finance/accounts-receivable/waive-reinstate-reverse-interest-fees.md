---
title: 이자 수수료 면제, 복구 또는 취소
description: 이 문서에서는 이자 및 수수료 부과를 면제, 복구 및 취소하는 방법을 설명합니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInterestJourList
audience: Application User
ms.reviewer: roschlom
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb022179a1eb919eaf3d2ea74927ab4d61bd6fffb81348e352af7cf78d4b178c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450574"
---
# <a name="waive-reinstate-or-reverse-interest-fees"></a>이자 수수료 면제, 복구 또는 취소

[!include [banner](../includes/banner.md)]

이 문서에서는 이자 및 수수료 부과를 면제, 복구 및 취소하는 방법을 설명합니다.

**모든 고객** 목록 페이지의 **수금** 탭에 있는 버튼을 사용하여 요금을 면제, 취소 또는 복구할 수 있습니다.

-   면제된 요금은 탕감됩니다. 예를 들어 고객이 요금에 이의를 제기할 때 해당 고객과 좋은 비즈니스 관계를 유지하기 위해 요금을 면제할 수 있습니다.
-   복구된 요금은 다시 지불해야 합니다. 이전에 면제된 요금을 복구할 수 있습니다. 면제하면 안 된다고 판단되는 경우 요금을 복구해야 할 수도 있습니다.
-   취소된 청구는 고객의 계정에서 제거되어 더는 청구되지 않습니다. 예를 들어 고객이 지불해야 하는 금액을 계산하기 위해 잘못된 이자율을 선택한 경우 요금을 취소할 수 있습니다. 별도의 프로세스를 사용하여 이자를 다시 계산하고 고객에 대한 새 비용이 포함된 이자를 생성할 수 있습니다.

이러한 모든 작업은 이자 계산서를 변경합니다. 이자 계산서는 고객의 계정에 이자 또는 수수료가 부과될 때 이를 알려주는 비즈니스 문서입니다. 이자 또는 수수료를 면제하거나 취소하면 비용을 정산하기 위해 대변표 또는 조정 송장이 자동으로 생성됩니다. 면제된 요금을 복구하면 고객이 지불해야 하는 요금을 복구하기 위해 출금 금액이 있는 송장이 자동으로 생성됩니다. 다음 테이블에서는 각 작업의 결과를 설명합니다.

| 작업                                                                                                                                                                                                            | 고객에 대한 결과                                                                                             | 프로세스                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 포함된 모든 이자 및 수수료와 함께 전체 이자 계산서를 면제합니다. –또는– 이자 계산서의 일부인 수수료 또는 이자 거래를 선택하고 면제합니다.                                        | 요금은 탕감됩니다.                                                                                           | 고객에 대한 대변표 또는 조정 송장이 생성됩니다. 대변표는 이자 메모 또는 선택한 이자 거래 또는 수수료를 자동으로 정산하는 데 사용됩니다. 정산 금액은 청구 총액에서 고객이 이전에 지불한 금액에서 이전에 면제되거나 상각된 금액을 뺀 금액입니다. 대변표 금액이 고객이 지불해야 하는 금액을 초과하는 경우 대변표를 공급업체 송장으로 변환할 수 있습니다. 그런 다음 고객에게 환불을 제공할 수 있습니다.                                                       |
| 포함된 모든 이자 및 수수료와 함께 전체 이자 계산서를 복구합니다. –또는– 이자 계산서의 일부인 수수료 또는 이자 거래를 선택하고 복구합니다.                                | 면제된 금액은 다시 지불해야 합니다.                                                                                     | 출금 금액이 있는 송장이 생성되고 금액은 이전에 면제된 요금에 대해 자동으로 정산됩니다. 실제 이자 계산서는 복구되지 않습니다. 대신 고객이 지불해야 하는 금액을 표시하는 송장이 생성됩니다. 면제된 이자 계산서를 결제하기 위해 생성된 대변표 또는 조정 송장은 이자 계산서를 결제하는 데 사용되지 않은 경우 계속 존재할 수 있습니다. 이 경우 미결제 대변표는 취소됩니다. 미결제 대변표는 일반적으로 이자 계산서가 면제될 때 자동으로 정산됩니다. 그러나 고객이 요금에 이의를 제기한 경우에도 고객이 이자 계산서를 지불한 경우 미결제 대변표가 존재할 수 있습니다. |
| 전체 이자 계산서를 취소합니다. –또는– 이자 계산서의 일부인 선택된 이자 거래를 취소합니다. **참고:** 수수료는 취소할 수 없습니다. 그러나 수수료가 포함된 전체 이자 계산서를 취소할 수 있습니다. | 고객에 더는 요금을 청구하지 않습니다. 그러나 이자를 다시 계산하면 요금이 다시 부과됩니다. | 이 과정은 이자 계산서 또는 선택한 이자 거래를 면제하는 과정과 동일합니다. 고객에 대한 대변표 또는 조정 송장이 생성됩니다. 이 대변표는 이자 계산서를 자동으로 정산하는 데 사용됩니다. 별도의 프로세스를 사용하여 이자를 다시 계산하고 새 이자 계산서를 생성할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> 또한 별도의 절차를 사용하여 불량 부채를 채무 인하할 수 있습니다. 이 프로세스는 이자 메모의 일부인 요금만 면제하는 대신 모든 고객 거래를 결제 대상으로 표시합니다.

## <a name="adjust-interest-for-invoices"></a>송장에 대한 이자 조정
이자 계산서를 조정하는 것 외에도 다음 프로세스 중 하나를 사용하여 송장의 이자 비용을 제거할 수 있습니다. 두 프로세스 모두 관련 이자 계산서를 조정합니다.

### <a name="correct-an-invoice-that-has-associated-interest"></a>관련 이자가 있는 송장 수정

이자 계산서에 포함된 게시된 송장을 수정할 수 있습니다. 이 프로세스는 기존 송장의 세부 정보를 새 송장으로 복사하여 원하는 수정만 수행합니다. 송장이 취소되고 새 송장이 생성됩니다. 이자 계산서가 게시된 경우 거래에 대한 이자는 이자 계산서에서도 취소됩니다. 

자유 텍스트 송장의 작업 창에서 **송장 수정** 버튼을 사용하여 수정할 수 있습니다. 이 버튼은 **자유 텍스트 송장 수정** 구성 키를 선택한 경우에만 사용할 수 있습니다.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>관련 이자가 있는 고객 거래 취소

송장이 잘못 생성된 경우 송장에 대한 고객 거래를 취소할 수 있습니다. 취소된 고객 거래에 이자 계산서에 포함된 이자가 있고 이자 계산서가 게시된 경우 거래에 대한 이자는 이자 계산서에도 취소됩니다. 이자 계산서가 게시되지 않은 경우 취소됩니다. 

**고객 거래** 페이지에서 **취소** 버튼을 사용하여 고객 거래를 취소할 수 있습니다.

## <a name="waive-or-reinstate-interest-notes"></a>이자 계산서 면제 또는 복구
선택한 이자 계산서에 대한 모든 비용을 면제하거나 복구할 수 있습니다. 요금을 면제할 때 면제할 총 금액은 설정된 금액 한도를 초과할 수 없습니다. 이전에 면제한 이자 계산서만 복구할 수 있습니다. 

**고객** 페이지의 **수금** 탭에 있는 **이자 계산서** 버튼을 사용하여 이자 계산서를 면제하거나 복구할 수 있습니다.

## <a name="waive-or-reinstate-interest-transactions"></a>이자 거래 면제 또는 복구
해당 이자 계산서의 모든 요금을 조정하는 대신 이자 계산서에 대한 특정 이자 거래를 면제하거나 복구할 수 있습니다. 요금을 면제할 때 면제할 총 금액은 설정된 금액 한도를 초과할 수 없습니다. 이전에 면제한 이자 거래만 복구할 수 있습니다. 

**고객** 페이지의 **수금** 탭에 있는 **거래 이자** 버튼을 사용하여 이자 계산서를 면제하거나 복구할 수 있습니다.

## <a name="waive-or-reinstate-fees"></a>수수료 면제 또는 복구
해당 이자 계산서의 모든 요금을 조정하는 대신 이자 계산서에 대한 특정 수수료를 면제하거나 복구할 수 있습니다. 요금을 면제할 때 면제할 총 금액은 설정된 금액 한도를 초과할 수 없습니다. 이전에 면제한 수수료만 복구할 수 있습니다. 

**고객** 페이지의 **수금** 탭에 있는 **수수료** 버튼을 사용하여 이자 계산서를 면제하거나 복구할 수 있습니다.

## <a name="reverse-interest-notes"></a>이자 계산서 취소
선택한 이자 계산서에 대한 모든 비용을 취소할 수 있습니다. 취소된 청구는 고객의 계정에서 제거되어 더는 청구되지 않습니다. 이자 계산서가 취소된 후 이자를 다시 계산하고 새 이자 계산서를 생성할 수 있습니다. 

**고객** 페이지의 **수금** 탭에 있는 **이자 계산서** 버튼을 사용하여 이자 계산서를 취소할 수 있습니다.

## <a name="reverse-interest-transactions"></a>이자 거래 취소
선택한 이자 거래를 모두 취소할 수 있습니다. 취소된 청구는 고객의 계정에서 제거되어 더는 청구되지 않습니다. 거래가 취소된 후 이자를 다시 계산하고 새 이자 계산서를 생성할 수 있습니다.

**고객** 페이지의 **수금** 탭에 있는 **거래 이자** 버튼을 사용하여 이자 거래를 취소할 수 있습니다.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>면제, 복구 또는 취소된 청구에 대한 조정 내역 보기
조정을 입력한 사용자, 조정 유형, 금액, 조정이 입력된 시점 등 이자 계산서에 적용된 세부 조정 내역을 볼 수 있습니다. 예를 들어, 새로운 이자 계산서를 생성하기 전에 이자 계산서에 적용된 이전 조정 사항을 볼 수 있습니다. 

**고객** 페이지의 **수금** 탭에 있는 **기록** 버튼을 사용하여 이자 거래를 취소할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]