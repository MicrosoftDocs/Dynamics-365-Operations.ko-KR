---
title: 전자 보고 공식에 지원되는 기본 데이터 유형
description: 이번에는 전자 보고(ER) 수식에서 지원되는 기본 데이터 유형에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 96fdf33f4cc5f22015c00c57858bd438e6465764
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461027"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>전자 보고 공식에 지원되는 기본 데이터 유형

[!include [banner](../includes/banner.md)]

이 주제에서는 [전자 보고(ER)](general-electronic-reporting.md) 표현식에서 지원되는 기본 데이터 유형에 대한 정보를 제공합니다. 다음은 기본 데이터 유형 목록입니다.

- [부울](#boolean)
- [(날짜)](#date)
- [날짜 시간](#datetime)
- [열거](#enumeration)
- [가이드](#guid)
- [정수](#integer)
- [int64](#int64)
- [진짜](#real)
- [스트링](#string)

## <a name="boolean"></a><a name="boolean"></a>부울

*부울* 기본 데이터 유형에는 *true* 또는 *false로* 평가되는 값이 포함됩니다. *부울* 표현식이 예상되는 모든 곳에서 예약된 리터럴 키워드 **True** 및 **False** 를 사용할 수 있습니다. 기본값은 *false* 입니다.

*부울* 의 내부 표현은 *정수* 입니다. *정수* 값 0(영)은 *false* 로 평가되고 다른 모든 *정수* 값은 *true* 로 평가됩니다. [ER 수식 디자이너](er-advanced-formula-editor.md)에서 *부울* 을 반환하는 구성된 식의 [유효성을](general-electronic-reporting-formula-designer.md#TestFormula) 검사할 때 식이 *false* 를 반환하면 테스트 결과 창에 *0*(영)이 표시됩니다. 그렇지 않으면 테스트 결과 창에 *1* 이 표시됩니다.

*부울* 에는 암시적 변환이 없습니다. 그러나 [TEXT](er-functions-text-text.md) 함수를 사용하여 *부울* 을 *스트링* 으로 명시적으로 변환할 수 있습니다.

- *false* 값은 텍스트 스트링 **False** 로 변환됩니다.
- *true* 값은 텍스트 스트링 **True** 로 변환됩니다.

> [!NOTE]
> 이 변환은 제공된 언어 및 문화권 [컨텍스트](er-design-multilingual-reports.md)에 의존하지 않습니다.

비교 [연산자](er-formula-language.md#Operators)는 *부울* 데이터 유형과 함께 사용할 수 있는 유일한 유형의 연산자입니다. 다음 연산자를 사용하여 두 *부울* 값을 비교할 수 있습니다. \<\> 그리고 =.

## <a name="date"></a><a name="date"></a>날짜

*날짜* 기본 데이터 유형에는 일, 월 및 연도가 포함됩니다. 날짜는 다음 함수를 사용하여 시작할 수 있습니다.

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [오늘의 세션](er-functions-datetime-sessiontoday.md)
- [오늘](er-functions-datetime-today.md)

*날짜* 데이터 유형은 1900년 1월 1일에서 2154년 12월 31일 사이의 날짜를 보유할 수 있습니다. 기본값은 **null** 이고 내부 표현은 1900년 1월 1일 날짜입니다.

*날짜* 에는 암시적 변환이 없습니다. 그러나 다음과 같은 명시적 변환 함수를 사용할 수 있습니다.

- [날짜 형식](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [텍스트](er-functions-text-text.md)

[ADDDAYS](er-functions-datetime-adddays.md) 함수를 사용하면 날짜에서 날짜를 더하거나 뺄 수 있습니다. 이러한 방식으로 날짜를 특정 일 수만큼 미래와 과거로 이동할 수 있습니다. [DAYS](er-functions-datetime-days.md) 함수를 사용하면 날짜를 서로 빼고 날짜의 차이를 계산할 수 있습니다. *날짜* 값 변환에 대한 자세한 내용은 [날짜 및 시간 범주의 ER 함수 목록](er-functions-category-datetime.md)을 참조하십시오.

비교 [연산자](er-formula-language.md#Operators)는 *날짜* 데이터 유형과 함께 사용할 수 있는 유일한 유형의 연산자입니다. 다음 연산자를 사용하여 두 *날짜* 값을 비교할 수 있습니다. \<\>, \<, \<=, =, \> 및 \>=.

## <a name="datetime"></a><a name="datetime"></a>날짜 시간

*datetime* 원시 데이터 유형은 *날짜* 유형과 자정 이후 경과된 시간을 나타내는 값을 결합합니다. 시간은 시, 분, 초 및 초 단위로 표시됩니다. *datetime* 값에는 시간대에 대한 정보도 포함됩니다.

*datetime* 데이터 유형은 1900년 1월 1일(왕복 형식의 경우 1900-01-01T00:00:00.0000000+00:00)에서 2154년 12월 31일(2154/12/31T11:59:59.999999) 사이의 날짜를 보유할 수 있습니다. :00 왕복 [형식](/dotnet/standard/base-types/standard-date-and-time-format-strings). *datetime* 의 가장 작은 시간 단위는 1000만분의 1초입니다.

> [!NOTE]
> **hh** [지정자](/dotnet/standard/base-types/standard-date-and-time-format-strings)가 시간에 사용될 때 12:59:59:9999999보다 큰 시간 값은 유효한 시간으로 해석될 수 없습니다.
>
> **HH** 지정자가 시간에 사용될 때 23:59:59:9999999보다 큰 시간 값은 유효한 시간으로 해석될 수 없습니다.

기본값은 **null** 이고 내부 표현은 1900년 1월 1일 날짜입니다(왕복 형식의 경우 1900-01-01T00:00:00.0000000+00:00).

날짜 시간은 다음 함수를 사용하여 시작할 수 있습니다.

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [지금 세션](er-functions-datetime-sessionnow.md)
- [-지금!](er-functions-datetime-now.md)

*datetime* 에는 암시적 변환이 없습니다. 그러나 다음과 같은 명시적 변환 함수를 사용할 수 있습니다.

- [날짜시간형식](er-functions-datetime-datetimeformat.md)
- [텍스트](er-functions-text-text.md)

*날짜/시간* 값 변환에 대한 자세한 내용은 [날짜 및 시간 범주의 ER 함수 목록](er-functions-category-datetime.md)을 참조하십시오.

비교 [연산자](er-formula-language.md#Operators)는 *날짜/시간* 데이터 유형과 함께 사용할 수 있는 유일한 유형의 연산자입니다. 다음 연산자를 사용하여 두 *날짜/시간* 값을 비교할 수 있습니다. \<\>, \<, \<=, =, \> 및 \>=.

## <a name="enumeration"></a><a name="enumeration"></a>열거

*열거* 기본 데이터 유형은 리터럴 목록입니다. 애플리케이션 [소스 코드](../dev-ref/xpp-data-primitive.md#enum)에 정의된 열거를 사용할 수 있습니다. ER 데이터 모델 및 ER 형식 구성 요소에 고유한 열거를 도입할 수도 있습니다.

애플리케이션 *열거* 는 모든 ER 모델 매핑 및 ER 형식의 표현식에 사용할 수 있습니다.

다음 그림은 **CustVendCorrectiveReasonCode** 모델 열거를 편집 가능한 ER 데이터 모델에 추가하는 방법을 보여줍니다.

[![ER 데이터 모델 디자이너에서 모델 열거 구성.](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

모델 *열거* 는 *열거* 가 도입된 데이터 모델에서 생성된 모든 ER 모델 매핑 및 ER 형식의 표현식에 사용할 수 있습니다.

다음 그림은 편집 가능한 ER 형식에 Natura 역전하 **하위 범주 형식 목록 목록** 을 추가하는 방법을 보여줍니다.

[![ER 형식 디자이너에서 형식 열거 구성.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

형식 *열거* 는 *열거* 가 도입된 ER 형식의 표현식에서만 사용할 수 있습니다.

적절한 유형의 ER 데이터 소스를 사용하여 구성된 ER 구성 요소에 대한 특정 열거를 상수로 가져오거나 ER 솔루션을 실행하는 사용자가 런타임 시 대화 상자에 정의한 값으로 가져와야 합니다.

- 애플리케이션 열거는 **Dynamics 365 for Operations \ 열거** 및 **일반 \ 사용자 입력 매개 변수** 데이터 소스를 사용하여 액세스할 수 있습니다. 다음 그림은 **NoYes** 애플리케이션 열거를 참조하는 **appenumNoYes** 및 **uipNoYes** 데이터 소스를 편집 가능한 ER 형식에 추가하는 방법을 보여줍니다.

    [![ER 형식 디자이너에서 애플리케이션 열거 데이터 소스를 추가합니다.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- 데이터 모델 열거는 **데이터 모델 \ 열거** 및 **데이터 모델 \ 열거 사용자 입력 매개 변수** 데이터 소스를 사용하여 액세스할 수 있습니다. 다음 그림은 **CustVendCorrectiveReasonCode** 데이터 모델 열거를 참조하는 **CustVendCorrectiveReasonCode** 데이터 소스를 편집 가능한 ER 형식에 추가하는 방법을 보여줍니다.

    [![ER 형식 디자이너에서 모델 열거 데이터 소스를 추가합니다.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- 형식 열거형은 **Format \ Enumeration** 및 **Format \ Enumeration 사용자 입력 매개 변수** 데이터 소스를 사용하여 액세스할 수 있습니다. 다음 그림은 편집 가능한 ER 형식에 **Natura 역전하 하위 범주** 형식 열거를 참조하는 **NaturaReverseCharge** 데이터 소스를 추가하는 방법을 보여줍니다.

    [![ER 형식 디자이너에서 형식 열거 데이터 소스를 추가합니다.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

*열거형* 에는 암시적 변환이 없습니다. 그러나 [TEXT](er-functions-text-text.md) 변환 함수를 사용하여 *열거* 를 텍스트 스트링으로 변환할 수 있습니다. 이 변환은 언어에 의존하지 않습니다. *열거형* 값을 적절한 언어별 레이블과 연결하는 방법을 배우려면 [LISTOFFIELDS](er-functions-list-listoffields.md) 및 [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md) 함수에 대한 사용 예를 참조하십시오.

비교 [연산자](er-formula-language.md#Operators)는 *열거* 데이터 유형과 함께 사용할 수 있는 유일한 유형의 연산자입니다. 다음 연산자를 사용하여 두 *열거형* 값을 비교할 수 있습니다. \<\> 그리고 =.

## <a name="guid"></a><a name="guid"></a>가이드

*guid* 기본 데이터 유형은 GUID(Globally Unique Identifier) 값을 보유합니다. GUID는 고유 식별자가 필요한 모든 컴퓨터와 네트워크에서 사용할 수 있는 값입니다. 번호가 중복될 가능성은 거의 없습니다. 유효한 GUID는 다음 사양을 모두 충족합니다.

- 32자리의 16진수가 있어야 합니다.
- 또한 다음 위치에 포함된 4개의 대시 문자가 있어야 합니다. 8-4-4-4-12.
- 또한 스트링의 시작과 끝에 \{\}선택적 중괄호를 추가할 수 있습니다. 예를 들어 **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** 및 **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** 모두 유효한 GUID 스트링입니다.
- 따라서 중괄호 추가 여부에 따라 총 36자 또는 38자여야 합니다.
- 16진수로 사용되는 문자는 대문자(A–F), 소문자(a–f) 또는 혼합일 수 있습니다.

다음과 같은 명시적 변환 함수를 사용할 수 있습니다.

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [텍스트](er-functions-text-text.md)

비교 [연산자](er-formula-language.md#Operators)는 *guid* 데이터 유형과 함께 사용할 수 있는 유일한 유형의 연산자입니다. 다음 연산자를 사용하여 두 *guid* 값을 비교할 수 있습니다. \<\> 그리고 =.

## <a name="integer"></a><a name="integer"></a>정수

*정수* 기본 데이터 유형은 소수점 이하 자릿수가 없는 숫자를 나타냅니다. 정수는 반복문에서 제어 변수로 사용되거나 기록 목록에서 색인으로 사용됩니다.

*정수* 리터럴은 **12345** 와 같은 ER [표현식](general-electronic-reporting-formula-designer.md#formula-designer-overview)(수식)에 직접 입력되는 정수입니다. *정수* 의 너비는 32비트입니다. 기본값은 **0** 이고 내부 표현은 긴 숫자입니다. *정수* 는 자동으로 *실수* 로 변환됩니다.

또한 다음과 같은 명시적 변환 함수를 사용할 수 있습니다.

- [INTVALUE](er-functions-conversion-intvalue.md)
- [숫자 형식](er-functions-text-numberformat.md)
- [텍스트](er-functions-text-text.md)

*정수* 의 범위는 \[-2,147,483,647입니다. 2,147,483,647\]. 이 범위의 모든 정수를 리터럴로 사용할 수 있습니다.

모든 비교 및 수학 [연산자](er-formula-language.md#Operators)는 *정수* 데이터 유형과 함께 사용할 수 있습니다.

## <a name="int64"></a><a name="int64"></a>Int64

*int64* 기본 데이터 유형은 소수점 이하 자릿수가 없는 숫자를 나타냅니다. *Int64* 값은 반복문에서 제어 변수로 사용되거나 기록 식별자로 사용됩니다.

*int64* 는 64비트 너비입니다. 기본값은 **0** 이고 내부 표현은 긴 숫자입니다. *int64* 는 자동으로 *실수* 로 변환됩니다.

또한 다음과 같은 명시적 변환 함수를 사용할 수 있습니다.

- [INT64VALUE](er-functions-conversion-int64value.md)
- [숫자 형식](er-functions-text-numberformat.md)
- [텍스트](er-functions-text-text.md)

*int64* 의 범위는 \[-9,223,372,036,854,775,807입니다. 9,223,372,036,854,775,807\].

모든 비교 및 수학 [연산자](er-formula-language.md#Operators)는 *int64* 데이터 형식과 함께 사용할 수 있습니다.

## <a name="real"></a><a name="real"></a>실수

*실제* 기본 데이터 유형은 정수 외에도 10진수 값을 보유할 수 있습니다. *실수* 가 예상되는 모든 위치에서 10진수 리터럴을 사용할 수 있습니다. 10진수 리터럴은 **2.19** 와 같이 코드에 직접 입력되는 10진수입니다.

> [!NOTE]
> ER 표현식에서 마침표(.)는 항상 소수점 구분 기호로 사용됩니다.

실수는 모든 표현식에 사용할 수 있으며 비교 및 산술 연산자와 함께 사용할 수 있습니다. *실수* 는 16개의 유효 숫자의 정밀도를 갖습니다. *실수* 의 기본값은 **0.0** 이고 내부 표현은 BCD(바이너리 코딩된 디지털) 숫자입니다. BCD 인코딩은 0.1의 배수인 값의 정확한 표현을 가능하게 합니다. *실수* 변수의 범위는 -(10)<sup>127</sup>에서 (10)<sup>127</sup>입니다. 이 범위의 모든 실수는 ER 표현식에서 리터럴로 사용할 수 있습니다.

*실수* 에는 암시적 변환이 없습니다. 그러나 다음 함수를 사용하여 *실수* 를 다른 데이터 형식으로, 다른 데이터 형식을 *실수* 로 명시적으로 변환할 수 있습니다.

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [숫자 형식](er-functions-text-numberformat.md)
- [텍스트](er-functions-text-text.md)
- [값,](er-functions-conversion-value.md)

모든 비교 및 수학 [연산자](er-formula-language.md#Operators)는 *실제* 데이터 유형과 함께 사용할 수 있습니다.

## <a name="string"></a><a name="string"></a>스트링

*스트링* 기본 데이터 유형은 텍스트, 계좌 번호, 주소 및 전화 번호로 사용되는 일련의 문자를 나타냅니다.

*스트링* 리터럴은 따옴표('')로 묶인 문자입니다. *스트링* 리터럴은 ER 표현식에서 *스트링* 값이 예상되는 모든 곳에서 사용할 수 있습니다. 비교와 같은 논리식에서 스트링을 사용할 수 있습니다. **\&** 연산자 또는 [CONCATENATE](er-functions-text-concatenate.md) 함수를 사용하여 *스트링* 값을 연결할 수도 있습니다.

> [!NOTE]
> 두 *스트링* 값을 연결하고 결과 *스트링* 이 두 줄 이상에 걸쳐지도록 하려면 값 사이에 줄 바꿈 구분 기호를 사용합니다. TEXT 출력의 경우 이 구분 기호는 [CHAR](er-functions-text-char.md)(10) 또는 CHAR(13) 표현식을 사용하여 생성된 문자일 수 있습니다. HTML의 경우 **\<br\>** 태그가 될 수 있습니다.

*스트링* 의 기본값은 문자가 없는 빈 텍스트 스트링이고 내부 표현은 문자 목록입니다.

스트링에 대한 자동 변환은 없습니다. 그러나 다음과 같은 명시적 변환 함수를 사용할 수 있습니다.

- [숯](er-functions-text-char.md)
- [형식](er-functions-text-format.md)
- [왼쪽](er-functions-text-left.md)
- [렌](er-functions-text-len.md)
- [중간](er-functions-text-mid.md)
- [패들](er-functions-text-padleft.md)
- [교체](er-functions-text-replace.md)
- [권리](er-functions-text-right.md)
- [텍스트](er-functions-text-text.md)
- [번역](er-functions-text-translate.md)
- [손질](er-functions-text-trim.md)
- [높은](er-functions-text-upper.md)

*스트링* 값 변환에 대한 자세한 내용은 [텍스트 범주의 ER 함수 목록](er-functions-category-text.md)을 참조하십시오.

*스트링* 은 무한한 수의 문자를 보유할 수 있습니다.

모든 비교 [연산자](er-formula-language.md#Operators)는 *스트링* 데이터 유형과 함께 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [전자 보고 공식 언어](er-formula-language.md)
- [지원되는 복합 데이터 유형](er-formula-supported-data-types-composite.md)
