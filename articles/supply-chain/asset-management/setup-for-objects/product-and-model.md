---
title: 자산 제조업체 및 모델
description: 이 항목에서는 자산 관리에서 자산 제조업체 및 관련 모델을 설정하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80fcb493d96209d78f842414c198a8275e4818ba365759466034faf5f3405540
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446878"
---
# <a name="asset-manufacturers-and-models"></a>자산 제조업체 및 모델

[!include [banner](../../includes/banner.md)]

 

이 항목에서는 자산 관리에서 자산 제조업체 및 관련 모델을 설정하는 방법에 대해 설명합니다. 모델은 자산 유형과 관련될 수 있습니다.

## <a name="set-up-product-model-relations"></a>제품 모델 관계 설정

1. **자산 관리** \> **설정** \> **자산** \> **제조업체 및 모델** 을 선택합니다.
2. **새로 만들기** 를 선택하여 새 제품을 만듭니다.
3. **제조업체** 필드에서 자산 제조업체의 이름을 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **모델** 빠른 탭에서 **추가** 를 선택하여 자산 제조업체와 관련되어야 하는 자산 모델을 생성합니다.
6. **모델** 필드에서 자산 모델의 이름을 입력합니다.
7. **설명** 필드에 설명을 입력합니다.
8. **자산 유형** 필드에서 제조업체 모델과 관련되어야 하는 자산 유형을 선택합니다.

    > [!NOTE]
    > **자산 유형** 조회에서 자산 유형, 제조업체 및 모델에 대한 관계를 설정할 수도 있습니다. 자세한 내용은 [자산 유형](../setup-for-objects/object-types.md)을 참조하세요.

    **세부 정보** 빠른 탭에서 **모델** 필드는 선택한 자산 제조업체에 설정된 자산 모델의 수를 보여줍니다. **자산** 필드는 선택한 제조업체를 사용하는 자산의 수를 보여줍니다.
    
    **자산** 필드는 제조업체 모델을 사용하는 개체의 수를 보여줍니다.

> [!NOTE]
> 자산 유형에는 자산 제조업체 모델 관계가 없을 수 있으며, 하나의 자산 제조업체 모델과 관련되거나 여러 자산 제조업체 모델과 관련될 수 있습니다. 자산 유형이 하나 이상의 제조업체 모델과 관련된 경우 자산 유형, 제조업체 및 모델의 조합을 설정할 수 있는 자산 관리 페이지에서 **제조업체 모델** 조회를 선택할 수 있습니다. 이러한 페이지에는 **모든 자산**, **자산 서비스 수준**, **작업 유형 기본값** 및 **유지 관리 예산 라인** 이 포함됩니다. 일부 자산 유형이 제조업체 모델과 관련이 없는 경우 해당 자산 유형 및 자산 유형과도 관련이 없는 제조업체 모델만 페이지에 표시됩니다.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>개체의 제조업체 및 모델 선택

1. **자산 관리** \> **공통** \> **자산** \> **모든 자산** 을 선택합니다.
2. **자산** 열에서 자산에 대한 링크를 선택합니다. **세부 정보** 페이지가 나타납니다.
3. **편집** 을 선택합니다.
4. **일반** 빠른 탭의 **제조업체** 및 **모델** 필드에서 값을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]