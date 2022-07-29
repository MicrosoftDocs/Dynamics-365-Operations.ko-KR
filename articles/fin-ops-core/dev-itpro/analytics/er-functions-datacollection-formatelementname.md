---
title: FORMATELEMENTNAME ER 함수
description: 이번에는 FORMATELEMENTNAME 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/05/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72977edfbe06e0d68d9226c9c25fa0633e7951d22438e053ae2a7cf4ef9a5848
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460974"
---
# <a name="formatelementname-er-function"></a>FORMATELEMENTNAME ER 함수

[!include [banner](../includes/banner.md)]

이 `FORMATELEMENTNAME` 함수는 현재 전자 보고(ER) 형식 요소의 이름을 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

이 함수는 **출력 세부 정보 수집** 옵션이 켜져 있는 **Common\\File** 구성 요소 아래에 있는 **텍스트** 그룹에서 ER 형식 구성 요소의 **수집된 데이터 키 이름** 및 **수집된 데이터 키 값** 속성에 대해 구성된 ER 표현식에서 호출할 수 있습니다.

## <a name="example"></a>예시

이 함수를 사용하는 방법에 대한 자세한 내용은 [IT 서비스/솔루션 구성 요소 획득/개발 비즈니스 프로세스](tasks/er-format-counting-summing-1.md)의 일부인 **계산 및 합산 작업 가이드에 ER 형식 출력 데이터 사용** 을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[데이터 수집 함수](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]