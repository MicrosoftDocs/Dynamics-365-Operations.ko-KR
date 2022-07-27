---
title: Excel용 예산 계획 템플릿
description: 이 토픽에서는 예산 계획에 사용할 수 있는 Microsoft Excel 템플릿을 만드는 방법에 대해 설명합니다.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: roschlom
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8297548bee83d1e982f50c4e5adae748f9f40137362f4ad47ad837ea2af96c29
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450814"
---
# <a name="budget-planning-templates-for-excel"></a>Excel용 예산 계획 템플릿

[!include [banner](../includes/banner.md)]

이 토픽에서는 예산 계획에 사용할 수 있는 Microsoft Excel 템플릿을 만드는 방법에 대해 설명합니다.

이 토픽에서는 표준 데모 데이터 집합 및 관리 사용자 로그인을 사용하여 예산 계획과 함께 사용할 Excel 템플릿을 만드는 방법을 보여줍니다. 예산 계획에 대한 자세한 내용은 [예산 계획 개요](budget-planning-overview-configuration.md)를 참조하십시오. 또한 [예산 계획](budget-plan.md) 자습서를 따라 기본 모듈 구성 및 사용 원칙을 배울 수 있습니다.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>예산 계획 문서 레이아웃을 사용하여 워크시트 생성

예산 계획 문서는 하나 이상의 레이아웃을 사용하여 보고 편집할 수 있습니다. 각 레이아웃에는 Excel 워크시트에서 예산 계획 데이터를 보고 편집하기 위한 관련 예산 계획 문서 템플릿이 있을 수 있습니다. 이 토픽에서는 기존 레이아웃 구성을 사용하여 예산 계획 문서 템플릿을 생성합니다. 

1. **예산 계획 목록**(**예산 편성** &gt; **예산 계획**)을 엽니다. 
2. **새로 만들기** 를 클릭하여 새 예산 계획 문서를 만듭니다. 

   [![예산 계획 목록.](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. 라인 **추가** 옵션을 사용하여 라인을 추가합니다. 예산 계획 문서 레이아웃 구성을 보려면 **레이아웃** 을 클릭하십시오. 

   [![예산 계획 추가.](./media/bpt2-1024x274.png)](./media/bpt2.png) 

레이아웃 구성을 검토하고 필요에 따라 조정할 수 있습니다. 
1. **템플릿** &gt; **생성** 으로 이동하여 이 레이아웃에 대한 Excel 파일을 만듭니다. 
2. 템플릿이 생성된 후 **템플릿** &gt; **보기** 로 이동하여 예산 계획 문서 템플릿을 열고 검토합니다. Excel 파일을 로컬 드라이브에 저장할 수 있습니다. 

[![다른 이름으로 저장.](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> Excel 템플릿이 연결된 후에는 예산 계획 문서 레이아웃을 편집할 수 없습니다. 레이아웃을 수정하려면 연결된 Excel 템플릿 파일을 삭제하고 다시 생성하십시오. 이는 레이아웃과 워크시트의 필드를 동기화된 상태로 유지하는 데 필요합니다. 

Excel 템플릿에는 **워크시트에서 사용 가능** 열이 True로 설정된 예산 계획 문서 레이아웃의 모든 요소가 포함됩니다. Excel 템플릿에는 겹치는 요소가 허용되지 않습니다. 예를 들어 레이아웃에 요청 Q1, 요청 Q2, 요청 Q3 및 요청 Q4 열이 포함되어 있고 4개 분기별 열의 합계를 나타내는 총 요청 열이 있는 경우 분기 열 또는 총계 열만 Excel 템플리트에서 사용할 수 있습니다. Excel 파일은 테이블의 데이터가 오래되고 정확하지 않을 수 있으므로 업데이트 중에 겹치는 열을 업데이트할 수 없습니다.

> [!NOTE] 
> Excel을 사용하여 예산 계획 데이터를 보고 편집할 때 발생할 수 있는 문제를 방지하려면 동일한 사용자가 Microsoft Dynamics 365 Finance 및 Microsoft Dynamics Office 추가 기능 데이터 커넥터에 모두 로그인해야 합니다.

## <a name="add-a-header-to-budget-plan-document-template"></a>예산 계획 문서 템플릿에 헤더 추가
헤더 정보를 추가하려면 Excel 파일에서 맨 위 행을 선택하고 빈 행을 삽입합니다. **데이터 커넥터** 에서 **디자인** 을 클릭하여 Excel 파일에 헤더 필드를 추가합니다.

**디자인** 탭에서 **추가** 필드를 클릭한 다음, 엔터티 데이터 원본으로 **BudgetPlanHeader** 를 선택합니다.

커서를 Excel 파일에서 원하는 위치로 이동합니다. **레이블 추가** 를 클릭하여 선택한 위치에 필드 레이블을 추가합니다. **값 추가** 를 선택하여 선택한 장소에 값 필드를 추가합니다. **완료** 를 클릭하여 디자이너를 닫습니다.

## <a name="select-add-valuemediabpt7png"></a>[![값 추가 선택.](./media/bpt7.png)](./media/bpt7.png)

## <a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>예산 계획 문서 템플릿 테이블에 계산된 열 추가

다음으로 생성된 예산 계획 문서 템플릿에 계산된 열이 추가됩니다. 요청 Q1을 요약하는 **총 요청** 열: 요청 Q4 열과 **조정** 열은 사전 정의된 요소로 **총 요청** 열을 다시 계산합니다.

**데이터 커넥터** 에서 **디자인** 을 클릭하여 테이블에 열을 추가합니다. **BudgetPlanWorksheet** 데이터 원본 옆에 있는 **편집** 을 클릭하여 열 추가를 시작합니다.

[![열 추가를 시작합니다.](./media/bpt8-1024x301.png)](./media/bpt8.png) 

선택한 필드 그룹에는 템플릿에서 사용할 수 있는 열이 표시됩니다. **수식** 을 클릭하여 새 열을 추가합니다. 새 열의 이름을 지정한 다음 수식을 **수식** 필드에 붙여넣습니다. **업데이트** 를 클릭하여 열을 삽입합니다.

[![열을 추가하고 삽입합니다.](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> 수식을 정의하려면 스프레드시트에서 수식을 만든 다음 **디자인** 창에 복사합니다. 금융 및 운영 바운드 테이블의 이름은 일반적으로 "AXTable1"입니다. 예를 들어 스프레드시트의 요청 Q1: 요청 Q4 열을 요약하려면 수식 = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\]입니다.

이 단계를 반복하여 **조정** 열을 삽입합니다. 수식 = AxTable1\[Total request\]\*$I$1을 이 열에 대해 사용합니다. 이것은 I1 셀의 값을 취하고 **총 요청** 열의 값을 곱하여 조정 금액을 계산합니다.

Excel 파일을 저장하고 닫습니다. **레이아웃** 에서 **템플릿 &gt; 업로드** 를 클릭하여 예산 계획에 사용할 저장된 Excel 템플릿을 업로드합니다. 

[![엑셀 템플릿을 업로드합니다.](./media/bpt10-1024x352.png)](./media/bpt10.png) 

**레이아웃** 슬라이더를 닫습니다. **예산 계획** 문서에서 **워크시트** 를 클릭하면 Excel에서 문서를 보고 편집할 수 있습니다. 조정된 Excel 템플릿은 이 예산 계획 워크시트를 만드는 데 사용되었으며 계산된 열은 이전 단계에서 정의된 수식을 사용하여 업데이트됩니다. 

[![Excel에서 문서를 보고 편집합니다.](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>예산 계획 템플릿을 만드는 팁 및 요령
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>예산 계획 템플릿에 추가 데이터 원본을 추가하고 사용할 수 있습니까?

예, **디자인** 메뉴를 사용하여 Excel 템플릿의 동일한 시트 또는 다른 시트에 추가 엔터티를 추가할 수 있습니다. 예를 들어 **BudgetPlanProposedProject** 데이터 원본을 추가하여 Excel에서 예산 계획 데이터로 작업할 때 제안된 프로젝트 목록을 만들고 유지 관리할 수 있습니다. 대용량 데이터 원본을 포함하면 Excel 통합 문서의 성능에 영향을 미칠 수 있습니다. 

**데이터 커넥터** 의 **필터** 옵션을 사용하여 추가 데이터 원본에 원하는 필터를 추가할 수 있습니다.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>다른 사용자의 데이터 커넥터에서 디자인 옵션을 숨길 수 있습니까?

예, **데이터 커넥터** 옵션을 열어 다른 사용자에게 **디자인** 옵션을 숨길 수 있습니다.

[![데이터 커넥터 옵션을 엽니다.](./media/bpt13-1024x565.png)](./media/bpt13.png)

**데이터 커넥터 옵션** 을 확장하고 **디자인 사용** 확인란의 선택을 취소합니다. **데이터 커넥터** 에서 **디자인** 옵션이 숨겨집니다.

[![데이터 커넥터에서 디자인 옵션을 숨깁니다.](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>사용자가 데이터로 작업하는 동안 실수로 데이터 커넥터를 닫는 것을 방지할 수 있습니까?

사용자가 템플릿을 닫지 못하도록 템플릿을 잠그는 것이 좋습니다. 잠금을 켜려면 **데이터 커넥터** 를 클릭하세요. 오른쪽 상단 모서리에 화살표가 나타납니다. 

[![잠금을 켭니다.](./media/bpt15-1024x285.png)](./media/bpt15.png) 

추가 메뉴를 보려면 화살표를 클릭하세요. **잠금** 을 선택합니다.

### <a name="select-lockmediabpt16png"></a>[![잠금을 선택합니다.](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>예산 계획 템플릿에서 셀 서식, 색상, 조건부 서식 및 차트와 같은 다른 Excel 기능을 사용할 수 있습니까?

예, 대부분의 표준 Excel 기능은 예산 계획 템플릿에서 작동합니다. 사용자가 읽기 전용 열과 편집 가능한 열을 구분하려면 색상 코딩을 사용하는 것이 좋습니다. 조건부 서식을 사용하여 예산의 문제 영역을 강조 표시할 수 있습니다. 열 합계는 표 위에 있는 표준 Excel 수식을 사용하여 쉽게 표시할 수 있습니다.

예산 데이터의 추가 그룹화 및 시각화를 위해 피벗 테이블과 차트를 만들고 사용할 수도 있습니다. **데이터** 탭의 **연결** 그룹에서 **모두 새로 고침**, **연결 속성** 을 차례로 클릭합니다. **사용** 탭을 클릭합니다. **새로 고침** 에서 **파일을 열 때 데이터 새로 고침** 확인란을 선택합니다. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]