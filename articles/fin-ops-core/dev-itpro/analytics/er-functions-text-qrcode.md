---
title: QRCODE ER 함수
description: 이번에는 QRCODE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: e9d5bd1fee8c310053b01ababb0eaafc6d5470a62786de1f502f175e634bda64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460753"
---
# <a name="qrcode-er-function"></a>QRCODE ER 함수

[!include [banner](../includes/banner.md)]

이 `QRCODE` 함수는 지정된 스트링에 대한 빠른 응답 코드(QR 코드) 이미지를 이진 형식으로 표시하는 *컨테이너* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
QRCODE (text)
```

## <a name="arguments"></a>인수

`text`: *스트링*

원본 텍스트를 나타내는 *스트링* 값입니다.

## <a name="return-values"></a>반환 값

*다음 포함*

결과 바이너리 스트림입니다.

## <a name="example"></a>예시

미리 정의된 템플릿을 사용하여 Microsoft Office 형식(Excel 통합 문서 또는 Word 문서)의 아웃바운드 문서를 생성하도록 전자 보고(ER) 형식을 구성할 수 있습니다. 이 템플릿에는 QR 코드 이미지의 자리 표시자로 **Picture** 개체(Excel 통합 문서) 또는 **Picture Content Control**(Word 문서)이 포함될 수 있습니다. 이 자리 표시자를 채우는 데 사용할 **셀** 요소를 구성된 ER 형식에 추가해야 합니다. QR 코드에 저장할 정보를 지정하려면 이 **Cell** 요소에 대한 바인딩을 정의해야 합니다. 예를 들어 다음 표현식을 포함하도록 이러한 바인딩을 구성할 수 있습니다.

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

구성된 ER 형식을 실행하면 **model.ListOfShelfLabels** 데이터 소스의 **LabelText** 필드 텍스트 값이 QR 코드 이미지를 생성하는 데 사용됩니다. 이 이미지는 아웃바운드 문서를 생성하는 데 사용하는 문서 템플릿의 QR 코드 이미지 자리 표시자를 대체합니다. 생성된 문서의 이 이미지가 스캔되면 **model.ListOfShelfLabels** 데이터 소스의 **LabelText** 필드에서 가져온 텍스트를 반환합니다. 자세한 내용은 [ER을 사용하여 생성한 문서에 이미지 및 도형 포함](electronic-reporting-embed-images-shapes.md)을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]