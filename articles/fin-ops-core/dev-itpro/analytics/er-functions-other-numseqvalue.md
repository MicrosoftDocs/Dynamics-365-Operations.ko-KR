---
title: NUMSEQVALUE ER 함수
description: 이번에는 NUMSEQVALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 53040d1f4b3c8089fab264a524309df909a90ed5e617bd86658704b286fabb34
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460701"
---
# <a name="numseqvalue-er-function"></a>NUMSEQVALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `NUMSEQVALUE` 함수는 지정된 숫자 시퀀스, 범위 및 범위 ID를 기반으로 새로 생성된 숫자 시퀀스 값을 나타내는 *스트링* 값을 반환합니다. 범위 ID는 전자 보고(ER) 형식이 실행되는 컨텍스트에서 제공하는 회사 코드와 같습니다.

## <a name="syntax-1"></a>구문 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>구문 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>구문 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>인수

`number sequence code`: *스트링*

새 값이 필요한 숫자 시퀀스의 코드를 나타내는 텍스트 값입니다.

`number sequence record ID` *Int64*

새 값이 필요한 숫자 시퀀스의 정의가 포함된 NumberSequenceTable 테이블에 있는 기록의 기록 ID를 나타내는 *Int64* 값입니다.

`scope type`: *열거형 값*

새 값이 필요한 숫자 시퀀스의 범위를 정의하는 **ERExpressionNumberSequenceScopeType** 열거형의 열거형 값입니다. 사용 가능한 범위 유형은 **공유**, **법인** 및 **회사** 입니다.

`scope ID`: *스트링*

지정된 범위 유형을 기반으로 범위를 식별하는 *스트링* 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

**공유** 범위 유형의 경우 빈 스트링을 범위 ID로 지정하십시오.

**회사** 및 **법인** 범위 유형의 경우 회사 코드를 범위 ID로 지정하십시오. 이러한 범위 유형의 범위 ID로 빈 스트링을 지정하면 현재 회사 코드가 사용됩니다.

구문 1이 사용되면 **회사** 범위 유형에 대해 번호 시퀀스가 요청되고 회사 코드는 ER 형식이 실행되는 컨텍스트에서 제공됩니다.

## <a name="example-1"></a>예시 1

ER 형식에서 *사용자 입력 매개 변수* 유형의 **AskNumSeq** 데이터 소스를 정의합니다. 이 데이터 소스는 **설명** 확장 데이터 유형(EDT)을 나타냅니다. 다음으로 *계산된 필드* 유형의 **NumSeq** 데이터 소스를 정의합니다. 이 데이터 소스에는 `NUMSEQVALUE (AskNumSeq)` 표현식이 포함되어 있습니다. **NumSeq** 데이터 소스가 호출되면 대화 상자에 해당 코드를 입력하여 런타임에 지정된 숫자 시퀀스의 새로 생성된 값을 반환합니다. **회사** 범위 유형에 대해 번호 시퀀스가 요청됩니다. 회사 코드는 ER 형식이 실행되는 컨텍스트에서 제공됩니다.

## <a name="example-2"></a>예시 2

다음 데이터 소스는 모델 매핑에 정의됩니다.

- *테이블* 유형의 **LedgerParms** 데이터 소스입니다. 이 데이터 소스는 LedgerParameters 테이블을 참조합니다.
- *계산된 필드* 유형의 **NumSeq** 데이터 소스입니다. 이 데이터 소스에는 `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)` 표현식이 포함되어 있습니다.

**NumSeq** 데이터 소스가 호출되면 ER 형식이 실행되는 컨텍스트를 제공하는 회사의 총계정원장 매개 변수에 구성된 숫자 시퀀스의 새로 생성된 값을 반환합니다. 이 번호 순서는 분개를 고유하게 식별하고 거래를 함께 연결하는 배치 번호 역할을 합니다.

## <a name="example-3"></a>예시 3

다음 데이터 소스는 모델 매핑에 정의됩니다.

- Microsoft Dynamics 365 Finance *열거형* 유형의 **enumScope** 데이터 원본입니다. 이 데이터 소스는 **ERExpressionNumberSequenceScopeType** 열거를 참조합니다.
- *계산된 필드* 유형의 **NumSeq** 데이터 소스입니다. 이 데이터 소스에는 `NUMSEQVALUE ("Gene_1", enumScope.Company, "")` 표현식이 포함되어 있습니다.

**NumSeq** 데이터 소스가 호출되면 ER 형식이 실행되는 컨텍스트를 제공하는 회사에 대해 구성된 **Gene\_1** 번호 시퀀스의 새로 생성된 값을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]