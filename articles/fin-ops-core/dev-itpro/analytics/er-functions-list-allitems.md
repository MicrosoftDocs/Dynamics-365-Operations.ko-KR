---
title: 모든 항목 ER 함수
description: 이번에는 ALLITEMS 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: cf1e05e9377ba18ad0269a48b13bd242a8e5356f4a52ea3723e347dcf5e138e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460851"
---
# <a name="allitems-er-function"></a>모든 항목 ER 함수

[!include [banner](../includes/banner.md)]

이 `ALLITEMS` 함수는 메모리 내 선택 항목으로 실행되고 지정된 경로와 일치하는 모든 항목을 나타내는 *기록 목록* 으로 새로운 병합된 기록 목록 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>인수

`path`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

경로는 *기록 목록* 데이터 유형의 데이터 소스 요소에 대한 유효한 데이터 소스 경로로 정의되어야 합니다. 경로 스트링 및 날짜와 같은 데이터 요소는 디자인 타임에 전자 보고(ER) 표현식 작성기에서 오류를 발생시켜야 합니다.

대용량 데이터를 포함할 수 있는 트랜잭션 데이터 원본에는 이 함수를 사용하지 않는 것이 좋습니다. 대신 [ALLTEMSQUERY](er-functions-list-allitemsquery.md) 함수를 사용하는 것이 좋습니다.

## <a name="example-1"></a>예시 1

`SPLIT("abcdef" , 2)` 데이터 소스 **DS** 로 입력하면 `COUNT( ALLITEMS (DS))` 표현식은 **3** 을 반환합니다.

## <a name="example-2"></a>예시 2

VendTable 애플리케이션 테이블을 참조하는 *기록 목록* 데이터 형식의 데이터 원본으로 **Vend** 를 입력하면 `ALLITEMS (Vend.'<Relations'.ContactPerson)` 식은 **ContactPerson** 테이블 구조가 있고 ContactPerson을 사용하여 액세스할 수 있는 모든 담당자가 포함된 병합된 기록 목록을 반환합니다. **ContactForParty == VendTable.Party** 관계이며 참조된 공급 업체 테이블의 모든 공급 업체에서 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]