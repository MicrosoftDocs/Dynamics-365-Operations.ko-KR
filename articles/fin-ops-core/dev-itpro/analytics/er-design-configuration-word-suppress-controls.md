---
title: 생성된 보고서에서 Word 콘텐츠 제어 억제
description: 이번에는 콘텐츠 제어가 표시되지 않는 Microsoft Word 파일로 보고서를 생성하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: f8e74902e939355aba9bbadd8e7f8f8aa46fe5c5
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461014"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>생성된 보고서에서 Word 콘텐츠 제어 억제

[!include [banner](../includes/banner.md)]

보고서를 Microsoft Word 문서로 생성하려면 보고서 템플릿을 Word 문서로 디자인해야 합니다. 이 템플릿은 런타임에 채워질 데이터의 자리 표시자로 Word 콘텐츠 컨트롤을 포함해야 합니다. 보고서의 템플릿으로 생성된 Word 문서를 사용하기 위해 새로운 [전자 보고(ER)](general-electronic-reporting.md) [솔루션](er-quick-start1-new-solution.md)을 [구성](er-design-configuration-word.md)할 수 있습니다. 솔루션에는 ER 형식 구성 요소가 포함된 ER [구성](general-electronic-reporting.md#Configuration)이 포함되어야 합니다. 보고서 생성을 위해 설계된 템플릿을 사용하려면 이 ER 형식을 구성해야 합니다.

Dynamics 365 Finance 버전 10.0.6 이상에서는 생성된 문서에서 일부 Word 콘텐츠 컨트롤을 표시하지 않도록 ER 형식의 수식을 구성할 수 있습니다.

다음 단계는 시스템 관리자 또는 전자 보고 함수 컨설턴트 역할에 할당된 사용자가 보고서를 Word 파일로 생성하고 Word를 사용하여 구성된 생성된 보고서의 일부 콘텐츠 제어를 억제하는 ER 형식을 구성하는 방법을 설명합니다. 주형.

이 단계는 GBSI 회사에서 완료할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

이 단계를 완료하려면 먼저 다음 작업 가이드의 단계를 완료해야 합니다.

- [OPENXML 형식의 보고서 생성을 위한 구성 설계](./tasks/er-design-reports-openxml-2016-11.md)
- [Excel 템플릿과 함께 ER 구성을 재사용하여 Word 형식으로 보고서 생성](./tasks/er-design-configuration-word-2016-11.md)

이 작업 가이드의 단계를 완료하면 다음 항목이 준비됩니다.

- Word 형식의 문서를 생성하도록 구성된 **샘플 워크시트 보고서** ER 형식
- **실행 가능** 으로 표시된 **샘플 워크시트 보고서** ER 형식의 [초안](general-electronic-reporting.md#component-versioning) 버전
- 공급 업체 지급 처리를 위해 **샘플 워크시트 보고서** ER 형식을 사용하도록 구성된 **전자** 지급 방법

또한 샘플 보고서에 대한 다음 템플릿을 다운로드하여 저장해야 합니다.

- [지급 보고서의 경계 템플릿 2(SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>다운로드한 Word 템플릿 검토

1. Word 데스크톱 애플리케이션에서 이전에 다운로드한 **SampleVendPaymDocReportBounded2.docx** 템플릿 파일을 엽니다.
2. 템플릿 파일에 처리된 지급에서 충족된 모든 통화 코드에 대한 총 지급 금액을 보여주는 요약 섹션이 포함되어 있는지 확인하십시오.

    - 요약 섹션은 Word 문서의 별도 표에 있습니다.
    - 이 테이블의 첫 번째 행은 테이블 열 머리글을 섹션 머리글로 보유합니다.
    - 이 테이블의 두 번째 행에는 섹션 세부 정보로 반복되는 콘텐츠 컨트롤이 있습니다.
    - 이 콘텐츠 컨트롤은 **보고서** 사용자 지정 XML 부분의 **SummaryLines** 필드에 매핑됩니다.
    - 이 매핑을 기반으로 콘텐츠 컨트롤은 편집 가능한 ER 형식의 **SummaryLines** 요소와 연결됩니다.

    > [!NOTE]
    > 반복 콘텐츠 컨트롤은 매핑된 사용자 지정 XML 부분의 필드와 일치하는 **SummaryLines** 키로 태그가 지정됩니다.

    ![워드 템플릿 레이아웃입니다.](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>기존 ER 보고서 구성 선택

다음 단계에서는 앞에서 언급한 작업 가이드의 단계를 완료할 때 구성한 기존 ER 구성을 다시 사용합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **보고 구성** 을 선택합니다.
3. **구성** 페이지의 구성 트리에서 **지급 모델** 을 확장하고 **샘플 워크시트 보고서** 를 선택합니다.
4. **디자이너** 를 선택하여 선택한 ER 형식의 초안 버전을 편집합니다.

## <a name="replace-the-current-template-with-the-new-template"></a>현재 템플릿을 새 템플릿으로 교체

현재 SampleVendPaymDocReportBounded.docx 파일은 Word 형식으로 출력을 생성하기 위한 템플릿으로 사용됩니다. 다음 단계에서는 이 Word 템플릿을 이전에 다운로드한 새 Word 템플릿 SampleVendPaymDocReportBounded2.docx로 바꿉니다.

1. **형식 디자이너** 페이지에서 **첨부 파일** 을 선택합니다.
2. **첨부 파일** 페이지에서 **삭제** 를 선택하여 기존 템플릿을 제거합니다.
3. **예** 를 선택하여 삭제를 확인합니다.
4. **새** \> **파일** 을 선택합니다.
5. **찾아보기** 를 선택하고 이전에 다운로드한 **SampleVendPaymDocReportBounded2.docx** 파일을 찾아 선택합니다.
6. **확인** 을 선택합니다.
7. **첨부 파일** 페이지를 닫습니다.
8. **형식 디자이너** 페이지의 **템플릿** 필드에서 **SampleVendPaymDocReportBounded2.docx** 파일을 입력하거나 선택합니다.

## <a name="run-the-format-to-create-word-output"></a>형식을 실행하여 Word 출력 생성

1. **미지급금** \> **지급** \> **지급 분개** 로 이동하십시오.
2. **공급 업체 지급** 페이지의 **목록** 탭에서 모든 지급을 선택합니다.
3. **지급 상태** \> **없음** 을 선택합니다.
4. **결제 생성** 을 선택합니다.
5. **결제 방법** 필드에서 **전자** 를 선택합니다.
6. **은행 계좌** 필드에 **GBSI OPER** 을 선택합니다.
7. **확인** 을 선택합니다.
8. **전자 보고서 매개 변수** 대화 상자에서 **확인** 을 선택하고 생성된 출력을 분석합니다.

    ![공급 업체 지급 페이지에서 처리를 위한 지급입니다.](./media/er-design-configuration-word-suppress-controls-image2.gif)

    출력은 Word 형식으로 제공되며 요약 섹션을 포함합니다.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>요약 섹션을 표시하지 않도록 편집 가능한 형식 구성

이 ER 형식을 실행하는 사용자의 요청에 따라 생성된 문서에서 요약 섹션을 표시하지 않으려면 편집 가능한 ER 형식을 수정해야 합니다.

1. **조직 관리** \> **작업 공간** \> **전자 보고** 로 이동하고 편집을 위해 ER 형식의 초안 버전을 엽니다.
2. **보고 구성** 을 선택합니다. 
3. **구성** 페이지의 구성 트리에서 **지급 모델** \> **샘플 워크시트 보고서** 를 확장합니다.
4. **디자이너** 를 선택합니다.
5. **서식 디자이너** 페이지에서 **Word** 를 확장하고 **SummaryLines** 를 선택합니다.
6. **매핑** 탭에서 런타임에 요약 섹션을 표시하지 않아야 하는지 여부를 사용자에게 묻는 새 데이터 소스를 추가합니다.

    1. **루트 추가** 를 선택합니다.
    2. **데이터 원본 추가** 대화 상자에서 **일반\사용자 입력 매개 변수** 를 선택하여 **'사용자 입력 매개 변수' 데이터 원본 속성** 대화 상자를 엽니다.
    3. **이름** 필드에 **uipSuppress** 를 입력합니다.
    4. **레이블** 필드에 **요약 섹션 표시 안 함** 을 입력합니다.
    5. **작업 데이터 유형 이름** 필드에서 **NoYes** 를 선택하거나 입력합니다.
    6. **확인** 을 선택합니다.

7. **NoYes** 애플리케이션 열거 유형의 새 데이터 소스를 추가합니다.

    1. **루트 추가** 를 선택합니다.
    2. **데이터 원본 추가** 대화 상자에서 **Dynamics 365 for Operations\Enumeration** 을 선택하여 **'열거' 데이터 원본 속성** 대화 상자를 엽니다.
    3. **이름** 필드에 **enumNoYes** 를 입력합니다.
    4. **레이블** 필드에 **옵션 억제** 를 입력합니다.
    5. **작업 데이터 유형 이름** 필드에서 **NoYes** 를 선택하거나 입력합니다.
    6. **확인** 을 선택합니다.

8. 선택한 **SummaryLines** 형식 요소에 대해 선택한 형식 요소와 연결된 Word 콘텐츠 컨트롤이 표시되지 않아야 하는 시기를 지정하도록 수식을 구성합니다.

    1. **매핑** 탭의 **제거됨** 섹션에서 **편집** 을 선택하여 **[수식 디자이너](general-electronic-reporting-formula-designer.md)** 페이지를 엽니다.
    2. **수식** 필드에 `uipSuppress = enumNoYes.Yes` 수식을 입력합니다.
    3. **저장** 을 선택하고 **수식 디자이너** 페이지를 닫습니다.

        > [!NOTE]
        > **이 공식은 다른 모든 형식 요소가 실행된 후** 생성된 문서에 적용됩니다. 이 수식을 적용하기 위해 수식이 구성된 형식 요소로 태그가 지정된 Word 콘텐츠 컨트롤(이 경우에는 **SummaryLines**)이 생성된 문서에서 발견됩니다. 그러면 해당 콘텐츠 컨트롤이 해당 콘텐츠 컨트롤을 포함하는 Word 테이블의 행과 함께 완전히 제거됩니다. 요약 섹션의 세부 정보 행이 생성된 문서에서 제거됩니다.
        >
        > 사용 중인 Word 템플릿의 콘텐츠 컨트롤에 **Removed** 속성이 구성된 형식 요소의 이름과 일치하는 태그가 없더라도 디자인 타임에 형식 요소에 대해 **Removed** 수식을 구성할 수 있습니다. 디자인 타임에 형식의 유효성을 검사하면 이 불일치에 대한 [경고가](er-components-inspections.md#i14) 나타납니다.
        >
        > 사용 중인 Word 템플릿의 콘텐츠 컨트롤에 **Removed** 속성이 구성된 형식 요소의 이름과 일치하는 태그가 없으면 런타임에 예외가 throw됩니다.

    4. **매핑** 탭의 **제거됨** 섹션에서 **부모 포함** 옵션을 **예** 로 설정합니다.

        > [!NOTE]
        > 요약 섹션 세부 정보가 있는 행의 상위 개체로 전체 Word 테이블을 제거하려면 이 옵션을 **예** 로 설정해야 합니다. 이 옵션을 **아니오** 로 설정하면 섹션 머리글 행이 생성된 문서에 남습니다.

9. **저장** 을 선택하여 변경 사항을 편집 가능한 형식으로 저장합니다.

    ![생성된 출력은 Word 형식입니다.](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>수정된 형식을 실행하여 Word 출력 생성

1. **미지급금** \> **지급** \> **지급 분개** 로 이동하십시오.
2. 생성한 지급 분개를 선택한 다음 **라인** 을 선택합니다.
3. **공급 업체 지급** 페이지에서 모든 행을 선택한 다음 **지급 상태** \> **없음** 을 선택합니다.
4. **결제 생성** 을 선택합니다.
5. **결제 방법** 필드에서 **전자** 를 선택합니다.
6. **은행 계좌** 필드에 **GBSI OPER** 을 선택합니다.
7. **확인** 을 선택합니다.
8. **전자 보고서 매개 변수** 대화 상자의 **요약 섹션 표시 안 함** 필드에서 **예** 를 선택합니다.
9. **확인** 을 선택하고 생성된 출력을 분석합니다.

    ![Word 형식으로 생성된 출력.](./media/er-design-configuration-word-suppress-controls-image4.gif)

    요약 섹션이 표시되지 않았기 때문에 출력에 요약 섹션이 포함되지 않습니다.

## <a name="additional-resources"></a>추가 리소스

- [OPENXML 형식의 보고서 생성을 위한 구성 설계](./tasks/er-design-reports-openxml-2016-11.md)
- [Word 형식으로 보고서를 생성하기 위한 새로운 ER 구성 설계](er-design-configuration-word.md)
- [Excel 템플릿과 함께 ER 구성을 재사용하여 Word 형식으로 보고서 생성](./tasks/er-design-configuration-word-2016-11.md)
- [런타임 문제를 방지하기 위해 구성된 ER 구성 요소 검사](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
