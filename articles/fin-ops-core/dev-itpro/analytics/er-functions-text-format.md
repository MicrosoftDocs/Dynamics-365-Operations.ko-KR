---
title: 포맷 ER 함수
description: 이번에는 FORMAT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 9dbde3ebfd2670639a2fff19d83ea9bd8d15c22b09b43ab49ae1b9e35562625a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460894"
---
# <a name="format-er-function"></a>포맷 ER 함수

[!include [banner](../includes/banner.md)]

이 `FORMAT` 함수는 **%N** 의 발생을 *N번째* 인수로 대체하여 형식이 지정된 후 지정된 스트링을 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>인수

`string`: *스트링*

형식을 지정해야 하는 *스트링* 유형의 데이터 소스에 대한 참조입니다. 이 인수는 필수입니다.

`argument 1`: *스트링*

**%1** 의 발생을 대체하는 데 사용되는 첫 번째 인수입니다. 이 인수는 필수입니다.

`argument N`: *스트링*

**%2**, **%3** 등의 발생을 대체하는 데 사용되는 *N번째* 인수입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

매개 변수에 대한 인수가 제공되지 않으면 매개 변수는 스트링에서 **'%N'** 으로 반환됩니다. *Real* 유형 값의 경우 기본 스트링 변환은 소수점 이하 두 자리로 제한됩니다.

## <a name="example"></a>예시

다음 그림에서 **PaymentModel** 데이터 소스는 **Customer** 구성 요소를 사용하여 고객 기록 목록을 반환합니다. **ProcessingDate** 필드를 사용하여 처리 날짜 값을 반환합니다.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

선택한 고객에 대한 전자 파일을 생성하도록 설계된 전자 보고(ER) 형식에서 **PaymentModel** 을 데이터 소스로 선택하고 프로세스 흐름을 제어합니다. 선택한 고객이 보고서가 처리되는 날짜에 중지되면 사용자에게 알리기 위해 예외가 발생합니다. 이러한 유형의 처리 제어를 위해 설계된 공식은 다음 리소스를 사용할 수 있습니다.

- 다음 텍스트가 있는 레이블 SYS70894:

    - **EN-US 언어의 경우:** 인쇄할 항목이 없습니다.
    - **DE 언어의 경우:** 약삭빠르게.

- 다음 텍스트가 있는 레이블 SYS18389:

    - **EN-US 언어의 경우:** %1 고객이 %2에 대해 중지되었습니다.
    - **DE 언어의 경우:** Debitor '%1' wird für %2 gesperrt.

다음은 디자인할 수 있는 표현입니다.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

2015년 12월 17일 **Litware Retail** 고객에 대한 보고서가 **EN-US** 문화권 및 **EN-US** 언어로 처리되는 경우 이 수식은 사용자에게 예외 메시지로 표시될 수 있는 다음 텍스트를 반환합니다.

*인쇄할 항목이 없습니다. Customer Litware Retail은 2015년 12월 17일에 중단되었습니다.*

2015년 12월 17일에 **Litware Retail** 고객에 대해 동일한 보고서가 **DE** 문화권 및 **DE** 언어로 처리되는 경우 수식은 다른 날짜 형식을 사용하는 다음 텍스트를 반환합니다.

*약삭빠르게. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> 다음 구문은 레이블에 대한 ER 공식에 적용됩니다.
>
> - **Microsoft Dynamics 365 Finance 앱의 리소스 레이블:** **\@X**, 여기서 **X는** AOT(애플리케이션 개체 트리)의 레이블 ID입니다.
> - **ER 구성에 있는 레이블의 경우:** **@"GER_LABEL:X"**, 여기서 **X** 는 ER 구성의 레이블 ID입니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]