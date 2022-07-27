---
title: 제품 구성 모델의 BOM 유지
description: 이 절차를 실행하려면 기존 제품 구성 모델이 필요합니다.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd78b06f10d0c9b1df57dacdd824b06ebe414b3b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448996"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>제품 구성 모델의 BOM 유지

[!include [banner](../../includes/banner.md)]

이 절차를 실행하려면 기존 제품 구성 모델이 필요합니다. 데모 회사 USMF의 고급 스피커 모델이 이 절차를 만드는 데 사용됩니다.

## <a name="add-a-bom-line"></a>BOM 라인 추가

1. **제품 정보 관리 \> 제품 \> 제품 구성 모델** 로 이동합니다.
1. 목록에서 원하는 레코드를 찾아 선택합니다.
    * 이 절차를 위해 하이엔드 스피커를 선택합니다.  
1. 목록에서 선택한 행의 링크를 선택합니다.
1. **BOM 라인** 섹션을 펼칩니다.
1. **추가** 를 선택합니다.
1. **이름** 필드에 값을 입력합니다.
1. **설명** 필드에 값을 입력합니다.
1. **저장** 을 선택합니다.

## <a name="add-bom-line-details"></a>BOM 라인 세부 정보 추가

1. **BOM 라인 세부 정보** 를 선택합니다.
2. **품목 번호** 필드에서 값을 입력하거나 선택합니다.
    * 예를 들어 M0055 항목을 선택할 수 있습니다.  
    * 각 BOM 라인 속성에 대해 고정 값을 사용하는지 또는 특성에 매핑되는지 선택할 수 있습니다.  
3. **설정** 확인란을 선택합니다.
4. **계산** 필드에서 *예* 를 선택합니다.
    * **계산** 속성을 *예* 로 설정하면 BOM 라인이 비용 계산에 포함됩니다.  
5. **설정** 탭을 선택합니다.
6. **설정** 확인란을 선택합니다.
7. **수량** 필드에 숫자를 입력합니다.
    * 수량 필드는 BOM에 포함될 항목의 양을 결정합니다. 이것은 특성 매핑의 명백한 후보가 될 수 있습니다.  
8. **차원** 탭을 선택합니다.
    * 제품 차원이 활성 상태인지 확인하고 값이나 특성을 할당해야 합니다.  
9. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]