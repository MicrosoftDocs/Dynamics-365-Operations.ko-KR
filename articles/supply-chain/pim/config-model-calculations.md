---
title: 제품 구성 모델 계산
description: 이 항목에서는 제품 구성 모델에서 속성에 대한 계산을 생성하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 349fed3ca75b94db2f421a1ff3c3553c96c202c37d59857a3d973f3de8f995ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447061"
---
# <a name="product-configuration-model-calculations"></a>제품 구성 모델 계산

[!include [banner](../includes/banner.md)]

이 항목에서는 제품 구성 모델에서 속성에 대한 계산을 생성하는 방법에 대해 설명합니다.

## <a name="prerequisites"></a>전제 조건

계산은 제품 구성 모델에서 제품의 구성 값을 계산하는 데 사용됩니다. 계산 설정을 시작하려면 관련 제품 구성 모델이 있어야 합니다. 구성 모델 및 관련 작업의 설정 프로세스에 대한 개요는 [제품 구성 모델 설정](set-up-maintain-product-configuration-model.md)을 참조하세요.

## <a name="create-a-calculation"></a>계산 만들기

계산은 식과 대상 특성으로 구성됩니다. 자세한 내용은 [제품 구성 모델에 대한 계산 FAQ](calculate-product-configuration-models.md)를 참조하세요.

기존 제품 모델에 대한 계산을 생성하려면 다음 단계를 따르세요.

1. **제품 정보 관리 \> 공통 \> 제품 구성 모델** 로 이동합니다.
1. 제품 구성 모델을 열고 **편집** 을 선택합니다.
1. **계산** 빠른 탭에서 **추가** 를 선택하여 계산을 추가하고 다음 필드를 설정합니다.

    - **이름** – 계산의 이름을 입력합니다.
    - **설명** - 계산의 설명을 입력합니다.
    - **대상 특성** – 계산할 특성을 선택합니다.

1. **식 편집** 을 선택합니다.
1. **계산 입력** 대화 상자에서 필요한 속성, 연산자 및 값을 표현식에 추가합니다. 이러한 요소가 작동하는 방식에 대한 자세한 내용은 [제품 구성 모델의 표현식 제약 조건 및 테이블 제약 조건](expression-constraints-table-constraints-product-configuration-models.md)을 참조하세요.
1. 식이 준비되면 **확인** 을 선택합니다.

## <a name="calculation-examples"></a>계산 예

이 섹션에서는 계산 작동 방식을 보여주는 몇 가지 예를 제공합니다.

### <a name="example-1"></a>예시 1

대상 특성은 부울이고 계산은 다음 조건식을 사용합니다.

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

`decimalAttribute2`가 `decimalAttribute1`보다 크거나 같으면 식은 대상 특성에 대해 *True* 값을 반환합니다. 그렇지 않으면 *False* 값을 반환합니다.

### <a name="example-2"></a>예시 2

이 예에서는 text 특성 `textFixedList`를 대상 속성으로 사용합니다. 이 특성에는 다음과 같은 고정 목록이 포함되어 있습니다.

| 값 | 솔버 값 |
|---|---|
| A | 1a |
| B | 2b |
| C | 2c |

다음 스크린샷은 이 속성에 대한 설정이 시스템에서 어떻게 보이는지 보여줍니다.

![예시 2의 속성 유형 설정.](media/model-calculations-example2.png "예시 2의 속성 유형 설정")

속성은 다음 조건문에서 사용됩니다.

`If[integerAttribute < 150, 0, 2]`

`integerAttribute`가 150보다 작으면 이 문은 고정 목록 *A* 에서 첫 번째 레코드의 텍스트 값을 반환합니다. 그렇지 않으면 고정 목록 *C* 에서 세 번째 레코드의 텍스트 값을 반환합니다.

> [!NOTE]
> 고정 목록은 0부터 시작하는 열거형(enum)과 동일하며 해당 값은 적절한 정수 값으로 액세스됩니다. 따라서 첫 번째 고정 목록 값(*A*)이 *0* 과 일치하고, 두 번째 값(*B*)은 *1* 과 일치하고, 세 번째 값(*C*)은 *2* 와 일치합니다.

### <a name="example-3"></a>예시 3

이 예에서는 이전 예의 `textFixedList` 대상 특성을 사용합니다. 또한 다음과 같은 고정 목록이 포함되어 있는 다른 텍스트 특성 `textAttribute`를 사용합니다.

| 값 | 솔버 값 |
|---|---|
| AA | 1aa |
| BB | 2bb |

다음 스크린샷은 이 속성에 대한 설정이 시스템에서 어떻게 보이는지 보여줍니다.

![예 3의 속성 유형 설정.](media/model-calculations-example3.png "예 3의 속성 유형 설정")

`textFixedList` 특성의 값은 다음 조건문을 사용하여 계산됩니다.

`If[textAttribute == "1aa", 0, 2]`

`textAttribute` 값이 *1aa* 와 같은 솔버 값을 가지고 있으면 이 식은 `textFixedList` 고정 목록 *A* 에서 첫 번째 레코드의 텍스트 값을 반환합니다. 그렇지 않으면 `textFixedList` 고정 목록 *C* 에서 세 번째 레코드의 텍스트 값을 반환합니다.

> [!NOTE]
> - 조건문은 속성의 솔버 값을 사용해야 합니다.
> - 고정 목록 텍스트 속성만 계산에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [제품 구성 모델 계산 FAQ](calculate-product-configuration-models.md)
- [제품 구성 모델에 식 제약 조건 추가](tasks/add-expression-constraint-product-configuration-model.md)
- [제품 구성 모델 개요](product-configuration-models.md)
