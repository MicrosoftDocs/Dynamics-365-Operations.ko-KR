---
title: Excel 형식의 문서 생성을 위한 구성 설계
description: 이번에는 Excel 템플릿을 채우도록 전자 보고(ER) 형식을 디자인한 다음 아웃바운드 Excel 형식 문서를 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b2f38aa9e5eff9366697afd57ceefd06f026096
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8460945"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Excel 형식의 문서 생성을 위한 구성 설계

[!include[banner](../includes/banner.md)]

Microsoft Excel 통합 문서 형식으로 아웃바운드 문서를 생성하도록 구성할 수 있는 ER 형식 구성 요소가 있는 [전자 보고(ER)](general-electronic-reporting.md) 형식 구성을 디자인할 수 있습니다. 이를 위해 특정 ER 형식 구성 요소를 사용해야 합니다.

이 기능에 대해 자세히 알아보려면 [OPENXML 형식으로 보고서를 생성하기 위한 구성 디자인](tasks/er-design-reports-openxml-2016-11.md) 항목의 단계를 따르십시오.

## <a name="add-a-new-er-format"></a>새 ER 형식 추가

**Excel** 통합 문서 형식으로 아웃바운드 문서를 생성하기 위해 새 ER 형식 구성을 추가하는 경우 형식의 **형식 유형** 속성에 대해 Excel 값을 선택하거나 **형식 유형** 속성을 비워 두어야 합니다.

- **Excel** 을 선택하면 Excel 형식으로만 아웃바운드 문서를 생성하도록 형식을 구성할 수 있습니다.
- 속성을 비워 두면 ER 프레임워크에서 지원하는 모든 형식으로 아웃바운드 문서를 생성하도록 형식을 구성할 수 있습니다.

구성의 ER 형식 구성 요소를 구성하려면 작업 창에서 **디자이너** 를 선택하고 ER 작업 디자이너에서 편집할 ER 형식 구성 요소를 엽니다.

![구성 페이지.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>엑셀 파일 컴포넌트

### <a name="manual-entry"></a>수동 입력

Excel 형식의 아웃바운드 문서를 생성하려면 구성된 ER 형식에 **Excel\\File** 구성 요소를 추가해야 합니다.

![Excel\파일 구성 요소.](./media/er-excel-format-add-file-component.png)

아웃바운드 문서의 레이아웃을 지정하려면 .xlsx 확장자가 있는 Excel 통합 문서를 아웃바운드 문서의 템플릿으로 **Excel\\File** 구성 요소에 첨부합니다.

> [!NOTE]
> 템플릿을 수동으로 첨부할 때 [ER 매개 변수](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)에서 해당 용도로 구성된 [문서 유형](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types)을 사용해야 합니다.

![Excel\File 구성 요소에 첨부 파일을 추가합니다.](./media/er-excel-format-add-file-component2.png)

구성된 ER 형식을 실행할 때 첨부된 템플릿을 채우는 방법을 지정하려면 중첩된 **시트**, **범위** 및 **셀** 구성 요소를 **Excel\\File** 구성 요소에 추가해야 합니다. 각 중첩 구성 요소는 Excel 명명된 항목과 연결되어야 합니다.

### <a name="template-import"></a>템플릿 가져오기

작업 창의 **가져오기** 탭에서 **Excel에서 가져오기** 를 선택하여 새 템플릿을 빈 ER 형식으로 가져올 수 있습니다. 이 예시에서는 **Excel\\File** 구성 요소가 자동으로 생성되고 가져온 템플릿이 여기에 첨부됩니다. 모든 필수 ER 구성 요소는 검색된 Excel 명명 항목 목록을 기반으로 자동으로 생성됩니다.

![Excel에서 가져오기를 선택합니다.](./media/er-excel-format-import-template.png)

> [!NOTE]
> 편집 가능한 ER 형식으로 선택적 **시트** 요소를 생성하려면 **Excel 시트 형식 요소 생성** 옵션을 **예** 로 설정합니다.

## <a name="sheet-component"></a>시트 구성 요소

**시트** 구성 요소는 채워야 하는 첨부된 Excel 통합 문서의 워크시트를 나타냅니다. Excel 템플릿의 워크시트 이름은 이 구성 요소의 **Sheet** 속성에 정의됩니다.

> [!NOTE]
> 이 구성 요소는 단일 워크시트가 포함된 Excel 통합 문서의 경우 선택 사항입니다.

ER 작업 디자이너의 **매핑** 탭에서 **시트** 구성 요소에 대한 **사용** 속성을 구성하여 구성 요소를 생성된 문서에 넣어야 하는지 여부를 지정할 수 있습니다.

- **Enabled** 속성의 식이 런타임에 **True** 를 반환하도록 구성된 경우 또는 식이 전혀 구성되지 않은 경우 적절한 워크시트가 생성된 문서에 배치됩니다.
- **Enabled** 속성의 식이 런타임에 **False** 를 반환하도록 구성된 경우 생성된 문서에는 워크시트가 포함되지 않습니다.

![시트 구성 요소의 예.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>범위 구성 요소

### <a name="nested-components"></a>내포된 구성 요소

#### <a name="data-typing"></a>데이터 유형,

**범위** 구성 요소에는 적절한 범위에 값을 입력하는 데 사용되는 다른 중첩된 ER 구성 요소가 있을 수 있습니다.

- **텍스트** 그룹의 구성 요소가 값을 입력하는 데 사용되는 경우 값은 Excel 범위에 텍스트 값으로 입력됩니다.

    > [!NOTE]
    > 이 패턴을 사용하여 애플리케이션에 정의된 로케일을 기반으로 입력된 값의 형식을 지정하십시오.

- **Excel** 그룹의 **셀** 구성 요소를 사용하여 값을 입력하는 경우 값은 해당 **셀** 구성 요소의 바인딩에 의해 정의된 데이터 유형의 값으로 Excel 범위에 입력됩니다. 예를 들어 데이터 유형은 **스트링**, **실수** 또는 **정수** 일 수 있습니다.

    > [!NOTE]
    > 이 패턴을 사용하여 Excel 애플리케이션이 아웃바운드 문서를 여는 로컬 컴퓨터의 로캘을 기반으로 입력한 값의 형식을 지정할 수 있도록 합니다.

#### <a name="row-handling"></a>행 처리

**Range** 구성 요소는 Excel 워크시트에 여러 행이 생성되도록 수직 복제로 구성할 수 있습니다. 행은 상위 **Range** 구성 요소 또는 중첩된 **Range** 구성 요소에서 생성할 수 있습니다.

버전 10.0.26 이상에서는 생성된 워크시트가 동일한 페이지에 생성된 행을 유지하도록 강제할 수 있습니다. ER 형식 디자이너에서 편집 가능한 ER 형식의 상위 **범위** 구성 요소에 대해 **행을 함께 유지** 옵션을 **예** 로 설정합니다. 이후 ER은 해당 범위에서 생성된 모든 콘텐츠를 동일한 페이지에 유지하려고 시도합니다. 콘텐츠의 높이가 현재 페이지의 남은 공간을 초과하는 경우 페이지 나누기가 추가되고 콘텐츠는 다음 새 페이지의 상단에서 시작됩니다.

> [!NOTE]
> 생성된 문서의 전체 너비에 걸쳐 있는 범위에 대해서만 **행을 함께 유지** 옵션을 구성하는 것이 좋습니다.
>
> **행을 함께 유지** 옵션은 Excel 통합 문서 템플릿을 사용하도록 구성된 **Excel \> 파일** 구성 요소에만 적용할 수 있습니다.
>
> **행을 함께 유지** 옵션은 전자 보고 프레임워크에서 **EPPlus 라이브러리 사용 활성화** 기능이 활성화된 경우에만 사용할 수 있습니다.
>
> 이 기능은 **페이지** 구성 요소 아래에 있는 **범위** 구성 요소에 사용할 수 있습니다. 그러나 [데이터 수집](er-data-collection-data-sources.md) 데이터 원본을 사용하여 [페이지 바닥글 합계](er-paginate-excel-reports.md#add-data-sources-to-calculate-page-footer-totals)가 올바르게 계산된다는 보장은 없습니다.

이 옵션을 사용하는 방법을 배우려면 [동일한 Excel 페이지에서 행을 함께 유지하도록 ER 형식 디자인](er-keep-excel-rows-together.md)의 예시 단계를 따르십시오.

### <a name="replication"></a>복제

**복제 방향** 속성은 생성된 문서에서 범위가 반복되는지 여부와 방법을 지정합니다.

- **복제 없음** – 생성된 문서에서 해당 Excel 범위가 반복되지 않습니다.
- **세로** – 생성된 문서에서 해당 Excel 범위가 세로로 반복됩니다. 복제된 각 범위는 Excel 템플릿의 원래 범위 아래에 배치됩니다. 반복 횟수는 이 ER 구성 요소에 바인딩된 **기록 목록** 유형의 데이터 소스에 있는 기록 수로 정의됩니다.
- **가로** – 생성된 문서에서 적절한 Excel 범위가 가로로 반복됩니다. 복제된 각 범위는 Excel 템플릿의 원래 범위 오른쪽에 배치됩니다. 반복 횟수는 이 ER 구성 요소에 바인딩된 **기록 목록** 유형의 데이터 소스에 있는 기록 수로 정의됩니다.

    수평 복제에 대해 자세히 알아보려면 [수평으로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가](tasks/er-horizontal-1.md)의 단계를 따르십시오.

### <a name="enabling"></a>사용

ER 작업 디자이너의 **매핑** 탭에서 **범위** 구성 요소에 대한 **사용** 속성을 구성하여 구성 요소를 생성된 문서에 넣어야 하는지 여부를 지정할 수 있습니다.

- **Enabled** 속성의 식이 런타임에 **True** 를 반환하도록 구성된 경우 또는 식이 전혀 구성되지 않은 경우 생성된 문서에 적절한 범위가 채워집니다.
- **Enabled** 속성의 식이 런타임에 **False** 를 반환하도록 구성된 경우 이 범위가 전체 행이나 열을 나타내지 않으면 생성된 문서에서 적절한 범위가 채워지지 않습니다.
- **Enabled** 속성의 식이 런타임에 **False** 를 반환하도록 구성되어 있고 이 범위가 전체 행이나 열을 나타내는 경우 생성된 문서에는 해당 행과 열이 숨겨진 행과 열로 포함됩니다.

### <a name="resizing"></a>크기 조정

셀을 사용하여 텍스트 데이터를 표시하도록 Excel 템플릿을 구성할 수 있습니다. 셀의 전체 텍스트가 생성된 문서에서 표시되도록 하려면 셀 내부의 텍스트를 자동으로 줄 바꿈하도록 해당 셀을 구성할 수 있습니다. 줄 바꿈된 텍스트가 완전히 표시되지 않는 경우 해당 셀이 포함된 행을 구성하여 높이를 자동으로 조정할 수도 있습니다. 자세한 내용은 [셀에서 잘린 데이터 수정](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e)의 '셀에서 텍스트 줄 바꿈' 섹션을 참조하십시오.

> [!NOTE]
> 알려진 [Excel 제한](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353)으로 인해 텍스트를 줄 바꿈하도록 셀을 구성하고 **줄 바꿈된 텍스트** 에 맞게 높이를 **자동으로 조정** 하도록 해당 셀이 포함된 행을 구성하더라도 자동 맞춤 및 텍스트 줄 바꿈 Excel 기능을 사용하지 못할 수 있습니다. 병합된 셀 및 이를 포함하는 행의 경우. 

Dynamics 365 Finance 버전 10.0.23부터 생성된 문서에서 해당 행에 구성된 병합된 셀이 하나 이상 포함될 때마다 중첩된 셀의 내용에 높이를 자동으로 맞추도록 구성된 모든 행의 높이를 ER이 계산하도록 할 수 있습니다. 그 안에 텍스트를 래핑합니다. 이후 계산된 높이를 사용하여 행의 모든 셀이 생성된 문서에서 표시되도록 행 크기를 조정합니다. Excel 템플릿을 사용하여 아웃바운드 문서를 생성하도록 구성된 ER 형식을 실행할 때 이 함수를 사용하려면 다음 단계를 따르십시오.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.
3. **전자 보고 매개 변수** 페이지의 **런타임** 탭에서 **자동 맞춤 행 높이** 옵션을 **예** 로 설정합니다.

단일 ER 형식에 대해 이 규칙을 변경하려면 다음 단계에 따라 해당 형식의 초안 버전을 업데이트하십시오.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 을 선택합니다.
3. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 Excel 템플릿을 사용하여 아웃바운드 문서를 생성하도록 설계된 ER 구성을 선택합니다.
4. **버전** 빠른 탭에서 상태가 **초안** 인 구성 버전을 선택합니다.
5. 작업 창에서 **디자이너** 를 선택합니다.
6. **형식 디자이너** 페이지의 왼쪽 창에 있는 형식 트리에서 Excel 템플릿에 연결된 Excel 구성 요소를 선택합니다.
7. **형식** 탭의 **행 높이 조정** 필드에서 값을 선택하여 런타임 시 ER이 편집된 ER 형식으로 생성된 아웃바운드 문서의 행 높이를 강제로 변경해야 하는지 여부를 지정합니다.

    - **기본값** – **전자 보고 매개 변수** 페이지의 **자동 맞춤 행 높이** 필드에 구성된 일반 설정을 사용합니다.
    - **예** – 일반 설정을 무시하고 런타임 시 행 높이를 변경합니다.
    - **아니요** – 일반 설정을 무시하고 런타임에 행 높이를 변경하지 마십시오.

## <a name="cell-component"></a>세포 성분

**Cell** 구성 요소는 Excel이라는 이름의 셀, 모양 및 그림을 채우는 데 사용됩니다. **Cell** ER 구성 요소가 채워야 하는 Excel 명명된 개체를 나타내려면 **Cell** 구성 요소의 **Excel 범위** 속성에서 해당 개체의 이름을 지정해야 합니다.

ER 작업 디자이너의 **매핑** 탭에서 생성된 문서에서 개체를 채워야 하는지 여부를 지정하기 위해 **Cell** 구성 요소에 대한 **Enabled** 속성을 구성할 수 있습니다.

- **Enabled** 속성의 표현식이 런타임에 **True** 를 반환하도록 구성된 경우 또는 표현식이 전혀 구성되지 않은 경우 생성된 문서에 적절한 개체가 채워집니다. 이 **Cell** 구성 요소의 바인딩은 적절한 개체에 있는 값을 지정합니다.
- **Enabled** 속성의 식이 런타임에 **False** 를 반환하도록 구성된 경우 적절한 개체가 생성된 문서에 채워지지 않습니다.

**셀** 구성 요소가 셀에 값을 입력하도록 구성된 경우 기본 데이터 유형(예: **스트링**, **실수** 또는 **정수**)의 값을 반환하는 데이터 소스와 바인딩될 수 있습니다. 이 경우 값은 동일한 데이터 유형의 값으로 셀에 입력됩니다.

**셀** 구성 요소가 Excel 셰이프에 값을 입력하도록 구성된 경우 기본 데이터 유형(예: **스트링**, **실수** 또는 **정수**)의 값을 반환하는 데이터 소스와 바인딩할 수 있습니다. 이 경우 값은 해당 도형의 텍스트로 Excel 도형에 입력됩니다. **스트링** 이 아닌 데이터 유형 값의 경우 텍스트로의 변환이 자동으로 수행됩니다.

> [!NOTE]
> 모양 텍스트 속성이 지원되는 경우에만 모양을 채우도록 **셀** 구성 요소를 구성할 수 있습니다.

**Cell** 구성 요소가 Excel 그림에 값을 입력하도록 구성된 경우 이미지를 바이너리 형식으로 나타내는 **Container** 데이터 형식의 값을 반환하는 데이터 원본과 바인딩할 수 있습니다. 이 경우 값은 Excel 그림에 이미지로 입력됩니다.

> [!NOTE]
> 모든 Excel 그림과 도형은 왼쪽 위 모서리에 의해 특정 Excel 셀 또는 범위에 고정된 것으로 간주됩니다. Excel 그림이나 도형을 복제하려면 고정된 셀이나 범위를 복제된 셀이나 범위로 구성해야 합니다.

이미지 및 모양을 포함하는 방법에 대한 자세한 내용은 [ER을 사용하여 생성한 문서에 이미지 및 모양 포함](electronic-reporting-embed-images-shapes.md)을 참조하십시오.

## <a name="page-break-component"></a>페이지 나누기 구성 요소

**PageBreak** 구성 요소는 Excel에서 새 페이지를 시작하도록 합니다. 이 구성 요소는 Excel의 기본 페이징을 사용하려는 경우 필요하지 않지만 Excel이 ER 형식을 따라 페이징을 구성하도록 하려는 경우에는 이 구성 요소를 사용해야 합니다.

## <a name="page-component"></a><a name="page-component"></a>페이지 구성 요소

### <a name="overview"></a>개요

Excel이 생성된 아웃바운드 문서에서 ER 형식 및 구조 페이지 매김을 따르도록 하려는 경우 **페이지** 구성 요소를 사용할 수 있습니다. ER 형식이 **페이지** 구성 요소 아래에 있는 구성 요소를 실행할 때 필요한 페이지 나누기가 자동으로 추가됩니다. 이 과정에서 생성된 콘텐츠의 크기, Excel 템플릿의 페이지 설정, Excel 템플릿에서 선택한 용지 크기를 고려합니다.

생성된 문서를 각기 다른 페이지 매김이 있는 다른 섹션으로 분할해야 하는 경우 모든 [시트](er-fillable-excel.md#sheet-component) 구성 요소에서 여러 **페이지** 구성 요소를 구성할 수 있습니다.

### <a name="structure"></a><a name="page-component-structure"></a>구조

**페이지** 구성 요소 아래의 첫 번째 구성 요소가 **복제 방향** 속성이 **복제 없음** 으로 설정된 [범위](er-fillable-excel.md#range-component) 구성 요소인 경우 이 범위는 현재 **페이지** 구성 요소의 설정을 기반으로 하는 페이지 매김에 대한 페이지 헤더로 간주됩니다. 이 서식 구성 요소와 연결된 Excel 범위는 현재 **페이지** 구성 요소의 설정을 사용하여 생성된 모든 페이지의 맨 위에 반복됩니다.

> [!NOTE]
> 올바른 페이지 매김을 위해 Excel 템플릿에 상위 범위에서 [반복할 행이 구성](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409)된 경우 이 Excel 범위의 주소는 이전에 설명한 **범위** 구성 요소와 연결된 Excel 범위의 주소와 같아야 합니다.

**페이지** 구성 요소 아래의 마지막 구성 요소가 **복제 방향** 속성이 **복제 없음** 으로 설정된 **범위** 구성 요소인 경우 이 범위는 현재 페이지 구성 요소의 설정을 기반으로 하는 페이지 매김에 대한 **페이지** 바닥글로 간주됩니다. 이 형식 구성 요소와 연결된 Excel 범위는 현재 **페이지** 구성 요소의 설정을 사용하여 생성된 모든 페이지의 맨 아래에 반복됩니다.

> [!NOTE]
> 올바른 페이지 매김을 위해 **Range** 구성 요소와 연결된 Excel 범위는 런타임에 크기가 조정되지 않아야 합니다. **셀의 텍스트 줄 바꿈** 및 **행 높이 자동 맞춤** Excel [옵션](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84)을 사용하여 이 범위의 셀에 서식을 지정하지 않는 것이 좋습니다.

선택적 **Range** 구성 요소 사이에 여러 개의 다른 **Range** 구성 요소를 추가하여 생성된 문서를 채우는 방법을 지정할 수 있습니다.

**Page** 구성 요소 아래의 중첩된 **Range** 구성 요소 집합이 앞에서 설명한 구조를 따르지 않으면 ER 형식 디자이너에서 디자인 타임에 유효성 검사 [오류](er-components-inspections.md#i17)가 발생합니다. 오류 메시지는 문제가 런타임에 문제를 일으킬 수 있음을 알려줍니다.

> [!NOTE]
> 올바른 출력을 생성하려면 해당 **범위** 구성 요소에 대한 **복제 방향** 속성이 **복제 없음** 으로 설정되고 **범위** 가 페이지 머리글 또는 페이지 바닥글을 생성하도록 구성된 경우 페이지 구성 요소 아래에서 **범위** 구성 요소에 대한 바인딩을 지정하지 마십시오.

페이지 매김 관련 합계 및 계산을 통해 누적 합계 및 페이지당 합계를 계산하려면 필요한 [데이터 수집](er-data-collection-data-sources.md) 데이터 원본을 구성하는 것이 좋습니다. **페이지** 구성 요소를 사용하여 생성된 Excel 문서에 페이지를 매기는 방법을 배우려면 [Excel 형식으로 생성된 문서에 페이지를 매기기](er-paginate-excel-reports.md) 위한 ER 형식 디자인의 절차를 완료하십시오.

### <a name="limitations"></a><a name="page-component-limitations"></a>한계

Excel 페이지 매김을 위해 **Page** 구성 요소를 사용하는 경우 페이지 매김이 완료될 때까지 생성된 문서의 최종 페이지 수를 알 수 없습니다. 따라서 ER 공식을 사용하여 총 페이지 수를 계산할 수 없으며 마지막 페이지 이전의 모든 페이지에 생성된 문서의 정확한 페이지 수를 인쇄할 수 없습니다.

> [!TIP]
> 머리글 및 바닥글에 대한 특수 Excel [서식을](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) 사용하여 Excel 머리글 또는 바닥글에서 이 결과를 얻으려면.

Dynamics 365 Finance 버전 10.0.22에서 편집 가능한 형식으로 Excel 템플릿을 업데이트할 때 구성된 **페이지** 구성 요소는 고려되지 않습니다. 이 함수은 Finance의 추가 릴리스에서 고려됩니다.

[조건부 서식](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting)을 사용하도록 Excel 템플릿을 구성하면 경우에 따라 예상대로 작동하지 않을 수 있습니다.

### <a name="applicability"></a>적용 가능성

**페이지** 구성 요소는 해당 구성 요소가 Excel의 템플릿을 사용하도록 구성된 경우에만 [Excel 파일](er-fillable-excel.md#excel-file-component) 형식 구성 요소에 대해 작동합니다. Excel 템플릿을 Word 템플릿으로 [바꾼](tasks/er-design-configuration-word-2016-11.md) 다음 편집 가능한 ER 형식을 실행하면 **페이지** 구성 요소가 무시됩니다.

**페이지** 구성 요소는 전자 보고 프레임워크 기능에서 EPPlus 라이브러리 사용 활성화가 **활성화된** 경우에만 작동합니다. 이 기능이 비활성화되어 있는 동안 ER이 **페이지** 구성 요소를 처리하려고 하면 런타임에 예외가 발생합니다.

> [!NOTE]
> ER 형식이 유효하지 않은 셀을 참조하는 수식을 하나 이상 포함하는 Excel 템플릿의 **페이지** 구성 요소를 처리하는 경우 런타임에 예외가 발생합니다. [런타임 오류를 방지하려면 #REF를 수정하는 방법](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be)에 설명된 대로 Excel 템플릿을 수정하십시오! 오류.

## <a name="footer-component"></a>바닥글 구성 요소

**바닥글** 구성 요소는 Excel 통합 문서에서 생성된 워크시트의 맨 아래에 바닥글을 채우는 데 사용됩니다.

> [!NOTE]
> 모든 **시트** 구성 요소에 대해 이 구성 요소를 추가하여 생성된 Excel 통합 문서의 서로 다른 워크시트에 대해 서로 다른 바닥글을 지정할 수 있습니다.

개별 **바닥글** 구성 요소를 구성할 때 **머리글/바닥글 모양** 속성을 사용하여 구성 요소가 사용되는 페이지를 지정할 수 있습니다. 다음 값을 사용할 수 있습니다.

- **모두** – 상위 Excel 워크시트의 모든 페이지에 대해 구성된 **바닥글** 구성 요소를 실행합니다.
- **첫 번째** – 상위 Excel 워크시트의 첫 번째 페이지에 대해서만 구성된 **바닥글** 구성 요소를 실행합니다.
- **짝수** – 상위 Excel 워크시트의 짝수 페이지에 대해서만 구성된 **바닥글** 구성 요소를 실행합니다.
- **홀수** – 상위 Excel 워크시트의 홀수 페이지에 대해서만 구성된 **바닥글** 구성 요소를 실행합니다.

단일 **시트** 구성 요소의 경우 **머리글/바닥글 모양** 속성에 대해 각각 다른 값을 갖는 여러 **바닥글** 구성 요소를 추가할 수 있습니다. 이러한 방식으로 Excel 워크시트의 다양한 페이지 유형에 대해 다른 바닥글을 생성할 수 있습니다.

> [!NOTE]
> 단일 **시트** 구성 요소에 추가하는 각 **바닥글** 구성 요소의 **머리글/바닥글 모양** 속성 값이 서로 다른지 확인하십시오. 그렇지 않으면 [유효성 검사 오류](er-components-inspections.md#i16)가 발생합니다. 수신된 오류 메시지는 불일치에 대해 알려줍니다.

추가된 **Footer** 구성 요소 아래에 **Text\\스트링**, **Text\\DateTime** 또는 기타 유형의 필수 중첩 구성 요소를 추가합니다. 페이지 바닥글이 채워지는 방식을 지정하려면 해당 구성 요소에 대한 바인딩을 구성합니다.

특수 [형식 지정 코드](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers)를 사용하여 생성된 바닥글 내용의 형식을 올바르게 지정할 수도 있습니다. 이 접근 방식을 사용하는 방법을 배우려면 이 항목의 뒷부분에 나오는 [예 1](#example-1)의 단계를 따르십시오.

> [!NOTE]
> ER 형식을 구성할 때 Excel [제한](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3)과 단일 머리글 또는 바닥글의 최대 문자 수를 고려해야 합니다.

## <a name="header-component"></a>헤더 구성 요소

**머리글** 구성 요소는 Excel 통합 문서에서 생성된 워크시트의 맨 위에 있는 머리글을 채우는 데 사용됩니다. **Footer** 컴포넌트처럼 사용됩니다.

## <a name="edit-an-added-er-format"></a>추가된 ER 형식 편집

### <a name="update-a-template"></a>템플릿 업데이트

작업 창의 **가져오기** 탭에서 **Excel에서 업데이트** 를 선택하여 업데이트된 템플릿을 편집 가능한 ER 형식으로 가져올 수 있습니다. 이 과정에서 선택한 **Excel\\File** 구성 요소의 템플릿이 새 템플릿으로 바뀝니다. 편집 가능한 ER 형식의 내용은 업데이트된 ER 템플릿의 내용과 동기화됩니다.

- 편집 가능한 형식에서 ER 형식 구성 요소를 찾을 수 없는 경우 모든 Excel 이름에 대해 새 ER 형식 구성 요소가 자동으로 생성됩니다.
- 적절한 Excel 이름이 없으면 모든 ER 형식 구성 요소가 편집 가능한 ER 형식에서 삭제됩니다.

> [!NOTE]
> **편집 가능한 ER 형식** 으로 선택적 시트 요소를 생성하려면 Excel 시트 형식 요소 **생성** 옵션을 **예** 로 설정합니다.
>
> 편집 가능한 ER 형식에 원래 **시트** 요소가 포함된 경우 **업데이트된 템플릿을 가져올 때 Excel 시트 형식 요소 생성** 옵션을 **예** 로 설정하는 것이 좋습니다. 그렇지 않으면 원래 **Sheet** 요소의 모든 중첩 요소가 처음부터 생성됩니다. 따라서 재생성된 형식 요소의 모든 바인딩은 업데이트된 ER 형식에서 손실됩니다.

![Excel에서 업데이트 대화 상자에서 Excel 시트 형식 요소 만들기 옵션.](./media/er-excel-format-update-template.png)

이 기능에 대해 자세히 알아보려면 [Excel 템플릿을 다시 적용하여 전자 보고 형식 수정](modify-electronic-reporting-format-reapply-excel-template.md)의 단계를 따르십시오.

## <a name="validate-an-er-format"></a>ER 형식 검증

편집 가능한 ER 형식의 유효성을 검사할 때 Excel 이름이 현재 사용 중인 Excel 템플릿에 있는지 확인하기 위해 일관성 검사가 수행됩니다. 불일치 사항에 대해 알림을 받게 됩니다. 일부 불일치의 경우 문제를 자동으로 수정하는 옵션이 제공됩니다.

![유효성 검사 오류 메시지입니다.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Excel 수식 계산 제어

Microsoft Excel 통합 문서 형식의 아웃바운드 문서가 생성되면 이 문서의 일부 셀에 Excel 수식이 포함될 수 있습니다. **전자 보고 프레임워크에서 EPPlus 라이브러리 사용 활성화** 기능이 활성화되면 사용 중인 Excel 템플릿에서 **계산 옵션** [매개 변수](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows)의 값을 변경하여 공식이 계산되는 시기를 제어할 수 있습니다.

- 생성된 문서에 새 범위, 셀 등이 추가될 때마다 모든 종속 수식을 다시 계산하려면 **자동을** 선택합니다.

    > [!NOTE]
    > 이로 인해 여러 관련 수식이 포함된 Excel 템플릿의 성능 문제가 발생할 수 있습니다.

- 문서가 생성될 때 수식을 다시 계산하지 않으려면 **수동을** 선택합니다.

    > [!NOTE]
    > Excel을 사용하여 미리 보기를 위해 생성된 문서를 열면 수식 재계산이 수동으로 강제 실행됩니다.
    > 생성된 문서에 수식이 포함된 셀의 값이 포함되지 않을 수 있으므로 Excel에서 미리 보기(PDF 변환, 이메일 전송 등) 없이 생성된 문서의 사용을 가정하는 ER 대상을 구성하는 경우 이 옵션을 사용하지 마십시오.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>예 1 : 바닥글 콘텐츠 형식 지정

1. 제공된 ER 구성을 사용하여 인쇄 가능한 자유 텍스트 송장(FTI) 문서를 [생성합니다](er-generate-printable-fti-forms.md).
2. 생성된 문서의 바닥글을 검토합니다. 여기에는 현재 페이지 번호와 문서의 총 페이지 수에 대한 정보가 포함되어 있습니다.

    ![Excel 형식으로 생성된 문서의 바닥글을 검토합니다.](./media/er-fillable-excel-footer-1.gif)

3. ER 형식 디자이너에서 검토를 위해 샘플 ER 형식을 [엽니다](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format).

    **송장** 워크시트의 바닥글은 **바닥글** 구성 요소 아래에 있는 두 개의 **스트링** 구성 요소 설정을 기반으로 생성됩니다.

    - 첫 번째 **스트링** 구성 요소는 다음과 같은 특수 서식 코드를 채워 Excel에서 특정 서식을 적용하도록 합니다.

        - **&C** – 바닥글 텍스트를 가운데에 맞춥니다.
        - **&"Segoe UI,Regular'&8** – 글꼴의 바닥글 텍스트를 8포인트 크기로 "Segoe UI Regular" 표시합니다.

    - 두 번째 **스트링** 구성 요소는 현재 문서의 현재 페이지 번호와 총 페이지 수를 포함하는 텍스트를 채웁니다.

    ![형식 디자이너 페이지에서 바닥글 ER 형식 구성 요소를 검토합니다.](./media/er-fillable-excel-footer-2.png)

4. 샘플 ER 형식을 사용자 지정하여 현재 페이지 바닥글을 수정합니다.

    1. 샘플 ER 형식을 기반으로 파생된 **자유 텍스트 송장(Excel)** 사용자 지정 ER 형식을 [만듭니다](er-quick-start2-customize-report.md#DeriveProvidedFormat).
    2. **송장** 워크시트의 **바닥글** 구성 요소에 대한 첫 번째 새 **스트링** 구성 요소 쌍을 추가합니다.

        1. 왼쪽에 회사 이름을 정렬하고 8포인트 "Segoe UI Regular" 글꼴(**'&L&"Segoe UI,Regular'&8'**)로 표시하는 **스트링** 구성 요소를 추가합니다.
        2. 회사 이름(**model.InvoiceBase.CompanyInfo.Name**)을 채우는 **스트링** 구성 요소를 추가합니다.

    3. **송장** 워크시트의 **바닥글** 구성 요소에 대한 두 번째 새 **스트링** 구성 요소 쌍을 추가합니다.

        1. 처리 날짜를 오른쪽에 맞추고 8포인트 "Segoe UI Regular" 글꼴(**'&R&"Segoe UI,Regular'&8'**)로 표시하는 **스트링** 구성 요소를 추가합니다.
        2. 처리 날짜를 사용자 지정 형식(**''&nbsp;&DATEFORMAT(SESSIONTODAY(), 'yyyy-MM-dd')**)으로 채우는 **스트링** 구성 요소를 추가합니다.

        ![형식 디자이너 페이지에서 바닥글 ER 형식 구성 요소를 검토합니다.](./media/er-fillable-excel-footer-3.png)

    4. 파생된 **자유 텍스트 송장(Excel)** 사용자 지정 ER 형식의 초안 버전을 [완성](er-quick-start2-customize-report.md#CompleteDerivedFormat)합니다.

5. 샘플 ER 형식 대신 파생된 **자유 텍스트 송장(Excel)** 사용자 지정 ER 형식을 사용하도록 인쇄 관리를 [구성](er-generate-printable-fti-forms.md#configure-print-management)합니다.
6. 인쇄 가능한 FTI 문서를 생성하고 생성된 문서의 바닥글을 검토합니다.

    ![Excel 형식으로 생성된 문서의 바닥글을 검토합니다.](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a>예 2 : 병합된 셀 EPPlus 문제 수정

ER 형식을 실행하여 Excel 통합 문서 형식으로 아웃바운드 문서를 생성할 수 있습니다. **기능 관리** 작업 공간에서 **전자 보고 프레임워크 기능에서 EPPlus 라이브러리 사용** 활성화가 활성화되면 EPPlus [라이브러리를](https://www.nuget.org/packages/epplus/4.5.2.1) 사용하여 Excel 출력을 만듭니다. 그러나 알려진 [Excel 동작](https://answers.microsoft.com/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9)과 EPPlus 라이브러리의 제한으로 인해 다음 예외가 발생할 수 있습니다. 병합된 셀을 삭제/덮어쓸 수 없습니다. 범위가 다른 병합된 범위와 부분적으로 병합되었습니다. 어떤 종류의 Excel 템플릿으로 인해 이 예외가 발생하고 문제를 해결할 수 있는지 알아보려면 다음 예를 완료하십시오.

1. Excel 데스크톱 애플리케이션에서 새 Excel 통합 문서를 만듭니다.
2. **Sheet1** 워크시트에서 **A2** 셀의 **ReportTitle** 이름을 추가합니다.
3. 셀 **A1** 과 **A2** 를 병합합니다.

    ![Excel 데스크톱 애플리케이션에서 설계된 Excel 통합 문서의 A1 및 A2 셀 병합 결과를 검토합니다.](./media/er-fillable-excel-example2-1.png)

3. **구성** 페이지에서 [새 ER 형식을 추가](er-fillable-excel.md#add-a-new-er-format)하여 Excel 통합 문서 형식의 아웃바운드 문서를 생성합니다.
4. **형식 디자이너** 페이지에서 디자인된 Excel 통합 문서를 아웃바운드 문서에 대한 새 템플릿으로 추가된 ER 형식으로 [가져옵니다](er-fillable-excel.md#template-import).
5. **매핑** 탭에서 [셀](er-fillable-excel.md#cell-component) 유형의 **ReportTitle** 구성 요소에 대한 바인딩을 구성합니다.
6. 구성된 ER 형식을 실행합니다. 다음 예외가 발생했습니다. 병합된 셀을 삭제/덮어쓸 수 없습니다. 범위가 다른 병합된 범위와 부분적으로 병합되었습니다.

    ![형식 디자이너 페이지에서 구성된 ER 형식을 실행한 결과를 검토합니다.](./media/er-fillable-excel-example2-2.png)

다음 방법 중 하나로 문제를 해결할 수 있습니다.

- **더 쉽지만 권장하지 않습니다.** **기능 관리** 작업 공간에서 **전자 보고 프레임워크 기능** 에서 EPPlus 라이브러리 사용 활성화를 끕니다. 이 접근 방식이 더 쉽지만 **전자 보고 프레임워크에서 EPPlus 라이브러리 사용 활성화** 기능이 활성화된 경우에만 일부 ER 기능이 지원되기 때문에 이를 사용하면 다른 문제가 발생할 수 있습니다.
- **추천:** 이 단계를 따르십시오:

    1. Excel 데스크톱 응용 프로그램에서 다음 방법 중 하나로 Excel 통합 문서를 수정합니다.

        - **Sheet1** 워크시트에서 **A1** 및 **A2** 셀 병합을 해제합니다.
        - **ReportTitle** 이름에 대한 참조를 **=Sheet1!$A$2** 에서 **=Sheet1!$A$1** 로 변경합니다.

        ![Excel 데스크톱 애플리케이션에서 설계된 Excel 통합 문서의 셀 병합 결과를 검토합니다.](./media/er-fillable-excel-example2-3.png)

    2. **형식 디자이너** 페이지에서 수정된 Excel 통합 문서를 편집 가능한 ER 형식으로 [가져와](er-fillable-excel.md#template-import) 기존 템플릿을 업데이트합니다.
    3. 구성된 ER 형식을 실행합니다.

        ![Excel 데스크톱 응용 프로그램에서 생성된 문서를 검토합니다.](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>한계

### <a name="known-epplus-library-limitations"></a>알려진 EPPlus 라이브러리 제한 사항

#### <a name="external-data-sources"></a>외부 데이터 소스

템플릿 중 하나에 [외부 데이터 소스](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b)를 참조하는 PowerPivot 모델을 기반으로 하는 피벗 테이블이 포함되어 있고 전자 보고 프레임워크에서 **EPPlus 라이브러리 사용** 기능이 활성화되어 있는 경우 ER 형식을 실행할 때 다음 오류 메시지가 나타납니다. 해당 템플릿을 사용하여 Excel 형식의 아웃바운드 문서를 생성합니다. "캐시 소스가 워크시트가 아닙니다." 이 문제를 해결하려면 다음과 같은 옵션이 있습니다.

- **추천:** 사용 중인 Excel 솔루션을 다시 디자인합니다.

    1. 별도의 Excel 통합 문서(통합 문서 A)에서 피벗이 포함된 부분을 분리합니다. 
    2. ER을 사용하여 필요한 세부 정보가 포함된 두 번째 Excel 통합 문서(통합 문서 B)를 재무에서 생성합니다. 
    3. 통합 문서 B가 생성되는 즉시 통합 문서 A의 통합 문서 B를 참조하십시오.

- EPPlus 이외의 옵션을 사용하려면 **전자 보고 프레임워크에서 EPPlus 라이브러리 사용** 활성화 기능을 끕니다. 

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[OPENXML 형식의 보고서 생성을 위한 구성 설계](tasks\er-design-reports-openxml-2016-11.md)

[Excel 템플릿을 다시 적용하여 전자 보고 형식 수정](modify-electronic-reporting-format-reapply-excel-template.md)

[수평으로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가](tasks/er-horizontal-1.md)

[ER을 사용하여 생성한 문서에 이미지 및 모양 포함](electronic-reporting-embed-images-shapes.md)

[데이터를 가져오도록 전자 보고(ER) 구성 Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
