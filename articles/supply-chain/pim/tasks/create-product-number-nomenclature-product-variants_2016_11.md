---
title: 구성된 제품 변형에 대한 제품 번호 명명법 생성
description: 이 절차에서는 구성된 제품 변형에 대한 제품 번호 명명법을 설정하는 방법과 구성 가능한 제품 마스터에 연결하는 방법을 보여줍니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7711d9832288327e700acd47fb30cce0c76e5e9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448108"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>구성된 제품 변형에 대한 제품 번호 명명법 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 구성된 제품 변형에 대한 제품 번호 명명법을 설정하는 방법과 구성 가능한 제품 마스터에 연결하는 방법을 보여줍니다. 이 절차는 또한 제품 구성 모델 구성 요소에 대한 구성 명명법을 구축하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 새 제품 번호 명명법은 D0004 제품 마스터에 할당됩니다. 이 작업은 일반적으로 제품 디자이너가 수행합니다.

## <a name="create-a-product-number-nomenclature"></a>제품 번호 명명법 만들기

1. **제품 정보 관리 \> 설정 \> 제품 명명법** 으로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **이름** 필드에 값을 입력합니다.
1. **설명** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **제품 마스터 번호** 를 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **구성** 을 선택합니다.
1. 페이지를 닫습니다.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>제품 마스터에 제품 번호 명명법 할당

1. **제품 정보 관리 \> 제품 \> 제품 마스터** 로 이동합니다.
1. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 'D'인 **제품 번호** 필드를 필터링합니다.
1. 목록에서 선택한 행의 링크를 선택합니다.
1. **편집** 을 선택합니다.
1. **명명법 사용** 필드에서 *예* 를 선택합니다.
1. **제품 변형 번호 명명법** 필드에서 값을 입력하거나 선택합니다.
1. 페이지를 닫습니다.
1. 페이지를 닫습니다.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>제품 구성 모델 구성 요소에 대한 명명법 만들기

1. **제품 정보 관리 \> 제품 \> 제품 구성 모델** 로 이동합니다.
1. 목록에서 원하는 레코드를 찾아 선택합니다.
1. 목록에서 선택한 행의 링크를 선택합니다.
1. **편집** 을 선택합니다.
1. **구성 명명법 사용** 필드에서 *예* 를 선택합니다.
1. **추가** 를 선택합니다.
1. **특성 값** 을 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **특성** 필드에서 값을 입력하거나 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **특성 값** 을 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **특성** 필드에서 값을 입력하거나 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **특성 값** 을 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **특성** 필드에서 값을 입력하거나 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **특성 값** 을 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **특성** 필드에서 값을 입력하거나 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **숫자 시퀀스 값** 을 선택합니다.
1. 목록에서 선택한 행을 표시합니다.
1. **숫자 시퀀스** 필드에서 값을 입력하거나 선택합니다.
1. 페이지를 닫습니다.
1. 페이지를 닫습니다.
1. 페이지를 닫습니다.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]