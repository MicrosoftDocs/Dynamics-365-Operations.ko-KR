---
title: FA_BALANCE ER 함수
description: 이번에는 FA_BALANCE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 17730b23313eaa417a824470d5b31abedb58bc7a7e8e62479358378b708b99e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460915"
---
# <a name="fa_balance-er-function"></a>FA_BALANCE ER 함수

[!include [banner](../includes/banner.md)]

`FA_BALANCE` 함수는 지정된 고정 자산 항목, 가치 모델 코드, 보고 연도 및 보고 날짜에 대한 고정 자산 잔액에 대한 데이터로 구성된 *컨테이너(기록)* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>인수

`fixed asset code`: *스트링*

잔액이 계산되는 고정 자산 항목의 코드를 나타내는 *스트링* 값입니다.

`value model code`: *스트링*

잔액이 계산되는 값 모델의 코드를 나타내는 *스트링* 값입니다.

`reporting year`: *열거 값*

잔액 계산 기간을 정의하는 **AssetYear** 애플리케이션 열거형의 열거형 값입니다.

`reporting date`: *날짜*

잔액 계산 날짜를 정의하는 *날짜* 값입니다.

## <a name="return-values"></a>반환 값

*컨테이너(기록)*

결과 기록 값입니다.

## <a name="example"></a>예시

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` 현재 애플리케이션 세션 날짜에 현재 가치 모델에 대해 준비된 고정 자산 **COMP-000001** 에 대한 잔액의 데이터 **컨테이너를** 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]