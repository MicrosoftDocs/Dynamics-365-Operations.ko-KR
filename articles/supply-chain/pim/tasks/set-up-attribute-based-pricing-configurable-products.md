---
title: 구성 가능한 제품에 대한 특성 기반 가격 책정 설정
description: 이 토픽에서는 특성 기반 가격 책정을 설정하는 방법을 설명합니다.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4acd7b423396124dd1059602f5aa6460ec5e259
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449080"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>구성 가능한 제품에 대한 특성 기반 가격 책정 설정

[!include [banner](../../includes/banner.md)]

이 토픽에서는 특성 기반 가격 책정을 설정하는 방법을 설명합니다. 전제 조건으로 하나 이상의 구성 요소와 특성이 있는 제품 구성 모델이 있어야 합니다. 이 예시는 USMF 데모 데이터 회사의 고급 스피커 상품 모델을 사용합니다. 일반적으로 제품 관리자는 이 절차를 사용합니다.


## <a name="create-a-new-price-model"></a>새 가격모델 만들기

1. **제품 정보 관리 \> 제품 \> 제품 구성 모델** 로 이동합니다.
1. 목록에서 **하이엔드 스피커** 라인을 선택하되 이름에 대한 링크는 선택하지 마세요.
1. 작업 창에서 **모델** 을 선택합니다.
1. **가격 모델** 을 선택합니다.
1. **새로 만들기** 를 선택합니다.
1. **가격 모델 이름** 필드에 값을 입력합니다. 모델을 쉽게 식별할 수 있는 이름을 사용합니다.  
1. **설명** 필드에 값을 입력합니다.
1. **저장** 을 선택합니다.

## <a name="add-price-elements"></a>가격 요소 추가

1. **편집** 을 선택합니다. 제품 모델의 각 구성 요소에는 기본 가격 요소와 여러 가격 표현식 규칙이 있을 수 있습니다. 다른 통화로 가격을 추가할 수도 있습니다.  
2. **기본 가격 표현식** 필드에 값을 입력합니다. 예를 들어 100을 입력합니다. 기본 가격 표현식은 숫자 값이거나 하나 이상의 특성을 포함하는 산술 계산으로 구성될 수 있습니다.  
3. **추가** 를 선택합니다.
4. **이름** 필드에 `Rosewood`를 입력합니다. 가격 표현식 이름은 가격 요소가 나타내는 것을 식별하는 데 도움이 됩니다. 이 예에서는 Rosewood 스피커 캐비닛 마감 옵션에 대한 가격 요소를 생성합니다.  
5. **조건 편집** 을 선택합니다. 가격 조건은 특성의 특정 조합이 있는 경우에만 가격 표현식 요소가 판매 가격에 포함되도록 보장하는 데 도움이 됩니다.  
6. **ConstraintBody** 필드에 `CabinetFinish=="Rosewood"`를 입력합니다.
7. **확인** 을 선택합니다.
8. **표현식** 필드에 값을 입력합니다. 예를 들어 `50`을 입력합니다. 
9. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]