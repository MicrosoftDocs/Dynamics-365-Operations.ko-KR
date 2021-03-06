---
title: 여러 고객 또는 공급업체 기록이 있는 단일 바우처
description: 이 항목에서는 여러 고객 또는 공급업체 레코드와 함께 단일 바우처를 게시할 때 발생하는 상황에 대한 개요를 제공합니다. 이 기능은 향후 버전의 Microsoft Dynamics 365 Finance에서 중단될 예정이므로 정산 처리에 회계 영향이 있으므로 이 게시 방법을 사용하지 않는 것이 좋습니다.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8677eba2c38c6273555e1189c0153272a8ff9e005655f3846c0d7605b872ff94
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450367"
---
# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>여러 고객 또는 공급업체 기록이 있는 단일 바우처

[!include [banner](../includes/banner.md)]

이 항목에서는 여러 고객 또는 공급업체 레코드와 함께 단일 바우처를 게시할 때 발생하는 상황에 대한 개요를 제공합니다. 이 기능은 향후 버전에서 중단될 예정이므로 정산 처리에 회계 영향이 있으므로 이 게시 방법을 사용하지 않는 것이 좋습니다. 

여러 고객 또는 공급업체에 대해 하나의 바우처가 사용되는 몇 가지 일반적인 예에는 고객 간 잔액 이전 및 동일한 조직의 고객과 공급업체 간의 상계 잔액이 포함됩니다. 

두 명 이상의 고객 또는 공급업체가 포함된 바우처는 다음 방법 중 하나를 사용하여 입력할 수 있습니다.

-   **단일 바우처 번호만** 옵션이 선택된 분개장을 사용하여 분개장에 추가된 모든 줄이 동일한 바우처에 포함되도록 합니다.
-   상계 원장 계정이 없는 다중 라인 바우처를 두 명 이상의 고객 또는 공급업체와 함께 사용합니다.
-   계정, 상쇄 계정이 공급업체/공급업체, 고객/고객, 공급업체/고객 또는 고객/공급업체인 바우처를 입력합니다.

이 항목은 여러 고객 또는 공급업체 레코드가 있는 하나의 바우처가 게시될 때 결제가 처리되는 방법을 보여줍니다. 또한 이 항목에서는 여러 고객 또는 공급업체에서 하나의 바우처를 사용하지 않는 방법을 이해하는 데 도움이 되는 해결 방법을 제공합니다. 특히, 여러 고객 또는 공급업체와 함께 하나의 바우처를 사용하면 영향을 받는 두 가지 일반적인 결제 시나리오를 보여주는 예가 있습니다.

-   현금 할인 회계
-   재평가 회계

## <a name="how-does-settlement-impact-single-voucher-usage"></a>결제가 단일 바우처 사용에 미치는 영향
여러 고객 또는 공급업체 레코드가 포함된 전표를 게시할 때 여러 미수금 또는 미지급금 잔액이 포함된 단일 회계 전표가 생성됩니다. 결산 프로세스 동안 원래 회계 입력은 현금 할인, 미실현 손익, 실현 손익, 원본 문서의 요약 계정 경감에 대한 회계 입력을 생성하는 데 사용됩니다. 예를 들어, 송장에 대한 공급업체 지불을 정산할 때 현금 할인이 적용되는 경우 현금 할인 회계는 원래 송장에서 미지급금 원장 계정으로 전기해야 합니다. 원래 송장이 여러 공급업체 레코드가 포함된 전표에 전기된 경우 원래 회계가 요약됩니다. 이 경우 단일 바우처에서 각 공급업체 거래에 대한 자세한 회계 항목에 액세스할 수 있는 방법이 없기 때문에 사용자가 현금 할인을 계산하는 방법을 결정할 방법이 없습니다.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>여러 벤더가 있는 하나의 바우처와 현금 할인 회계에 미치는 영향

다음 예제에서는 여러 공급업체 송장이 **총계정원장** 페이지의 단일 바우처에 총계정원장에 기록됩니다. 이러한 송장은 여러 계정 차원에 배포됩니다.

| 바우처 | 계정 유형 | 거래처  | 설명 | 차변 | 크레딧 |
|-------------|------------------|--------------|-----------------|-----------|------------|
| GNJL001     | 공급업체           | 1001         | INV1            |           | 100.00     |
| GNJL001     | 공급업체           | 1001         | INV2            |           | 200.00     |
| GNJL001     | 공급업체           | 1001         | INV3            |           | 300.00     |
| GNJL001     | 원장           | 606300-001-- | INV1            |   50.00   |            |
| GNJL001     | 원장           | 606300-002-- | INV1            |   50.00   |            |
| GNJL001     | 원장           | 606300-003-- | INV2            | 200.00    |            |
| GNJL001     | 원장           | 606300-004-- | INV3            | 300.00    |            |

게시 후 하나의 바우처가 생성됩니다.

| 바우처 | 거래처  | 전기 유형 | 트랜잭션 통화 금액 |
|-------------|--------------|------------------|------------------------------------|
| GNJL001     | 606300-001-- | 원장 분개장   | 50.00                              |
| GNJL001     | 606300-002-- | 원장 분개장   | 50.00                              |
| GNJL001     | 606300-003-- | 원장 분개장   | 200.00                             |
| GNJL001     | 606300-004-- | 원장 분개장   | 300.00                             |
| GNJL001     | 200110-001-  | 공급업체 잔액   | -100.00                            |
| GNJL001     | 200110-001-  | 공급업체 잔액   | -200.00                            |
| GNJL001     | 200110-001-  | 공급업체 잔액   | -300.00                            |

바우처에는 단일 바우처의 전기 공급업체 잔액 유형에 대한 세 가지 항목이 포함되어 있습니다. 606300-001에 대한 50.00 차변과 606300-002에 대한 50.00 차변이 200110-001의 공급업체 잔액 항목을 상쇄하기 위한 것임을 나타낼 방법이 없습니다. 이는 사용자가 단일 바우처에 여러 공급업체 레코드를 입력했기 때문입니다.

이 예를 사용하여 하나의 바우처를 사용하는 것이 다운스트림 결제 회계에 미치는 영향을 분석할 수 있습니다. 200.00 송장 중 197.00을 지불하고 3.00의 현금 할인을 적용한다고 가정합니다. 현금 할인 계정 값은 송장 전표의 비용 계정에서 모든 차원에 걸쳐 할당됩니다. 위의 송장을 게시하는 데 하나의 바우처가 사용되었기 때문입니다. 사용자가 비용 분배를 단일 바우처의 공급업체 잔액과 어떻게 연관시키려 했는지 표시하지 않았기 때문입니다.

| 바우처 | 거래처  | 전기 유형     | 차변 | 크레딧 |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | 공급업체 잔액       | 197.00    |            |
| APPAYM001   | 110110-001-  | 은행                 |           | 197.00     |
| 14000056    | 520200-001-- | 공급업체 현금 할인 |           | 0.25       |
| 14000056    | 520200-002-- | 공급업체 현금 할인 |           | 0.25       |
| 14000056    | 520200-003-- | 공급업체 현금 할인 |           | 1.00       |
| 14000056    | 520200-004-- | 공급업체 현금 할인 |           | 1.50       |
| 14000056    | 200110-001-  | 공급업체 잔액       | 3.00      |            |

사용자가 하나의 바우처 대신 원래 송장의 모든 비용 분배에 대해 현금 할인이 할당되는 것에 만족하지 못하는 경우 여러 바우처를 사용하여 송장을 기록해야 합니다. 다음은 이 예의 시작 부분에 표시된 대로 하나의 바우처를 사용하는 대신 총계정원장에 여러 개의 바우처를 입력할 수 있는 방법의 예입니다.

| 바우처 | 계정 유형 | 거래처  | 설명 | 차변 | 크레딧 | 상쇄 유형 | 상쇄 계정 |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL001     | 공급업체           | 1001         | INV1            |           | 100.00     | 원장          | &lt;비어 있음&gt;      |
| GNJL001     | 원장           | 606300-001-- | INV1            |   50.00   |            | 원장          | &lt;비어 있음&gt;      |
| GNJL001     | 원장           | 606300-002-- | INV1            |   50.00   |            | 원장          | &lt;비어 있음&gt;      |
| GNJL002     | 공급업체           | 1001         | INV2            |           | 200.00     | 원장          | 606300-003--       |
| GNJL003     | 공급업체           | 1001         | INV3            |           | 300.00     | 원장          | 606300-004--       |

이제 INV2가 지급되면 다음과 같이 입력됩니다. 현금 할인의 재무 차원은 관련 비용의 재무 차원을 따릅니다.

| 바우처 | 거래처  | 전기 유형     | 차변 | 크레딧 |
|-------------|--------------|----------------------|-----------|------------|
| APPAYM001   | 200110-001-  | 공급업체 잔액       | 197.00    |            |
| APPAYM001   | 110110-001-  | 은행                 |           | 197.00     |
| 14000056    | 520200-003-- | 공급업체 현금 할인 |           | 3.00       |
| 14000056    | 200110-001-  | 공급업체 잔액       | 3.00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>여러 벤더가 있는 하나의 바우처와 실현 이익/손실 회계에 미치는 영향

| 바우처 | 계정 유형 | 거래처 | 설명 | 차변 | 크레딧 | 계정 유형 | 거래처  |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| GNJL001     | 공급업체           | 1001        | INV1            |           | 100.00     | 원장           | 606300-001-- |
| GNJL001     | 공급업체           | 1001        | INV2            |           | 200.00     | 원장           | 606300-002-- |

다음 예제에서는 여러 공급업체 송장이 **총계정원장** 페이지의 단일 바우처에 총계정원장에 기록됩니다. 이러한 송장은 여러 계정 차원에 배포됩니다. 게시 후 하나의 바우처가 생성됩니다.

| 바우처 | 거래처  | 전기 유형 | 트랜잭션 통화 금액(EUR) | 회계 통화 금액(USD) |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| GNJL001     | 606300-001-- | 원장 분개장   | 100.00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | 원장 분개장   | 200.00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | 공급업체 잔액   | -100.00                                  | -114.00                                 |
| GNJL001     | 200110-001-  | 공급업체 잔액   | -200.00                                  | -228.00                                 |

바우처에는 단일 바우처의 전기 공급업체 잔액 유형에 대한 두 가지 항목이 포함되어 있습니다. 606300-001에 대한 차변이 200110-001에 대한 100.00의 공급업체 잔액 항목을 상쇄하기 위한 것임을 나타낼 방법이 없습니다. 이는 사용자가 단일 바우처에 여러 공급업체 레코드를 입력했기 때문입니다. 

이 예를 사용하여 하나의 바우처를 사용하는 것이 다운스트림 결제 회계에 미치는 영향을 분석할 수 있습니다. 회계 통화가 USD이고 위의 거래가 EUR의 거래 통화로 전기되었다고 가정합니다. 200.00 EUR 송장을 완전히 지불했지만 송장을 게시한 시점과 지불 시점 사이의 환율 차이로 인해 실현 손실이 발생했다고 가정합니다. 실현 손실 계정 값은 송장 전표의 비용 계정에서 모든 차원에 걸쳐 할당됩니다. 이 경우 결제 중인 송장의 비용 계정에 002만 속하는 것으로 사용자가 인식할 수 있지만 차원 001과 002가 모두 할당되었습니다. 이는 하나의 바우처가 위의 송장을 게시하는 데 사용되었기 때문에, 사용자가 단일 바우처에 공급업체의 균형과 관련되는 비용 분배의 의도를 나타낼 방법이 없기 때문입니다.

| 바우처 | 거래처 | 전기 유형   | 트랜잭션 통화 금액(EUR) | 회계 통화 금액(USD) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | 공급업체 잔액     | 200.00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | 은행               | -200.00                                  | -230.00                                 |
| 14000056    | 801300-001- | 환율 손실 | 0.00                                     | 0.67                                    |
| 14000056    | 801300-002- | 환율 손실 | 0.00                                     | 1.33                                    |
| 14000056    | 200110-001- | 공급업체 잔액     |                                          | -2.00                                   |

사용자가 하나의 바우처 대신 원래 송장의 모든 비용 분배에 대해 환율 손실이 할당되는 것에 만족하지 못하는 경우 여러 바우처를 사용하여 송장을 기록해야 합니다. 다음은 이 예의 시작 부분에 표시된 대로 하나의 바우처를 사용하는 대신 총계정원장에 여러 개의 바우처를 입력할 수 있는 방법의 예입니다.

| 바우처 | 계정 유형 | 거래처 | 설명 | 차변 | 크레딧 | 상쇄 유형 | 상쇄 계정 |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| GNJL002     | 공급업체           | 1001        | INV1            |           | 100.00     | 원장          | 606300-001--       |
| GNJL003     | 공급업체           | 1001        | INV2            |           | 200.00     | 원장          | 606300-002--       |

이제 INV2가 지급되면 다음과 같이 입력됩니다. 환율 손실의 재무 차원은 관련 비용의 재무 차원을 따릅니다.

| 바우처 | 거래처 | 전기 유형   | 트랜잭션 통화 금액(EUR) | 회계 통화 금액(USD) |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| APPAYM001   | 200110-001- | 공급업체 잔액     | 200.00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | 은행               | -200.00                                  | -230.00                                 |
| 14000056    | 801300-002- | 환율 손실 | 0.00                                     | 2.00                                    |
| 14000056    | 200110-001- | 공급업체 잔액     |                                          | -2.00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>잔액 이전 및 순이익 시나리오에 대한 하나의 바우처
여러 고객 또는 공급업체가 포함된 하나의 바우처를 사용하는 일반적으로 사용되는 두 가지 시나리오에는 한 고객/공급업체에서 다른 고객/공급업체로의 잔액 이전과 동일한 조직인 고객과 공급업체의 상계가 포함됩니다. 다음 두 가지 예는 하나의 바우처에 시나리오를 입력하는 대신 이러한 시나리오를 입력할 때 선호하는 방법을 보여줍니다. 

*잔액 이체* 는 여러 고객이 있는 하나의 바우처로, 한 고객에서 다른 고객으로 잔액을 이전하기 위해 입력됩니다(공급업체도 동일). 이 시나리오는 자회사가 모회사에 책임을 전가하는 등 송장 결제 책임이 다른 당사자에게 전가될 때 발생할 수 있습니다. 

이 예에서는 10일 이내에 결제되는 경우 고객이 현금 할인을 받을 수 있는 판매를 가정합니다. 이 예에서 고객은 송장 결제를 책임질 보험 회사를 활용합니다. 그 보험 회사는 그 시스템에서 두 번째 고객으로 설정됩니다. 원래 고객의 잔액은 보험사가 보험료를 납부하고, 할인 기간 내 납부하면 2%의 현금 할인을 받습니다. 

설명을 위해 고객 ACME에게 다음 판매가 이루어졌다고 가정합니다. 다음 회계 항목은 판매를 나타냅니다.

| 원장 계정 | 전기 유형 | 차변 | 크레딧 |
|--------------------|------------------|-----------|------------|
| 401100-002-023-    | 수익          |           | 100        |
| 130100-002-        | 고객 잔액 | 100       |            |

다음으로, 사용자는 미수금 지급 저널에 있는 하나의 바우처에 ACME의 미지불 잔액을 보험 회사로 이체합니다. 보험 회사는 고객 보험으로 설정됩니다.

| 바우처 | 계정 유형 | 거래처 | 설명 | 차변 | 크레딧 | 상쇄 유형 | 상쇄 계정 |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | 고객         | ACME        | 전송        |           | 100.00     | 고객        | 보험          |

위의 항목은 하나의 바우처에 포함되어 있습니다. 이 바우처에는 두 개의 고객 기록이 포함되어 있습니다. 위의 총계정원장 항목이 전기되면 다음 바우처가 생성됩니다.

| 바우처 | 거래처 | 전기 유형 | 트랜잭션 통화 금액 |
|-------------|-------------|------------------|------------------------------------|
| ARPAYM001   | 130100-002- | 고객 잔액 | 100.00                             |
| ARPAYM001   | 130100-002- | 고객 잔액 | -100.00                            |

그런 다음 보험 고객으로부터 98.00에 대한 결제를 받고 잔액 이체로 생성된 송장으로 결제를 결제하기로 선택했다고 가정합니다. 이렇게 하면 다음 바우처가 게시됩니다. 정산이 원래 송장의 재무 차원을 사용할 것이라는 예상이 있을 수 있지만, 보험 고객에 대한 송장 문서가 없기 때문에 불가능합니다. 기본적으로 현금 할인의 분배 차원은 원래 송장의 수익 계정이 아니라 이전에서 생성된 고객 거래에서 비롯됩니다. 기본값은 하나의 바우처를 사용하여 잔액을 전송한 결과입니다.

| 바우처 | 거래처 | 전기 유형 | 차변 | 크레딧 |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM002   | 110110-002- | 은행             | 98.00     |            |
| ARPAYM002   | 130100-002- | 고객 잔액 |           | 98.00      |

현금 할인에 대한 관련 바우처에서는 재무 차원에 대한 기본값이 이전으로 인해 생성된 고객 트랜잭션에서 비롯되는데, 이는 이전이 둘 이상의 고객을 가지고 있기 때문입니다.

| 바우처 | 거래처 | 전기 유형       | 차변 | 크레딧 |
|-------------|-------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002- | 고객 현금 할인 | 2.00      |            |
| ARP-00001   | 130100-002- | 고객 잔액       |           | 2.00       |

사용자가 현금 할인에 대한 재무 차원의 기본값에 만족하지 못할 경우, 하나의 바우처 대신 복수의 바우처를 사용하여 잔액 이전을 기록해야 합니다. 이 시나리오는 잔액이 이동된 고객에 대한 크레딧 메모와 잔액이 이동된 고객에 대한 차변 메모 또는 송장을 생성하여 달성해야 합니다. 다음 예는 이 사례의 앞부분에서 보듯이 하나의 바우처를 사용하는 대신 잔액을 이전하기 위해 여러 개의 바우처를 계정 수취 계정 결제 분개장에 입력할 수 있는 방법을 보여줍니다.

| 바우처 | 계정 유형 | 거래처 | 설명 | 차변 | 크레딧 | 상쇄 유형 | 상쇄 계정 |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| ARPAYM001   | 고객         | ACME        |                 |           | 100.00     | 원장          | 401100-002-023-    |
| ARPAYM002   | 고객         | 보험   |                 | 100.00    |            | 원장          | 401100-002-023-    |

즉, 보험 고객이 바우처 ARPAYM02로 98.00을 결제할 때 바우처 ARPAYM002의 원장 계좌 입력에서 정확한 재무 차원이 사용됩니다.

| 바우처 | 거래처 | 전기 유형 | 차변 | 크레딧 |
|-------------|-------------|------------------|-----------|------------|
| ARPAYM003   | 110110-002- | 은행             | 98.00     |            |
| ARPAYM003   | 130100-002  | 고객 잔액 |           | 98.00      |

현금 할인 관련 바우처에는 ARPAYM002 바우처에 표시된 상계 수입 계좌에서 재무 차원이 사용됩니다.

| 바우처 | 거래처     | 전기 유형       | 차변 | 크레딧 |
|-------------|-----------------|------------------------|-----------|------------|
| ARP-00001   | 403300-002-023- | 고객 현금 할인 | 2.00      |            |
| ARP-00001   | 130100-002-     | 고객 잔액       |           | 2.00       |

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>여러 고객, 공급업체를 위한 순금액 계산이 포함된 하나의 바우처
순금액 계산은 조직이 동일한 회사를 구매하고 판매할 때 유용할 수 있습니다. 공급업체 송장을 지불하고 고객 송장에 대한 지불을 받기를 기다리는 대신 공급업체와 고객 송장의 순금액이 계산됩니다. 순 트랜잭션은 미결제 잔액에 대해 결제됩니다. 

예를 들어, 공급업체 1001과 고객 US-008이 동일한 실체이므로, 조직은 남은 잔액을 결제/수령하기 전에 미수금 잔액을 차액으로 계산하려고 합니다. 고객 기록이 75.00 EUR을 빚지고 공급업체 기록이 100.00 EUR을 빚지고 있다고 가정하면 잔액을 차감한 후 공급업체에게 25.00 EUR을 결제하는 것이 좋습니다. 또한 회계 통화가 USD라고 가정합니다. 이 경우, 순트랜잭션은 미결제 계좌 결제 분개장에 하나의 바우처에 입력됩니다.

| 바우처 | 계정 유형 | 거래처 | 설명 | 차변 | 크레딧 | 상쇄 유형 | 상쇄 계정 |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| APPAYM001   | 공급업체           | 1001        | 상계         |  75.00    |            | 고객        | US-008             |

이 트랜잭션에 대한 향후 결제와 관련된 원치 않는 문제를 방지하려면 하나의 바우처를 사용하는 대신 여러 개의 바우처를 분개장에 입력하여 순트랜잭션을 기록해야 합니다. 고객, 공급업체 잔액은 여러 고객, 공급업체 잔액이 포함된 하나의 바우처를 사용하지 않도록 단일 지급 계정으로 상쇄됩니다.

| 바우처 | 계정 유형 | 거래처 | 설명 | 차변 | 크레딧 | 상쇄 유형 | 상쇄 계정 |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| 001         | 고객         | US-008      |                 |           |  75.00     | 원장          | 999999---          |
| 002         | 공급업체           | 1001        |                 |  75.00    |            | 원장          | 999999---          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]