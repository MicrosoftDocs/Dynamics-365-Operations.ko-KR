---
title: 리베이트 관리 매개 변수
description: 이번에는 리베이트 관리 매개 변수 페이지에 대해 설명합니다. 이 페이지에는 전기, 상태 업데이트, 번호 시퀀스 및 기타 동작에 영향을 주는 설정이 포함되어 있습니다.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0665ce41233308c814a514fccf3b73e20de64098
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448930"
---
# <a name="rebate-management-parameters"></a>리베이트 관리 매개 변수

[!include [banner](../includes/banner.md)]

**리베이트 관리 매개 변수** 페이지는 **리베이트 관리** 모듈에 적용되는 설정을 정의하는 데 사용됩니다. 이러한 설정은 전기, 상태 업데이트, 번호 시퀀스 및 기타 동작에 영향을 줍니다. 이 페이지의 설정은 법인 간에 공유되며 적절한 보안 권한이 있는 사용자가 수정할 수 있습니다.

**리베이트 관리 매개 변수** 페이지를 열려면 **리베이트 관리 \> 설정 \> 리베이트 관리 매개 변수** 로 이동하세요. 이후 다음 하위 섹션에 설명된 대로 필드를 설정합니다.

## <a name="rebate-management-tab"></a>리베이트 관리 탭

다음 표에서는 **리베이트 관리 매개 변수** 페이지의 **리베이트 관리** 탭에서 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 기본 상태 | 모든 신규 거래의 기본 상태를 선택합니다. 선택할 수 있는 상태 값 세트를 정의하려면 [**리베이트 상태** 페이지](rebate-statuses.md)를 사용하세요. |
| 차원별 처리 | 제공, 리베이트 및 상쇄 거래를 재무 차원별로 처리할지를 선택합니다. 이 옵션이 켜져 있으면 시스템은 대상 거래의 소스 거래에서 재무 차원을 사용합니다. |
| 이전에 전기되었는지 확인 | <p>미전기 리베이트 거래가 같은 기간 동안 두 번 이상 처리되는 경우 시스템 동작을 선택합니다.</p><ul><li>**경고** – 시스템에서 사용자가 기존 거래 라인을 대체할 수 있지만 경고가 표시됩니다.</li><li>**오류** – 시스템에서 사용자가 기존 거래 라인을 무시하는 것을 방지하고 오류 메시지가 표시됩니다. |
| 자동으로 원장 전기 | 시스템에서 제안한 원장을 자동으로 전기할지를 선택합니다. 이러한 원장에는 충당금 및 고객 공제에 사용되는 일일 원장과 공급 업체 세금 계산서 원장이 포함됩니다. |
| 무료 텍스트 송장 자동 전기 | 시스템에서 자유 텍스트 송장을 자동으로 전기할지를 선택합니다. 이 옵션은 지불 유형이 *세금 계산서 고객 공제* 로 설정된 무료 텍스트 송장에만 적용됩니다. |
| 리베이트 품목 주문 참조 | 리베이트 프로세스(*없음*, *리베이트 관리 거래*, *리베이트 관리 번호*, *리베이트 거래 번호* 또는 *문서 메모*)에서 생성된 판매 주문 및 구매 주문에 사용할 리베이트 참조를 선택합니다. |
| 클레임 프로세스 사용 | <p>청구 프로세스를 사용하려면 이 옵션을 *예* 로 설정하세요. 이러한 방식으로 리베이트 관리가 생성한 거래를 청구 또는 미청구로 표시한 후, 청구된 거래만 전기할 수 있습니다.</p><p>예를 들어, 한 달치 거래에 대한 리베이트를 계산했지만 고객이 이틀 동안 청구하지 않은 상태로 남습니다. 이 경우 다음 기간 동안 *처리* 기능을 실행할 때 청구되지 않은 거래가 다시 생성됩니다.</p><p>이 옵션을 *아니요* 로 설정하면 모든 청구 거래가 전기됩니다.</p> |
| 주문 유형 원장 포함 | 트랜잭션 유형이 *주문* 으로 설정된 거래 또는 거래 라인의 경우 이 옵션은 *원장* 유형의 판매 주문이 포함되어야 하는지를 제어합니다. 리베이트가 아직 적용되지 않아야 하는 시나리오에서 이러한 유형의 주문이 사용되는 경우 유연성을 제공합니다. |

## <a name="number-sequences-tab"></a>번호 시퀀스 탭

**리베이트 관리 매개 변수** 페이지의 **번호 시퀀스** 탭을 사용하여 리베이트 관리가 사용하는 다른 번호 시퀀스에 번호 시퀀스 코드를 할당합니다. 다음 표에서는 이러한 각 번호 시퀀스의 목적을 설명합니다. 번호 시퀀스에 대한 자세한 내용은 [숫자 시퀀스 개요](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) 및 관련 품목을 참조하세요.

| 참조 | 설명 |
|---|---|
| 리베이트 관리 거래 | 번호 시퀀스는 각 리베이트 거래에 고유한 키 값을 할당합니다. 이 키는 거래가 생성될 때 사용됩니다. |
| 리베이트 관리 번호 | 번호 순서는 각 리베이트에 고유한 키 값을 할당합니다. 이 키는 리베이트 관계를 식별하는 데 사용됩니다. |
| 리베이트 거래 번호 | 번호 순서는 각 리베이트 거래에 고유한 키 값을 할당합니다. 이 키는 리베이트 거래를 식별하는 데 사용됩니다. |
| 세금 계산서 | 번호 시퀀스는 각 리베이트 송장에 고유한 키 값을 할당합니다. 이 키는 리베이트 원장이 자동으로 전기될 때 사용됩니다. |

## <a name="feature-visibility-tab"></a>기능 가시성 탭

리베이트 관리는 Microsoft Dynamics 365 Supply Chain Management에서 자주 사용하는 여러 페이지에 기능(필드 및 기능)을 추가합니다. 이러한 페이지에는 판매 주문 및 판매 거래와 관련된 페이지가 포함됩니다. 리베이트 관리를 사용하는 경우 혜택을 받기 전에 해당 기능을 모든 곳에서 볼 수 있도록 해야 합니다. 리베이트 관리를 사용하지 않는 경우 기능을 숨겨 방해가 되지 않도록 할 수 있습니다.

**리베이트 관리 매개 변수** 페이지의 **기능 가시성** 탭에서 **활성화** 옵션을 *예* 로 설정하여 사용 가능한 모든 리베이트 관리 기능을 볼 수 있도록 합니다. **리베이트 관리** 모듈 외부의 공통 페이지에서 기능을 숨기려면 *아니요* 로 설정하세요. 그러나 옵션이 *아니요* 로 설정된 경우에도 **리베이트 관리 매개 변수 페이지** 를 포함한 모듈 자체는 액세스할 수 있는 적절한 권한이 있는 사용자가 계속 사용할 수 있습니다.