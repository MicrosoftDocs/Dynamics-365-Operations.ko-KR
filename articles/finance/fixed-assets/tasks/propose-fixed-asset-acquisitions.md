---
title: 고정 자산 취득 제안
description: 이 항목에서는 고정 자산 저널의 취득 제안을 사용하여 고정 자산을 취득하는 방법을 설명합니다.
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70347009ede494760cd7f51b46db04b434b9fbcc
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451270"
---
# <a name="propose-fixed-asset-acquisitions"></a>고정 자산 취득 제안

[!include [banner](../../includes/banner.md)]

이 항목에서는 고정 자산 저널의 취득 제안을 사용하여 고정 자산을 취득하는 방법을 설명합니다. 이 절차에서는 USMF 법인에 대한 회계사 역할과 데모 데이터를 사용합니다. 고정 자산 제안 저널을 통해 고정 자산을 취득하려면 먼저 고정 자산 레코드를 생성한 다음 자산 장부에 취득 가격을 정의해야 합니다.

## <a name="create-an-asset-acquisition-proposal"></a>자산 취득 제안 생성

다음 단계를 완료하여 자산 취득 제안을 생성합니다. 

1. 탐색 창에서 **모듈 > 고정 자산 > 분개장 기입 > 고정 자산 분개장** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드에 값을 입력하거나 선택합니다.
4. 작업 창에서 **라인** 을 선택합니다.
5. **제안** 을 선택합니다.
6. **취득 제안** 을 선택합니다.
7. **필터** 를 선택합니다. 이전 값을 지우려면 **재설정** 을 선택합니다.
8. **고정 자산 수** 행을 선택합니다.
9. **기준** 필드에서 값을 입력하거나 선택합니다. 이 제안으로 취득할 고정 자산에 대한 나머지 기준을 설정합니다.  
10. **확인** 을 두 번 선택하여 창을 종료합니다.
- 트랜잭션 라인이 생성되었는지 확인합니다.  
- 장부에 취득 날짜와 취득 가격이 정해진 고정 자산만 취득 제안에 포함됩니다.  
11. 페이지에서 **장부** 탭을 선택합니다.
12. **게시** 를 선택합니다.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>취득 제안에 기본 재무 차원 포함

취득 트랜잭션은 Excel 추가 기능을 사용하여 **고정 자산 > 저널 항목 > 고정 자산 저널** 로 이동하여 생성할 수 있습니다. 새 저널을 만들고 페이지의 **라인** 섹션으로 이동하여 Excel 아이콘을 선택한 다음 고정 자산 저널 라인을 선택합니다. 시스템은 저널 라인을 나타내는 Excel 템플릿을 만들고 엽니다. 추가할 저널 라인에 대한 데이터를 템플릿에 추가한 다음 해당 정보를 시스템에 다시 게시할 수 있습니다. 

선택한 자산 장부 및 Excel 템플릿에 입력된 해당 고정 자산에 대해 기본 치수가 설정된 경우 저널이 Excel에서 시스템으로 게시될 때 자산 장부 마스터 데이터에서 기본 재무 차원이 호출됩니다. Excel 추가 기능에서 고정 자산 저널을 게시하는 동안 자산 장부에 재무 차원을 자동으로 포함하려면 미리 기본 차원을 설정해야 합니다.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
