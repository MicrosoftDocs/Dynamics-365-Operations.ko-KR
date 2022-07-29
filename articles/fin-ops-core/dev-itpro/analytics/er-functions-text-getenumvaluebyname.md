---
title: GETENUMVALUEBYNAME ER 함수
description: 이번에는 GETENUMVALUEBYNAME 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 09/23/2020
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
ms.openlocfilehash: 03759852e5ceb13b79b0df4592bdcef76eb0a82865725c00df40b9cc5f786240
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460939"
---
# <a name="getenumvaluebyname-er-function"></a>GETENUMVALUEBYNAME ER 함수

[!include [banner](../includes/banner.md)]

이 `GETENUMVALUEBYNAME` 함수는 *스트링* 값으로 지정된 열거형 이름을 사용하여 지정된 *열거형* 데이터 소스에서 특정 열거형 값을 검색합니다. *Enum* 값이 발견되면 함수가 이를 반환합니다. 그렇지 않으면 함수는 **null** 열거형 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>인수

`enumeration data source path`: *열거*

다음 열거 유형 중 하나의 데이터 소스의 유효한 경로:

- 전자 보고(ER) 모델 열거
- ER 형식 열거
- Microsoft Dynamics 365 Finance 열거

`enumeration value text`: *스트링*

단일 열거형 값의 이름을 나타내는 스트링 값입니다.

## <a name="return-values"></a>반환 값

Nullable *열거형*

결과 열거형 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

*스트링* 값으로 지정된 열거형 값의 이름을 사용하여 *열거형* 값을 찾을 수 없는 경우 예외가 throw되지 않습니다.

## <a name="example-1"></a>예시 1

다음 그림에서는 **ReportDirection** 열거가 데이터 모델에 도입되었습니다. 열거형 값에 대해 레이블이 정의되어 있습니다.

![데이터 모델 열거에 사용 가능한 값입니다.](./media/ER-data-model-enumeration-values.PNG)

다음 그림은 이러한 세부 정보를 보여줍니다.

- **$Direction** 데이터 소스는 ER 보고서에서 구성됩니다. 이 데이터 원본은 **ReportDirection** 모델 열거를 기반으로 구성됩니다.
- `$IsArrivals` 표현식은 모델 열거 기반 **$Direction** 데이터 소스를 이 함수의 매개 변수로 사용하도록 설계되었습니다.
- 이 비교 표현식의 값은 **TRUE** 입니다.

![데이터 모델 열거의 예.](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>예시 2

`GETENUMVALUEBYNAME` 및 [`LISTOFFIELDS`](er-functions-list-listoffields.md) 함수를 사용하면 지원되는 열거의 값과 레이블을 텍스트 값으로 가져올 수 있습니다. (지원되는 열거형은 애플리케이션 열거형, 데이터 모델 열거형 및 형식 열거형입니다.)

다음 그림에서는 모델 매핑에 **TransType** 데이터 소스가 도입되었습니다. 이 데이터 소스는 **LedgerTransType** 애플리케이션 열거를 참조합니다.

![애플리케이션 열거를 참조하는 모델 매핑의 데이터 소스입니다.](./media/er-functions-text-getenumvaluebyname-example2-1.png)

다음 그림은 모델 매핑에 구성된 **TransTypeList** 데이터 소스를 보여줍니다. 이 데이터 소스는 **TransType** 애플리케이션 열거를 기반으로 구성됩니다. 이 `LISTOFFIELDS` 함수는 모든 열거형 값을 필드가 포함된 기록 목록으로 반환하는 데 사용됩니다. 이러한 방식으로 모든 열거 값의 세부 정보가 노출됩니다.

> [!NOTE]
> **EnumValue** 필드는 `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` 식을 사용하여 **TransTypeList** 데이터 원본에 대해 구성됩니다. 이 필드는 이 목록의 모든 기록에 대한 열거 값을 반환합니다.

![선택한 열거의 모든 열거 값을 기록 목록으로 반환하는 모델 매핑의 데이터 소스입니다.](./media/er-functions-text-getenumvaluebyname-example2-2.png)

다음 그림은 모델 매핑에 구성된 **VendTrans** 데이터 소스를 보여줍니다. 이 데이터 소스는 **VendTrans** 애플리케이션 테이블에서 공급 업체 트랜잭션 기록을 반환합니다. 모든 트랜잭션의 원장 유형은 **TransType** 필드의 값으로 정의됩니다.

> [!NOTE]
> **TransTypeTitle** 필드는 `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` 표현식을 사용하여 **VendTrans** 데이터 소스에 대해 구성됩니다. 이 필드는 이 열거 값을 사용할 수 있는 경우 현재 트랜잭션의 열거 값 레이블을 텍스트로 반환합니다. 그렇지 않으면 빈 스트링 값을 반환합니다.
>
> **TransTypeTitle** 필드는 데이터 모델을 데이터 소스로 사용하는 모든 ER 형식에서 이 정보를 사용할 수 있도록 하는 데이터 모델의 **LedgerType** 필드에 바인딩됩니다.

![공급 업체 트랜잭션을 반환하는 모델 매핑의 데이터 소스입니다.](./media/er-functions-text-getenumvaluebyname-example2-3.png)

다음 그림은 [데이터 소스 디버거](er-debug-data-sources.md)를 사용하여 구성된 모델 매핑을 테스트하는 방법을 보여줍니다.

![데이터 소스 디버거를 사용하여 구성된 모델 매핑을 테스트합니다.](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

데이터 모델의 **LedgerType** 필드는 예상대로 트랜잭션 유형의 레이블을 노출합니다.

대량의 트랜잭션 데이터에 이 접근 방식을 사용하려는 경우 실행 성능을 고려해야 합니다. 자세한 내용은 [ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)을 참조하세요.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)

[ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)

[LISTOFFIELDS ER 함수](er-functions-list-listoffields.md)

[FIRSTORNULL ER 함수](er-functions-list-firstornull.md)

[WHERE ER 함수](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]