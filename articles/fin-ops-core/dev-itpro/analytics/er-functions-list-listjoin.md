---
title: LISTJOIN ER 함수
description: 이번에는 LISTJOIN 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9346afc88adb89c08098f39a5fd1c2cb82f664af2244b8cafbbe8a4d2f516c6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460796"
---
# <a name="listjoin-er-function"></a>LISTJOIN ER 함수

[!include [banner](../includes/banner.md)]

이 `LISTJOIN` 함수는 지정된 인수에서 생성된 새로운 결합된 *기록 목록* 을 나타내는 기록 목록 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
LISTJOIN (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>인수

`list 1`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스에 대한 참조입니다. 이 인수는 필수입니다.

`list N`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스에 대한 참조입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

생성된 목록의 구조에는 인수에서 참조되는 모든 기록 목록의 구조에 있는 필드만 포함됩니다.

## <a name="example"></a>예시

`Container` 유형의 데이터 소스 **기록 1** 을 입력합니다. 이 데이터 소스에는 다음 `Calculated field` 유형의 중첩 필드가 포함되어 있습니다.

- **코드**: 이 필드에는 해당 `String` 유형의 값을 반환하는 표현식이 포함됩니다.
- **값** 이 필드에는 해당 `Real` 유형의 값을 반환하는 표현식이 포함됩니다.

이후 `Container` 유형의 데이터 소스 **기록 2** 를 입력합니다. 이 데이터 소스에는 다음 `Calculated field` 유형의 중첩 필드가 포함되어 있습니다.

- **값** 이 필드에는 해당 `Real` 유형의 값을 반환하는 표현식이 포함됩니다.
- **유효함**: 이 필드에는 해당 `Boolean` 유형의 값을 반환하는 표현식이 포함됩니다.

![ER 모델 매핑 디자이너 페이지.](./media/er-functions-list-listjoin-image1.gif)

이 경우 `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` 표현식은 두 개의 기록이 포함된 새 목록을 반환합니다.

![두 개의 기록이 있는 ER 모델 매핑 디자이너 페이지.](./media/er-functions-list-listjoin-image2.gif)

이 목록의 구조는 `Real` 유형의 단일 **Amount** 필드로 구성됩니다. 이 필드는 호출된 함수의 모든 인수에 표시되는 유일한 필드이기 때문입니다.

![ER 모델 매핑 디자이너 페이지 금액 필드입니다.](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)

[실행된 ER 형식의 데이터 소스를 디버그하여 데이터 흐름 및 변환 분석](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
