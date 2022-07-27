---
title: 판매가 선택 기준 만들기
description: 이 절차에서는 속성 기반 판매 가격 모델에 대한 판매 가격 선택 기준을 만드는 방법을 보여줍니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed7083f289948033782f74dd9ed1b3c2d2a73aea
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448111"
---
# <a name="create-sales-price-selection-criteria"></a>판매가 선택 기준 만들기

[!include [banner](../../includes/banner.md)]

이 절차에서는 속성 기반 판매 가격 모델에 대한 판매 가격 선택 기준을 만드는 방법을 보여줍니다. 이 절차를 수행하려면 하나 이상의 판매 가격 모델을 사용할 수 있어야 합니다. 이 예에서는 USMF 데모 데이터 회사의 스피커 솔루션 판매 가격 모델에 대한 가격 모델을 사용합니다. 일반적으로 제품 관리자는 이 절차를 사용합니다.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>기존 판매 가격 모델에 대한 새 기준 추가

1. **제품 정보 관리 \> 제품 \> 제품 구성 모델** 로 이동합니다.
1. 목록에서 스피커 솔루션 제품 모델에 대한 행을 선택하지만 모델 이름에 대한 링크는 선택하지 마세요.
1. 작업 창에서 **모델** 을 선택합니다.
1. **가격 모델 기준** 을 선택합니다.
1. **새로 만들기** 를 선택합니다.
1. **이름** 필드에 '고객 그룹 10'을 입력합니다.
    * 가격 모델 기준의 이름은 기본 선택 기준을 식별하는 데 사용됩니다.  
1. **가격 모델** 필드에서 값을 입력하거나 선택합니다.
1. **주문 유형** 필드에서 *판매 주문* 을 선택합니다.
    * 주문 유형은 선택 쿼리에 사용할 수 있는 데이터베이스 필드를 결정합니다.  
1. **적용 날짜** 필드에 날짜를 입력합니다.
1. **만료일** 필드에 날짜를 입력합니다.
1. **저장** 을 선택합니다.

## <a name="create-the-query-for-the-selection-criteria"></a>선택 기준에 대한 쿼리 만들기

1. **편집** 을 선택합니다.
2. **테이블** 필드에서 *고객* 을 선택합니다.
3. **필드** 필드에서 *고객 그룹* 을 선택합니다.
    * 이 예에서는 선택 기준으로 특정 고객 그룹을 사용합니다.  
4. **기준** 필드에서 *고객 그룹 10* 을 선택합니다.
5. **확인** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]