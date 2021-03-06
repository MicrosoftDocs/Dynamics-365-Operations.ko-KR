---
title: 소비 감가상각
description: 이 문서에서는 소비 감가상각 방법에 대한 개요를 제공합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9b97caefcb650f289e7f29f14473e0a22aa5d88
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451054"
---
# <a name="consumption-depreciation"></a>소비 감가상각

[!include [banner](../includes/banner.md)]

이 문서에서는 소비 감가상각 방법에 대한 개요를 제공합니다.

고정 자산에 대한 감가상각 프로필을 설정하고 **감가상각 프로필** 페이지의 **방법** 필드에서 **소비** 를 선택하면, 고정 자산은 사용량에 따라 감가상각 프로필에 할당됩니다. **감가상각 프로필** 페이지에서 비율과 간격을 설정할 필요가 없습니다. 소비 방법을 사용하는 감가상각 프로파일을 생성한 후 다양한 방법으로 방법을 설정할 수 있습니다.

## <a name="set-up-and-use-consumption-depreciation"></a>소비 감가상각 설정 및 사용
1.  **감가상각 프로필** 페이지에서 감가상각 프로필을 생성합니다. 소비 계산의 경우 감가상각 프로필에는 ID와 이름이 있어야 하며 **방법** 필드에서 **소비** 를 선택해야 합니다.
2.  **소비 계수** 페이지에서 소비 계수를 설정합니다. 각 소비 계수에는 ID와 이름이 있어야 하며 수량 또는 백분율로 지정되는 소비 계수가 있어야 합니다.
3.  **소비 단위** 페이지에서 소비 단위를 설정합니다. 각 소비 단위에는 ID와 이름이 있어야 합니다. 감가상각 단위는 **소비 감가상각** 페이지에서 소비 감가상각을 계산하는 데 사용됩니다. 단위의 예로는 킬로미터(km), 킬로그램(kg) 및 시간이 있습니다.
4.  **고정 자산** 페이지에서 개별 고정 자산을 설정합니다. 각 고정 자산에 대해 감가상각 프로필이 있는 가치 모델 및 감가상각 장부를 선택합니다. 고정 자산이 소비 방법을 기반으로 하는 감가상각 프로파일을 사용하는 경우 소비 감가상각에 대한 가치 모델 또는 감가상각 장부를 설정해야 합니다. 이 설정은 **가치 모델** 페이지의 **감가상각** 탭 또는 **감가상각 프로필** 페이지의 **일반** 빠른 탭에서 수행됩니다. 여러 고정 자산에 동일한 가치 모델을 사용할 수 있습니다. 감가상각 프로필은 각 고정 자산에 대해 선택하는 가치 모델 또는 감가상각 장부의 일부입니다. **고정 자산** 페이지에서 직접 감가상각 프로필을 추가하거나 수정할 수 없습니다. **감가상각 장부** 페이지에서만 감가상각 프로필을 수정할 수 있습니다.
5.  **가치 모델** 페이지 또는 **감가상각 장부** 페이지의 **소비 감가상각** 필드 그룹에서 다음 필드에 정보를 입력합니다.
    -   소비 계수
    -   단위
    -   단위 감가상각
    -   예상 소비량

    **전기된 소비** 필드는 고정 자산과 가치 모델의 조합 또는 감가상각 장부에 대해 이미 전기된 소비 감가상각을 단위로 표시합니다. 이 필드의 값은 수동으로 업데이트할 수 없습니다.

## <a name="examples"></a>예
### <a name="example-1"></a>예시 1

다음 소비 계수는 1월 31일에 설정됩니다.

-   수량은 1,000입니다.
-   고정 자산에 대해 지정된 감가상각 단가는 1.5입니다.

1월 31일 감가상각 제안은 다음과 같습니다. 수량 × 단위 감가상각 1,000 × 1.5 = 1,500 고정 자산에 대해 지정된 계수가 백분율 계수인 경우 고정 자산의 가치 모델에 대한 **예상 소비량** 필드에서 예상되는 수량에 선택한 종료 날짜에 대해 설정된 백분율을 곱합니다. 결과 수량은 해당 기간의 감가상각 수량으로 제안됩니다.

### <a name="example-2"></a>예시 2

다음 소비 감가상각 계수는 1월 31일에 설정됩니다.

-   백분율은 10%입니다.
-   고정 자산에 대해 지정된 감가상각 단가는 1.5입니다.
-   고정 자산의 예상 수량은 2,000입니다.

1월 31일의 감가상각 제안은 다음과 같습니다. 예상 수량 × 백분율 × 단위 감가상각 2,000 × .10 × 1.5 = 300





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
