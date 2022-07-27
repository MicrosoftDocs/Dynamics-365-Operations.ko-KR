---
title: 통합용 가져오기 형식
description: 이 토픽에서는 여러 법인의 재무 데이터를 통합할 때 사용되는 가져오기 형식에 대한 자세한 정보를 제공합니다.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6d25ebfedfe748dfa262c1d4b0671539e6150a0f9f05dfca42e87f23486fbb19
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450496"
---
# <a name="import-format-for-consolidation"></a>통합용 가져오기 형식

[!include [banner](../includes/banner.md)]

이 토픽에서는 여러 법인의 재무 데이터를 통합할 때 사용되는 가져오기 형식에 대한 자세한 정보를 제공합니다. 가져오기 형식은 텍스트(.txt) 파일로 저장해야 합니다.

## <a name="import-format"></a>가져오기 형식

다음 표에는 가져오기 중 통합을 수행할 때 사용해야 하는 가져오기 형식이 나열되어 있습니다.

| 레코드 테이블 | 포맷 | 메모 |
|--------------|---------|-------|
| 1            | 170150, 영업권, 4 | <ul><li>레코드 테이블</li><li>원본 주 계정 ID</li><li>주 계정 라인</li><li>주 계정 유형</li></ul> |
| 2            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>주 계정 ID</li><li>거래일</li><li>회계 기간 유형(**0** = 개시, **1** = 운영 및 **2** = 마감)</li><li>거래 통화</li><li>차변 또는 대변(**0** = 차변 및 **1** = 대변)</li><li>포스팅 레이어</li><li>거래 금액</li><li>수량</li><li>로컬 RecID(거래에 대한 모호하고 고유한 int64 값)</li></ul> |
| 3            | USMF0000009, 2017/01/01, FY2017, 1, 2017,01,01, 602200, USD, 6053.6.0 | <ul><li>항목 번호(예산 헤더 거래 번호)</li><li>예산 헤더의 기본 날짜</li><li>예산 모델 ID</li><li>예산 유형(**1** - 원본 예산, **2** - 송금, **3** - 개정, **4** - 지출원인행위, **5** - 사전 지출원인행위, **6** - 이월예산, **7** - 프로젝트, **8** - 고정 자산, **9** - 수요예측, **10** - 공급 예측, **11** - 분배, **12** - 예비 예산.)</li><li>라인의 날짜</li><li>라인의 기본 계정 ID</li><li>라인의 통화 코드</li><li>거래 통화의 라인에 대한 금액</li><li>라인의 예산 유형에 대한 열거 정수 값(비용 또는 수익)</li></ul> |
| 4            | DEMF | RecordCompany는 원본 법인입니다. |
| 5            | 110130, 2015/01/01, 1, USD, 0,0,80699.39,0,1 | <ul><li>주 계정 ID</li><li>거래 날짜</li><li>회계 기간 유형(0 개시, 1 운영, 2 마감)</li><li>거래 통화</li><li>차변 또는 대변(0 차변, 1 대변)</li><li>포스팅 레이어</li><li>거래 금액</li><li>수량</li><li>로컬 recid(거래에 대한 모호하고 고유한 int64 값)</li></ul>  |
| 6            | BusinessUnit, 1 부서, 2 | 세그먼트 순서에 정의된 재무 차원 특성입니다.<p>**내보내기** 페이지를 사용하여 특성이 정의된 방식을 확인할 수 있습니다.</p> |
| 7            | 002,1,658 | <ul><li>재무 차원 값</li><li>재무 차원(RecordDimensions에서 제공되는 인덱스)</li><li>RecordTrans 또는 RecordTrans2의 고유 레코드 ID와 연결된 모호하고 고유한 레코드 ID</li></ul> |
| 8            | 002,1,1 | <ul><li>RecordBudget의 거래와 연결된 차원 값</li><li>재무 차원(RecordDimensions에서 제공되는 인덱스)</li><li>파일의 거래 라인 순서와 일치하는 모호한 라인 레코드 ID</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
