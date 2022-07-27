---
title: 사전 정의된 제품 변형에 대한 제품 번호 명명법 생성
description: 이 항목에서는 사전 정의된 제품 변형에 대한 제품 번호 명명법을 설정하는 방법과 적절한 제품 차원 그룹에 할당하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5179dd54f22de11dc4c0f54113376f13b2f59c48
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448219"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>사전 정의된 제품 변형에 대한 제품 번호 명명법 생성

[!include [banner](../../includes/banner.md)]

이 항목에서는 사전 정의된 제품 변형에 대한 제품 번호 명명법을 설정하는 방법과 적절한 제품 차원 그룹에 할당하는 방법에 대해 설명합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 새 제품 번호 명명법은 색상 및 크기 제품 차원 그룹에 할당됩니다. 이 작업은 일반적으로 제품 디자이너가 수행합니다.


## <a name="create-a-product-number-nomenclature"></a>제품 번호 명명법 만들기

1. **제품 정보 관리 \> 설정 \> 제품 명명법** 으로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **이름** 필드에 대상 제품 차원 그룹을 식별하는 데 도움이 되는 명명법 이름을 입력합니다(예: `ColorSize`).
1. **설명** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **제품 마스터** 번호를 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **색상** 을 선택합니다.
1. **추가** 를 선택합니다.
1. **텍스트 상수** 를 선택합니다.
1. **텍스트** 필드에 값을 입력합니다.
1. **추가** 를 선택합니다.
1. **크기** 를 선택합니다.
1. 페이지를 닫습니다.

## <a name="assign-the-nomenclature-to-a-product-master"></a>제품 마스터에 명명법 할당

1. **제품 크기 그룹** 을 선택합니다.
2. **SizeCol 제품 크기** 그룹을 선택합니다.
3. **편집** 을 선택합니다.
4. **명명법 사용** 필드에서 **예** 를 선택합니다.
5. **제품 변형 번호 명명법** 필드에서 값을 입력하거나 선택합니다.
6. 페이지를 닫습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]