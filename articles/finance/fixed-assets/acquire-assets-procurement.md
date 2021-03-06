---
title: 조달을 통한 자산 획득
description: 이 토픽에서는 구매 주문 또는 공급업체 송장에서 고정 자산을 자동으로 생성하거나 고정 자산에 대한 취득 및 취득 조정 트랜잭션을 자동으로 게시하기 위해 고정 자산과 지급 계정 간의 통합을 설정하는 방법에 대해 설명합니다.
author: moaamer
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c51abd3ce380f0cb1ad688ffab16b239460bc45
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451072"
---
# <a name="acquire-assets-through-procurement"></a>조달을 통한 자산 획득

[!include [banner](../includes/banner.md)]

이 토픽에서는 구매 주문 또는 공급업체 송장에서 고정 자산을 자동으로 생성하거나 고정 자산에 대한 취득 및 취득 조정 트랜잭션을 자동으로 게시하기 위해 고정 자산과 지급 계정 간의 통합을 설정하는 방법에 대해 설명합니다. 하나의 구매 라인은 구매 라인의 수량에 관계없이 하나의 자산을 생성합니다. 여러 고정 자산을 생성해야 하는 경우 여러 구매 라인을 생성해야 합니다.

 고정 자산과 지급 계정을 통합하는 데 다음 방법을 사용할 수 있으며 모든 고정 자산에 대해 동일한 방법을 사용해야 합니다.
-   구매 주문 또는 공급업체 송장의 라인에 고정 자산 번호를 추가하기 전에 고정 자산을 수동으로 생성합니다. 공급업체 송장을 전기하면 자산에 대한 취득 트랜잭션이 자동으로 전기됩니다. 이는 기본 방법입니다.
-   구매 주문 또는 공급업체 송장의 라인에 고정 자산 번호를 추가하기 전에 고정 자산을 수동으로 생성합니다. 공급업체 송장을 전기하면 자산에 대한 취득 트랜잭션이 전기되지 않습니다.
-   새 고정 자산 생성 확인란이 선택된 제품 영수증 또는 공급업체 송장을 전기하면 고정 자산이 자동으로 생성됩니다. 공급업체 송장을 전기하면 자산에 대한 취득 트랜잭션이 자동으로 전기됩니다.
-   새 고정 자산 생성 확인란이 선택된 제품 영수증 또는 공급업체 송장을 전기하면 고정 자산이 자동으로 생성됩니다. 공급업체 송장을 전기하면 자산에 대한 취득 트랜잭션이 전기되지 않습니다.

고정 자산을 수동으로 생성하려는 경우 처음 두 가지 방법 중 하나를 선택한 다음 구매 주문서 또는 공급업체 송장에 고정 자산 번호를 지정합니다. 보다 유연한 접근 방식을 선호하는 경우 마지막 두 가지 방법 중 하나를 선택합니다. 고정 자산을 수동으로 생성할 수도 있고 라인 항목 세부 정보의 고정 자산 정보를 기반으로 고정 자산을 자동 생성할 수도 있습니다. 

고정 자산을 수동으로 생성하든 보다 유연한 접근 방식을 사용하든, 취득 거래를 고정 자산에만 전기할 수 있는지 또는 공급업체 송장을 전기할 때 전기할 수 있는지도 결정해야 합니다. 일부 조직에서는 사용자가 수동 분개 또는 제안을 사용하여 고정 자산에서 인수 및 인수 트랜잭션을 수동으로 생성하는 것을 선호합니다. 

이 토픽에서는 각 방법에 대해 자세히 설명합니다.

## <a name="methods-for-manually-creating-fixed-assets"></a>고정 자산을 수동으로 생성하는 방법
라인에 고정 자산 번호가 입력된 공급업체 송장을 전기할 때 고정 자산 매개 변수 페이지에서 구매에서 자산 취득 허용 옵션이 선택된 경우 취득이 자동으로 전기되고 자산 상태가 개설로 변경됩니다. 

인수를 전기할 수 없는 경우 고정 자산에 인수 거래를 수동으로 입력하거나 고정 자산 분개장의 인수 제안을 사용하여 동시에 여러 인수 거래를 생성할 수 있습니다.

> [!NOTE]                                                                                                                              
> 고정 자산이 취득 거래 전기를 특정 사용자 그룹으로 제한하도록 설정된 경우 송장에서 취득 거래를 전기하려면 해당 사용자 그룹의 구성원이어야 합니다.

## <a name="methods-for-automatically-creating-fixed-assets"></a>고정 자산을 자동으로 생성하는 방법
라인에 대해 새 고정 자산 생성 옵션이 선택된 제품 입고를 전기하면 아직 취득하지 않음 상태인 새 고정 자산이 생성됩니다. 그런 다음 새 고정 자산이 포함된 공급업체 송장을 전기하면 새 자산에 대한 취득 거래가 전기되고, 자산 상태가 지급 계정에서 자산 취득을 허용하도록 고정 자산이 설정되었으며 귀하가 취득 거래를 게시할 수 있는 사용자 그룹의 구성원인 경우 자산 상태가 미결로 변경됩니다. 

제품 영수증을 전기할 때 구매 라인에서 새 고정 자산 여부 옵션이 선택되지 않았지만 공급업체 송장을 전기할 때 선택된 경우, 고정 자산이 생성 및 획득을 허용하도록 설정되었다면 새 고정 자산이 생성되고 개방 상태로 획득됩니다. 제품 영수증을 게시할 때 이미 생성된 공급업체 송장을 게시할 때 추가 자산이 생성되지 않습니다.

### <a name="capitalization-threshold"></a>자본 총액 임계값

자산이 자동으로 생성되어 취득되는 방식을 사용하는 경우 고정 자산의 구매 금액이 자산 감가상각에 대해 지정된 자본화 임계값을 충족하는지 확인하도록 시스템을 설정할 수 있습니다. 그렇다면 자산이 지급 계정에서 생성될 때 자산 장부에서 감가상각 옵션이 선택됩니다. 

자본화 임계값은 자산이 지정된 금액을 충족할 경우 감가상각되는지 여부를 결정하는 통화 금액입니다. 예를 들어, 자산을 구매하고 구매 금액이 자본화 임계값보다 적은 경우 자산은 감가상각 대상이 아닙니다. 구매 금액이 임계값을 충족하거나 초과하면 자산이 감가상각되도록 지정됩니다. 

고정 자산 그룹 페이지에서 자본화 임계값을 설정할 수 있습니다.

## <a name="scenario"></a>시나리오
다음 시나리오는 고정 자산 및 지급 계정 통합의 전체 주기에 대해 설명합니다. 샘플 설정이 표시되고 획득 제안의 사용도 설명됩니다. 

이 시나리오에서 시스템은 다음과 같이 설정됩니다.

-   자산은 제품 수령 또는 공급업체 송장 전기 중에 자동으로 생성되지만 고정 자산은 지급 계정에서 취득 트랜잭션을 전기하지 못하도록 설정됩니다.
-   계정은 품목 그룹 페이지의 고정 자산 수령 및 고정 자산 발행 계정 유형에 대한 계정 타입 필드에 지정됩니다.
-   컴퓨터 그룹(COMP)의 자본화 사용 임계값은 1,500입니다.
-   당신의 임무는 직원이 사용할 새 노트북에 대한 구매 주문을 입력하고, 구매 주문을 게시하고, 배송 직원이 제품 영수증을 게시하는지 확인하고, 공급업체 송장을 게시한 다음, 회계사가 노트북 자산을 진행 중 상태로 업데이트하는지 확인하는 것입니다.

시작하려면 구매 주문 페이지를 사용하여 1,600의 비용이 드는 노트북에 대한 세부 정보를 입력합니다. 구매 주문 라인의 고정 자산 빠른 탭에서 새 고정 자산을 선택하시겠습니까? 옵션을 선택하고 고정 자산 그룹으로 COMP를 선택하고 구매 주문을 저장합니다. 

노트북이 입고되면 배송담당자가 입장하여 제품 영수증을 게시하여 노트북의 영수증을 기록합니다. 노트북 자산이 생성되었으며 아직 획득하지 않음 상태입니다. 금액이 자본화 임계값을 초과합니다. 따라서 감가상각 옵션은 랩톱 자산에 대한 장부에서 선택됩니다. 다음 거래가 발생했습니다.

| 설명                               | 거래처             | 차변    | 대변   |
|-------------------------------------------|---------------------|----------|----------|
| 구매, 제품 영수증 구매        | 청구되지 않은 영수증 | 1,600.00 |          |
| 구매, 제품 영수증 구매 상쇄 | 미수 구매   |          | 1,600.00 |

그런 다음 랩톱에 대한 공급업체 송장을 전기합니다. 공급업체 송장이 전기될 때 자산 취득 트랜잭션이 전기되지 않도록 고정 자산이 설정되어 있기 때문에 랩탑 상태는 변경되지 않습니다. 공급업체 송장이 전기될 때 새 고정 자산 생성 옵션이 선택되었습니다. 따라서 고정 자산 입고 계정이 사용됩니다. 전기된 취득이 없기 때문에 고정 자산 발행 계정이 사용되지 않았습니다. 나중에 조직의 회계사가 인수 제안을 사용하여 고정 자산에 인수 거래를 게시할 때 사용됩니다. 

다음 거래가 발생했습니다.

| 설명                               | 거래처             | 차변    | 대변   |
|-------------------------------------------|---------------------|----------|----------|
| 구매, 제품 영수증 구매 상쇄 | 미수 구매   | 1,600.00 |          |
| 공급업체 잔액                            | 지급 계정    |          | 1,600.00 |
| 구매, 고정 자산 수령             | 컴퓨터 비용    | 1,600.00 |          |
| 구매, 제품 영수증 구매        | 청구되지 않은 영수증 |          | 1,600.00 |

마지막으로 회계사는 아직 취득하지 않음 상태인 모든 고정 자산을 검토합니다. 따라서 새 랩톱 자산이 검토됩니다. 그런 다음 회계사는 고정 자산 분개장 라인에서 취득 제안 페이지를 열고 송장이 있지만 아직 취득하지 않음 상태인 모든 자산에 대한 취득 거래를 생성합니다. 분개가 전기되면 랩톱 자산의 상태가 미결로 변경됩니다. 고정 자산 발행 계정이 대변에 기입되고 자산 취득 계정이 차변에 기입됩니다. 

다음은 이 시나리오의 변형입니다.

-   공급업체 송장이 전기될 때 자산 취득 트랜잭션이 전기될 수 있도록 고정 자산이 설정된 경우, 회계사는 취득 트랜잭션이 생성되기 때문에 고정 자산에서 취득 제안을 사용할 필요가 없습니다. 또한 공급업체 송장을 게시할 때 다른 계정이 업데이트됩니다. 컴퓨터 비용 대신 고정 자산 입고 재고 계정이 차변에 기입되고 두 가지 추가 트랜잭션이 발생합니다. 자산 취득 계정은 차변에 기입되고 고정 자산 발행 재고 계정은 대변에 기입됩니다.
-   제품 입고가 전기될 때 새 고정 자산 생성 옵션을 선택하지 않으면 해당 시점에 자산이 생성되지 않습니다. 공급업체 송장을 전기하기 전에 새 고정 자산 생성 옵션을 선택하면 자산이 생성되고 상태가 아직 취득되지 않음 또는 공급업체 송장이 전기될 때 취득 트랜잭션도 전기하는 경우 미결 상태가 됩니다.
-   랩톱 비용이 1,600이 아닌 1,400이면 자본화 임계값에 도달하지 않은 것입니다. 따라서 자산이 생성되고 감가상각 옵션이 지워집니다.
-   송장 등록부를 사용하는 경우 송장 등록부가 전기된 후 송장 승인 분개장 페이지를 사용하여 바우처를 검색하고 구매 주문서를 공급업체 송장에 연결하고 새 고정 자산 생성 옵션을 선택한 다음 공급업체 송장을 게시합니다. 취득 거래를 생성할 수 있는 사용자 그룹의 구성원인 경우 취득이 생성되고 자산은 미결 상태가 됩니다.
-   일부 수량만 받은 경우 사용자 그룹 제한으로 인해 첫 번째 공급업체 송장에 대해 자산 취득이 생성되지 않습니다. 주문 수량을 완료한 두 번째 공급업체 송장에 대해 취득을 전기할 수 있는 유일한 방법은 첫 번째 공급업체 송장에 대해 취득 거래가 이미 입력되었고 귀하가 취득을 전기할 수 있는 사용자 그룹의 구성원인 경우입니다.


자세한 내용은 [고정 자산 통합](fixed-asset-integration.md)을 참조하세요.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
