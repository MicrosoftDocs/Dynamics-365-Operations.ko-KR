---
title: 비즈니스 문서 템플릿에 새 필드 추가 Microsoft Excel
description: 이번에는 비즈니스 문서 관리 기능을 사용하여 Microsoft Excel 비즈니스 문서 템플릿에 새 필드를 추가하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 57eebdc38fb3f74690b92c03fa60e10c7610db1fe413320a6d167f05b0658bf1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460756"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>비즈니스 문서 템플릿에 새 필드 추가 Microsoft Excel

[!include[banner](../includes/banner.md)]

Microsoft Excel 형식의 비즈니스 문서를 생성하는 데 사용되는 템플릿에 새 필드를 추가할 수 있습니다. 이러한 필드는 애플리케이션의 필수 정보로 생성된 문서를 채우는 데 사용되는 자리 표시자로 추가할 수 있습니다. 추가하는 모든 필드에 대해 데이터 소스에 대한 바인딩을 지정하여 템플릿을 사용하여 비즈니스 문서를 생성할 때 필드에 입력할 애플리케이션 데이터를 지정할 수도 있습니다.

이 기능에 대해 자세히 알아보려면 이 항목의 예시를 완료하십시오. 이 예는 생성된 자유 텍스트 송장 양식의 필드를 채우도록 템플릿을 업데이트하는 방법을 보여줍니다.

## <a name="configure-business-document-management-to-edit-templates"></a>템플릿을 편집하도록 비즈니스 문서 관리 구성

비즈니스 문서 관리(BDM)는 [전자 보고(ER) 개요](general-electronic-reporting.md) 프레임워크를 기반으로 하기 때문에 BDM 작업을 시작하기 전에 필요한 ER 및 BDM 매개 변수를 구성해야 합니다.

1.  시스템 관리자로 Microsoft Dynamics 365 Finance 인스턴스에 로그인합니다.
2.  [비즈니스 문서 관리 개](er-business-document-management.md)요 주제에 있는 예시의 다음 단계를 완료하십시오.

    1.  ER 매개 변수를 구성합니다.
    2.  BDM을 켭니다.

이제 BDM을 사용하여 비즈니스 문서 템플릿을 편집할 수 있습니다.

## <a name="import-er-solutions-that-contain-a-template"></a>템플릿이 포함된 ER 솔루션 가져오기

이 절차의 예시에서는 공식적으로 게시된 ER 솔루션을 사용합니다. 이 솔루션의 ER 구성을 현재 Finance 인스턴스로 가져와야 합니다.

이 솔루션의 **자유 텍스트 송장(Excel)** ER 형식 구성에는 BDM을 사용하여 편집할 수 있는 Excel 형식의 비즈니스 문서 템플릿이 포함되어 있습니다. Microsoft Dynamics LCS(Lifecycle Service)에서 이 ER 형식 구성의 최신 버전을 가져옵니다. 해당 ER 데이터 모델 및 ER 모델 매핑 구성을 자동으로 가져옵니다.

ER 구성을 가져오는 방법에 대한 자세한 내용은 [ER 구성 수명 주기 관리](general-electronic-reporting-manage-configuration-lifecycle.md)를 참조하십시오.

![LCS 공유 자산 라이브러리 페이지.](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>응급실 솔루션 템플릿 편집

1.  **비즈니스 문서 관리** 작업 영역에 대한 액세스 권한이 있는 사용자로 로그인합니다.
2.  **비즈니스 문서 관리** 작업 영역을 엽니다.

    ![비즈니스 문서 관리 작업 공간.](./media/BDM-AddFldExcel-Workspace.png)

3.  그리드에서 **자유 텍스트 송장(Excel)** 템플릿을 선택합니다.
4.  오른쪽 창에서 **새 템플릿** 을 선택하여 선택한 템플릿을 기반으로 하는 새 템플릿을 만듭니다.
5.  **제목** 필드에 새 템플릿의 제목으로 **자유 텍스트 송장(Excel) Contoso** 를 입력합니다.
6.  **확인** 을 선택하여 편집 프로세스의 시작을 확인합니다.

BDM 템플릿 편집기 페이지가 나타납니다. 포함된 컨트롤에서 온라인으로 선택한 Microsoft 365 템플릿을 편집하는 데 사용할 수 있습니다.

![BDM 템플릿 편집기 페이지.](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>템플릿에 새 필드에 대한 레이블 추가

1.  BDM 템플릿 편집기 페이지의 Excel 리본에 있는 **보기** 탭에서 편집 가능한 Excel 템플릿에 대한 **머리글 및 눈금선** 확인란을 선택합니다.

    ![머리글 및 눈금선 확인란이 선택되었습니다.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  셀 **E8:F8** 을 선택합니다.
3.  Excel 리본의 **홈** 탭에서 **병합 및 가운데** 맞춤을 선택하여 선택한 셀을 병합된 새 **E8:F8** 셀로 병합합니다.
4.  병합된 셀 **E8:F8** 에 **URL** 을 입력합니다.
5.  병합된 셀 **E7:F7** 을 선택하고 **서식 화가** 를 선택한 다음 병합된 셀 **E8:F8** 을 선택하여 병합된 셀 **E7:F7** 과 같은 방식으로 서식을 지정합니다.

    ![템플릿에 새 필드 레이블이 추가되었습니다.](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>새 필드를 위한 공간을 예약하도록 템플릿 서식 지정

1.  BDM 템플릿 편집기 페이지에서 병합된 셀 **G8:H8** 을 선택합니다.
2.  Excel 리본의 **홈** 탭에서 **병합 및 가운데** 를 선택하여 선택한 셀을 병합된 새 **G8:H8** 셀로 병합합니다.
3.  병합된 셀 **G7:H7** 을 선택하고 **서식 페인터** 를 선택한 다음 병합된 셀 **G8:H8** 을 선택하여 병합된 셀 **G7:H7** 과 같은 방식으로 서식을 지정합니다.

    ![새 필드를 위해 예약된 공간입니다.](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  **이름** 상자 필드에서 **CompanyInfo** 를 선택합니다.

    현재 Excel 템플릿의 **CompanyInfo** 범위에는 생성된 보고서의 헤더를 판매자 당사자인 현재 회사의 세부 정보로 채우는 데 사용되는 모든 필드가 있습니다.

    ![CompanyInfo 범위가 선택되었습니다.](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>템플릿에 새 필드 추가

1.  **BDM 템플릿 편집기** 페이지의 작업 창에서 **형식 표시** 를 선택합니다.
2.  **템플릿 구조** 창에서 **추가** 를 선택합니다.

    > [!NOTE]
    > 새 필드로 사용하려는 템플릿의 섹션을 조정해야 합니다. 병합된 셀 **G8:H8** 의 서식을 지정하여 이미 이 조정을 수행했습니다.

    ![템플릿에 새 필드를 추가합니다.](./media/BDM-AddFldExcel-AddCell.png)

3.  **Excel\Cell** 을 선택하여 템플릿의 셀로 새 필드를 추가합니다.

    템플릿에 새 범위를 추가하려면 **Excel\Range** 를 선택할 수 있습니다. 입력한 범위에는 여러 셀이 포함될 수 있습니다. 나중에 이러한 셀을 추가할 수 있습니다.
    
    **CompanyInfo** 템플릿 구성 요소는 추가하는 필드에 대한 현재 **템플릿 구조** 에서 가장 적합한 상위 구성 요소이기 때문에 템플릿 구조 창에서 자동으로 선택됩니다.
    
4.  **Excel 범위** 필드에 **CompanyURL_Value** 를 입력합니다.
5.  **확인** 을 선택합니다.

    ![템플릿 구조에 CompanyURL_Value 필드가 추가되었습니다.](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  **템플릿 구조** 창에서 줄임표 버튼(...)를 선택한 다음 **바인딩 표시** 를 선택합니다.

    ![선택한 바인딩을 표시합니다.](./media/BDM-AddFldExcel-ShowBindings.png)

    이제 **템플릿 구조** 창에 기본 ER 형식으로 사용할 수 있는 데이터 소스가 표시됩니다.

7.  기본 ER 형식의 데이터 원본에 바인딩하려는 필드로 **CompanyInfo_Value** 를 선택합니다.
8.  **템플릿 구조** 창의 **데이터 원본** 섹션에서 **Model \> InvoiceBase \> CompanyInfo** 를 확장합니다.
9.  **CompanyInfo** 에서 **WebsiteURI** 항목을 선택합니다.

    ![웹사이트URI 항목이 선택되었습니다.](./media/BDM-AddFldExcel-BindURL.png)

10. **바인딩** 을 선택합니다.
11. **템플릿 구조** 창에서 **저장** 을 선택한 다음 BDM 템플릿 편집기 페이지를 닫습니다.

**비즈니스 문서 관리** 작업 공간에서 오른쪽 창의 **템플릿** 탭에는 업데이트된 템플릿이 표시됩니다. 그리드에서 편집된 템플릿의 **상태** 필드가 **초안** 으로 변경되었으며 **개정** 필드가 더 이상 비어 있지 않습니다. 이러한 변경은 이 템플릿 편집 프로세스가 시작되었음을 나타냅니다.

![비즈니스 문서 관리 작업 영역에서 편집된 템플릿입니다.](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>회사 설정 검토

1.  **조직 관리 \> 조직 \> 법인** 으로 이동합니다.
2.  **연락처 정보** FastTab에서 회사 URL이 입력되었는지 확인합니다.

![법인 페이지에 입력된 회사 URL입니다.](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>업데이트된 템플릿을 테스트하기 위한 비즈니스 문서 생성

1.  애플리케이션에서 회사를 **USMF** 로 변경하고 **미수금 \> 송장 \> 전체 무료 텍스트 송장** 으로 이동합니다.
2.  송장 **FTI-00000002** 를 선택한 다음 **인쇄 관리** 를 선택합니다.
3.  왼쪽 창에서 **모듈 - 미수금 \> 문서 \> 무료 텍스트 송장** 을 확장합니다.
4.  **자유 텍스트 송장** 에서 **원본 문서** 수준을 선택하여 처리할 송장의 범위를 지정합니다.
5.  오른쪽 창의 **보고서 형식** 필드에서 지정된 문서 수준에 대한 **자유 텍스트 송장(Excel) Contoso** 템플릿을 선택합니다.

    ![무료 텍스트 송장(Excel) Contoso 템플릿이 선택되었습니다.](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  **Esc** 키를 눌러 현재 페이지를 닫습니다.
7.  **선택한 항목 \> 인쇄** 를 선택합니다.
8.  생성된 문서를 다운로드하여 Excel에서 엽니다.

    ![Excel의 무료 텍스트 송장.](./media/BDM-AddFldExcel-PreviewReport.png)

수정된 템플릿은 선택한 항목에 대한 자유 텍스트 송장 보고서를 생성하는 데 사용됩니다. 템플릿 변경이 이 보고서에 미치는 영향을 분석하려면 다른 애플리케이션 세션에서 템플릿을 변경한 직후 한 애플리케이션 세션에서 보고서를 실행하십시오.

## <a name="related-links"></a>관련된 링크들

[전자 보고(ER) 개요](general-electronic-reporting.md)

[비즈니스 문서 관리 개요](er-business-document-management.md)

[OPENXML 형식의 보고서 생성을 위한 구성 설계](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]