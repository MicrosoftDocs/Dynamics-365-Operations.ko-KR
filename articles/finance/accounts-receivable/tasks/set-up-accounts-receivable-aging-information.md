---
title: 수취 계정 에이징 정보 설정 및 생성
description: 이 가이드는 에이징 기간 정의를 설정하고, 고객 잔고를 에이징하며, 에이징 잔고 목록과 수금 페이지에서 잔고를 보는 데 도움이 됩니다.
author: abruer
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 996fb289c32a1819103fd67ffddc940dfd2870fb
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451150"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>수취 계정 에이징 정보 설정 및 생성

[!include [banner](../../includes/banner.md)]

이 가이드는 에이징 기간 정의를 설정하고, 고객 잔고를 에이징하며, 에이징 잔고 목록과 수금 페이지에서 잔고를 보는 데 도움이 됩니다. 이 레코딩은 USMF 데모 회사를 사용합니다.


## <a name="create-an-aging-period-definition"></a>에이징 기간 정의 만들기
1. **탐색 창 > 모듈 > 신용 및 수금 > 설정 > 에이징 기간 정의** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **에이징 기간 정의** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **아래에 추가** 를 클릭하여 새 에이징 기간을 삽입합니다.
6. **기간** 필드에 에이징 보고서에 표시할 설명을 입력합니다.
7. **단위** 필드에 숫자를 입력합니다.
8. **간격** 필드에서 옵션을 선택합니다. 원장 기간은 기간을 원장 달력과 일치시킵니다. 일, 주, 월, 분기 및 연도는 날짜 유형별로 간격의 크기를 정의합니다. 무제한은 첫 번째 기간인지 마지막 기간인지에 따라 이전 기간 이전 또는 이후의 모든 거래를 선택합니다.  
9. **에이징 표시기** 필드에서 옵션을 선택합니다.
10. 그리드 상단에서 기간을 선택합니다. 에이징 기간 정의에서 가장 오래된 기간을 설명하도록 설명 업데이트
11. **기간** 필드에 에이징 기간에 대한 새 설명을 입력합니다.
12. 페이지를 닫습니다.

## <a name="age-the-balances"></a>잔액 에이징
1. **신용 및 수금 > 정기 작업 > 고객 잔액 에이징** 으로 이동합니다.
2. **에이징 기간 정의** 필드에서 생성한 에이징 기간 정의를 선택합니다.
    + 각 에이징 기간 정의에 대해 하나의 활성 스냅샷을 가질 수 있습니다.  
    + 모든 고객은 기본적으로 처리됩니다. 이 선택 사항을 사용하여 고객의 단일 수금 풀을 계산할 수 있습니다.  
    + 에이징에 사용할 거래 날짜를 선택합니다.  
    + 에이징에 대한 "기준" 날짜를 선택합니다. 기본값은 오늘이지만 이 필드를 선택한 날짜로 변경하면 원하는 날짜를 선택할 수 있습니다. 일괄 처리의 경우 오늘 날짜를 사용합니다.  
3. **회사** 범위를 확장합니다. 스냅샷에 포함될 회사를 선택할 수 있습니다. 현재 회사가 기본적으로 선택됩니다.
4. **확인** 을 클릭하여 스냅샷을 처리합니다. 시간이 약간 걸리므로 슬라이더가 사라질 때까지 기다렸다가 메시지 센터에서 메시지를 확인하세요.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>에이징 잔액 목록 및 수금 페이지에서 잔액 보기
1. **신용 및 수금 > 수금 > 에이징 잔액** 으로 이동합니다. 목록 페이지에는 고객의 잔액이 표시됩니다. 에이징 아이콘은 가장 오래된 거래의 에이징 기간을 보여줍니다.  
2. 잔액이 있는 고객을 선택합니다.
3. 에이징 잔액을 보려면 **에이징 팩트** 상자 영역을 확장합니다. 팩트 상자에 대한 에이징 기간 정의는 매개 변수에 지정된 기본 에이징 기간 정의에서 가져옵니다. 수금 메뉴를 사용하여 변경할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
