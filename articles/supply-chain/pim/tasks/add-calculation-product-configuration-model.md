---
title: 제품 구성 모델에 계산 추가
description: 이 절차는 제품 구성 모델에 새 계산을 추가하는 방법을 보여줍니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d201061ff47203f09f96dc08ff6fc8ac437a6f9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448333"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>제품 구성 모델에 계산 추가

[!include [banner](../../includes/banner.md)]

이 절차는 제품 구성 모델에 새 계산을 추가하는 방법을 보여줍니다. 흰색 스피커의 경우 스피커 높이를 10으로 설정하고 다른 모든 캐비닛 마감재의 경우 15로 설정하기 위해 "If" 연산자를 사용하여 논리적 표현을 만드는 방법을 보여줍니다. 이 절차는 데모 회사 USMF의 고급 스피커 구성 요소를 사용합니다.


## <a name="add-a-calculation"></a>계산 추가

## <a name="create-calculation-expression"></a>계산식 만들기
1. 식 편집을 클릭합니다.
2. ConstraintBody 필드에 'If[CabinetFinish=="White", 10, 15]'를 입력합니다.
3. 유효성 검사를 클릭합니다.
4. 닫기를 클릭합니다.
5. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]