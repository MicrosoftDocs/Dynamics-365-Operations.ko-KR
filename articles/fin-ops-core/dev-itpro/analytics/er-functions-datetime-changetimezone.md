---
title: CHANGETIMEZONE ER 함수
description: 이번에는 CHANGETIMEZONE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 48e96cfbc19503daf6a20363c4520c765f11a249
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "8461035"
---
# <a name="changetimezone-er-function"></a>CHANGETIMEZONE ER 함수

[!include [banner](../includes/banner.md)]

이 `CHANGETIMEZONE` 함수는 한 시간대의 지정된 *[날짜/시간](er-formula-supported-data-types-primitive.md#datetime)* 값에서 다른 시간대의 날짜/시간 값으로 변환된 표준 시간대(그리니치 표준시 \[GMT\])의 DateTime 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>인수

`datetime`: *날짜 시간*

변환할 날짜/시간 값을 나타내는 표준 시간대 시간대의 날짜/시간 값입니다.

`base time zone` *[스트링](er-formula-supported-data-types-primitive.md#string)*

지정된 날짜/시간 값이 변환되기 전에 이동되는 시간대의 이름입니다.

`target time zone`: *스트링*

변환하는 동안 변환된 날짜/시간 값이 이동되는 시간대의 이름입니다.

## <a name="return-values"></a>반환 값

*날짜 시간*

표준 시간대 시간대의 결과 날짜/시간 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

원본 및 대상 시간대를 지정하려면 [IANA(Internet Assigned Numbers Authority)](https://www.iana.org/)에서 [제공하거나](https://data.iana.org/time-zones/releases/) Microsoft Windows에서 [지원하는](/windows-hardware/manufacture/desktop/default-time-zones) 시간대 이름을 사용할 수 있습니다.

런타임 시 제공된 이름이 IANA 목록이나 Windows 레지스트리에 없으면 'Time zone '\<time zone name\>' does not exist' 예외가 발생합니다.

일광 절약 시간제가 적용되는 시간대의 경우 변환 시 표준 시간대(Coordinated Universal Time) 일광 절약 시간 오프셋을 고려합니다. 이 오프셋에 대해 사용 가능한 최신 정보는 변환 중에 사용됩니다.

## <a name="example-1"></a>예시 1

이 예시에서는 Windows의 표준 시간대 이름이 사용됩니다.

**계산된 필드** 유형의 **DSX** 데이터 소스를 구성합니다. 다음과 같은 표현이 포함되어 있습니다.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

**계산된 필드** 유형의 **DSY** 데이터 소스 표현식을 `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`로 구성하면 **DSX** 데이터 소스는 **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00** 텍스트를 반환합니다. :00. 이 텍스트는 6월 1일에 제공된 두 시간대 간의 시차가 24시간 이상임을 보여줍니다. 따라서 변환된 날짜/시간 값은 기본 표준 시간대가 대상 표준 시간대보다 빠르기 때문에 지정된 날짜/시간 값보다 하루 빠릅니다.

**계산된 필드** 유형의 **DSY** 데이터 소스 표현식을 `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`로 구성하면 **DSX** 데이터 소스는 **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00** 텍스트를 반환합니다. :00. 이 텍스트는 12월 1일에 제공된 두 시간대 간의 시차가 24시간 미만임을 보여줍니다. 따라서 변환된 날짜/시간 값은 주어진 날짜/시간 값과 같습니다.

> [!NOTE]
> 동일한 식은 제공된 날짜/시간에 제공된 표준 시간대에 대해 다른 표준 시간대 일광 절약 시간 오프셋이 관찰되기 때문에 동일한 표준 시간대 쌍에 대해 제공된 날짜/시간 값과 변환된 날짜/시간 값 간에 다른 차이를 반환합니다.

## <a name="example-2"></a>예시 2

이 예시에서는 IANA 시간대 이름이 사용됩니다.

**계산된 필드** 유형의 **DSX** 데이터 소스를 구성합니다. 다음과 같은 표현이 포함되어 있습니다.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

**계산된 필드** 유형의 **DSY** 데이터 소스 표현식을 `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`로 구성하면 **DSX** 데이터 소스는 **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00** 텍스트를 반환합니다. :00. 이 텍스트는 6월 1일에 제공된 두 시간대 간의 시차가 24시간 이상임을 보여줍니다. 따라서 변환된 날짜/시간 값은 기본 표준 시간대가 대상 표준 시간대보다 빠르기 때문에 지정된 날짜/시간 값보다 하루 빠릅니다.

**계산된 필드** 유형의 **DSY** 데이터 소스 표현식을 `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`로 구성하면 **DSX** 데이터 소스는 **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00** 텍스트를 반환합니다. :00. 이 텍스트는 12월 1일에 제공된 두 시간대 간의 시차가 24시간 미만임을 보여줍니다. 따라서 변환된 날짜/시간 값은 주어진 날짜/시간 값과 같습니다.

## <a name="example-3"></a>예시 3

**계산된 필드** 유형의 **DSX** 데이터 소스를 구성합니다. 다음과 같은 표현이 포함되어 있습니다.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

**계산된 필드** 유형의 **DSY** 데이터 소스 표현식을 `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`로 구성하면 **DSX** 데이터 소스는 **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00** 텍스트를 반환합니다. :00'. 이 텍스트는 6월 1일에 제공된 두 시간대 간의 시차가 24시간 이상임을 보여줍니다. 따라서 변환된 날짜/시간 값은 지정된 날짜/시간 값보다 하루 늦습니다. 대상 시간대가 기준 시간대보다 앞서기 때문입니다.

## <a name="example-4"></a>예시 4

표준 시간대 정보가 포함되지 않은 텍스트로 외부 소스에서 날짜/시간 스탬프를 받을 수 있습니다. 그러나 소스가 작동하는 시간대를 알고 있을 수 있습니다. 예를 들어, 스페인에서 운영되는 서비스에서 날짜/시간 스탬프 **01/12/2021 12:55:00** 을 받습니다. 이 날짜/시간 값을 데이터베이스에 올바르게 저장하려면 다음 변환을 완료하십시오.

- 날짜/시간 스탬프를 텍스트에서 표준 시간대 날짜/시간 값으로 변환하도록 **계산된 필드** 유형의 **DSY** 데이터 원본을 구성합니다.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- 변환된 날짜/시간 값을 외부 소스 표준 시간대의 날짜/시간 값으로 표준 시간대(UTC)로 이동하도록 **계산 필드** 유형의 **DSX** 데이터 소스를 구성합니다.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> 날짜/시간 변환 `CHANGETIMEZONE` 함수를 사용할 때 모든 날짜/시간 값은 표준 시간대(Coordinated Universal Time) 시간대의 값으로 데이터베이스에 저장된다는 점에 유의하십시오. 이 값은 애플리케이션 페이지에 표시되기 전에 변환됩니다. 변환은 현재 로그인한 애플리케이션 사용자의 기본 설정대로 [설정된](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) 표준 시간대를 고려합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
