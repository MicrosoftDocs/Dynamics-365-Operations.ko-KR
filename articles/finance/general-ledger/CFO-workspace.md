---
title: CFO 작업 영역에 재무 차원 추가
description: 이 토픽에서는 원장 및 예산 보고서에 사용할 수 있도록 재무 차원을 CFO 작업 영역에 추가하는 방법에 대해 설명합니다.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3acff8a0cf36ee6958effd9c5384895df20c180499437c43feddce31c884dbbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450304"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>CFO 작업 영역에 재무 차원 추가

[!include [banner](../includes/banner.md)]

이 토픽에서는 원장 및 예산 보고서에 사용할 수 있도록 재무 차원을 최고재무책임자(CFO) 작업 영역에 추가하는 방법에 대해 설명합니다. CFO 작업 영역에는 **개요** 탭과 **재무** 탭이 있습니다. 이 두 탭의 보고서는 LedgerActivityMeasure 및 BudgetActivityMeasure의 두 가지 측정값으로 뒷받침됩니다. 이 두 측정값과 DimensionCombinationEntity 엔터티 간에는 관계가 있습니다. 따라서 차원을 선택할 수 있습니다.

1. 재무의 **엔터티 스토어** 페이지에서 **LedgerActivityMeasure** 및 **BudgetActivityMeasure** 측정값을 업데이트합니다.
2. Microsoft Visual Studio에서 애플리케이션 탐색기를 열고 **LedgerCFO** 를 검색합니다.
3. **리소스** 에서 **LedgerCFOWorkspacePBIX** 를 엽니다.
4. 리소스가 Microsoft Power BI desktop에서 열리면 **데이터 가져오기**, **SQL Server 데이터베이스**, **연결** 을 차례로 선택합니다.
5. 서버 이름을 입력하고 데이터베이스로 **AxDW** 를 입력합니다. **DirectQuery** 를 선택하고 **확인** 을 선택합니다.
6. **LedgerActivityMeasure\_DimensionCombination** 을 검색하여 선택한 다음 **불러오기** 를 선택합니다.

    > [!TIP]
    > **필드** 목록에서 쉽게 식별할 수 있도록 **재무 차원** 테이블의 이름을 바꿉니다.

7. **관계 관리** 를 선택한 다음 **새로 만들기** 를 선택합니다.
8. 첫 번째 필드에서 **총계정원장 활동** 을 선택한 다음 **LedgerDimension** 를 선택합니다.
9. 두 번째 필드에서 **LedgerActivityMeasure\_DimensionCombination**(또는 테이블 이름을 변경한 경우 **재무 차원**)을 선택합니다. **DimensionCombinationRECID** 헤더를 선택합니다.
10. **관계 수** 필드에서 **다대일** 을 선택합니다.
11. **교차 필터 방향** 값을 **단일** 로 변경합니다.
12. **이 관계를 활성화** 및 **참조 무결성 가정** 을 모두 선택하고 **확인** 을 선택한 다음 **닫기** 를 선택합니다.

    [![관계를 만드십시오.](./media/Create-relationship.png)](./media/Create-relationship.png)

13. **필드** 목록에 테이블과 사용 가능한 재무 차원이 표시되어야 합니다. 보고서 수준 필터로 원하는 재무 차원을 끌어다 놓습니다.
14. 변경 사항을 저장합니다.
15. 애플리케이션 개체 트리(AOT)에서 프로젝트를 마우스 오른쪽 버튼으로 클릭한 다음 **동기화** 를 선택합니다.
16. 프로젝트를 빌드한 다음 애플리케이션을 열어 결과를 봅니다.

    [![완성된 작업 영역.](./media/workspace.png)](./media/workspace.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]