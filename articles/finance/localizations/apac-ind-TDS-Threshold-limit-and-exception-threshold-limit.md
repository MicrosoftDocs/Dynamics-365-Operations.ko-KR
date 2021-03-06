---
title: 임계값 한도 및 예외 임계값 한도
description: 이 토픽에서는 원천공제세(TDS)에 대한 임계값 및 예외 한도에 대해 설명합니다.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 8391953024f302e75f23c72f8078d59a5541e24b
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451828"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>임계값 한도 및 예외 임계값 한도

[!include [banner](../includes/banner.md)]

이 토픽에서는 원천공제세(TDS)에 대한 임계값 및 예외 한도에 대해 설명합니다. 송장 및 지불에 대한 TDS는 항상 **원천징수세 구성요소** 페이지의 TDS 세금 구성 요소에 대해 정의된 임계값 한도 및 예외 임계값 한도를 고려하여 계산됩니다. TDS 세금 구성요소는 TDS 세금 그룹에 포함된 TDS 세금 코드에 첨부됩니다. TDS 세금 그룹은 송장 수준 또는 지불 수준에서 TDS를 계산하기 위해 공급업체 및 고객에 연결됩니다.

TDS는 트랜잭션 금액 또는 공급업체에 대한 특정 TDS 그룹으로 전기된 누적 트랜잭션 금액이 **원천징수세 구성요소** 페이지에 지정된 임계값 한도를 초과하는 경우 계산됩니다. TDS는 누적 트랜잭션 금액이 지정된 임계값 한도를 초과할 때까지 계산되지 않습니다.

TDS 구성요소에 대한 임계값 한도와 함께 예외 임계값 한도를 지정하면 누적 트랜잭션 금액이 지정된 임계값 한도를 초과하지 않더라도 특정 트랜잭션 금액이 예외 임계값 한도를 초과하는 경우 TDS가 계산됩니다.

### <a name="example"></a>예
TDS라는 세금 구성요소가 설정되어 계약자라는 TDS 세금 그룹에 연결됩니다. 임계값은 50,000으로 정의되었으며 예외 임계값은 TDS 세금 구성요소에 대해 20,000으로 정의되었습니다. TDS 그룹 계약자는 공급업체 1의 기본 TDS 그룹으로 정의됩니다.

구매 송장 001이 공급업체 1에 대해 10000으로 전기됩니다. 송장 금액이 임계값 한도 또는 예외 임계값 한도를 초과하지 않았기 때문에 송장에 대한 TDS가 계산되지 않습니다. 구매 송장 002가 공급업체 1에 대해 25,000으로 전기됩니다. 송장 금액이 예외 임계값 한도를 초과했기 때문에 송장에 대해 TDS가 계산됩니다. 구매 송장 003이 공급업체 1에 대해 20,000으로 전기됩니다. 공급업체에 대해 발행된 송장 3개의 총 송장 금액이 임계값 한도를 초과했기 때문에 송장에 대해 TDS가 계산됩니다. TDS는 이전에 TDS가 계산되지 않은 공급업체에 대해 발행된 모든 송장에 대해 계산됩니다. 따라서 TDS는 송장 001과 003의 총 송장 금액인 30,000에 대해 계산됩니다.

트랜잭션에 연결된 TDS 그룹의 TDS 세금 코드에 대해 **임계값 간과** 확인란이 선택된 경우 임계값 한도 및 예외 임계값 한도는 TDS 계산에 고려되지 않습니다. 임계값 한도는 **임계값 간과** 확인란이 있는 TDS 그룹의 TDS 세금 코드에서 사용되지 않습니다.

일부 송장에 대한 특정 TDS 그룹에 **임계값 간과** 확인란이 선택되었지만 특정 공급업체/고객에 대해 생성된 다른 송장에 대해 선택되지 않은 경우, 일부 송장에 대한 임계값 한도를 간과하지 않고 TDS 계산이 TDS가 이전에 계산되지 않은 모든 송장의 누적 금액을 고려하여 발생할 수 있습니다.

예를 들어 임계값 한도는 25000입니다. 공급업체 A에 대해 다음 송장이 생성됩니다.

- 송장 1 – 2,0000 – (**임계값 간과** 확인란이 선택되지 않음): TDS가 계산되지 않습니다.

- 송장 2 – 4,000 – (**임계값 간과** 확인란이 선택됨): 4,000에 대한 TDS가 계산됩니다.

- 송장 2 – 3,000 – (**임계값 간과** 확인란이 선택되지 않음): TDS는 누적 송장 금액으로 계산됩니다. 즉, 27,000 (20000+4000+3000) 임계값 한도를 초과했습니다. TDS는 이전에 TDS가 계산되지 않은 인보이스의 누적 금액, 즉 23,000 (20000+3000)에 대해 계산됩니다.
