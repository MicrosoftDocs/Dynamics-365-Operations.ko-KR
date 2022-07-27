---
title: 제품 구성 모델 계산 FAQ
description: 이 항목에서는 제품 구성 모델에 대한 계산을 설명하고 제약 조건과 함께 계산을 사용하는 방법을 설명합니다.
author: t-benebo
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9463fac363f6bb25c1bd2afebe5737e47aa8b3cf
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448348"
---
# <a name="calculations-for-product-configuration-models-faq"></a>제품 구성 모델 계산 FAQ

[!include [banner](../includes/banner.md)]

이 항목에서는 제품 구성 모델에 대한 계산을 설명하고 제약 조건과 함께 계산을 사용하는 방법을 설명합니다.

계산은 산술 또는 논리 연산에 사용할 수 있습니다. 제품 구성 모델의 표현 제약 조건을 보완합니다. **제약 기반 제품 구성 모델 세부 정보** 페이지에서 계산을 정의한 다음 표현식 편집기에서 계산을 위한 표현식을 작성할 수 있습니다. 자세한 내용은 계산 생성을 참조하세요.

## <a name="what-is-a-calculation"></a>계산이란 무엇입니까?
계산은 제품 구성 모델에서 사용할 수 있는 요소입니다. 계산은 제품을 구성할 때 10진수를 사용하여 값을 계산할 수 있도록 하여 제약 조건을 보완합니다. 또한 계산에는 제약 조건보다 더 많은 사용 가능한 연산자 집합이 있습니다.  

제약 조건과 마찬가지로 계산은 제품 구성 모델의 특정 구성 요소와 연결되며 다른 구성 요소에서 재사용하거나 공유할 수 없습니다. 계산과 제약 조건의 중요한 차이점 중 하나는 계산이 명령적(단방향)인 반면 제약 조건은 선언적(양방향)이라는 점입니다. 제약 조건에 대한 자세한 내용은 [제품 구성 모델의 표현식 제약 조건 및 테이블 제약 조건](expression-constraints-table-constraints-product-configuration-models.md)을 참조하세요.  

계산은 대상 속성과 계산 식으로 구성됩니다.

## <a name="what-is-a-target-attribute"></a>대상 속성이란 무엇입니까?
대상 속성은 계산식의 결과를 받는 속성입니다.  

다음 표현식에서 대상 속성은 식탁보 측정입니다.  

**식:** If\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]  

**DecimalAttribute1** 은 테이블 길이이고 **decimalAttribute2** 는 식탁보 길이입니다. **decimalAttribute2** 가 **decimalAttribute1** 보다 크거나 같으면 식은 대상 특성에 대해 **True** 값을 반환합니다. 그렇지 않으면 식은 **False** 를 반환합니다. 따라서 식탁보 길이가 테이블 길이와 같거나 초과하면 식탁보 측정이 허용됩니다.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>대상 속성으로 설정할 수 있는 속성 유형은 무엇입니까?
제품 구성자가 지원하는 모든 속성 유형은 고정 목록이 없는 텍스트를 제외하고 대상 속성으로 설정할 수 있습니다.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>대상 속성의 값이 계산에서 입력 속성의 값을 제한할 수 있습니까?
아니요, 계산이 단향성이므로 대상 속성의 값은 입력 속성의 값을 제한할 수 없습니다. 따라서 대상 속성의 값은 입력 속성 값의 변경에 따라 설정되지만 대상 값의 변경은 입력 속성 값에 영향을 미치지 않습니다. 이 동작은 제약 조건의 동작과 다릅니다. 제약 조건은 양방향으로 발생합니다.

### <a name="example"></a>예

다음 식에서 계산 대상은 전원 코드의 길이이고 입력 값은 색상입니다.  

**식:** \[If Color == "Green", 1.5, 1.0\]  

항목을 구성할 때 색상 특성의 값으로 **Green** 을 지정할 경우 전원 코드의 길이는 **1.5** 로 설정됩니다. 다른 색상을 지정하면 길이가 **1.0** 으로 설정됩니다. 그러나 계산은 단방향이기 때문에 길이를 **1.5** 로 지정할 경우 계산은 색상 속성 값을 **Green** 으로 설정하지 않습니다.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>계산에 정수 유형의 대상 속성이 있지만 계산에서 십진수를 생성하는 경우 어떻게 됩니까?
대상 속성이 정수 유형이지만 계산에서 십진수를 생성하는 경우 계산된 결과의 정수 부분만 반환됩니다. 소수 부분이 제거되고 결과가 반올림되지 않습니다. 예를 들어, 12.70의 결과는 12로 표시됩니다.

## <a name="when-do-calculations-occur"></a>계산은 언제 발생합니까?
모든 입력 속성에 값이 제공되면 계산이 발생합니다.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>대상 속성에 대해 계산된 값을 덮어쓸 수 있습니까?
대상 속성이 숨김 또는 읽기 전용으로 설정되지 않은 경우 대상 속성에 대해 계산된 값을 덮어쓸 수 있습니다.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-read-only"></a>대상 속성을 숨김 또는 읽기 전용으로 설정하려면 어떻게 합니까?
속성을 숨김 또는 읽기 전용으로 설정하려면 다음 단계를 따르세요.

1.  **제품 정보 관리** &gt; **공통** &gt; **제품 구성 모델** 을 클릭합니다.
2.  제품 구성 모델을 선택한 다음 작업 창에서 **편집** 을 클릭합니다.
3.  **제약 기반 제품 구성 모델 세부 정보** 페이지에서 대상 속성으로 사용할 속성을 선택합니다.
4.  **속성** 빠른 탭에서 **숨김** 또는 **읽기 전용** 을 선택합니다.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>계산이 내가 설정한 값을 덮어쓸 수 있습니까?
아니요. 제품을 구성할 때 설정한 값이 사용되는 값입니다. 계산의 입력 값이 변경될 때 발생하는 계산은 특정 속성에 대해 제공한 값을 덮어쓸 수 없습니다.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>계산에서 입력 값을 제거하면 어떻게 됩니까?
계산에서 입력 값을 제거하면 대상 속성의 값도 제거됩니다.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>내 모델이 모순된다는 오류 메시지가 표시되는 이유는 무엇입니까?
이 메시지는 계산에 오류가 포함되거나 하나 이상의 제약 조건에 모순이 있을 때 표시됩니다. 제약 조건의 모순에 대한 자세한 내용은 [제품 구성 모델의 표현식 제약 조건 및 테이블 제약 조건](expression-constraints-table-constraints-product-configuration-models.md)을 참조하세요. 다음은 계산에서 오류가 발생할 수 있는 몇 가지 상황입니다.

-   값은 0(영)으로 나뉩니다.
-   다음 두 요소 사이에 충돌이 있습니다.
    -   속성에 사용할 수 있고 제약 조건에 의해 제한되는 값
    -   계산에 의해 생성된 값
-   계산에서 반환된 값은 속성의 도메인 외부에 있습니다. 예를 들어 \[1..10\]의 정수는 0으로 계산됩니다.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>제품 모델을 성공적으로 검증했는데도 오류 메시지가 표시되는 이유는 무엇입니까?
계산은 유효성 검사에 포함되지 않습니다. 계산에서 오류를 찾으려면 제품 구성 모델을 테스트해야 합니다. 제품 구성 모델을 테스트하려면 다음 단계를 따르세요.

1.  **제품 정보 관리** &gt; **공통** &gt; **제품 구성 모델** 을 클릭합니다.
2.  제품 구성 모델을 선택한 다음 작업 창의 **실행** 그룹에서 **테스트** 를 클릭합니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]