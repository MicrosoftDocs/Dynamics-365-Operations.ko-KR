---
title: 비즈니스 영역별 범주의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 비즈니스 도메인 특정 함수에 대한 정보를 제공합니다.
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
ms.openlocfilehash: a8f0812e4262a264ffc89b72e0f4fc8c55d6c6822095f550c8f05296bb057a38
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460965"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>비즈니스 영역별 범주의 ER 함수 목록

[!include [banner](../includes/banner.md)]

전자 보고(ER) 도메인별 함수를 사용하여 Microsoft Dynamics 365 Finance 구현과 관련된 계산 및 데이터 액세스 요청을 수행할 수 있습니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="list-of-supported-functions"></a>지원되는 함수 목록

| 직렬| 설명 |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | 이 함수는 지정된 송장 번호의 자릿수를 기반으로 MOD10 표현식으로 채권자 참조를 나타내는 *스트링* 값을 반환합니다. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | 이 함수는 지정된 스트링에서 가져온 단일 재무 차원 ID를 나타내는 *스트링* 값을 반환합니다. 지정된 스트링은 모든 차원을 쉼표로 구분된 ID 목록으로 표시합니다. |
| [변환화폐](er-functions-other-convertcurrency.md) | 이 함수는 지정된 날짜에 지정된 회사의 설정을 사용하여 지정된 통화 금액을 지정된 소스 통화에서 지정된 대상 통화로 변환한 결과를 나타내는 *Real* 값을 반환합니다. |
| [CurCredRef](er-functions-other-curcredref.md) | 이 함수는 지정된 송장 번호의 자릿수를 기반으로 채권자 참조를 나타내는 *스트링* 값을 반환합니다. |
| [FA_밸런스](er-functions-other-fabalance.md) | 이 함수는 지정된 고정 자산 항목, 가치 모델 코드, 보고 연도 및 보고 날짜에 대한 고정 자산 잔액에 대한 데이터로 구성된 *컨테이너(기록)* 값을 반환합니다. |
| [FA_Sum](er-functions-other-fasum.md) | 이 함수는 지정된 고정 자산 항목, 가치 모델 코드 및 날짜 기간에 대한 고정 자산 금액에 대한 데이터로 구성된 *컨테이너(기록)* 값을 반환합니다. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | 이 함수는 사용자가 현재 로그인한 법인(회사)의 코드를 나타내는 *스트링* 값을 반환합니다. |
| [ISOCredRef](er-functions-other-isocredref.md) | 이 함수는 지정된 송장 번호의 숫자와 알파벳 기호를 기반으로 ISO(International Organization for Standardization) 채권자 참조를 나타내는 *스트링* 값을 반환합니다. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | 이 함수는 지정된 스트링이 유효한 국제 은행 계좌 번호(IBAN)를 나타내는 경우 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [Mod_97](er-functions-other-mod97.md) | 이 함수는 지정된 송장 번호의 자릿수를 기반으로 MOD97 표현식으로 채권자 참조를 나타내는 *스트링* 값을 반환합니다. |
| [NumSeq값](er-functions-other-numseqvalue.md) | 이 함수는 지정된 숫자 시퀀스, 범위 및 범위 ID를 기반으로 숫자 시퀀스의 새로 생성된 값을 나타내는 *스트링* 값을 반환합니다. 범위 ID는 ER 형식이 실행되는 컨텍스트에서 제공하는 회사 코드와 같습니다. |
| [라운드 금액](er-functions-other-roundamount.md) | 이 함수는 지정된 반올림 규칙에 따라 지정된 소수점 이하 자릿수로 지정된 금액을 반올림한 결과를 나타내는 *실수* 값을 반환합니다. |
| [TableName2ID](er-functions-other-tablename2id.md) | 이 함수는 지정된 테이블 이름에 대한 테이블 ID의 숫자 표현을 *정수* 값으로 반환합니다. |

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]