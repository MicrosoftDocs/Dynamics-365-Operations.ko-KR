---
title: 균형 조정 재무 차원은 어떻게 설정하나요?
description: 이 항목에서는 균형 조정 재무 차원 기능을 설정하고 사용하기 위한 옵션에 관해 설명합니다.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: 188c15c4cb0c295a9fcbb08273ddb391fbc29e24
ms.sourcegitcommit: b4c78655f2ab4b0e7ead96dfb9cf087a18014253
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2021
ms.locfileid: "8450964"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>균형 조정 재무 차원은 어떻게 설정하나요?

[!include [banner](../includes/banner.md)]

이 항목에서는 균형 조정 재무 차원 기능을 설정하고 사용하기 위한 옵션에 관해 설명합니다.

## <a name="symptom"></a>증상

균형 조정 재무 차원을 설정하기 위한 두 가지 옵션이 있습니다. 첫 번째 옵션은 **원장** 설정 페이지(**총계정원장 \> 원장 설정 \> 원장**)의 **균형 조정 재무** 차원 필드를 사용하는 것입니다. 두 번째 옵션은 **재무 차원** 페이지(**총계정원장 > 계정 차트 \> 차원 \> 재무 차원**)에서 **차원의 균형 조정이 필요함** 필드를 사용하는 것입니다. 이 항목에서는 이 두 옵션의 차이점을 설명합니다.

## <a name="resolution"></a>해결

조직은 일반적으로 균형 조정 차원을 사용하여 재무 차원 수준에서 균형을 이루는 대차 대조표를 생성합니다. 두 기능 중 하나를 활성화해도 게시된 불균형 차원이 균형을 이루지 않습니다. 두 기능 중 하나를 활성화하기 전에 대차 대조표를 균형 상태로 만들려면 먼저 조정 항목을 수동으로 입력해야 합니다.

두 옵션은 상호 배타적입니다. 조직에서 사용하는 옵션은 비즈니스 요구 사항을 기반으로 해야 합니다. 원장 설정과 재무 차원 설정 모두에서 균형 조정 차원을 정의한 다음 필요한 추가 설정의 일부 또는 전체를 완료하는 고객에 관한 이야기를 자주 듣습니다. 그러나 재무 차원의 불균형으로 인해 여전히 게시할 수 없습니다.

다음 섹션에서는 두 가지 옵션을 설명하고 설정 방법을 설명합니다.

### <a name="ledger--balancing-financial-dimension"></a>원장 – 균형 조정 재무 차원

**원장** 설정 페이지의 차원 균형 조정은 단위 간 회계를 활성화하는 데 사용됩니다. 기능을 켜려면 다음 단계를 따르세요.

1. 균형 조정 차원이 될 재무 차원을 결정합니다.

    - 이 기능을 사용하면 하나의 재무 차원만 균형 조정 차원으로 선택할 수 있습니다.
    - 아직 **원장** 설정 페이지에서 차원을 선택하지 마세요.
    - 대차 대조표가 선택한 재무 차원에 대해 이미 균형을 이루고 있는지 확인합니다.

2. 균형 조정 재무 차원에 대한 계정 구조를 업데이트합니다.

    - 균형 조정 재무 차원은 원장에 할당된 모든 계정 구조에 포함되어야 합니다.
    - 재무 차원은 계정 구조에 공백을 허용하지 않아야 합니다. 이 제한은 총계정원장에 제시된 모든 회계 항목에 재무 차원 값이 포함되도록 합니다. 균형 조정 차원을 사용하는 경우 빈 차원은 유효하지 않습니다.

3. **자동 거래용 계정** 페이지(**총계정원장 \> 게시 설정 \> 자동 거래용 계정**)에서 단위 간 차변 및 대변 주 계정을 정의합니다.
4. **원장** 설정 페이지(**총계정원장 \> 원장 설정 \> 원정**)의 **균형 조정 재무 차원** 필드에서 재무 차원에 균형 조정을 사용하도록 선택합니다.

거래가 입력 및 게시될 때 선택한 재무 차원의 균형이 맞지 않으면 게시 중에 회계 입력의 균형을 맞추는 데 필요한 차변 또는 대변 입력이 시스템에서 자동으로 추가됩니다. 단위 간 거래에 대한 차변 및 대변 원장 계정은 총계정원장의 게시된 전표에 표시됩니다. 그러나 회계 항목이 게시된 분개장이나 출처 문서에는 표시되지 않습니다.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>재무 차원 – 차원의 균형 조정이 필요함

**재무 차원** 페이지의 균형 조정 차원은 일반적으로 공공 부문 회사에서 사용되지만, 기능은 공공 부문 구성 키와 연결되는 것은 아닙니다. 시스템에 제한이 없기 때문에 공공기관이 아니더라도 이 기능을 사용할 수 있습니다.

이 기능은 일반적으로 각 거래의 균형을 자동으로 조정하기 위해 게시 정의를 사용해야 하기 때문에 공공 부문 고객 기반에서 사용됩니다. **자동 거래를 위한 계정** 페이지에 정의된 단위 간 차변 및 대변 계정을 사용하여 회계 항목의 잔액을 자동으로 조정하지 않습니다. 게시 정의가 적용된 후 회계 항목이 차원 수준에서 균형을 이루지 않으면 단위 간 차변 및 대변 계정이 정의된 경우에도 거래가 게시되지 않습니다.

원장 설정과 재무 차원 설정 모두에서 균형 조정 차원을 정의하는 고객에 관해 자주 듣습니다. 이 경우 시스템은 재무 차원 기능을 사용합니다. 재무 차원 수준의 균형 조정 차원 설정은 게시 중에 우선 적용됩니다. 게시 정의가 재무 차원 수준에서 균형 조정 회계 항목을 생성하지 않으면 게시가 실패합니다.

재무 차원 수준에 균형 조정 차원의 사용을 설정하려면 다음 단계를 따릅니다.

1. 균형 조정 차원이 될 재무 차원을 결정합니다.

    - 둘 이상의 재무 차원을 균형 조정 차원으로 설정할 수 있습니다.
    - 아직은 **재무 차원** 페이지에서 거래의 균형을 맞추는 데 필요한 재무 차원을 설정하지 마세요.

2. 조직에서 사용하는 각 유형의 분개장 또는 소스 문서에 대한 기장 정의를 정의합니다. 기장 정의는 게시되지 않은 분개장 또는 소스 문서의 원장 계정을 '일치 기준'으로 사용합니다. 그런 다음 기장 정의는 회계 항목이 되는 '생성된 항목'을 반환합니다. 기장 정의가 올바르게 설정된 경우 생성된 항목에는 대응 기준 원장 계정과 차원 수준에서 회계 항목의 균형을 맞추기 위한 추가 계정이 포함됩니다. 자세한 내용은 [기장 정의](posting-definitions.md)를 참조하세요. 
   
   기장 정의는 모든 유형의 거래에서 지원되지는 않습니다. 예를 들어, 일반 분개장이나 고정 자산 분개장을 통해 입력된 거래에 대해서는 기장 정의를 정의할 수 없습니다. 분개장 또는 소스 문서에 대해 기장 정의를 정의할 수 없는 경우 재무 차원 값에서 거래를 수동으로 균형 조정해야 합니다. 예를 들어 일반 분개장 항목이 작성되고 부서 차원이 균형 조정 차원인 경우 각 부서 값이 균형을 이루고 있는지 확인해야 합니다.  차원이 각 부서 값에 대해 균형이 맞지 않으면 전표에 단위 간 차변 또는 대변을 수동으로 추가하여 불균형을 수정할 때까지 전표가 게시되지 않습니다. 

    > [!IMPORTANT]
    > 과도한 수의 거래를 수동으로 균형 조정해야 하는 경우 **재무 차원** 페이지에서 균형 조정 차원 기능을 **사용하지 마세요**. 대신 **원장** 설정 페이지에서 균형 차원 기능을 사용하세요.

3. 기장 정의를 정의한 후 재무 차원을 균형 조정에 필요한 것으로 표시할 수 있습니다.

거래를 입력하고 게시할 때 게시하는 동안 기장 정의가 호출되어 회계 항목을 결정합니다. 재무 차원이 균형을 이루면 회계 항목이 결정된 후 유효성 검사가 수행됩니다. 재무 차원의 균형이 맞지 않으면 거래가 게시되지 않으며 차변이 특정 차원의 대변과 같지 않다는 메시지를 받게 됩니다.