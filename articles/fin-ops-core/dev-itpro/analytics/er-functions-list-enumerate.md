---
title: ENUMERATE ER 함수
description: 이번에는 ENUMERATE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 97677a52e04f03dd39f507b8f63c8daf32140c2321b0d64a8ba5685d2841be3c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460804"
---
# <a name="enumerate-er-function"></a>ENUMERATE ER 함수

[!include [banner](../includes/banner.md)]

이 `ENUMERATE` 함수는 지정된 목록의 열거된 기록으로 구성된 새 *기록 목록* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

반환되는 열거된 기록 목록은 다음과 같은 추가 요소를 노출합니다.

- 필드 기록(**값** 구성 요소)
- 현재 기록 색인(**숫자** 구성 요소)

## <a name="example"></a>예시

다음 그림에서 **열거** 데이터 소스는 VendTable 테이블을 참조하는 공급 업체 데이터 소스의 **공급 업체** 기록 열거 목록으로 생성됩니다.

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

다음 그림은 전자 보고(ER) 형식을 보여줍니다. 이 형식에서는 데이터 바인딩이 생성되어 XML 형식으로 출력을 생성합니다. 이 출력은 개별 공급 업체를 열거된 노드로 표시합니다.

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

다음 그림은 설계된 포맷을 실행했을 때의 결과를 보여줍니다.

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]