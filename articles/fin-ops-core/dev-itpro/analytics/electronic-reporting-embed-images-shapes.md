---
title: ER을 사용하여 생성한 문서에 이미지 및 모양 포함
description: 이번에는 전자 보고 도구를 사용하여 이미지와 모양이 포함된 비즈니스 문서를 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 550ecca31af48e624e292b342d909abd6eb3e87af122f736eb388524b42f1e05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460760"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>ER을 사용하여 생성한 문서에 이미지 및 모양 포함

[!include [banner](../includes/banner.md)]

전자 보고(ER) 도구를 사용하여 필요한 전자 문서를 생성하기 위해 실행할 수 있는 보고서를 디자인할 수 있습니다. Microsoft Excel 또는 Microsoft Word 문서를 사용하여 보고서의 레이아웃을 지정할 수 있습니다. ER Operations Designer를 사용하면 Excel 또는 Word 문서를 보고서 템플릿으로 첨부할 수 있습니다. 첨부된 템플릿의 명명된 요소는 ER 보고서의 형식 요소와 연결됩니다. 보고서의 형식 요소는 데이터 소스에 바인딩됩니다. 이러한 요소는 생성되는 문서에 런타임에 입력할 데이터를 지정합니다.

이 새로운 함수은 Microsoft Office 형식으로 문서를 생성하기 위한 기존 ER 함수를 능가합니다. 자세한 내용은 다음 작업 가이드를 재생하십시오. 이 작업 가이드는 7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677) 비즈니스 프로세스에서 찾을 수 있습니다.

- ER OPENXML 형식의 보고서 생성을 위한 구성 설계
- ER Microsoft WORD 형식의 보고서 생성을 위한 구성 설계

## <a name="embed-an-image-in-an-excel-document"></a>Excel 문서에 이미지 포함

### <a name="embed-an-image-in-an-excel-worksheet"></a>Excel 워크시트에 이미지 포함

먼저 Excel 문서에서 이미지에 대한 자리 표시자를 추가해야 합니다. Excel 통합 문서를 열고 나중에 추가할 이미지의 자리 표시자로 그림을 추가합니다. 이후 ER 도구를 사용하여 디자인 중인 보고서를 포함할 새 ER 형식 구성을 추가합니다. 엑셀 워크북을 보고서 형식에 대한 템플릿으로 첨부한 후 워크북의 내용을 ER 형식으로 가져옵니다. 형식 정의가 자동으로 생성됩니다. 추가한 이미지 자리 표시자는 ER 형식 정의에 **CELL** 요소로 포함됩니다.

> [!NOTE]
> 형식 정의를 가져오는 대신 수동으로 지정할 수 있습니다. 변경 사항을 저장하면 형식이 확인됩니다.

다음으로 ER 형식의 **CELL** 요소를 런타임에 이진 형식으로 그림 데이터를 제공하는 형식 데이터 소스의 필드에 바인딩합니다. ER 데이터 모델이 형식의 데이터 소스로 사용되는 경우 필드의 데이터 유형은 [컨테이너](er-formula-supported-data-types-composite.md#container)여야 합니다. 현재 [컨테이너](er-formula-supported-data-types-composite.md#container) 데이터 유형이 있는 ER 데이터 모델 필드는 이미지를 바이너리 형식으로 반환하는 여러 유형의 데이터 소스에 바인딩될 수 있습니다. 문서 관리 프레임워크를 사용하여 데이터 테이블의 필드와 데이터 테이블의 기록에 첨부된 파일에 액세스할 수 있습니다.

> [!IMPORTANT]
> - Excel 템플릿을 사용하여 만들고 있는 문서의 이미지 자리 표시자를 채우려면 ER 형식에 Excel 템플릿의 명명된 그림 요소를 참조하는 **CELL** 요소가 포함되어야 합니다. 그렇지 않으면 보고서 출력에 이미지 자리 표시자가 나타나지 않습니다. **CELL** 요소의 바인딩이 런타임에 데이터를 반환하지 않으면 생성되는 문서에 템플릿의 이미지 자리 표시자가 표시됩니다. 생성 중인 문서에서 이미지를 숨기려면 **CELL** 요소를 정의하고 **활성화** 표현식이 **FALSE** 값을 반환하도록 지정합니다.
> - Excel 템플릿에서 모든 요소에 고유한 이름을 사용합니다. 이러한 요소에는 그림과 셀이 포함됩니다. 요소 이름을 복제하면 생성되는 보고서의 내용이 모호하고 혼란스러워집니다.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Excel 워크시트의 머리글과 바닥글에 이미지 포함

Excel 통합 문서 문서를 템플릿으로 사용하여 보고서 레이아웃을 지정합니다. 통합 문서에는 여러 워크시트가 포함될 수 있으며 각 워크시트에는 머리글과 바닥글이 있도록 디자인할 수 있습니다. Excel은 모든 워크시트의 머리글과 바닥글에서 최대 3개의 이미지를 지원합니다. 이미지를 왼쪽, 오른쪽 또는 중앙으로 정렬할 수 있습니다.

Finance 릴리스 10.0.21에서는 Excel 템플릿이 있는 ER 솔루션에서 생성된 머리글 및 바닥글 이미지를 관리할 수 있습니다.

생성된 문서의 머리글이나 바닥글에 기본 그림을 표시하려면 ER 템플릿 워크시트의 머리글이나 바닥글에 이미지를 추가할 수 있습니다. ER 형식의 이 이미지에 액세스하려면 형식의 [머리글](er-fillable-excel.md#header-component) 또는 [바닥글](er-fillable-excel.md#footer-component) 구성 요소 아래에 **그림** 구성 요소를 추가해야 합니다. **그림** 구성 요소의 맞춤을 적절하게 구성합니다. 

템플릿에 기본 이미지가 없는 경우에도 **Picture** 구성 요소를 사용하여 런타임에 생성된 문서의 머리글이나 바닥글에 이미지를 넣을 수도 있습니다. 생성된 문서의 머리글이나 바닥글에 새 이미지 또는 기본 이미지의 대체물로 넣어야 하는 미디어 콘텐츠를 지정하려면 이미지를 바이너리로 나타내는 [컨테이너](er-formula-supported-data-types-composite.md#container) 유형의 데이터 소스에 **Picture** 구성 요소를 바인딩해야 합니다. 체재.

모든 **머리글** 또는 **바닥글** 구성 요소는 지원되는 각 정렬에 대해 하나의 **그림** 구성 요소를 보유할 수 있습니다. **왼쪽**, **가운데**, **오른쪽입니다**.

**Picture** 구성 요소의 **Scale height** 속성을 사용하면 구성된 바인딩을 사용하여 이미지 크기를 제어할 수 있습니다.

- 이미지의 초기 크기를 유지하려면 **원본** 을 선택합니다.
- 해당 이미지를 포함하는 머리글 또는 바닥글의 높이에 비례하여 이미지의 높이를 조정하려면 **상대** 를 선택합니다.

    - 이 경우 이미지의 높이는 상위 머리글 또는 바닥글의 백분율로 정의되어야 합니다.
    - 배율 값이 100%를 초과하면 이미지가 해당 워크시트의 데이터 영역과 겹칠 수 있습니다.
    - 스케일링 적용 시 이미지의 높이가 변경되면 이미지의 원래 종횡비를 유지하기 위해 너비도 변경됩니다.

- 디자인 타임에 제공된 높이 및 너비 값(픽셀 단위)에 따라 이미지 크기를 조정하려면 **절대** 를 선택합니다.

    - 지정된 높이가 상위 머리글 또는 바닥글의 높이를 초과하는 경우 이미지가 해당 워크시트의 데이터 영역과 겹칠 수 있습니다.

**Picture** 구성 요소의 **Enabled** 속성을 사용하여 이 구성 요소를 사용하여 생성된 문서에 삽입되는 이미지의 가시성을 제어할 수도 있습니다.

> [!NOTE]
> 편집 가능한 ER 형식에 **그림** 구성 요소를 추가하려면 ER 형식 디자이너를 사용해야 합니다. [비즈니스 문서 관리](er-business-document-management.md) 작업 영역을 사용하여 비즈니스 문서의 템플릿을 편집하는 경우 구성 요소를 추가할 수 없습니다.

이 함수에 대해 자세히 알아보려면 ER 형식 디자인의 단계에 따라 [페이지 머리글 또는 바닥글에 이미지가 포함된 Excel 형식의 보고서를 생성](er-embed-images-header-footer-excel-reports.md)하십시오.

## <a name="embed-a-shape-in-an-excel-document"></a>Excel 문서에 도형 포함

먼저 Excel 문서에서 도형에 대한 자리 표시자를 추가해야 합니다. Excel 통합 문서를 열고 **도형**, **텍스트 상자** 또는 **WordArt** 를 도형의 자리 표시자로 선택합니다. 이후 ER 도구를 사용하여 디자인 중인 보고서를 포함할 새 ER 형식 구성을 추가합니다. 엑셀 워크북을 보고서 형식에 대한 템플릿으로 첨부한 후 워크북의 내용을 ER 형식으로 가져옵니다. 형식 정의가 자동으로 생성됩니다. 추가한 모양 자리 표시자는 명명된 Excel 모양 요소를 참조하는 **CELL** 요소로 ER 형식 정의에 포함됩니다.

> [!NOTE]
> 형식 정의를 가져오는 대신 수동으로 지정할 수 있습니다. 변경 사항을 저장하면 형식이 확인됩니다.

이후 런타임에 데이터를 제공하는 형식의 데이터 소스에서 필드에 ER 형식의 **CELL** 요소를 바인딩합니다. 이 데이터는 텍스트 스트링으로 변환될 수 있습니다. ER 형식의 **CELL** 요소가 텍스트를 지원하는 Excel 템플릿의 모양 요소를 참조하는 경우 런타임에 이 바인딩을 통해 제공되는 텍스트가 생성되는 문서의 모양으로 표시됩니다.

> [!IMPORTANT]
> - 모양 자리 표시자가 포함된 Excel 템플릿을 사용하여 새 문서를 생성하려면 ER 형식에 Excel 모양 요소를 참조하는 **CELL** 요소가 포함되어야 합니다. 그렇지 않으면 보고서 출력에 모양 자리 표시자가 나타나지 않습니다. 명명된 Excel 모양 요소를 참조하는 **CELL** 요소의 바인딩이 런타임에 데이터를 반환하지 않으면 생성되는 문서에 Excel 템플릿의 모양 자리 표시자의 텍스트가 표시됩니다. 생성 중인 문서에서 모양을 숨기려면 명명된 Excel 모양 요소를 참조하는 **CELL** 요소를 정의하고 **활성화** 표현식이 **FALSE** 값을 반환하도록 지정합니다.
> - Excel 템플릿에서 모든 요소에 고유한 이름을 사용합니다. 이러한 요소에는 모양과 셀이 포함됩니다. 요소 이름을 복제하면 생성되는 보고서의 내용이 모호하고 혼란스러워집니다.

## <a name="embed-an-image-in-a-word-document"></a>Word 문서에 이미지 포함
> [!IMPORTANT]
> Excel 템플릿을 사용하는 ER 형식을 재사용하여 포함된 이미지가 포함된 문서를 생성할 수 있습니다. ER 형식에서 Excel의 명명된 그림 요소를 참조하고 런타임에 그림을 반환하는 데이터 소스에 바인딩된 **CELL** 요소에 이름이 지정되었는지 확인하십시오.

먼저 Word 문서의 레이아웃을 구성해야 합니다. **그림 콘텐츠** 컨트롤을 사용하여 포함된 이미지에 대한 자리 표시자를 만듭니다. 이 컨트롤에 액세스하려면 먼저 Word 리본에 **개발** 도구 탭을 표시해야 합니다.

이후 ER 형식에서 Excel 템플릿을 삭제하고 Word 템플릿 문서를 첨부합니다. 템플릿에 대한 참조를 업데이트하고 변경 사항을 저장합니다. 현재 ER 형식의 구조는 **보고서** 라는 새 사용자 지정 XML 부분으로 Word 템플릿에 저장됩니다.

이후 현재 ER 형식에 대한 Word 템플릿을 로컬 컴퓨터에 저장합니다. 템플릿을 열고 **XML 매핑** 창을 엽니다. **보고서** 라는 사용자 지정 XML 부분을 찾은 다음 이진 형식으로 이미지를 반환하는 데이터 원본에 바인딩된 ER 보고서의 **CELL** 요소를 가리킵니다. 이 XML 부분의 항목을 선택한 **그림 콘텐츠** 컨트롤에 매핑하고 변경 사항을 저장합니다.

[![이미지를 삽입합니다.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

마지막으로 ER 형식에서 Word 템플릿을 삭제하고 매핑된 사용자 지정 XML 부분이 포함된 Word 문서를 첨부합니다. 템플릿에 대한 형식 참조를 업데이트하고 이 ER 형식에 대한 변경 사항을 저장합니다.

## <a name="more-information"></a>추가 정보
이 기능의 세부 사항에 익숙해지려면 작업 가이드 세트를 재생하십시오. **ER은 이미지가 포함된 MS Office 형식으로 보고서를 만듭니다**. 이 작업 가이드는 Excel 및 Word 문서에서 ER 도구를 사용하여 생성된 지급 수표에 회사 로고 및 승인된 사람의 서명 이미지를 포함하는 방법을 보여줍니다.

다음 표에는 포함된 이미지 작업 가이드가 포함된 **MS Office 형식의 ER Make 보고서를 완료하는 데 필요한 파일** 이 나열되어 있습니다. 파일을 다운로드하여 로컬 컴퓨터에 저장합니다.

| 설명                                          | 파일 이름                   |
|------------------------------------------------------|-----------------------------|
| ER 데이터 모델 구성                          | [cheques.xml용 모델](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER 형식 구성                              | [format.xml 인쇄 확인](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| 회사 로고 이미지                                   | [회사 로고.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| 서명 이미지                                      | [서명 이미지.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| 대체 서명 이미지                          | [서명 이미지 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Microsoft Word 지급 수표 인쇄용 템플릿  | [템플릿 Word.docx 확인](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Microsoft Excel 지급 수표 인쇄용 템플릿 | [template.xlsx 확인](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

다음 그래픽은 Excel 템플릿에서 생성된 지급 수표에 대한 테스트 인쇄물의 예를 제공합니다.

[![결제 확인 테스트 출력.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
