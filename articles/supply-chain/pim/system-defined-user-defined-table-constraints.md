---
title: 시스템 정의 및 사용자 정의 테이블 제약 조건
description: 이 문서에서는 제품 구성 모델의 구성 요소에 대한 두 가지 유형의 테이블 제약 조건(사용자 정의 및 시스템 정의)에 대해 설명합니다. 테이블 제약 조건은 허용된 특성 조합의 행렬을 나타내며, 여기서 각 행은 가능한 특성 값의 집합을 정의합니다.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4b484c99bc8f1cc830d4177460ec15a26714a56
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449008"
---
# <a name="system-defined-and-user-defined-table-constraints"></a>시스템 정의 및 사용자 정의 테이블 제약 조건

[!include [banner](../includes/banner.md)]

이 문서에서는 제품 구성 모델의 구성 요소에 대한 두 가지 유형의 테이블 제약 조건(사용자 정의 및 시스템 정의)에 대해 설명합니다. 테이블 제약 조건은 허용된 특성 조합의 행렬을 나타내며, 여기서 각 행은 가능한 특성 값의 집합을 정의합니다.

테이블 제약 조건은 제품 구성 모델의 구성 요소에 허용되는 특성 조합의 매트릭스를 나타냅니다. 테이블의 각 행은 하나의 가능한 특성 값 세트를 정의합니다. 제품 구성 모델에서 두 가지 유형의 제약 조건을 선언할 수 있습니다.

-   **표현식 제약** – 제품 구성 중에 호환 가능한 값만 선택할 수 있도록 특성 간의 관계를 정의하는 표현식을 작성합니다.
-   **테이블 제약** – 지정된 특성 세트에 허용되는 모든 조합을 정의하는 테이블을 작성합니다. 사용자 정의 테이블 제약 조건과 시스템 정의 테이블 제약 조건이라는 두 가지 유형의 테이블 제약 조건을 사용할 수 있습니다.

이 문서에서는 제품 구성 모델의 구성 요소에 대한 사용자 정의 및 시스템 정의 테이블 제약 조건에 대해 설명합니다.

## <a name="user-defined-table-constraints"></a>사용자 정의 테이블 제약 조건
사용자 정의 테이블 제약 조건은 특성 유형에 의해 정의되는 특성 값의 조합을 설명하는 데 사용되는 매트릭스 유형입니다. 예를 들어 스피커를 제작하는 경우 사용자 정의 테이블 제약 조건에 캐비닛 마감 및 전면 그릴에 대한 열을 포함할 수 있습니다. 캐비닛 마감에 대한 특성 유형에는 4가지 값이 있고 전면 그릴에 대한 특성 유형에는 3가지 값이 있습니다. 따라서 제약 조건을 사용하지 않는 경우 4 × 3 = 12개의 가능한 조합이 있습니다. 그러나 이 예에서는 다음 표와 같이 6개의 조합만 허용됩니다. 이 정보는 **테이블 제약 조건 편집** 페이지의 **허용된 조합** 탭에 표시됩니다.

| 캐비닛 마감 | 전면 그릴 |
|----------------|-------------|
| 검정          | 검정       |
| 검정          | 메탈       |
| 오크            | 검정       |
| 로즈우드       | 흰색       |
| 흰색          | 검정       |
| 흰색          | 흰색       |

사용자 정의 테이블 제약 조건은 표현식 제약 조건과 동일한 방식으로 작동하는 정적 테이블 입력에 의해 정의됩니다. 사용자 정의 테이블 제약 조건을 사용하면 긴 표현식 제약 조건보다 테이블을 만들고 이해하고 유지 관리하기가 더 쉽다는 장점이 있습니다.

## <a name="system-defined-table-constraints"></a>시스템 정의 테이블 제약 조건
시스템 정의 테이블 제약 조건은 속성 유형과 테이블의 필드 간에 동적 매핑을 생성합니다. 시스템 정의 테이블 제약 조건이 제품 구성 모델에 포함된 경우 매핑은 속성 유형의 값 대신 테이블의 데이터가 표시되도록 보장합니다. 테이블 내용이 수정될 수 있기 때문에 결과는 동적 제약 조건입니다(예: 다른 모듈에 의해).  

시스템 정의 테이블 제약 조건을 생성할 때 테이블을 선택하고 선택적으로 사용할 쿼리를 정의한 다음 속성 유형을 선택한 테이블의 필드에 연결합니다. 필드 유형은 특성 유형 유형과 일치해야 합니다.  

테이블 제약 조건이 제품 구성 모델에 적용되기 전에 테이블 제약 조건이 모델의 구성 요소 중 하나에 대한 제약 조건에 포함되어야 합니다. 절차는 새 제약 조건을 만들고 테이블 제약 조건 유형을 선택한 다음 사용할 테이블 제약 조건 정의를 선택하는 것입니다. 마지막으로 테이블 제약 조건의 모든 필드는 제품 구성 모델의 특성에 매핑되어야 합니다.

## <a name="additional-resources"></a>추가 리소스

[제품 구성 모델 개요](product-configuration-models.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]