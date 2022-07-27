---
title: 예산 계획
description: 이 실습의 목표는 예산 계획 영역에서 Microsoft Dynamics 365 Finance 기능 업데이트에 대한 안내 보기를 제공하는 것입니다. 이 실습의 목적은 예산 계획 모듈의 빠른 구성 예를 보여주고 이 구성을 사용하여 예산 계획을 수행하는 방법을 보여주는 것입니다.
author: panolte
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0420887c35bbb07aaf8cce05a68173ab6c534f92
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451027"
---
# <a name="budget-planning"></a>예산 계획

[!include [banner](../includes/banner.md)]

이 실습의 목표는 예산 계획 영역에서 Microsoft Dynamics 365 Finance 기능 업데이트에 대한 안내 보기를 제공하는 것입니다. 이 실습의 목적은 예산 계획 모듈의 빠른 구성 예를 보여주고 이 구성을 사용하여 예산 계획을 수행하는 방법을 보여주는 것입니다.  이 실습에서는 특히 다음과 같은 비즈니스 프로세스 또는 작업에 중점을 둘 것입니다.
- 예산 계획 및 사용자 보안 구성을 위한 조직 계층 생성
- 예산 계획 시나리오, 예산 계획 열, 레이아웃 및 Excel 템플릿 정의
- 예산 계획 프로세스 생성 및 활성화
- 총계정원장에서 실제를 가져와서 예산 계획 문서 생성
- 할당을 사용하여 예산 계획 문서 데이터 조정
- Excel에서 예산 계획 문서 데이터 편집 

## <a name="prerequisites"></a>전제 조건 

이 자습서에서는 Contoso 데모 데이터를 사용하여 Microsoft Dynamics 365 Finance 환경에 액세스하고 인스턴스에서 관리자로 프로비저닝해야 합니다. 이 실습에서는 비공개 브라우저 모드를 사용하지 마십시오. 필요한 경우 브라우저의 다른 계정에서 로그아웃하고 관리자 자격 증명으로 로그인합니다. 로그인할 때 **반드시** "로그인 유지" 확인란을 선택해야 합니다. 이렇게 하면 현재 Excel 앱에 필요한 영구 쿠키가 생성됩니다. IE 이외의 브라우저를 사용하여 애플리케이션에 로그인하면 Excel 앱 내에서 로그인하라는 메시지가 표시됩니다. Excel 앱에서 "로그인"을 클릭하면 IE 팝업 창이 열리고 로그인할 때 **반드시** "로그인 유지" 확인란을 선택합니다. Excel 앱에서 "로그인"을 클릭해도 아무 작업도 수행되지 않는 경우 IE 쿠키 캐시를 지워야 합니다.

## <a name="scenario-overview"></a>**시나리오 개요**
Julia는 독일의 Contoso Entertainment Systems(DEMF)에서 관리자로 일하고 있습니다. FY2016이 다가옴에 따라 그녀는 다음 해의 회사 예산 설정 작업을 해야 합니다. 예산 준비는 다음과 같습니다.

1.  Julia는 예산을 작성하기 위한 출발점으로 전년도 실제 금액을 사용합니다.
2.  전년도 실제 금액을 기반으로 다가오는 연도의 12개월 동안의 추정치를 생성합니다
3.  Julia는 CFO와 함께 예산을 검토합니다. 완료되면 그녀는 예산 계획에 필요한 조정을 하고 예산 준비를 마무리합니다.

시나리오에 대한 예산 계획 구성 스키마는 다음과 같습니다.

![예산 계획 구성 스키마.](./media/screenshot1-300x152.png)

Julia는 다음 Excel 템플릿을 사용하여 예산을 준비합니다.

[![Excel 템플릿.](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>연습 1: 구성

### <a name="task-1-create-organizational-hierarchy"></a>**작업 1: 조직 계층 구조 만들기**
모든 예산 책정 프로세스가 재무 부서에서 이루어지므로 Julia는 재무 부서로만 구성된 매우 간단한 조직 계층 구조를 만들어야 합니다. 

1.1. 조직 계층 구조(조직 관리&gt; 조직&gt; 조직 계층 구조)으로 이동하고 새로 만들기 버튼을 클릭합니다.

![조직 계층 구조.](./media/screenshot3.png) 

1.2. 이름 상자에 조직 계층 구조의 이름을 입력하고 목적 할당을 클릭합니다.

1.3. 예산 계획 목적을 선택하고 추가를 클릭한 다음 새로 생성된 조직 계층 구조를 할당합니다. 

[![목적을 할당합니다.](./media/screenshot5.png)](./media/screenshot5.png)

1.4. 보안 조직 목적을 위해 위의 단계를 반복합니다. 완료되면 양식을 닫습니다.

1.5. 조직 계층 구조 양식에서 보기를 클릭합니다. 계층 디자이너에서 편집을 클릭하고 삽입을 클릭하여 계층을 생성합니다.

[![삽입.](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. 예산 계층에 대해 재무 부서를 선택합니다. 

[![재무.](./media/screenshot8.png)](./media/screenshot8.png)

1.7. 완료되면 게시 및 닫기를 클릭합니다. 계층 게시의 적용 날짜로 2015년 1월 1일을 선택합니다.

[![적용 날짜.](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>작업 2: 사용자 보안 구성
예산 계획은 특수 보안 정책을 사용하여 예산 계획 데이터에 대한 액세스를 구성합니다. Julia는 자신을 위해 재무 예산 계획에 대한 액세스 권한을 부여해야 합니다. 

2.1. DEMF 법인 컨텍스트로 전환합니다. 


2.2. 예산 편성 &gt; 설정 &gt; 예산 계획 &gt; 예산 계획 구성으로 이동합니다. 매개 변수 탭에서 보안 모델 값을 보안 조직 기반으로 설정하십시오. 

[![매개 변수.](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. 시스템 관리 &gt; 사용자 &gt; 사용자로 이동합니다. 사용자 관리자(Julia Funderburk)에게 예산 관리자 역할을 부여합니다. 

[![예산 관리자.](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. 사용자 역할을 선택하고 조직 할당을 클릭합니다. 

[![조직 할당.](./media/screenshot13.png)](./media/screenshot13.png)

2.5. "특정 조직에 대한 액세스 권한 부여"를 선택하십시오. 첫 번째 단계에서 만든 조직 계층 구조를 선택합니다. 재무 노드를 선택하고 하위 권한 부여 버튼을 클릭합니다. 

***중요!** _ _조직 보안이 법인별로 적용되므로 이 작업을 수행할 때 DEMF 법인 컨텍스트에 있는지 확인하십시오.* 

### <a name="task-3-create-scenarios"></a>작업 3: 시나리오 만들기
3.1. 예산 편성&gt;설정 &gt; 예산 계획 &gt; 예산 계획 구성으로 이동합니다. 시나리오 페이지에서 이 실습에서 추가로 사용할 시나리오인 전년도 실제 금액 및 예산을 확인합니다. 

*참고: 원하는 경우 이 연습에 대한 새 시나리오를 만들고 대신 사용할 수 있습니다.* 

[![새로운 시나리오.](./media/screenshot15.png)](./media/screenshot15.png) 

*참고: Julia는 예산 준비를 위해 공식 승인 프로세스를 사용하지 않으므로 이 실습의 워크플로, 단계 및 워크플로 단계 설정을 건너뛰고 자동 승인 워크플로에 기존 설정을 사용합니다. 이 워크플로 구성에 대한 부록을 참조하십시오.*

### <a name="task-4-create-budget-plan-columns"></a>작업 4: 예산 계획 열 만들기
예산 계획 열은 예산 계획 문서 레이아웃에서 사용할 수 있는 화폐 또는 수량 기반 열입니다. 이 예에서는 이전 연도 실제 금액에 대한 열과 예산이 책정된 연도의 각 월을 나타내는 12개의 열을 만들어야 합니다. 추가 버튼을 클릭하고 값을 채우거나 데이터 엔터티를 사용하여 열을 만들 수 있습니다. 이 실습에서는 데이터 엔터티를 사용하여 값을 채웁니다. 

4.1. 예산 편성&gt;설정 &gt; 예산 계획 &gt; 예산 계획 구성에서 열 페이지를 엽니다. 양식의 오른쪽 상단 모서리에 있는 Office 단추를 클릭하고 열(필터링되지 않음)을 선택합니다. 

[![필터링되지 않은 열입니다.](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. 시스템은 값을 채우는 데 사용할 Excel 통합 문서를 엽니다. 메시지가 표시되면 편집 활성화 및 이 앱 신뢰를 클릭합니다. 

4.3. 값을 채우려면 더 많은 열이 필요합니다. 오른쪽 창에서 설계를 클릭하여 그리드에 열을 추가합니다. 

[![설계.](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. PlanColumns 옆에 있는 연필 버튼을 클릭하여 그리드에 추가할 수 있는 열을 확인합니다. 

[![편집.](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. 사용 가능한 각 필드를 두 번 클릭하여 선택한 필드에 추가하고 업데이트를 클릭합니다. 

4.6. Excel 테이블에서 생성해야 하는 모든 열을 추가합니다. Excel의 자동 채우기 기능을 사용하여 라인을 빠르게 추가합니다. 행이 테이블의 일부로 추가되었는지 확인합니다(수직 스크롤을 사용할 때 그리드 상단에서 열 헤더를 볼 수 있어야 함). 

4.7. 애플리케이션으로 돌아가서 페이지를 새로 고칩니다. 게시된 값이 나타납니다. 

[![새로 고침.](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>작업 5: 예산 계획 문서 레이아웃 및 템플릿 만들기
레이아웃은 사용자가 예산 계획 문서를 열 때 예산 계획 문서 라인 그리드가 어떻게 보일지 정의합니다. 예산 계획 문서의 레이아웃을 전환하여 동일한 데이터를 다른 각도에서 볼 수도 있습니다. 이제 예산 계획 문서와 함께 사용하도록 정의된 열이 있으므로 Julia는 예산 데이터를 생성하는 데 사용하는 Excel 테이블과 유사한 예산 계획 문서 레이아웃을 생성해야 합니다(이 랩의 시나리오 개요 섹션 참조) 

5.1. 예산 편성&gt;설정 &gt; 예산 계획 &gt; 예산 계획 구성에서 레이아웃 페이지를 엽니다. 월별 예산 항목을 위한 새 레이아웃 생성:

-   레이아웃에 주 계정 및 사업부를 포함하도록 MA+BU 차원 집합을 선택합니다.
-   요소 섹션의 이전 단계에서 생성된 모든 예산 계획 열을 나열합니다. 이전 연도 실제 금액을 제외한 모든 항목을 편집 가능하게 만듭니다.
-   설명 단추를 눌러 그리드에 설명을 표시할 재무 차원을 선택합니다.

[![설명.](./media/screenshot24.png)](./media/screenshot24.png) 

예산 계획 레이아웃 정의에 따라 예산 데이터를 편집하는 대체 방법으로 사용할 Excel 템플릿을 만들 수 있습니다. Excel 템플릿은 예산 계획 레이아웃 정의와 일치해야 하기 때문에 Excel 템플릿을 생성한 후에는 예산 계획 레이아웃을 편집할 수 없으므로 이 작업은 모든 레이아웃 구성 요소를 정의한 후에 수행해야 합니다. 

5.2. 5.1 단계에서 만든 레이아웃의 경우, 템플릿 &gt; 생성 버튼을 클릭합니다. 경고 메시지를 확인합니다. 템플릿을 보려면 템플릿 &gt; 보기를 클릭합니다. 

*참고: "다른 이름으로 저장"을 선택하고 템플릿을 편집하려면 템플릿을 저장할 위치를 선택해야 합니다. 사용자가 저장하지 않고 대화 상자에서 "열기"를 선택하면 파일을 닫을 때 파일에 대한 변경 사항이 유지되지 않습니다.* 
[![템플릿 보기.](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt;선택적 단계&gt; Excel 템플릿을 수정하여 사용자 친화적으로 보이게 합니다. 총 수식, 헤더 필드, 서식 등을 추가합니다. 변경 사항을 저장하고 레이아웃 &gt; 업로드를 클릭하여 파일을 예산 계획 레이아웃에 업로드합니다. 


### <a name="task-6-create-a-budget-planning-process"></a>작업 6: 예산 계획 프로세스 만들기
Julia는 예산 계획 입력을 시작하기 위해 위의 모든 설정을 결합한 새로운 예산 계획 프로세스를 만들고 활성화해야 합니다. 예산 계획 프로세스는 예산 계획 생성에 사용할 예산 편성 조직, 워크플로, 레이아웃 및 템플릿을 정의합니다. 

6.1. 예산 편성 &gt; 설정 &gt; 예산 계획 &gt; 예산 계획 프로세스로 이동하여 새 기록을 만듭니다.

-   예산 계획 프로세스 – DEMF 예산 편성 FY2016
-   예산 주기 – FY2016
-   원장 – DEMF
-   기본 계정 구조 – 제조 손익
-   조직 계층 구조 – 실습 시작 시 만든 계층 선택
-   예산 계획 워크플로 – 자동 할당 – 재무 부서의 워크플로 승인
-   예산 계획 단계 규칙 및 템플릿에서 각 워크플로에 대해 예산 계획 단계에서 라인 추가 및 수정이 허용되는지 여부와 기본적으로 사용되어야 하는 레이아웃 선택

*참고: 대체 레이아웃 버튼을 클릭하여 추가 문서 레이아웃을 생성하고 예산 계획 워크플로 단계에서 사용할 수 있도록 할당할 수 있습니다.* 

[![대체 레이아웃.](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. 작업 &gt; 활성화를 선택하여 이 예산 계획 워크플로를 활성화합니다. 

[![활성화.](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>연습 2: 공정 시뮬레이션

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>작업 7: 총계정원장에서 예산 계획에 대한 초기 데이터 생성
7.1. 예산 편성 &gt; 정기 &gt; 총계정원장에서 예산 계획 생성으로 이동합니다. 정기 프로세스 매개 변수를 입력하고 생성을 클릭합니다. 

7.2. 예산 편성 &gt; 예산 계획으로 이동하여 생성 프로세스에서 만든 예산 계획을 찾습니다. 

[![예산 계획.](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. 문서 번호 하이퍼링크를 클릭하여 문서 세부 정보를 엽니다. 예산 계획은 이 실습에서 생성된 레이아웃에 정의된 대로 표시됩니다. 

[![예산 계획 표시.](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>작업 8: 전년도 실제 금액을 기반으로 올해 예산 작성
예산 계획에서 할당 방법을 사용하여 한 시나리오에서 다른 시나리오로 예산 계획에 대한 정보를 쉽게 복사/기간에 걸쳐 분산/차원에 할당할 수 있습니다. 할당을 사용하여 전년도 실제에서 현재 연도 예산을 생성합니다. 

8.1. 예산 계획 문서 그리드에서 모든 라인을 선택하고 예산 할당을 클릭합니다. 

[![모든 라인.](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. 할당 방법, 기간 키, 소스 및 대상 시나리오를 선택하고 할당을 클릭합니다. 

[![할당.](./media/screenshot33.png)](./media/screenshot33.png)

전년도 실제 금액은 현재 연도 예산에 복사되고 영업 곡선 기간 키를 사용하여 기간에 할당합니다. 

[![영업 곡선.](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>작업 9: Excel을 사용하여 예산 계획 문서 조정 및 문서 마무리
9.1. 워크시트 버튼을 클릭하여 Excel에서 문서 내용을 엽니다.

9.2. Excel 통합 문서가 열리면 예산 계획 문서의 숫자를 조정하고 게시 버튼을 클릭합니다.

9.3. 예산 계획 문서로 돌아갑니다. 워크플로 &gt; 제출을 클릭하여 문서를 자동 승인합니다.

[![자동 승인.](./media/screenshot37.png)](./media/screenshot37.png) 

워크플로가 완료되면 예산 계획 문서 단계가 승인됨으로 변경됩니다. [![승인됨.](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>부록

### <a name="auto-approve-workflow-configuration"></a>워크플로 구성 자동 승인

A. 예산 편성 &gt; 설정 &gt; 예산 계획 &gt; 예산 편성 워크플로. 예산 계획 워크플로 템플릿을 사용하여 새 워크플로 만들기:

[![새 워크플로 만들기.](./media/screenshot39.png)](./media/screenshot39.png)

이 워크플로에는 단계 전환 예산 계획이라는 하나의 작업만 포함됩니다. 

[![단계 전환 예산 계획.](./media/screenshot40.png)](./media/screenshot40.png) 

워크플로를 저장하고 활성화합니다. 

B. 예산 편성 &gt; 설정 &gt; 예산 계획 &gt; 예산 계획 구성으로 이동합니다. 단계 탭에서 초기 및 제출됨의 두 단계를 만듭니다. 

[![초기 및 제출됨.](./media/screenshot41.png)](./media/screenshot41.png)

C. 예산 편성 &gt; 설정 &gt; 예산 계획 &gt; 예산 계획 구성으로 이동합니다. 워크플로 단계 탭에서 A단계에서 만든 워크플로 자동 승인을 초기 및 제출됨 단계와 연결합니다.

[![예산 편성 및 예산 계획.](./media/screenshot42.png)](./media/screenshot42.png)  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
