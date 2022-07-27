---
title: 예산 계획 근거 문서
description: 근거 문서는 특정 예산이 필요한 이유를 설명하기 위해 예산을 요청하는 사람들에게 설명을 제공합니다.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5eb74b5d2b71372f99dd927ff6e2bee96e199a6f75b3ae920607e5ec37a4241a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450559"
---
# <a name="budget-planning-justification-documents"></a>예산 계획 근거 문서

[!include [banner](../includes/banner.md)]

근거 문서는 특정 예산이 필요한 이유를 설명하기 위해 예산을 요청하는 사람들에게 설명을 제공합니다. 

예산 계획 템플릿은 예산 관리자가 Microsoft Word에서 만들고 현재 예산 계획 프로세스에 할당합니다. 그런 다음 예산 담당자는 템플릿을 열고 예산 요청에 따라 Word에서 데이터를 자동으로 채울 수 있습니다. 그런 다음 개인화된 근거 문서를 저장하고 예산 계획에 첨부하기 전에 텍스트나 데이터를 추가할 수 있습니다.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Microsoft Word용 Microsoft Dynamics Office 추가 기능 설정

1.  새 Microsoft Word 문서를 엽니다.
2.  리본에서 **삽입** 을 클릭하고 **저장** 을 클릭합니다.
3.  Microsoft Dynamics Office 추가 기능을 검색하고 **추가** 를 클릭합니다.
4.  Word의 오른쪽 창에서 **서버 정보 추가** 를 클릭합니다.
5.  서버 URL을 입력하거나 붙여넣고 **확인** 을 클릭합니다.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Microsoft Word에서 근거 템플릿 정의

1.  로그인한 후 Microsoft Dynamics Office 추가 기능에서 **디자인** 을 클릭합니다.
2.  헤더 정보를 보려면 **필드 추가** 버튼을 사용하세요.
3.  BudgetPlanJustification의 엔터티 데이터 원본을 선택하고 **다음** 을 클릭합니다. **참고:** 이 엔터티는 모든 근거 문서에 필요합니다. 다른 엔터티를 사용할 수 있지만 이 엔터티가 포함되어 있지 않으면 Microsoft Dynamics 365 Finance로 다시 업로드할 수 없습니다.
4.  Word 문서에 BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter 및 DocumentNumber 레이블과 값을 추가합니다. **참고:** 필요한 경우 표준 레이블 대신 사용자 지정 레이블을 사용할 수 있습니다.
5.  헤더 섹션을 완료하려면 **완료** 를 클릭하세요.
6.  예산 계획 금액의 라인 수준 세부 정보를 보려면 **테이블 추가** 를 클릭합니다.
7.  다시 BudgetPlanJustification의 엔터티 데이터 원본을 선택하고 **다음** 을 클릭합니다.
8.  EffectiveDate, ScenarioName, AccountDisplayValue 및 AccountingCurrencyExpenseAmount에 대한 필드를 추가합니다. **참고:** 개별 예산 계획 라인에 추가할 수 있는 설명이 있는 경우 여기 테이블에 추가할 수 있습니다.
9.  최종 사용자에게 제공할 추가 지침을 추가하고 문서에 필요한 서식 또는 스타일 지정을 수행합니다.
10. 계속하기 전에 문서를 로컬 컴퓨터에 저장하고 파일을 닫습니다.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>근거 템플릿을 사용하도록 예산 계획 프로세스 설정

1.  **예산 책정** &gt; **설정** &gt; **예산 계획** &gt; **근거 문서 템플릿** 으로 이동합니다.
2.  **새로 만들기** 를 클릭하고 새로 만든 Microsoft Word 문서를 찾습니다.
3.  템플릿 표시 이름과 설명을 입력합니다. **확인** 을 클릭합니다.
4.  **예산 책정** &gt; **설정** &gt; **예산** **계획** &gt; **예산 계획 프로세스** 로 이동합니다.
5.  근거 템플릿을 사용해야 하는 프로세스를 선택하고 **편집** 을 클릭합니다.
6.  **근거 문서 템플릿** 필드에서 적절한 템플릿을 선택하고 저장합니다.

##### <a name="edit-and-save-personalized-justification-documents"></a>개인 설정된 근거 문서 편집 및 저장

1.  새 예산 계획을 만들거나 기존 예산 계획을 엽니다.
2.  **근거** 드롭다운 메뉴에서 **새 근거 만들기** 를 선택합니다.
3.  세부 정보를 입력한 후 **근거** 드롭다운 메뉴에서 개인 설정된 문서 업로드를 선택합니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]