---
title: SPLITLISTBYLIMIT ER 함수
description: 이번에는 SPLITLISTBYLIMIT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 52351c131480119ce9fb98a75307ebf6026cb12b9977e8b4236d3a24ef6a140e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460933"
---
# <a name="splitlistbylimit-er-function"></a>SPLITLISTBYLIMIT ER 함수

[!include [banner](../includes/banner.md)]

이 `SPLITLISTBYLIMIT` 함수는 지정된 목록을 새 하위 목록(배치) 목록으로 분할합니다. 각 배치의 기록 수는 동적으로 계산됩니다. 이후 이 함수는 배치로 구성된 새 *기록 목록* 값으로 결과를 반환합니다.

## <a name="syntax"></a>구문

```vb
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`limit value`: *정수* 또는 *실수*

원본 목록을 일괄 처리로 분할하는 데 사용되는 제한의 최대값입니다.

`limit source` *필드*

지정된 목록에서 *정수* 또는 *실수* 유형 필드의 유효한 경로입니다. 이 필드의 값은 총 합계가 증가하는 단계를 정의합니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

반환되는 배치 목록에는 다음 요소가 포함됩니다.

- **값** *목록*

    현재 배치에 속한 기록 목록입니다.

- **배치 번호**: *정수*

    반환된 목록의 현재 배치 번호입니다.

제한 소스가 정의된 제한을 초과하는 경우 원래 목록의 단일 항목에 제한이 적용되지 않습니다.

## <a name="example"></a>예시

다음 그림은 전자 보고(ER) 형식을 보여줍니다.

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

다음 그림은 형식에 사용되는 데이터 소스를 보여줍니다.

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

다음 그림은 포맷을 실행할 때의 결과를 보여줍니다. 이 경우 출력은 상품 항목의 단순 목록입니다.

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

다음 그림에서는 단일 배치에 상품이 포함되어야 하고 총 중량이 9개 제한을 초과하지 않아야 하는 경우 일괄 상품 목록을 표시하도록 동일한 형식이 조정되었습니다.

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

다음 그림은 조정된 형식을 실행할 때의 결과를 보여줍니다.

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> 한계 소스(**가중치**)의 값(**11**)이 정의된 한계(**9**)를 초과하므로 원래 목록의 마지막 항목에는 한계가 적용되지 않습니다. 보고서 생성 중 하위 목록을 무시하려면 필요에 따라 해당 형식 요소의 **Enabled** 표현식 또는 `WHERE` 함수를 사용하십시오.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]