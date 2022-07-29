---
title: 텍스트 ER 함수
description: 이번에는 TEXT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 38550b8b5181b49bcb8504129932f185ea95e038e38d4581bc3e0fa076f4fb50
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460603"
---
# <a name="text-er-function"></a>텍스트 ER 함수

[!include [banner](../includes/banner.md)]

이 `TEXT` 함수는 현재 애플리케이션 인스턴스의 서버 로케일 설정에 따라 형식이 지정된 텍스트 스트링으로 변환된 후 지정된 숫자를 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
TEXT (number)
```

## <a name="arguments"></a>인수

`number`: *정수* 또는 *실수*

텍스트 스트링으로 변환해야 하는 숫자입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

*Real* 유형 값의 경우 스트링 변환은 소수점 이하 두 자리로 제한됩니다.

## <a name="example"></a>예시

Microsoft Dynamics 365 Finance인스턴스의 서버 로케일이 **EN-US** 로 정의된 경우 `TEXT (NOW ())` 현재 재무 세션 날짜인 2015년 12월 17일을 **'12/17/2015 07:59:23 AM'** 이라는 텍스트 스트링으로 반환합니다. `TEXT (1/3)` **0.33** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]