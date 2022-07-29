---
title: JSONVALUE ER 함수
description: 이 주제에서는 JSONVALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 10/25/2021
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
ms.openlocfilehash: ff33098e5be4dd9748d01d45b596360617305724
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "8460938"
---
# <a name="jsonvalue-er-function"></a>JSONVALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `JSONVALUE` 함수는 지정된 경로에서 액세스되는 JavaScript Object Notation(JSON) 형식의 데이터를 구문 분석하고 지정된 ID를 가진 스칼라 값을 추출합니다. 이후 추출된 스칼라 값을 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>인수

`input`: *스트링*

JSON 데이터를 포함하는 *스트링* 유형의 데이터 소스의 유효한 경로입니다.

`path`: *스트링*

JSON 데이터의 스칼라 값 식별자입니다. 슬래시(/)를 사용하여 관련 JSON 노드의 이름을 구분합니다. 대괄호(\[\]) 표기법을 사용하여 JSON 배열에서 특정 값의 색인을 지정합니다. 이 색인에는 0부터 시작하는 번호 매기기가 사용됩니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example-1"></a>예시 1

**JsonField** 데이터 소스에는 JSON 형식의 다음 데이터가 포함됩니다. **{빌드 번호: '7.3.1234.1', '키 지문': '7366E}**'. 이 경우 `JSONVALUE (JsonField, "BuildNumber")` 표현식은 *스트링* 데이터 유형의 다음 값을 반환합니다. **"7.3.1234.1"**.

## <a name="example-2"></a>예시 2

*계산된 필드* 유형의 **JsonField** 데이터 소스에는 다음 표현식이 포함됩니다. `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

다음 데이터를 JSON 형식으로 나타내는 [*스트링*](er-formula-supported-data-types-primitive.md#string) 값을 반환하도록 구성된 이 표현식입니다.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

이 경우 `JSONVALUE(json, "workers/[1]/emails/[0]")` 표현식은 *스트링* 데이터 유형의 다음 값을 반환합니다. `JohnS@Contoso.com`.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
