---
title: 텍스트 카테고리의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 텍스트 함수에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 5d185c128de1120e93d1779db04a7666ba557707
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460942"
---
# <a name="list-of-er-functions-of-the-text-category"></a>텍스트 카테고리의 ER 함수 목록

[!include [banner](../includes/banner.md)]

전자 보고(ER) 텍스트 함수를 사용하여 *스트링* 데이터 유형의 데이터 소스에 대한 작업을 수행할 수 있습니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="list-of-supported-functions"></a>지원되는 함수 목록

| 직렬 | 설명 |
|----------|-------------|
| [숯](er-functions-text-char.md) | 이 함수는 지정된 유니코드 번호가 참조하는 단일 문자를 나타내는 *스트링* 값을 반환합니다. |
| [사슬 같이 잇다](er-functions-text-concatenate.md) | 이 함수는 지정된 모든 텍스트 스트링을 하나의 스트링으로 결합한 후 *스트링* 값으로 반환합니다. |
| [포맷](er-functions-text-format.md) | 이 함수는 **%N** 의 발생을 *N* 번째 인수로 대체하여 형식화된 후 지정된 스트링에 *스트링* 값을 반환합니다. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | 이 함수는 *스트링* 값으로 지정된 열거형 이름을 사용하여 지정된 열거형 데이터 원본에서 특정 *열거형* 값을 검색합니다. *Enum* 값이 발견되면 함수가 이를 반환합니다. |
| [GetLabelText](er-functions-text-getlabeltext.md) | 이 함수는 특정 레이블을 검색하여 지정된 언어로 지정된 레이블의 번역을 나타내는 *[스트링](er-formula-supported-data-types-primitive.md#string)* 값을 반환합니다. |
| [GuidValue](er-functions-text-guidvalue.md) | 이 함수는 *스트링* 유형의 지정된 입력을 *GUID* 유형의 데이터 항목으로 변환합니다. |
| [제이슨값](er-functions-text-jsonvalue.md) | 이 함수는 지정된 경로에서 액세스되는 JSON(JavaScript Object Notation) 형식의 데이터를 구문 분석하고 지정된 ID를 기반으로 하는 스칼라 값을 추출합니다. 이후 추출된 스칼라 값을 *스트링* 값으로 반환합니다. |
| [왼쪽](er-functions-text-left.md) | 이 함수는 지정된 스트링의 시작 부분부터 지정된 문자 수를 나타내는 *스트링* 값을 반환합니다. |
| [렌](er-functions-text-len.md) | 이 함수는 지정된 스트링의 문자 수를 나타내는 *정수* 값을 반환합니다. |
| [낮추다](er-functions-text-lower.md) | 이 함수는 지정된 텍스트 스트링을 소문자로 변환한 후 *스트링* 값으로 반환합니다. |
| [중반](er-functions-text-mid.md) | 이 함수는 지정된 위치에서 시작하여 지정된 스트링에서 지정된 문자 수를 나타내는 *[스트링](er-formula-supported-data-types-primitive.md#string)* 값을 반환합니다. |
| [NewGUID](er-functions-text-newguid.md) | 이 함수는 새로 생성된 *[GUID](er-formula-supported-data-types-primitive.md#guid)* 값을 반환합니다. |
| [숫자 형식](er-functions-text-numberformat.md) | 이 함수는 지정된 형식과 선택적으로 지정된 문화권에서 지정된 숫자를 나타내는 *스트링* 값을 반환합니다. |
| [숫자로 텍스트](er-functions-text-numeralstotext.md) | 이 함수는 지정된 언어로 철자된(즉, 텍스트 스트링으로 변환된) 지정된 숫자를 *스트링* 값으로 반환합니다. |
| [왼쪽 패드](er-functions-text-padleft.md) | 이 함수는 지정된 길이의 *스트링* 값을 반환합니다. 여기서 지정된 스트링의 시작은 지정된 문자의 하나 이상의 인스턴스로 채워집니다. |
| [QR 코드](er-functions-text-qrcode.md) | 이 함수는 지정된 스트링에 대한 빠른 응답 코드(QR 코드) 이미지를 이진 형식으로 표시하는 *컨테이너* 값을 반환합니다. |
| [바꾸기](er-functions-text-replace.md) | 이 함수는 전체 또는 일부가 다른 스트링으로 대체된 후 지정된 텍스트 스트링을 *스트링* 값으로 반환합니다. |
| [오른쪽](er-functions-text-right.md) | 이 함수는 지정된 스트링의 끝에서 지정된 문자 수를 나타내는 *스트링* 값을 반환합니다. |
| [텍스트](er-functions-text-text.md) | 이 함수는 현재 애플리케이션 인스턴스의 서버 로케일 설정에 따라 형식이 지정된 텍스트 스트링으로 변환된 후 지정된 숫자를 *스트링* 값으로 반환합니다. |
| [번역](er-functions-text-translate.md) | 이 함수는 제공된 다른 문자 집합에 대해 지정된 텍스트를 문자로 대체한 결과를 포함하는 *스트링* 값을 반환합니다. |
| [손질](er-functions-text-trim.md) | 이 함수는 탭, 캐리지 리턴, 줄 바꿈 및 양식 피드 문자가 단일 공백 문자로 대체된 후, 선행 및 후행 공백이 잘린 후, 단어 사이의 여러 공백이 제거된 후 지정된 텍스트 스트링을 *스트링* 값으로 반환합니다. 제거됨. |
| [높은](er-functions-text-upper.md) | 이 함수는 지정된 텍스트 스트링을 대문자로 변환한 후 *스트링* 값으로 반환합니다. |

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
