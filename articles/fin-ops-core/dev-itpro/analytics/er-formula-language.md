---
title: 전자 보고 공식 언어
description: 이번에는 전자 보고(ER)에서 공식 언어를 사용하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 05/04/2020
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ef0b9e411fabca1427b985eb51640bfd2a0d59318a456cb5b1ecdea1445fab5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460625"
---
# <a name="electronic-reporting-formula-language"></a>전자 보고 공식 언어

[!include [banner](../includes/banner.md)]

전자 보고(ER)는 강력한 데이터 변환 경험을 제공합니다. [ER 수식 디자이너](general-electronic-reporting-formula-designer.md)에서 필요한 데이터 조작을 표현하는 데 사용되는 언어는 Microsoft Excel의 수식 언어와 유사합니다.

## <a name="basic-syntax"></a>기본 구문

ER 표현식은 다음 요소 중 일부 또는 전부를 포함할 수 있습니다.

- [상수](#Constants)
- [연산자,](#Operators)
- [참고 자료](#References)
- [길](#Paths)
- [직렬](#Functions)

## <a name="constants"></a><a name="Constants"></a>상수

식을 디자인할 때 텍스트 및 숫자 상수(즉, 계산되지 않은 값)를 사용할 수 있습니다. 예를 들어 `VALUE ("100") + 20` 표현식은 숫자 상수 **20** 과 스트링 상수 **'100'** 을 사용하고 숫자 값 **120** 을 반환합니다.

ER 공식 디자이너는 이스케이프 시퀀스를 지원합니다. 따라서 다르게 처리해야 하는 표현식 스트링을 지정할 수 있습니다. 예를 들어 `"Leo Tolstoy ""War and Peace"" Volume 1"` 표현식은 텍스트 스트링 **Leo Tolstoy 'War and Peace' Volume 1** 을 반환합니다.

## <a name="operators"></a><a name="Operators"></a>연산자,

다음 표는 더하기, 빼기, 곱하기 및 나누기와 같은 기본 수학 연산을 수행하는 데 사용할 수 있는 산술 연산자를 보여줍니다.

| 작업 | 의미               | 예시     |
|----------|-----------------------|-------------|
| +        | 더하기              | `1+2`       |
| -        | 빼기, 부정 | `5-2`, `-1` |
| \*       | 다중        | `7\*8`      |
| /        | 부문              | `9/3`       |

다음 표는 지원되는 비교 연산자를 보여줍니다. 이러한 연산자를 사용하여 두 값을 비교할 수 있습니다.

| 작업 | 의미                  | 예시      |
|----------|--------------------------|--------------|
| =        | Equal                    | `X=Y`        |
| &gt;     | Greater than             | `X>Y`        |
| &lt;     | Less than                | `X<Y`        |
| &gt;=    | 크거나 같음 | `X>=Y`       |
| &lt;=    | 다음 이하    | `X<=Y`       |
| &lt;&gt; | 같지 않음             | `X<>Y`       |

또한 앰퍼샌드(&)를 텍스트 연결 연산자로 사용할 수 있습니다. 이러한 방식으로 하나 이상의 텍스트 스트링을 단일 텍스트 조각으로 결합하거나 연결할 수 있습니다.

| 작업 | 의미     | 예시                                               |
|----------|-------------|-------------------------------------------------------|
| &        | 사슬 같이 잇다 | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>연산자 우선 순위

복합 표현식의 일부가 평가되는 순서는 중요합니다. 예를 들어 덧셈이나 나눗셈을 먼저 하느냐에 따라 `1 + 4 / 2` 식의 결과가 달라진다. 괄호를 사용하여 표현식이 평가되는 방식을 명시적으로 정의할 수 있습니다. 예를 들어, 더하기 연산이 먼저 수행되어야 함을 나타내기 위해 앞의 표현식을 `(1 + 4) / 2`로 변경할 수 있습니다. 식에서 작업 순서를 명시적으로 지정하지 않으면 지원되는 연산자에 할당된 기본 우선 순위를 기반으로 합니다. 다음 표는 각 연산자에 할당된 우선 순위를 보여줍니다. 우선 순위가 높은 연산자(예: 7)는 우선 순위가 낮은 연산자(예: 1)보다 먼저 평가됩니다.

| 상위, | 연산자,      | 구문                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | 그룹,       | ( … )                                                                   |
| 6          | 회원 액세스  | … . …                                                                   |
| 5          | 함수 호출  | … ( … )                                                                 |
| 4          | 다중 | … \* …<br>… / …                                                         |
| 3          | 추가       | … + …<br>… - …                                                          |
| 2          | 비교     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | 별거     | … , …                                                                   |

식에 우선 순위가 동일한 여러 개의 연속 연산자가 포함된 경우 해당 연산은 왼쪽에서 오른쪽으로 평가됩니다. 예를 들어 `1 + 6 / 2 \* 3 > 5` 표현식은 **true** 를 반환합니다. 표현식을 더 쉽게 읽고 유지 관리할 수 있도록 표현식에서 원하는 작업 순서를 명시적으로 나타내기 위해 괄호를 사용하는 것이 좋습니다.

## <a name="references"></a><a name="References"></a>참고 자료

표현식을 설계하는 동안 사용할 수 있는 현재 ER 구성 요소의 모든 데이터 소스는 명명된 참조로 사용할 수 있습니다. 현재 ER 구성 요소는 모델 매핑 또는 형식일 수 있습니다. 예를 들어 현재 ER 모델 매핑에는 [*DateTime*](er-formula-supported-data-types-primitive.md#datetime) 데이터 형식의 값을 반환하는 **ReportingDate** 데이터 원본이 포함되어 있습니다. 생성 문서에서 해당 값의 형식을 올바르게 지정하려면 `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")` 표현식의 데이터 소스를 로 참조할 수 있습니다.

알파벳 문자를 나타내지 않는 참조 데이터 소스 이름의 모든 문자 앞에는 작은따옴표(')가 있어야 합니다. 참조하는 데이터 원본의 이름에 알파벳 문자를 나타내지 않는 기호가 하나 이상 포함되어 있으면 이름을 작은따옴표로 묶어야 합니다. 예를 들어, 알파벳이 아닌 이러한 기호는 구두점이나 기타 서면 기호일 수 있습니다. 여기 예시들이 있습니다 :

- **오늘의 날짜 및 시간** 데이터 소스는 ER 표현식에서 `'Today''s date & time'`로 참조되어야 합니다.
- **고객** 데이터 원본의 **name()** 메서드는 ER 표현식에서 `Customers.'name()'`로 참조되어야 합니다.

애플리케이션 데이터 소스의 메소드에 매개 변수가 있는 경우 다음 구문을 사용하여 해당 메소드를 호출합니다.

- **시스템** 데이터 소스의 **isLanguageRTL** 메소드에 [*스트링*](er-formula-supported-data-types-primitive.md#string) 데이터 유형의 **EN-US** 매개 변수가 있는 경우 이 메소드는 ER 표현식에서 `System.isLanguageRTL("EN-US")`로 참조되어야 합니다.
- 메서드 이름에 영숫자 기호만 포함된 경우 따옴표는 필요하지 않습니다. 그러나 이름에 대괄호가 포함된 경우 테이블의 메서드에 필요합니다.

**시스템** 데이터 소스가 **전역** 애플리케이션 클래스를 참조하는 ER 매핑에 추가되면 `System.isLanguageRTL("EN-US ")` 식은 *부울* 값 **FALSE** 를 반환합니다. 수정된 표현식은 `System.isLanguageRTL("AR")` *부울* 값 **TRUE** 를 반환합니다.

이 유형의 메소드의 매개 변수에 값이 전달되는 방식을 제한할 수 있습니다.

- 이 유형의 메서드에는 상수만 전달할 수 있습니다. 상수 값은 디자인 타임에 정의됩니다.
- 이 유형의 매개 변수에는 [기본](er-formula-supported-data-types-primitive.md)(기본) 데이터 유형만 지원됩니다. 기본 데이터 유형에는 *정수*, *실수*, *부울* 및 *스트링* 이 있습니다.

## <a name="paths"></a><a name="Paths"></a>길

표현식이 구조화된 데이터 소스를 참조하는 경우 경로 정의를 사용하여 해당 데이터 소스의 특정 기본 요소를 선택할 수 있습니다. 점 문자(.)는 구조화된 데이터 소스의 개별 요소를 구분하는 데 사용됩니다. 예를 들어 현재 ER 모델 매핑에는 **InvoiceTransactions** 데이터 원본이 포함되어 있으며 이 데이터 원본은 기록 목록을 반환합니다. **InvoiceTransactions** 기록 구조에는 **AmountDebit** 및 **AmountCredit** 필드가 포함되어 있으며 이 두 필드는 모두 숫자 값을 반환합니다. 따라서 다음 표현식을 설계하여 송장 금액을 계산할 수 있습니다. `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. 이 `InvoiceTransactions.AmountDebit` 식의 구성은 *기록 목* 록 유형의 **InvoiceTransactions** 데이터 원본에 대한 **AmountDebit** 필드에 액세스하는 데 사용되는 경로입니다.

### <a name="relative-path"></a>상대 경로

구조화된 데이터 소스의 경로가 'at' 기호(@)로 시작하는 경우 상대 경로입니다. 사용되는 계층적 트리 구조의 절대 경로의 나머지 부분 대신 'at' 기호가 표시됩니다. 다음 그림은 예를 보여줍니다. 여기서 `Ledger.'accountingCurrency()'` 절대 경로는 **원장** 데이터 소스의 회계 통화 값이 데이터 모델의 **AccountingCurrency** 필드에 입력되었음을 나타냅니다.

![ER 모델 매핑 디자이너 페이지의 절대 경로 예.](./media/ER-FormulaLanguage-AbsolutePath.png)

다음 그림의 예는 상대 경로가 사용되는 방법을 보여줍니다. `@.AccountNum` 상대 경로는 **Intrastat** 데이터 소스의 **AccountNum** 필드(데이터 모델의 계층 트리에서 **AccountNum** 필드보다 한 수준 위에 표시됨)가 데이터 모델의 **AccountNum** 필드에 고객 또는 공급 업체 계정 번호를 입력하는 데 사용됨을 나타냅니다.

![ER 모델 매핑 디자이너 페이지의 상대 경로 예.](./media/ER-FormulaLanguage-RelativePath1.png)

절대 경로의 나머지 부분은 [ER 공식 편집기](general-electronic-reporting-formula-designer.md)에도 표시됩니다.

![ER 공식 디자이너 페이지에서 절대 경로의 나머지 부분.](./media/ER-FormulaLanguage-RelativePath2.png)

자세한 내용은 [ER 모델 및 형식의 데이터 바인딩에 상대 경로 사용](relative-path-data-bindings-er-models-format.md)을 참조하십시오.

## <a name="functions"></a><a name="Functions"></a>직렬

ER 내장 함수는 ER 표현식에서 사용할 수 있습니다. 표현식 컨텍스트의 모든 데이터 소스(즉, 현재 ER 모델 매핑 또는 ER 형식)는 호출 함수에 대한 인수 목록에 따라 호출 함수의 매개 변수로 사용할 수 있습니다. 상수는 호출 함수의 매개 변수로도 사용할 수 있습니다. 예를 들어 현재 ER 모델 매핑에는 **InvoiceTransactions** 데이터 원본이 포함되어 있으며 이 데이터 원본은 기록 목록을 반환합니다. **InvoiceTransactions** 기록 구조에는 **AmountDebit** 및 **AmountCredit** 필드가 포함되어 있으며 이 두 필드는 모두 숫자 값을 반환합니다. 따라서 송장 금액을 계산하기 위해 내장된 ER 반올림 함수를 사용하는 다음 표현식을 설계할 수 있습니다. `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

ER 모델 매핑 및 ER 보고서를 디자인할 때 다음 범주의 ER 함수를 사용할 수 있습니다.

- [날짜 및 시간 함수](er-functions-category-datetime.md)
- [함수 나열](er-functions-category-list.md)
- [논리 함수](er-functions-category-logical.md)
- [수학 함수](er-functions-category-mathematical.md)
- [기록 함수](er-functions-category-record.md)
- [텍스트 함수](er-functions-category-text.md)
- [데이터 수집 함수](er-functions-category-data-collection.md)
- [기타(비즈니스 도메인별) 함수](er-functions-category-other.md)
- [유형 변환 함수](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>함수 목록 확장

ER을 사용하면 ER 표현식에 사용되는 함수 목록을 확장할 수 있습니다. 약간의 엔지니어링 노력이 필요합니다. 자세한 내용은 [전자 보고(ER) 함수 목록 확장](general-electronic-reporting-formulas-list-extension.md)을 참조하십시오.

## <a name="compound-expressions"></a>복합 표현식

데이터 유형이 일치하는 경우 다른 범주의 함수를 사용하는 복합 표현식을 작성할 수 있습니다. 함수를 함께 사용할 때 한 함수의 출력 데이터 유형을 다른 함수에 필요한 입력 데이터 유형과 일치시키십시오. 예를 들어, 필드를 ER 형식 요소에 바인딩할 때 가능한 '목록이 비어 있음' 오류를 방지하려면 다음 예시와 같이 [목록](er-functions-category-list.md) 범주의 함수를 [논리](er-functions-category-logical.md) 범주의 함수과 결합하십시오. 여기에서 수식은 [IF](er-functions-logical-if.md) 함수를 사용하여 해당 목록에서 필요한 집계 값을 반환하기 전에 **IntrastatTotals** 목록이 비어 있는지 여부를 테스트합니다. **IntrastatTotals** 목록이 비어 있으면 수식은 **0** 을 반환합니다.

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>여러 솔루션

종종 다른 범주의 함수 또는 동일한 범주의 다른 함수를 사용하여 여러 가지 방법으로 동일한 데이터 변환 결과를 얻을 수 있습니다. 예를 들어, 이전 표현식은 [목록](er-functions-category-list.md) 범주의 [COUNT](er-functions-list-count.md) 함수를 사용하여 구성할 수도 있습니다.

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 함수 목록 확장](general-electronic-reporting-formulas-list-extension.md)

[지원되는 기본 데이터 유형](er-formula-supported-data-types-primitive.md)

[지원되는 복합 데이터 유형](er-formula-supported-data-types-composite.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
