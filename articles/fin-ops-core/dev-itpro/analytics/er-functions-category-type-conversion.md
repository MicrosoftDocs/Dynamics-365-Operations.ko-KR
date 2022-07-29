---
title: 유형 변환 범주의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 변환 함수에 대한 정보를 제공합니다.
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
ms.openlocfilehash: a6d678c2a38039285bd835abcbbaf13ec00298c0660c62e7496a5d7405db8f61
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460643"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>유형 변환 범주의 ER 함수 목록

[!include [banner](../includes/banner.md)]

ER(Electronic Reporting) 유형 변환 함수를 사용하여 유형 간에 값을 변환할 수 있습니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="type-conversion-functions"></a>유형 변환 함수

| 직렬 | 설명 |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | 이 함수는 지정된 스트링을 나타내는 *Int64* 값을 반환합니다. |
| [정수 값](er-functions-conversion-intvalue.md)       | 이 함수는 지정된 스트링을 나타내는 *Int* 값을 반환합니다. |
| [숫자값](er-functions-conversion-numbervalue.md) | 이 함수는 지정된 *스트링* 값에서 변환된 *Real* 값을 반환합니다. 변환하는 동안 지정된 소수 및 자릿수 그룹화 구분 기호가 고려됩니다. |
| [값](er-functions-conversion-value.md)             | 이 함수는 지정된 *스트링* 값에서 변환된 *Real* 값을 반환합니다. |

## <a name="type-conversion-functions-in-the-container-category"></a>컨테이너 범주의 유형 변환 함수

다음 표에서는 [컨테이너](er-functions-category-container.md) 범주의 유형 변환 함수에 대해 설명합니다.

| 직렬 | 설명 |
|----------|-------------|
| [Base64스트링ToContainer](er-functions-container-base64stringtocontainer.md) | 이 함수는 *스트링* 유형의 지정된 입력을 *Container* 유형의 데이터 항목으로 변환합니다. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>날짜 및 시간 범주의 유형 변환 함수

다음 표에서는 [날짜 및 시간 범주](er-functions-category-datetime.md)의 유형 변환 함수에 대해 설명합니다.

| 직렬 | 설명 |
|----------|-------------|
| [날짜시간값](er-functions-datetime-datetimevalue.md)   | 이 함수는 지정된 형식과 선택적으로 지정된 문화권의 지정된 스트링 값에서 *날짜/시간* 값으로 변환된 *DateTime* 값을 반환합니다. |
| [날짜까지 날짜 시간](er-functions-datetime-datetodatetime.md) | 이 함수는 지정된 *날짜* 값에서 표준 시간대(그리니치 표준시 \[GMT\])의 날짜/시간 값으로 변환된 *DateTime* 값을 반환합니다. |
| [날짜 값](er-functions-datetime-datevalue.md)           | 이 함수는 지정된 형식과 선택적으로 지정된 문화권의 지정된 *스트링* 값에서 날짜 값으로 변환된 *날짜* 값을 반환합니다. |

## <a name="type-conversion-functions-in-the-list-category"></a>목록 범주의 유형 변환 함수

다음 표에서는 [목록 범주](er-functions-category-list.md)의 유형 변환 함수에 대해 설명합니다.

| 직렬 | 설명 |
|----------|-------------|
| [목록](er-functions-list-list.md)                 | 이 함수는 *컨테이너(기록)* 유형의 지정된 인수에서 생성된 새 목록으로 *기록 목록* 값을 반환합니다. |
| [필드 목록](er-functions-list-listoffields.md) | 이 함수는 *열거형* 또는 *컨테이너(기록)* 유형의 지정된 인수 구조를 기반으로 생성된 *기록 목록* 값을 반환합니다. |
| [스플릿:](er-functions-list-split.md)               | 이 함수는 지정된 *스트링* 값을 하위 스트링으로 분할하고 결과를 새 *기록 목록* 값으로 반환합니다. |
| [스트링 조인](er-functions-list-stringjoin.md)     | 이 함수는 지정된 *기록 목록* 값에서 지정된 필드의 연결된 값으로 구성된 *스트링* 값을 반환합니다. 값은 지정된 구분 기호로 구분할 수 있습니다. |

## <a name="type-conversion-functions-in-the-text-category"></a>텍스트 범주의 유형 변환 함수

다음 표에서는 [텍스트 범주](er-functions-category-text.md)의 유형 변환 함수에 대해 설명합니다.

| 직렬 | 설명 |
|----------|-------------|
| [숯](er-functions-text-char.md)                 | 이 함수는 지정된 유니코드 번호가 참조하는 단일 문자를 나타내는 *스트링* 값을 반환합니다. |
| [GuidValue](er-functions-text-guidvalue.md)       | 이 함수는 *스트링* 유형의 지정된 입력을 *GUID* 유형의 데이터 항목으로 변환합니다. |
| [숫자 형식](er-functions-text-numberformat.md) | 이 함수는 지정된 형식과 선택적으로 지정된 문화권에서 지정된 숫자를 나타내는 *스트링* 값을 반환합니다. |
| [QR 코드](er-functions-text-qrcode.md)             | 이 함수는 지정된 스트링에 대한 빠른 응답 코드(QR 코드) 이미지를 이진 형식으로 표시하는 *컨테이너* 값을 반환합니다. |
| [텍스트](er-functions-text-text.md)                 | 이 함수는 현재 애플리케이션 인스턴스의 서버 로케일 설정에 따라 형식이 지정된 텍스트 스트링으로 변환된 후 지정된 숫자를 나타내는 *스트링* 값을 반환합니다. |

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]