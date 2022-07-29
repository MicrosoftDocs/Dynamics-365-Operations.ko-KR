---
title: SPLITLIST ER 함수
description: 이번에는 SPLITLIST 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 03/15/2021
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
ms.openlocfilehash: ef0b548173a01cc5a15fcfb743dfb29397c1349b3c2926fa6401399459d07026
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460934"
---
# <a name="splitlist-er-function"></a>SPLITLIST ER 함수

[!include [banner](../includes/banner.md)]

이 `SPLITLIST` 함수는 지정된 목록을 하위 목록(또는 일괄 처리)으로 분할하며, 각 하위 목록에는 지정된 수의 기록이 포함됩니다. 이후 배치로 구성된 새 *기록 목록* 값으로 결과를 반환합니다.

## <a name="syntax-1"></a>구문 1

```vb
SPLITLIST (list, number)
```

## <a name="syntax-2"></a>구문 2

```vb
SPLITLIST (list, number, on-demand reading flag)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`number`: *정수*

배치당 최대 기록 수입니다.

`on-demand reading flag`: *부울*

요청 시 하위 목록의 요소를 생성해야 하는지 여부를 지정하는 *부울* 값입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

반환되는 배치 목록에는 다음 요소가 포함됩니다.

 - **값** *목록*

    현재 배치에 속한 기록 목록입니다.

- **배치 번호:** *정수*

    반환된 목록의 현재 배치 번호입니다.

주문형 읽기 플래그가 **True** 로 설정되면 요청 시 하위 목록이 생성되어 메모리 소비를 줄일 수 있지만 요소가 순차적으로 사용되지 않으면 성능이 저하될 수 있습니다.

## <a name="example"></a>예시

다음 그림에서 **Lines** 데이터 소스는 3개의 기록이 있는 기록 목록으로 생성됩니다. 이 목록은 배치로 나뉘며 각 배치에는 최대 2개의 기록이 포함됩니다.

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

다음 그림은 디자인된 형식 레이아웃을 보여줍니다. 이 형식 레이아웃에서는 XML 형식으로 출력을 생성하기 위해 **Lines** 데이터 소스에 대한 바인딩이 생성됩니다. 이 출력은 각 배치 및 그 안의 기록에 대한 개별 노드를 표시합니다.

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

다음 그림은 설계된 포맷을 실행했을 때의 결과를 보여줍니다.

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
