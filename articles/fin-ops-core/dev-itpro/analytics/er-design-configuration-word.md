---
title: Word 형식으로 보고서를 생성하기 위한 새로운 ER 구성 설계
description: 이번에는 보고서를 Microsoft Word 문서로 생성하기 위해 사용자가 새로운 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 12/17/2020
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
ms.openlocfilehash: 27e9e977193f9ff5c8188b780e8de955742c4ebe
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461007"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Word 형식으로 보고서를 생성하기 위한 새로운 ER 구성 설계

[!include [banner](../includes/banner.md)]

보고서를 Microsoft Word 문서로 생성하려면 예를 들어 Word 데스크톱 애플리케이션을 사용하여 보고서 템플릿을 디자인해야 합니다. 다음 그림은 처리된 공급 업체 지급에 대한 세부 정보를 표시하기 위해 생성할 수 있는 제어 보고서의 샘플 템플릿을 보여줍니다.

![Word 데스크톱 애플리케이션의 제어 보고서에 대한 샘플 템플릿입니다.](./media/er-design-configuration-word-image1.png)

Word 문서를 Word 형식의 보고서에 대한 템플릿으로 사용하기 위해 새로운 [전자 보고(ER)](general-electronic-reporting.md) [솔루션](er-quick-start1-new-solution.md)을 구성할 수 있습니다. 이 솔루션에는 ER 형식 구성 요소가 포함된 ER [구성](general-electronic-reporting.md#Configuration)이 포함되어야 합니다.

> [!NOTE]
> **Word** 형식의 보고서를 생성하기 위해 새 ER 형식 구성을 만들 때 **구성 만들기** 드롭다운 대화 상자에서 형식 유형으로 Word를 선택하거나 **형식 유형** 필드를 비워 두어야 합니다.

![구성 페이지에서 형식 구성을 생성합니다.](./media/er-design-configuration-word-image2.gif)

솔루션의 ER 형식 구성 요소에는 **Excel\\File** 형식 요소가 포함되어야 하며 해당 형식 요소는 런타임 시 생성된 보고서의 템플릿으로 사용될 Word 문서에 연결되어야 합니다. ER 형식 구성 요소를 구성하려면 ER 형식 디자이너에서 생성된 ER 구성의 [초안](general-electronic-reporting.md#component-versioning) 버전을 열어야 합니다. 이후 **Excel\\File** 요소를 추가하고 Word 템플릿을 편집 가능한 ER 형식에 첨부하고 해당 템플릿을 추가한 **Excel\\File** 요소에 연결합니다.

> [!NOTE]
> 템플릿을 첨부할 때 ER 형식의 템플릿을 저장하려면 ER 매개 변수에서 이전에 [구성된](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) [문서 유형](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)을 사용해야 합니다.

![서식 디자이너 페이지에서 템플릿을 첨부합니다.](./media/er-design-configuration-word-image3.gif)

**Excel\\File** 요소에 대해 **Excel\\Range** 및 **Excel\\Cell** 중첩 요소를 추가하여 런타임에 생성된 보고서에 입력할 데이터 구조를 지정할 수 있습니다. 이후 런타임에 생성된 보고서에 입력할 실제 데이터를 지정하려면 해당 요소를 편집 가능한 ER 형식의 데이터 소스에 바인딩해야 합니다.

![형식 디자이너 페이지에서 중첩 요소 추가](./media/er-design-configuration-word-image4.gif)

디자인 타임에 ER 형식에 대한 변경 사항을 저장하면 계층적 형식 구조가 **보고서** 라는 [사용자 지정 XML 부분](/visualstudio/vsto/custom-xml-parts-overview)으로 첨부된 Word 템플릿에 저장됩니다. 수정된 템플릿에 액세스하고 Finance에서 다운로드하여 로컬에 저장하고 Word 데스크톱 애플리케이션에서 열어야 합니다. 다음 그림은 **보고서** 사용자 지정 XML 부분이 포함된 제어 보고서에 대해 로컬로 저장된 샘플 템플릿을 보여줍니다.

![Word 데스크톱 애플리케이션에서 샘플 보고서 템플릿을 미리 봅니다.](./media/er-design-configuration-word-image5.gif)

**Excel\\Range** 및 **Excel\\Cell** 형식 요소의 바인딩이 런타임에 실행될 때 모든 바인딩이 전달하는 데이터는 **보고서** 사용자 지정 XML 부분의 개별 필드로 생성된 Word 문서에 들어옵니다. 생성된 문서에서 사용자 지정 XML 부분의 필드 값을 입력하려면 런타임에 채워질 데이터에 대한 자리 표시자로 사용할 적절한 Word [콘텐츠 컨트롤](/office/client-developer/word/content-controls-in-word)을 Word 템플릿에 추가해야 합니다. 콘텐츠 컨트롤을 채우는 방법을 지정하려면 모든 콘텐츠 컨트롤을 **보고서** 사용자 지정 XML 부분의 해당 필드에 매핑합니다.

![Word 데스크톱 애플리케이션에서 콘텐츠 컨트롤 추가 및 매핑.](./media/er-design-configuration-word-image6.gif)

이후 편집 가능한 ER 형식의 원래 Word 템플릿을 **보고서** 사용자 지정 XML 부분의 필드에 매핑된 Word 콘텐츠 컨트롤이 포함된 수정된 템플릿으로 바꿔야 합니다.

![서식 디자이너 페이지에서 템플릿 바꾸기.](./media/er-design-configuration-word-image7.gif)

구성된 ER 형식을 실행할 때 첨부된 Word 템플릿을 사용하여 새 보고서를 생성합니다. 실제 데이터는 **보고서** 라는 사용자 지정 XML 부분으로 Word 보고서에 저장됩니다. 생성된 보고서가 열리면 Word 콘텐츠 컨트롤이 **보고서** 사용자 지정 XML 부분의 데이터로 채워집니다.

## <a name="frequently-asked-questions"></a>자주 하는 질문

**질문:** 회사 주소가 포함된 Word 문서를 인쇄하도록 ER 형식을 구성했습니다. 이 ER 형식의 Word 템플릿에서 회사 주소를 표시하기 위해 서식 있는 텍스트 콘텐츠 컨트롤을 삽입했습니다. 재무에서 회사 주소를 여러 줄 텍스트로 입력하고 **Enter** 를 선택하여 입력한 모든 줄에 캐리지 리턴을 추가했습니다. 따라서 회사 주소가 생성된 문서에서 여러 줄 텍스트로 나타날 것으로 예상합니다. 그러나 주소는 캐리지 리턴 대신 특수 기호가 포함된 한 줄의 텍스트로 나타납니다. 내 설정에 어떤 문제가 있습니까?

**답변:** 서식 있는 텍스트 콘텐츠 컨트롤을 사용하는 대신 일반 텍스트 콘텐츠 컨트롤을 사용하고 컨트롤 속성에서 **캐리지 리턴(여러 단락) 허용** 확인란을 선택해야 합니다.

## <a name="additional-resources"></a>추가 리소스

- [Excel 템플릿과 함께 ER 구성을 재사용하여 Word 형식으로 보고서 생성](./tasks/er-design-configuration-word-2016-11.md)
- [ER을 사용하여 생성한 문서에 이미지 및 모양 포함](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
