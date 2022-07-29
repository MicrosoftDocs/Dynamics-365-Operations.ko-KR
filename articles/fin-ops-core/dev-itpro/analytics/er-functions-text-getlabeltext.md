---
title: GETLABELTEXT ER 함수
description: 이번에는 GETLABELTEXT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 01/04/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 911567a94b80c2b762a37e83d37fc500132edb18
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8461043"
---
# <a name="getlabeltext-er-function"></a>GETLABELTEXT ER 함수

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

이 `GETLABELTEXT` 함수는 특정 레이블을 검색하여 지정된 언어로 지정된 레이블의 번역을 나타내는 *[스트링](er-formula-supported-data-types-primitive.md#string)* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>인수

### <a name="label-id"></a>라벨 ID

`label id`: *스트링* 또는 *레이블 ID*

다음 레이블 유형 중 하나의 유효한 ID:

- [전자 보고(ER)](general-electronic-reporting.md) 라벨
- Microsoft Dynamics 365 Finance 레이블

#### <a name="usage-notes"></a>사용 참고 사항

이 인수는 다음 지원 패턴 중 하나를 사용하여 상수로만 정의할 수 있습니다.

- ER 라벨의 경우:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- 재무 레이블의 경우:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> 디자인 타임에 제공된 레이블 ID를 사용하여 레이블을 찾을 수 없는 경우 **[수식 디자이너](er-advanced-formula-editor.md)** 페이지에 유효성 검사 오류 메시지가 표시됩니다.

### <a name="language"></a>언어

`language`: *스트링*

언어 코드를 나타내는 스트링입니다.

#### <a name="usage-notes"></a>사용 참고 사항

이 인수는 텍스트 상수 또는 *스트링* 값을 반환하는 데이터 소스 필드의 경로로 정의할 수 있습니다.

> [!NOTE]
> 텍스트 상수로 정의된 제공된 `language` 인수를 사용하여 언어 코드를 찾을 수 없으면 디자인 타임에 유효성 검사 오류 메시지가 표시됩니다.
>
> 런타임 시 제공된 `language` 인수를 사용하여 언어 코드를 찾지 못한 경우 지정된 레이블에 대해 `EN-US` 시스템 언어 번역이 반환됩니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example-1-system-label"></a><a name=example-1></a>예 1 : 시스템 레이블

`GETLABELTEXT (@"SYS70894", "en-us")` `GETLABELTEXT ("SYS70894", "en-us")` 표현식을 반환하고 `@SYS70894` 애플리케이션 레이블에 대한 영어 번역 'Nothing to print'를 반환합니다.

## <a name="example-2-er-label"></a><a name=example-2></a>예 2 : 응급실 라벨

**ISO20022 크레딧 전송(DE)** 구성에서 [파생된](er-quick-start2-customize-report.md#DeriveProvidedFormat) ER [구성](general-electronic-reporting.md#Configuration) 편집을 시작하고 *[계산된 필드](er-calculated-field-ds-performance.md)* 유형의 새 데이터 소스를 입력하고 이 데이터 소스에 대한 `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` 표현식을 구성합니다. 이 경우 런타임 시 데이터 소스는 기본 **ISO20022 크레딧 전송(DE)** ER 구성에서 처음에 구성된 ER 레이블에 대한 `@GER_LABEL:VendorName` 독일어 번역 'Kreditorenname'을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)

[전자 보고에서 다국어 보고서 디자인](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
