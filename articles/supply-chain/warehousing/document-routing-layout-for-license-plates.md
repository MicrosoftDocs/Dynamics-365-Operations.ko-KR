---
title: 번호판 레이블에 대한 문서 라우팅 레이아웃
description: 이 토픽에서는 서식 지정 방법을 사용하여 레이블에 값을 인쇄하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 9055e4c6e35099b7769faa6fc83f71523f2e64fd
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450046"
---
# <a name="document-routing-layout-for-license-plate-labels"></a>번호판 레이블에 대한 문서 라우팅 레이아웃

[!include [banner](../includes/banner.md)]


문서 라우팅 레이아웃은 번호판 레이블의 레이아웃과 여기에 인쇄되는 데이터를 정의합니다. 모바일 디바이스 메뉴 항목 및 작업 템플릿을 설정할 때 인쇄 트리거 지점을 구성합니다.

일반적인 시나리오에서 창고 수령 직원은 입고 영역에 도착하는 팔레트의 내용물을 기록한 직후 번호판 레이블을 인쇄합니다. 물리적 레이블이 팔레트에 부착됩니다. 그런 다음 이후의 아웃바운드 피킹 작업과 이후의 보관 프로세스의 일부로 검증에 사용할 수 있습니다.

인쇄 디바이스가 전송된 텍스트를 해석할 수 있는 경우 매우 복잡한 레이블을 인쇄할 수 있습니다. 예를 들어 바코드가 포함된 ZPL(Zebra 프로그래밍 언어) 레이아웃은 다음 예와 유사할 수 있습니다.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

레이블 인쇄 프로세스의 일부로 텍스트 `$LicensePlateId$`이 예에서는 데이터 값으로 대체됩니다.

인쇄될 값을 보려면 **창고 관리 \> 문의 및 보고서 \> 번호판 레이블** 로 이동하세요.

널리 사용되는 여러 레이블 생성 도구를 사용하여 레이블 레이아웃의 텍스트 서식을 지정할 수 있습니다. 이러한 도구 중 대부분은 `$FieldName$` 형식을 지원합니다. 또한 Microsoft Dynamics 365 Supply Chain Management 문서 라우팅 레이아웃에 대한 필드 매핑의 일부로 특수 형식 지정 논리를 사용합니다.

## <a name="turn-on-this-feature-for-your-system"></a>시스템에 이 기능 사용 설정

시스템에 이 항목에서 설명하는 기능이 아직 포함되어 있지 않으면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)로 이동하여 *향상된 번호판 레이블 레이아웃* 기능을 켭니다. (Supply Chain Management 버전 10.0.21부터 이 기능은 기본적으로 켜져 있습니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다.)

## <a name="custom-number-formats"></a>사용자 지정 숫자 형식

다음 형식의 코드를 사용하여 인쇄되는 숫자 필드 값의 형식을 사용자 지정할 수 있습니다.

```dos
$FieldName:FormatString$
```

다음은 이 형식에 대한 설명입니다.

- `FieldName` 데이터 필드의 이름(예: **수량**)입니다.
- `FormatString` 데이터를 인쇄해야 하는 방법을 정의합니다.

다음 예는 작업 수량(**수량**) 필드를 사용자 정의하는 방법을 보여줍니다.

- 항상 4자리를 표시하려면(자리 표시자로 0을 사용하여) `$Qty:0000$`을 사용합니다. 예를 들어 수량이 10이면 레이블에 "0010"이 표시됩니다.
- 항상 소수점 이하 두 자리를 표시하려면 `$Qty:0.00$`를 사용하세요. 예를 들어 수량이 10이면 레이블에 "10.00"이 표시됩니다.

사용 가능한 숫자 형식 문자열의 전체 목록은 [사용자 지정 숫자 형식 문자열](/dotnet/standard/base-types/custom-numeric-format-strings)을 참조하세요.

## <a name="custom-string-formats"></a>사용자 지정 문자열 형식

다음 필드 및 형식 코드를 사용하여 문자열의 첫 번째 문자를 제거할 수 있습니다.

```dos
$FieldName:#..$
```

여기서 `#` 문자는 건너뛸 문자의 번호를 지정합니다. 예를 들어, 처음 두 문자를 포함하지 않는 SSCC(Serial Shipping Container Code) 번호판 번호를 인쇄하려면 `$LicensePlateId:2..$`을 사용합니다. 이 경우 번호판 번호 0011111111111222221는 "11111111111222221"로 인쇄됩니다.

## <a name="custom-datetime-formats"></a>사용자 지정 날짜/시간 형식

다음 예는 날짜를 인쇄하는 데 사용되는 형식을 제어하는 방법을 보여줍니다.

```dos
$PrintedDate:dd-MM-yyyy$
```

이 예에서 2020년 4월 30일 날짜는 "30-04-2020"으로 인쇄됩니다.

사용 가능한 날짜/시간 형식의 전체 목록은 [사용자 지정 날짜 및 시간 형식 문자열](/dotnet/standard/base-types/custom-date-and-time-format-strings)을 참조하세요.

## <a name="print-individual-lines-from-multiline-data"></a>여러 줄 데이터에서 개별 줄 인쇄

데이터 필드에 여러 줄(즉, 줄 바꿈로 구분된 줄)이 포함된 경우 다음 형식을 사용하여 개별 줄을 인쇄할 수 있습니다.

```dos
$FieldName[#]$
```

여기서,`#` 문자는 인쇄할 줄 번호입니다. (첫 번째 줄에는 1을 사용합니다.)

예를 들어 시스템에는 다음과 같은 여러 줄 주소를 저장하는 `AdditionalAddress` 필드가 있습니다.

Contoso Inc.  
123 도로명  
특정 도시, 특정 주

다음 코드를 사용하여 이 주소를 한 번에 한 줄씩 인쇄할 수 있습니다.

| 코드 | 인쇄되는 텍스트 |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 도로명 |
| `$AdditionalAddress[3]$` | 특정 도시, 특정 주 |

## <a name="print-and-format-from-a-display-method"></a>표시 방법에서 인쇄 및 서식 지정

다음 형식을 사용하여 표시 방법에서 인쇄할 수 있습니다.

```dos
$DisplayMethod()$
```

이 형식을 이 항목의 앞부분에서 설명한 다른 형식과 결합할 수 있습니다. 예를 들어, ``DisplayListOfItemsNumbers()`이라는 표시 메서드가 있고 이 메서드의 첫 번째 품목 번호를 인쇄하려고 합니다. 이 경우 다음 코드를 사용할 수 있습니다.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>레이블 인쇄 방법에 대한 추가 정보

레이블을 설정하고 인쇄하는 방법에 대한 자세한 내용은 [번호판 레이블 인쇄 활성화](tasks/license-plate-label-printing.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]