---
title: Excel 템플릿과 함께 ER 구성을 재사용하여 Word 형식으로 보고서 생성
description: 이번에는 보고서를 Excel 통합 문서로 생성하도록 설계된 보고서 형식을 구성하여 보고서를 Word 문서로 생성할 수 있는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de8286c7612cd588b28cf4667340374906962dde
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460716"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Excel 템플릿과 함께 ER 구성을 재사용하여 Word 형식으로 보고서 생성

[!include [banner](../../includes/banner.md)]

보고서를 Microsoft Word 문서로 생성하기 위해 새로운 [전자 보고(ER)](../general-electronic-reporting.md) 형식을 [구성](../er-design-configuration-word.md)할 수 있습니다. 또는 원래 보고서를 Excel 통합 문서로 생성하도록 설계된 ER 형식을 재사용할 수 있습니다. 이 경우 Excel 템플릿을 Word 템플릿으로 바꿔야 합니다.

다음 절차는 시스템 관리자 역할 또는 전자 보고 개발자 역할의 사용자가 보고서를 Excel 파일로 생성하도록 설계된 ER 형식을 재사용하여 보고서를 Word 파일로 생성하도록 ER 형식을 구성하는 방법을 보여줍니다.

이번에는 GBSI 회사에서 완료할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

이러한 절차를 완료하려면 먼저 [OPENXML 형식으로 보고서를 생성하기 위한 구성 설계 작업](er-design-reports-openxml-2016-11.md) 가이드의 단계를 따라야 합니다.

또한 샘플 보고서에 대한 다음 템플릿을 다운로드하여 로컬에 저장해야 합니다.

- [지불 보고서 템플릿(SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [지급 보고서의 경계 템플릿(SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

이번에는 Dynamics 365 for Operations 버전 1611(2016년 11월)에 추가된 기능에 대한 것입니다.

## <a name="select-the-existing-er-report-configuration"></a>기존 ER 보고서 구성 선택

1. Dynamics 365 Finance에서 **조직 관리** \> **작업 공간** \> **전자 보고** 로 이동합니다.
2. **Litware, Inc.** 구성 공급자가 **활성** 으로 선택되어 있는지 확인합니다. 그렇지 않은 경우 [구성 공급자 만들기](er-configuration-provider-mark-it-active-2016-11.md)의 단계를 따르고 활성 작업으로 표시합니다.
3. **보고 구성** 을 선택합니다. 보고서 출력을 OPENXML 형식으로 생성하도록 설계된 기존 ER 구성을 다시 사용합니다.
4. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **지급 모델** 을 확장하고 **샘플 워크시트 보고서** 를 선택합니다.

    > [!NOTE]
    > 선택한 ER 형식의 초안 버전은 **버전** FastTab에서 편집할 수 있습니다.

5. **디자이너** 를 선택합니다.
6. **형식 디자이너** 페이지에서 루트 형식 요소의 제목은 Excel 템플릿이 현재 사용 중임을 나타냅니다.

![기존 구성 선택.](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>다운로드한 Word 템플릿 검토

1. Word 데스크톱 애플리케이션에서 이전에 다운로드한 **SampleVendPaymDocReport.docx** 템플릿 파일을 엽니다.
2. 템플릿에 ER 출력으로 생성하려는 문서의 레이아웃만 포함되어 있는지 확인합니다.

![데스크톱 애플리케이션의 Word 템플릿 레이아웃입니다.](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Excel 템플릿을 Word 템플릿으로 교체하고 사용자 지정 XML 부분 추가

현재 Excel 문서는 OPENXML 형식으로 출력을 생성하기 위한 템플릿으로 사용됩니다. 이 템플릿을 이전에 다운로드한 SampleVendPaymDocReport.docx Word 템플릿 파일로 교체합니다. 또한 사용자 지정 XML 부분을 추가하여 Word 템플릿을 확장합니다.

1. Finance의 **형식 디자이너** 페이지에 있는 **형식** 탭에서 **첨부 파일** 을 선택합니다.
2. **첨부 파일** 페이지에서 **삭제** 를 선택하여 기존 Excel 템플릿을 제거합니다. **예** 를 선택하여 변경 사항을 확인합니다.
3. **새** \> **파일** 을 선택합니다.

    > [!NOTE]
    > ER 형식의 템플릿을 저장하려면 ER 매개 변수에 [구성된](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) 문서 유형을 선택해야 합니다.

4. **찾아보기** 를 선택한 다음 이전에 다운로드한 **SampleVendPaymDocReport.docx** 파일을 찾아 선택합니다.
5. **확인** 을 선택합니다.
6. **첨부 파일** 페이지를 닫습니다.
7. **서식 디자이너** 페이지의 **템플릿** 필드에서 **SampleVendPaymDocReport.docx** 파일을 입력하거나 선택하여 이전에 사용한 Excel 템플릿 대신 해당 Word 템플릿을 사용합니다.
8. **저장** 을 선택합니다.

    구성 변경 사항을 저장하는 것 외에도 **저장** 작업은 첨부된 Word 템플릿을 업데이트합니다. 디자인된 형식의 계층 구조는 **보고서** 라는 새 사용자 지정 XML 부분으로 첨부된 Word 문서에 추가됩니다. 첨부된 Word 템플릿에는 ER 출력으로 생성될 문서의 레이아웃과 런타임에 ER이 해당 템플릿에 입력할 데이터 구조가 포함됩니다.

9. 루트 형식 요소의 제목은 현재 Word 템플릿이 사용 중임을 나타냅니다.

    ![Excel 템플릿을 Word 템플릿으로 교체하고 사용자 지정 XML 부분을 추가합니다.](../media/er-design-configuration-word-2016-11-image03.gif)

10. **형식** 탭에서 **첨부 파일** 을 선택합니다.

이제 **보고서** 사용자 지정 XML 부분의 요소를 Word 문서의 콘텐츠 컨트롤에 매핑할 수 있습니다.

Word 문서를 [사용자 지정 XML 부분](/visualstudio/vsto/custom-xml-parts-overview)의 요소에 매핑된 [콘텐츠 컨트롤](/office/client-developer/word/content-controls-in-word)이 포함된 양식으로 디자인하는 프로세스에 익숙한 경우 다음 절차의 모든 단계를 완료하여 문서를 만듭니다. 자세한 내용은 [사용자가 Word에서 작성하거나 인쇄하는 양식 만들기](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b)를 참조하십시오. 그렇지 않으면 다음 절차를 건너뜁니다.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>사용자 지정 XML 부분이 있는 Word 문서를 가져오고 데이터 매핑을 수행합니다.

1. Finance의 **첨부** 페이지에서 **열기** 를 선택하여 Finance에서 선택한 템플릿을 다운로드하고 로컬에 Word 문서로 저장합니다.
3. Word 데스크톱 애플리케이션에서 방금 다운로드한 문서를 엽니다.
4. **개발 도구** 탭에서 **XML 매핑** 창을 선택합니다.

    > [!NOTE]
    > **개발 도구** 탭이 리본에 표시되지 않으면 리본을 사용자 지정하여 추가하십시오.

5. **XML 매핑** 창의 **사용자 지정 XML 부분** 필드에서 **보고서** 사용자 지정 XML 부분을 선택합니다.
6. 선택한 **보고서** 사용자 지정 XML 부분의 요소와 Word 문서의 콘텐츠 컨트롤을 매핑합니다.
7. 업데이트된 Word 문서를 **SampleVendPaymDocReportBounded.docx** 로 로컬에 저장합니다.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>사용자 지정 XML 부분이 콘텐츠 컨트롤에 매핑되는 Word 템플릿 검토

1. Word 데스크톱 애플리케이션에서 **SampleVendPaymDocReportBounded.docx** 템플릿 파일을 엽니다.
2. 템플릿에 ER 출력으로 생성하려는 문서의 레이아웃이 포함되어 있는지 확인합니다. 런타임 시 ER이 이 템플릿에 입력할 데이터의 자리 표시자로 사용되는 콘텐츠 컨트롤은 **보고서** 사용자 지정 XML 부분의 요소와 Word 문서의 콘텐츠 컨트롤 간에 구성된 매핑을 기반으로 합니다.

![데스크톱 애플리케이션의 Word 템플릿 미리 보기.](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>사용자 지정 XML 부분이 콘텐츠 컨트롤에 매핑되는 Word 템플릿 업로드

1. Finance의 **첨부 파일** 페이지에서 **삭제** 를 선택하여 **보고서** 사용자 지정 XML 부분과 콘텐츠 컨트롤의 요소 간에 매핑이 없는 Word 템플릿을 제거합니다. **예** 를 선택하여 변경 사항을 확인합니다.
2. **보고서** 사용자 지정 XML 부분의 요소와 콘텐츠 컨트롤 간의 매핑이 포함된 새 템플릿 파일을 추가하려면 **새** \> **파일** 을 선택합니다.

    > [!NOTE]
    > ER 형식의 템플릿을 저장하려면 ER 매개 변수에 [구성된](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) 문서 유형을 선택해야 합니다.

3. **찾아보기** 를 선택한 다음 데이터 매핑을 수행할 [사용자 지정 XML 부분이 있는 Word 가져오기](#get-word-doc) 섹션의 절차를 완료하여 다운로드하거나 준비한 **SampleVendPaymDocReportBounded.docx** 파일을 찾아 선택합니다.
4. **확인** 을 선택합니다.
5. **첨부 파일** 페이지를 닫습니다.
6. **서식 디자이너** 페이지의 **템플릿** 필드에서 방금 다운로드한 문서를 선택합니다.
7. **저장** 을 선택합니다.
8. **형식 디자이너** 페이지를 닫습니다.

## <a name="mark-the-configured-format-as-runnable"></a>구성된 형식을 실행 가능한 것으로 표시

편집 가능한 형식의 초안 버전을 실행하려면 [실행 가능하게](../er-quick-start2-customize-report.md#MarkFormatRunnable) 만들어야 합니다.

1. Finance의 **구성** 페이지에 있는 작업 창에 있는 **구성** 탭에 있는 **고급 설정** 그룹에서 **사용자 매개 변수** 를 선택합니다.
2. **사용자 매개 변수** 대화 상자에서 **실행 설정** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
3. **편집** 을 선택하여 필요에 따라 현재 페이지를 편집 가능하게 만듭니다.
4. 현재 선택한 **샘플 워크시트 보고서** 구성의 경우 **초안 실행** 옵션을 **예** 로 설정합니다.
5. **저장** 을 선택합니다.

## <a name="run-the-format-to-create-output-in-word-format"></a>형식을 실행하여 Word 형식으로 출력 생성

1. 재무에서 **미지급금** \> **지급** \> **분개** 로 이동합니다.
2. 이전에 입력한 지급 분개에서 **라인** 을 선택합니다.
3. **공급 업체 지급** 페이지에서 그리드의 모든 행을 선택합니다.
4. **지급 상태** \> **없음** 을 선택합니다.

    ![공급 업체 지급 페이지에서 처리를 위한 지급입니다.](../media/er-design-configuration-word-2016-11-image05.png)

5. 작업 창에서 **수량 조정** 을 선택합니다.
6. 표시되는 대화 상자에서 다음 단계를 따르십시오.

    1. **결제 방법** 필드에서 **전자** 를 선택합니다.
    2. **은행 계좌** 필드에 **GBSI OPER** 을 선택합니다.
    3. **확인** 을 선택합니다.

7. **전자 보고서 매개 변수** 대화 상자에서 **확인** 을 선택합니다.
8. 생성된 출력은 Word 형식으로 표시되며 처리된 지급에 대한 세부 정보를 포함합니다. 생성된 출력을 분석합니다.

    ![Word 형식으로 생성된 출력.](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>추가 리소스

- [Word 형식으로 보고서를 생성하기 위한 새로운 ER 구성 설계](../er-design-configuration-word.md)
- [ER을 사용하여 생성한 문서에 이미지 및 모양 포함](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
