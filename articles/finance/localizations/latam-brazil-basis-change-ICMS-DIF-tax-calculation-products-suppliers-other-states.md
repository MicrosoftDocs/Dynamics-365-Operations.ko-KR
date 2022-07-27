---
title: 다른 주의 공급업체 제품에 대한 ICMS-DIF 세금 계산의 기준 변경
description: 이 항목에서는 브라질의 Rio Grande do Sul(RS) 또는 São Paulo(SP) 주에서 회계 문서를 수신할 때 ICMS-DIF 세금 유형 계산을 위한 구성에 관해 설명합니다.
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 16f78b85567e6d08c588e621119513ff070bf618
ms.sourcegitcommit: 68655c5673aef9892063e5913ffee6bfc3817387
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2022
ms.locfileid: "8451492"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>다른 주의 공급업체 제품에 대한 ICMS-DIF 세금 계산의 기준 변경

이 항목에서는 브라질의 Rio Grande do Sul(RS) 또는 São Paulo(SP) 주에서 회계 문서를 수신할 때 **ICMS-DIF** 세금 유형 계산을 위한 구성에 관해 설명합니다.

주법의 정의에 따르면 다음 규칙에 따라 ICMS(Imposto sobre Circulação de Mercadorias e Serviços)를 징수해야 합니다.

*징수할 ICMS* = ([(*운영 금액* – *원본의 ICMS*) ÷ (1 – *ICMS % 내부*)] × *ICMS % 내부*) – *원본의 ICMS 금액*

## <a name="example"></a>예

RS 주의 브라질 회사는 SP 주의 공급업체로부터 구매를 위한 회계 문서를 받습니다. 회사는 RS 주(18%)와 SP 주(12%) 간의 ICMS 비율 차이를 징수해야 합니다. 다만, 기준은 앞의 규정에 따라 계산해야 합니다.

- **운영 금액:** 1,000.00 브라질 레알(R$ 1,000.00)
- **ICMS 주간:** R$ 120.00
- **RS 주의 ICMS 백분율:** 18%
- **RS 주에서 징수할 ICMS:** (\[(1,000 – 120) ÷ (1 – 0.18)\] × 0.18 ) – 120 = R$ 73.17 

## <a name="resolution"></a>해결

RS 주의 규칙에 따라 차등 ICMS(ICMS-DIF)를 계산하려면 다음과 같은 방식으로 판매세 코드와 판매세 그룹을 설정해야 합니다.

1. 12% ICMS(다른 주의 경우)를 수신하려면 판매세 코드를 만듭니다. 이 코드는 공급업체에서 받을 세금을 등록하는 데 사용됩니다.
2. ICMS-DIF를 징수하기 위한 판매세 코드를 만듭니다. 이 판매세 코드는 18%와 12% 간의 차이를 정의하기 위해 18%(자신의 주의 경우)의 백분율 금액을 가져야 합니다. 세금 유형을 **ICMS-DIF** 로 설정합니다. 이 판매세 코드는 계산 매개 변수에서 다음과 같은 방식으로 정의되어야 합니다.

    - **기준** 필드에서 **총액 비율** 을 선택합니다.
    - **한계 기준** 필드에서 **라인당 순액** 또는 **송장 잔액의 순액** 을 선택합니다.
    - 회계 값이 **3** 이 되도록 과세 코드를 정의합니다. 이런 식으로 **회계 장부** 모듈이 활성화되면 조정 거래가 자동으로 생성됩니다.
    - 판매세 그룹 구성에서 **ICMS-DIF** 판매세 코드에 대해 **사용세** 옵션을 선택합니다.
