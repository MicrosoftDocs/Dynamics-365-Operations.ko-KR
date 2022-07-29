---
title: 목록 ER 함수
description: 이번에는 LIST 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: ac8d3971a5502ce567069e0c97247d75a25ae3d38e2cd91e875d4c0d2681d01d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460800"
---
# <a name="list-er-function"></a>목록 ER 함수

[!include [banner](../includes/banner.md)]

이 `LIST` 함수는 지정된 인수에서 생성된 새 기록 목록으로 구성된 *기록 목록* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>인수

`record 1`: *컨테이너(기록)*

*기록* 데이터 유형의 데이터 소스에 대한 참조입니다. 이 인수는 필수입니다.

`record N`: *컨테이너(기록)*

*기록* 데이터 유형의 데이터 소스에 대한 참조입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

생성된 목록의 구조에는 인수에 언급된 모든 기록의 구조에 표시되는 필드만 포함됩니다.

## <a name="example"></a>예시

*컨테이너* 유형의 데이터 소스 **기록 1** 을 입력합니다. 이 데이터 원본에는 *계산된 필드* 유형의 다음 중첩 필드가 포함되어 있습니다.

- **코드:** 이 필드는 *스트링* 유형의 값을 반환하는 표현식을 포함합니다.
- **값** 이 필드는 *Real* 유형의 값을 반환하는 표현식을 포함합니다.

이후 *컨테이너* 유형의 데이터 소스 **기록 2** 를 입력합니다. 이 데이터 원본에는 *계산된 필드* 유형의 다음 중첩 필드가 포함되어 있습니다.

- **값** 이 필드는 *Real* 유형의 값을 반환하는 표현식을 포함합니다.
- **유효함:** 이 필드는 *부울* 유형의 값을 반환하는 표현식을 포함합니다.

이 경우 `LIST('Record 1', 'Record 2')` 표현식은 두 개의 기록이 포함된 새 목록을 반환합니다. 이 목록의 구조는 *Real* 유형의 단일 **Amount** 필드로 구성됩니다. 이 필드는 호출된 함수의 모든 인수에 표시되는 유일한 필드이기 때문입니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]