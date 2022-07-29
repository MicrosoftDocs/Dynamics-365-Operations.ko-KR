---
title: 필터 ER 함수
description: 이번에는 FILTER 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: e857306574dda7bad5dd25fc7708514997d8e86f
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2021
ms.locfileid: "8460803"
---
# <a name="filter-er-function"></a>필터 ER 함수

[!include [banner](../includes/banner.md)]

이 `FILTER` 함수는 쿼리가 지정된 조건을 필터링하도록 변경된 후 지정된 목록을 *기록 목록* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
FILTER (list, condition)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`condition`: *부울*

지정된 목록의 기록을 필터링하는 데 사용되는 유효한 조건식입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a><a name="usage-notes"></a>사용 참고 사항

지정된 조건이 *데이터베이스* 수준에서 테이블 기록 유형의 전자 보고(ER) 데이터 소스에 적용된다는 점에서 이 함수는 [WHERE](er-functions-list-where.md) 함수와 다릅니다. 목록과 조건은 테이블과 관계를 사용하여 정의할 수 있습니다.

이 함수(`list` 및 `condition`)에 대해 구성된 인수 중 하나 또는 둘 모두에서 이 요청이 직접 SQL 호출로 변환되는 것을 허용하지 않으면 디자인 타임에 예외가 발생합니다. 이 예외는 사용자에게 데이터베이스를 쿼리하는 데 사용할 수 없거나 `list` `condition` 사용할 수 없음을 알려줍니다.

> [!NOTE]
> `FILTER` 함수를 사용하여 선택 기준을 지정할 때 [`VALUEIN`](er-functions-logical-valuein.md) 함수는 `WHERE` 함수와 다르게 작동합니다.
> 
> - `VALUEIN` 함수가 `WHERE` 함수 범위에서 사용되고 `VALUEIN`의 두 번째 인수가 기록을 반환하지 않는 데이터 소스를 참조하는 경우 `VALUEIN` 반환하는 부울 *[False](er-formula-supported-data-types-primitive.md#boolean)* 값이 고려됩니다. 따라서 **VendGroups** 데이터 소스가 공급 업체 그룹 기록을 반환하지 않는 경우 `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` 표현식은 공급 업체 기록을 반환하지 않습니다.
> - `VALUEIN` 함수가 `FILTER` 함수 범위에서 사용되고 `VALUEIN`의 두 번째 인수가 기록을 반환하지 않는 `VALUEIN` 데이터 소스를 참조하는 경우 반환하는 부울 *[False](er-formula-supported-data-types-primitive.md#boolean)* 값은 무시됩니다. 따라서 **VendGroups** 데이터 원본이 공급 업체 그룹 기록을 반환하지 않는 경우에도 `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` 식은 공급 업체 데이터 원본의 모든 **공급 업체** 기록을 반환합니다.

## <a name="example-1"></a>예시 1

**Vendor** 가 VendTable 테이블을 참조하는 ER 데이터 소스로 구성된 경우 `FILTER (Vendors, Vendors.VendGroup = "40")` 표현식은 공급 업체 그룹 40에 속하는 공급 업체의 목록만 반환합니다.

## <a name="example-2"></a>예시 2

**Vendor** 가 VendTable 테이블을 참조하는 ER 데이터 원본으로 구성되고 **parmVendorBankGroup** 이 *스트링* 데이터 유형의 값을 반환하는 ER 데이터 원본으로 구성된 경우 `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` 표현식은 특정 은행 그룹.

## <a name="example-3"></a>예시 3

*계산된 필드* 유형의 데이터 소스 **DS** 를 입력하고 여기에 `SPLIT ("A,B,C", ",")` 식이 포함됩니다. 이후 다른 표현식 `FILTER( DS, DS.Value = "B")`을 입력합니다. ER 수식 디자이너에서 이 식을 저장하려고 하면 다음 예외가 throw됩니다. 확인 오류 FILTER 함수의 목록 표현식을 쿼리할 수 없습니다.'

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
