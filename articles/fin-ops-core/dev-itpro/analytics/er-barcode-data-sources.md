---
title: 바코드 데이터 소스를 사용하여 바코드 이미지 생성
description: 이번에는 바코드 데이터 소스를 사용하여 바코드 이미지를 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: a5a396080d8b5dd4c2ed9a0eb15c1286e8799ebf
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460743"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>바코드 데이터 소스를 사용하여 바코드 이미지 생성

[!include[banner](../includes/banner.md)]

[전자 보고(ER)](general-electronic-reporting.md) 프레임워크를 사용하여 필요한 전자 및 인쇄 가능한 아웃바운드 문서를 생성하기 위해 실행할 수 있는 ER 형식 구성 요소를 설계할 수 있습니다. 아웃바운드 문서를 Microsoft Office 형식으로 생성하려면 Microsoft Excel 문서 또는 Microsoft Word 문서를 보고서 템플릿으로 사용하여 보고서 레이아웃을 지정해야 합니다. [ER Operations Designer](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base)를 사용하면 Excel 또는 Word 문서를 ER 형식의 템플릿으로 첨부할 수 있습니다. 첨부된 템플릿의 다음 명명된 요소는 구성된 형식 구성 요소의 요소와 연결됩니다.

- Word의 콘텐츠 컨트롤
- Excel의 명명된 시트, 범위, 셀, 도형 및 이미지

이러한 명명된 요소는 ER 형식이 실행될 때 생성된 문서에 입력되는 데이터의 자리 표시자로 사용됩니다. ER 형식 요소는 데이터 소스에 바인딩됩니다. 이러한 데이터 소스는 런타임에 생성된 문서에 입력할 데이터를 지정합니다. 자세한 내용은 [ER을 사용하여 생성한 문서에 이미지 및 도형 포함](electronic-reporting-embed-images-shapes.md)을 참조하십시오.

ER은 이제 **바코드** 데이터 소스 유형을 지원합니다. 따라서 이제 지정된 텍스트의 바코드를 나타내는 이미지를 생성할 수 있습니다. ER 형식을 구성할 때 바코드 유형의 데이터 소스를 지정하여 **바코드** 이미지를 생성할 수 있습니다. 이후 주문, 송장, 포장 명세서 및 영수증과 같은 생성된 비즈니스 문서에 해당 이미지를 추가할 수 있습니다. 또한 제품 및 선반 레이블, 포장 및 배송 레이블과 같은 다양한 종류의 레이블에 추가할 수 있습니다.

다음 자리 표시자는 보고서 템플릿에서 바코드 이미지를 입력하는 데 사용할 수 있습니다.

- Word용 [그림](/office/client-developer/word/content-controls-in-word) 콘텐츠 제어
- Excel의 [그림](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) 개체

**바코드** 유형의 데이터 소스를 사용하여 다음 형식의 바코드를 생성할 수 있습니다.

- 1차원 바코드:

    - 코다바
    - 코드 39
    - 코드 93
    - 코드 128
    - EAN-8
    - EAN-13
    - ITF-14
    - 지능형 메일
    - MSI
    - 플레시
    - PDF417
    - UPC-A
    - UPC-E

- 2차원 바코드:

    - 아즈텍
    - 데이터 매트릭스
    - QR 코드

**바코드** 데이터 소스를 구성할 때 이미지를 생성하는 데 사용되는 특정 렌더링 매개 변수를 정의할 수 있습니다.

- **너비** – 바코드의 너비를 픽셀 단위로 지정합니다. 값이 **0**(영)이면 기본 너비가 사용됨을 나타냅니다. 의미는 형식에 따라 다를 수 있습니다.
- **높이** – 바코드의 높이를 픽셀 단위로 지정합니다. **0**(영) 값은 기본 높이가 사용됨을 나타냅니다. 의미는 형식에 따라 다를 수 있습니다.
- **여백** – 바코드의 여백 크기를 픽셀 단위로 지정합니다. 여백은 명확하게 유지되어야 하는 바코드의 각 측면 영역입니다(여백 영역). 값 **0**(영)은 기본 여백이 사용됨을 나타냅니다. 의미는 형식에 따라 다를 수 있습니다.
- **출력 콘텐츠** – 인코딩된 정보를 텍스트로 포함하는 바코드 이미지를 생성하려면 값을 **예** 로 설정합니다. 기본값은 **아니요** 입니다.
- **인코딩** – 생성된 바코드 이미지에 인코딩되는 문자 유형을 지정합니다. 기본적으로 **UTF-8** 인코딩이 사용됩니다.

> [!IMPORTANT]
> 새 **바코드** 데이터 소스를 추가할 때 다른 항목(컨테이너) 아래에 중첩 요소로 배치해야 합니다.
>
> **바코드** 데이터 소스를 형식의 셀 요소에 바인딩하고 셀 요소가 Word 콘텐츠 컨트롤 또는 Excel 그림을 나타내는 경우 데이터 소스는 해당 바인딩에 **스트링** 유형의 단일 매개 변수가 있는 함수로 표시됩니다. . 이 매개 변수를 사용하여 바코드 이미지로 변환하고 생성된 바코드를 스캔할 때 읽어야 하는 텍스트를 지정해야 합니다.

이 기능에 대한 자세한 내용은 이 항목의 예시를 완료하십시오.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>예:, 지급할 금액을 인코딩하는 바코드가 포함된 지급 수표 생성

이 예시에서는 **시스템 관리자** 또는 **전자 보고 함수 컨설턴트** 역할의 사용자가 바코드가 포함된 Excel 형식의 아웃바운드 문서를 생성하는 데 사용되는 템플릿이 포함된 ER 형식을 구성할 수 있는 방법을 보여줍니다. 다음은 관련된 단계에 대한 개요입니다.

1. [전제 조건을 완료합니다](#ExamplePrerequisites).
2. [구성 공급자를 활성화합니다](#ExampleProvider).
3. [제공된 ER 솔루션을 가져옵니다](#ExampleImportSolution).
4. [지급 수표를 생성합니다](#ExampleGenerateCheque).
5. [생성된 지급 수표를 검토합니다](#ExampleReviewGeneratedCheque).
6. [제공된 ER 솔루션의 형식을 수정합니다](#ExampleModifyFormat).

    1. [새 수표 템플릿을 적용합니다](#ExampleModifyFormatApplyTemplate).
    2. [새 바코드 데이터 소스를 추가합니다](#ExampleModifyFormatAddDataSource).
    3. [새 형식 요소를 바인딩합니다](#ExampleModifyFormatBindFormatElement).
    4. [수정된 버전을 테스트 실행에 사용할 수 있도록 합니다](#ExampleModifyFormatMakeVersionAvailable).

        1. [수정된 형식 버전을 완료합니다](#CompleteToRun).
        2. [초안 버전을 사용할 수 있도록 합니다](#MarkToRun).

7. [지급 수표를 생성합니다](#ExampleGenerateCheque2).
8. [생성된 수표를 PDF로 변환합니다](#ExampleConvertToPDF).

이 예시에서는 지급 수표를 생성하도록 구성된 제공된 ER 솔루션을 사용합니다. 이 솔루션은 지급할 금액이 숫자와 텍스트로 모두 쓰여진 지급 수표를 생성합니다. 지급 금액이 인코딩되고 바코드 스캐너를 사용하여 읽을 수 있는 생성된 바코드도 수표에 포함되도록 이 ER 솔루션을 수정합니다.

단계는 Microsoft Dynamics 365 Finance의 **USMF** 회사에서 완료할 수 있습니다.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>전제 조건 완료

이 예를 완료하려면 다음 역할 중 하나에 대해 재무의 USMF 회사에 대한 액세스 권한이 있어야 합니다.

- 전자 보고 기능 컨설턴트
- 시스템 관리자

[ER을 사용하여 생성하는 문서에 이미지 및 모양 포함](electronic-reporting-embed-images-shapes.md) 항목의 예시를 아직 완료하지 않은 경우 샘플 ER 솔루션의 다음 구성을 다운로드하십시오.

| 콘텐츠 설명         | 파일 이름                   |
|-----------------------------|-----------------------------|
| ER 데이터 모델 구성 | [cheques.xml용 모델](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)      |
| ER 형식 구성     | [format.xml 인쇄 확인](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |

또한 제공된 ER 솔루션에 대해 수정된 템플릿이 포함된 다음 Excel 파일을 다운로드합니다.

| 콘텐츠 설명 | 파일 이름                 |
|---------------------|---------------------------|
| 보고서 템플릿     | [템플릿 Excel.xlsx 확인](https://download.microsoft.com/download/3/b/d/3bd3b944-da8f-43b4-8533-3c1292a4c3ef/CheckTemplateExcel.xlsx) |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Litware, Inc.** 샘플 회사의 [구성 공급자](general-electronic-reporting.md#Provider)가 나열되어 있고 활성으로 표시되어 있는지 확인합니다. 목록에 없거나 활성으로 표시되지 않은 경우 [구성 공급자 생성 및 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md) 항목의 단계를 따르십시오.

![현지화 구성 페이지에서 샘플 회사를 활성으로 설정합니다.](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>제공된 ER 솔루션 가져오기

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성 페이지** 에서 구성 트리에서 **검사용 모델** 구성을 사용할 수 없는 경우 다음 단계에 따라 ER 데이터 모델 구성을 가져옵니다.

    1. 작업 창에서 **XML 파일에서** \> **Exchange 로드** 를 선택합니다.
    2. 대화 상자에서 **찾아보기** 를 선택하고 **cheques.xml** 파일에 대한 모델을 찾아 선택한 다음 **확인** 을 선택합니다.

4. 구성 트리에서 **수표 인쇄 형식** 구성을 사용할 수 없는 경우 다음 단계에 따라 ER 형식 구성을 가져옵니다.

    1. 작업 창에서 **XML 파일에서** \> **Exchange 로드** 를 선택합니다.
    2. 대화 상자에서 **찾아보기** 를 선택하고 **검사 인쇄 format.xml 파일** 을 찾아 선택한 다음 **확인** 을 선택합니다.

5. 구성 트리에서 **수표 모델** 을 확장합니다.
6. 구성 트리에서 가져온 ER 구성 목록을 검토합니다.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>지급 수표 생성

1. **현금 및 은행 관리** \>로 이동합니다. **은행 계좌** \> **은행 계좌**.
2. **은행 계좌** 페이지에서 **USMF OPER** 계좌를 선택합니다.
3. 판매 주문 세부 정보 페이지의 작업 창에 있는 **판매 주문** 탭에 있는 **유지 보수** 그룹에서 **취소** 를 선택합니다.
4. **레이아웃 확인** 페이지에서 **편집** 을 선택합니다.
5. **일반** FastTab에서 **보충 작업 릴리스 자동화** 옵션을 **예** 로 설정합니다.
6. **내보내기 형식 구성** 필드에서 이전에 **가져온 검사 인쇄 형식** ER 형식을 선택합니다.
7. 작업 창에서 **인쇄** 를 선택합니다.
8. 대화 상자에서 **협상 가능한 수표 형식** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.

    ![레이아웃 확인 - 테스트 대화 상자를 인쇄합니다.](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>생성된 지급 수표 검토

- Excel에서 생성된 수표를 엽니다.
2. 생성된 수표를 검토합니다.

    ![Excel에서 생성된 지급 수표.](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>제공된 ER 솔루션의 형식 수정

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>새 수표 템플릿 적용

Excel 데스크톱 애플리케이션을 사용하여 이전에 가져온 **Check 템플릿 Excel.xlsx** 파일을 열 수 있습니다. 이 템플릿은 제공된 ER 솔루션에서 지급 수표를 생성하는 데 사용한 템플릿과 다릅니다. 또한 바코드 이미지에 대한 **AmountBarcode** 요소를 포함합니다.

![Excel 템플릿의 AmountBarcode 요소입니다.](./media/er-barcode-data-source-cheque2.png)

이제 ER 솔루션을 수정한 다음 수정된 템플릿을 [다시 적용](modify-electronic-reporting-format-reapply-excel-template.md)해야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 을 선택합니다.
3. **구성** 페이지의 구성 트리에서 **수표 모델** 을 확장하고 **수표 인쇄 형식** 을 선택합니다.
4. 작업 창에서 **디자이너** 를 선택합니다.
5. ER Operations 디자이너에서 페이지 오른쪽의 **매핑** 탭을 선택한 다음 왼쪽의 형식 트리 창에서 **확장/축소** 를 선택합니다.
6. 모든 셀 형식 요소는 적절한 데이터 소스에 바인딩됩니다.

    ![ER Operations Designer의 데이터 소스에 셀 형식 요소 바인딩.](./media/er-barcode-data-source-cells-bound.png)

7. 페이지 오른쪽에 있는 **형식** 탭을 선택합니다.
8. 작업 창에서 줄임표(**...**)를 선택한 다음 **가져오기** 를 선택합니다.
9. **가져오기** 그룹에서 **Excel에서 업데이트** 를 선택한 다음 **템플릿 업데이트** 를 선택합니다.
10. 대화 상자에서 컴퓨터에 저장된 **Check template Excel.xlsx** 파일을 찾아 선택한 다음 **확인** 을 선택하여 선택한 템플릿을 적용해야 하는지 확인합니다.
11. 페이지 오른쪽의 **매핑** 탭을 선택한 후 왼쪽의 서식 트리 창에서 **확장/축소** 를 선택합니다.
12. **AmountBarcode** 셀 요소가 형식에 추가되었습니다. 이 요소는 수정된 Excel 템플릿에 바코드 이미지의 자리 표시자로 추가된 **AmountBarcode** 요소와 연결됩니다.

    ![ER 작업 디자이너의 형식에 추가된 AmountBarcode 셀 요소입니다.](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>새 바코드 데이터 소스 추가

다음으로 **바코드** 유형의 새 데이터 소스를 추가해야 합니다.

1. ER 작업 디자이너의 페이지 오른쪽에 있는 **매핑** 탭에서 **인쇄** 데이터 소스를 선택합니다.
2. **추가** 를 선택한 다음, **함수** 그룹에서 **바코드** 데이터 원본 유형을 선택합니다.

    ![바코드 데이터 소스 유형 선택.](./media/er-barcode-data-source-add.png)

3. 대화 상자의 **이름** 필드에 **바코드** 를 입력합니다.
4. **바코드 형식** 에서 **코드 128** 을 선택합니다.
5. **너비** 필드에 **500** 을 입력합니다.
6. **확인** 을 선택합니다.

    ![데이터 소스 속성 대화 상자.](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>새 형식 요소 바인딩

다음으로, 방금 추가한 데이터 소스에 새 형식 요소를 바인딩해야 합니다.

1. ER 작업 디자이너의 페이지 오른쪽에 있는 **매핑** 탭에서 **인\\쇄** 데이터 소스를 선택합니다.
2. 왼쪽의 형식 트리 창에서 **AmountBarcode** 셀 요소를 선택한 다음 **바인딩** 을 선택합니다.
3. 작업 창에서 **수량 조정** 을 선택합니다.
4. **Barcode** 데이터 소스는 단일 매개 변수를 포함하는 함수로 바인딩에 표시되기 때문에 바인딩된 형식 요소의 이름은 자동으로 해당 매개 변수의 인수로 사용됩니다.

    ![ER Operations Designer의 바코드 데이터 소스에 대한 세부 정보입니다.](./media/er-barcode-data-source-bind1.png)

5. **수식 편집** 을 선택하여 바인딩을 조정합니다.

    셀 요소의 이름이 반환되는 것을 원하지 않습니다. 따라서 현재 수표의 지급 금액이 포함된 텍스트를 반환하는 표현식을 구성해야 합니다. 상위 **ChequeLines** 범위는 **model.cheques** 데이터 소스에 바인딩되기 때문에 현재 수표의 지급 가능한 금액은 **실제** 데이터 유형의 **model.cheques.attributes.amount** 필드에서 사용할 수 있습니다.

6. **수식** 필드에 **print.barcode(NUMBERFORMAT(@.attributes.amount, 'F2'))** 를 입력합니다.
7. **저장** 을 선택한 다음 [ER 수식 디자이너](general-electronic-reporting-formula-designer.md)를 닫습니다.
8. 바인딩이 조정되었음을 알 수 있습니다.

    ![ER Operations 디자이너에서 바인딩이 조정되었습니다.](./media/er-barcode-data-source-bind2.png)

9. **저장** 을 선택한 다음 ER 작업 디자이너를 닫습니다.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>수정된 버전을 테스트 실행에 사용할 수 있도록 설정

기본적으로 상태가 **완료됨** 및 **공유** 인 버전만 ER 형식을 실행할 때 사용됩니다.

변경 사항을 완료했다면 현재 초안 버전으로 작업을 완료하고 변경 사항을 사용할 수 있도록 할 수 있습니다. 지침은 다음에 나오는 [수정된 형식 버전 완료](#CompleteToRun) 섹션을 참조하십시오.

현재 초안 버전으로 계속 작업하고 싶지만 이를 사용하여 수표를 생성해야 하는 경우 실행을 위해 형식의 초안 버전을 사용하도록 명시적으로 지정해야 합니다. 지침은 [초안 버전을 사용할 수 있도록 설정](#MarkToRun) 섹션을 참조하십시오.

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>수정된 형식 버전 완성

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 을 선택합니다.
3. **구성** 페이지의 구성 트리에서 **수표 모델** 을 확장하고 **수표 인쇄 형식** 을 선택합니다.
4. **버전** FastTab에서 상태가 **초안** 인 기록을 선택합니다.
5. **상태 변경** 을 선택한 다음 **완료** 를 선택합니다.
6. 대화 상자에서 **확인** 을 선택합니다.

현재 버전의 상태가 **초안** 에서 **완료** 로 변경되고 **초안** 상태의 새 버전이 생성됩니다. 이 새 초안 버전을 사용하여 추가 변경 사항을 적용할 수 있습니다.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>사용 가능한 초안 버전 만들기

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 을 선택합니다.
3. **구성** 페이지의 작업 창에 있는 **구성** 탭에 있는 **고급 설정** 그룹에서 **사용자 매개 변수** 를 선택합니다.
4. 대화 상자에서 **실행 설정** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
5. 구성 트리에서 **수표 모델** 을 확장하고 **수표 인쇄 형식** 을 선택합니다.
6. **초안 실행** 옵션을 **예** 로 설정합니다.
7. **저장** 을 선택합니다.

선택한 형식의 초안 버전은 선택한 형식이 실행될 때 사용할 수 있는 것으로 표시됩니다.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>지급 수표 생성

1. **현금 및 은행 관리** \>로 이동합니다. **은행 계좌** \> **은행 계좌**.
2. **은행 계좌** 페이지에서 **USMF OPER** 계좌를 선택합니다.
3. 판매 주문 세부 정보 페이지의 작업 창에 있는 **판매 주문** 탭에 있는 **유지 보수** 그룹에서 **취소** 를 선택합니다.
4. **레이아웃 확인** 페이지의 작업 창에서 **테스트 인쇄** 를 선택합니다.
5. 대화 상자에서 **협상 가능한 수표** 형식 옵션을 **예** 로 설정합니다.
6. **확인** 을 선택합니다.
7. 생성된 수표를 검토합니다. 수표의 지급 가능한 금액을 인코딩하기 위해 바코드가 생성되었음을 알 수 있습니다.

    ![Excel에서 바코드로 결제 수표를 생성했습니다.](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> **바코드** 데이터 소스의 인수가 바코드 형식과 관련된 적절한 요구 사항을 준수하지 않는 경우 예외가 발생합니다. 예를 들어, 제공된 텍스트에 대한 [EAN-8](https://wikipedia.org/wiki/EAN-8) **바코드** 를 생성하기 위해 Barcode 데이터 소스가 호출될 때 텍스트 길이가 7자를 초과하면 예외가 발생합니다.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>생성된 수표를 PDF로 변환

인쇄 가능한 [FTI 양식 생성](er-generate-printable-fti-forms.md#finland) 항목에 설명된 대로 특수 글꼴을 사용하여 생성된 문서에 바코드를 생성할 수 있습니다. 이 경우 생성된 문서의 추가 변환은 변환 환경에서 해당 글꼴의 가용성에 따라 달라질 수 있습니다. 예를 들어 문서를 PDF 형식으로 변환하거나 글꼴이 없는 환경에서 미리 볼 경우 바코드가 올바르게 렌더링되지 않습니다.

그러나 **바코드** 데이터 소스를 사용하여 바코드를 생성하는 경우 해당 바코드의 렌더링은 글꼴에 의존하지 않습니다. 따라서 바코드가 포함된 문서를 PDF 형식으로 쉽게 변환할 수 있습니다. 다음 그림은 구성된 ER [대상](electronic-reporting-destinations.md) 설정에 따라 PDF로 [변환](electronic-reporting-destinations.md#OutputConversionToPDF)된 생성된 지급 수표의 미리보기를 보여줍니다.

![지급 수표의 PDF 미리보기.](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>한계

> [!NOTE]
> 생성되는 일부 유형의 바코드에는 고정된 종횡비가 있습니다. 이 동작은 전자 보고 프레임워크에서 **EPPlus 라이브러리 사용 활성화** 기능을 켜서 ER에서 Excel 문서로 작업한 경우 의미가 있습니다. 이 경우 가로 세로 비율이 잠긴 자리 표시자에 이미지가 입력됩니다. 따라서 템플릿의 자리 표시자의 크기가 입력된 이미지의 비율과 일치하는 경우 생성된 문서의 실제 그림은 필요한 가로 세로 비율을 유지하기 위해 크기가 조정될 수 있습니다. 그림 크기 조정을 방지하려면 예상 가로 세로 비율이 있는 자리 표시자를 사용하십시오.

## <a name="additional-resources"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [전자 보고 대상](electronic-reporting-destinations.md)
- [전자 보고 공식 언어](er-formula-language.md)
- [NUMBERFORMAT 함수](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
