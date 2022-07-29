---
title: LISTOFFIELDS ER 함수
description: 이번에는 LISTOFFIELDS 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 1d15649aed4343f2ed9192834047a17e273e29f190aa83c386bebe7857b47908
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460797"
---
# <a name="listoffields-er-function"></a>LISTOFFIELDS ER 함수

[!include [banner](../includes/banner.md)]

이 `LISTOFFIELDS` 함수는 *열거형* 또는 *컨테이너(기록)* 유형의 지정된 인수 구조를 기반으로 생성된 *기록 목록* 값을 반환합니다.

## <a name="syntax-1"></a>구문 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>구문 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>인수

`path`: 데이터 소스 참조

다음 데이터 유형 중 하나의 데이터 소스에 대한 유효한 참조 경로:

- 모델 열거
- 형식 열거
- 애플리케이션 열거
- 컨테이너(기록)

`language`: *스트링*

언어 코드를 나타내는 텍스트입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

생성된 목록은 다음 필드가 있는 기록으로 구성됩니다.

- **이름**(*스트링* 데이터 유형)
- **레이블**(*스트링* 데이터 유형)
- **설명**(*스트링* 데이터 유형)
- **IsTranslated**(*부울* 데이터 유형)

`path` 인수가 *컨테이너(기록)* 유형의 데이터 소스를 참조하는 경우 참조된 컨테이너 기록의 모든 필드에 대해 생성되는 목록에 새 기록이 추가됩니다. 생성된 모든 기록에 대해 **Name** 필드는 현재 기록이 생성된 참조 컨테이너 기록의 필드 이름을 반환합니다.

`path` 인수가 열거 유형 중 하나의 데이터 소스를 참조하는 경우 참조된 열거의 모든 *열거* 값에 대해 생성되는 목록에 새 기록이 추가됩니다. 생성된 모든 기록에 대해 **이름** 필드는 현재 기록이 생성된 참조된 열거형의 값을 반환하고 **설명** 필드는 해당 열거형에 대한 설명을 반환하며 **레이블** 필드는 해당 열거형의 레이블을 반환합니다.

런타임 시 구문 1이 사용될 때 **레이블** 및 **설명** 필드는 실행 중인 전자 보고(ER) 형식의 언어 설정을 기반으로 하는 값을 반환해야 합니다.

- 요청한 언어에 대한 **레이블** 및 **설명** 을 사용할 수 있는 경우 레이블 및 설명 필드는 해당 언어를 기반으로 하는 값을 반환하고 **IsTranslated** 필드는 **True** 를 반환합니다.
- 요청한 언어에 대한 **레이블** 및 **설명** 을 사용할 수 없는 경우 레이블 및 설명 필드는 기본 **EN-US** 언어를 기반으로 하는 값을 반환하고 **IsTranslated** 필드는 **False** 를 반환합니다.

런타임 시 구문 2가 사용될 때 **레이블** 및 **설명** 필드는 호출된 함수의 두 번째 인수로 정의된 언어를 기반으로 하는 값을 반환해야 합니다.

- 요청한 언어에 대한 **레이블** 및 **설명** 을 사용할 수 있는 경우 레이블 및 설명 필드는 해당 언어를 기반으로 하는 값을 반환하고 **IsTranslated** 필드는 **True** 를 반환합니다.
- 요청한 언어에 대한 **레이블** 및 **설명** 을 사용할 수 없는 경우 레이블 및 설명 필드는 **EN-US** 언어를 기반으로 하는 값을 반환하고 **IsTranslated** 필드는 **False** 를 반환합니다.

## <a name="example-1"></a>예시 1

다음 그림에서는 ER 데이터 모델에 열거가 도입되었습니다.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

다음 그림은 이러한 세부 정보를 보여줍니다.

- 모델 열거는 보고서에 데이터 소스로 삽입됩니다.
- ER 표현식은 모델 열거를 `LISTOFFIELDS` 함수의 매개 변수로 사용합니다.
- *기록 목록* 유형의 데이터 소스는 생성된 ER 표현식을 사용하여 보고서에 삽입됩니다.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

다음 예시는 `LISTOFFIELDS` 함수를 사용하여 생성된 *기록 목록* 유형의 데이터 소스에 바인딩된 ER 형식 요소를 보여줍니다.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

다음 그림은 설계된 포맷을 실행했을 때의 결과를 보여줍니다.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> 상위 **FILE** 및 **FOLDER** 형식 요소의 언어 설정에 따라 레이블 및 설명에 대한 번역된 텍스트가 ER 형식의 출력에 입력됩니다.

## <a name="example-2"></a>예시 2

*계산된 필드* 데이터 원본 유형을 사용하여 **enumType** 데이터 모델 열거에 대한 **enumType\_de** 및 **enum\_TypedeCH** 데이터 원본을 구성합니다.

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

이 경우 다음 표현식을 사용하여 스위스 독일어로 된 열거형 값의 레이블을 가져올 수 있습니다(해당 번역을 사용할 수 있는 경우). 스위스 독일어 번역을 사용할 수 없는 경우 레이블은 독일어입니다.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]