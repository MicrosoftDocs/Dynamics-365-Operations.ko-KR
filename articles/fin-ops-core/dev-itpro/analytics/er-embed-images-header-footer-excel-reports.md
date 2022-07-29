---
title: 페이지 머리글 또는 바닥글에 이미지가 포함된 Excel 형식의 보고서를 생성하는 ER 형식 디자인
description: 이번에는 전자 보고(ER)를 사용하여 페이지 머리글 또는 바닥글에 이미지와 모양이 포함된 비즈니스 문서를 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3f3f77a9e6104a31995c9ee398504982fe43ac9e
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8461029"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>페이지 머리글 또는 바닥글에 이미지가 포함된 Excel 형식의 보고서를 생성하는 ER 형식 디자인

[!include[banner](../includes/banner.md)]

이번에는 시스템 관리자 또는 전자 보고 함수 컨설턴트 역할의 사용자가 다음 작업을 수행할 수 있는 방법에 대해 설명합니다.

- [전자 보고(ER)](general-electronic-reporting.md) 프레임워크에 대한 매개 변수를 구성합니다.
- Microsoft에서 [제공하고](general-electronic-reporting.md#Provider) Microsoft Excel 형식의 [템플릿](er-fillable-excel.md#excel-file-component)을 기반으로 [무료 텍스트 송장](../../../finance/accounts-receivable/create-free-text-invoice-new.md)을 생성하는 데 사용되는 ER [구성](general-electronic-reporting.md#Configuration)을 가져옵니다.
- Microsoft에서 제공하는 표준 ER 형식 구성의 [사용자 지정(파생)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) 버전을 만듭니다.
- 바닥글에 회사 로고 이미지가 있는 자유 텍스트 송장 보고서를 생성하도록 사용자 지정 ER 형식 구성을 수정하십시오.

이 항목의 절차는 **USMF** 회사에서 완료할 수 있습니다. 코딩이 필요하지 않습니다. 시작하기 전에 다음 파일을 다운로드하여 저장합니다.

| 설명        | 파일 이름 |
|--------------------|-----------|
| 회사 로고 이미지 | [회사 로고.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>콘텐츠

- [법인 구성](#ConfigureLegalEntity)
- [ER 프레임워크 구성](#ConfigureFramework)

    - [ER 매개 변수 구성](#ConfigureParameters)
    - [ER 구성 공급자 활성화](#ActivateProvider)

        - [ER 구성 제공자 목록 검토](#ReviewProvidersList)
        - [새 ER 구성 공급자 추가](#AddProvider)
        - [새 ER 구성 공급자 활성화](#ActivateAddedProvider)

- [표준 ER 형식 구성 가져오기](#ImportERSolution1)

    - [표준 ER 구성 가져오기](#ImportERFormat)
    - [가져온 ER 구성 검토](#ReviewImportedERSolution)

- [표준 ER 형식을 사용하여 무료 텍스트 송장 인쇄](#PrintInvoice1)

    - [인쇄 관리 설정](#ConfigurePrintManagement1)
    - [무료 텍스트 송장 인쇄](#ProcessInvoice1)

- [표준 ER 형식 사용자 지정](#CustomizeProvidedFormat)

    - [사용자 지정 형식 만들기](#DeriveProvidedFormat)
    - [사용자 지정 형식 편집](#ConfigureDerivedFormat)
    - [사용자 지정 형식을 실행 가능한 것으로 표시](#MarkFormatRunnable)

- [사용자 지정 ER 형식을 사용하여 무료 텍스트 송장 인쇄](#PrintInvoice2)

    - [인쇄 관리 설정](#ConfigurePrintManagement2)
    - [무료 텍스트 송장 인쇄](#ProcessInvoice2)

- [추가 리소스](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>법인 구성

1. **조직 관리** \> **조직** \> **법인** 으로 이동합니다.
2. **법인** 페이지의 **회사 로고 이미지** FastTab 보고에서 **변경** 을 선택합니다.
3. **업로드할 이미지 파일 선택** 대화 상자에서 **찾아보기** 를 선택하고 이전에 다운로드한 **Company logo.png** 파일을 선택합니다.
4. **저장** 을 선택한 다음 **법인** 페이지를 닫습니다.

![법인 페이지에서 선택한 회사 로고 이미지.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>ER 프레임워크 구성

전자 보고 함수 컨설턴트 역할의 사용자는 ER 프레임워크를 사용하여 표준 ER 형식의 사용자 지정 버전을 디자인하기 시작하기 전에 최소 ER 매개 변수 세트를 구성해야 합니다.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>ER 매개 변수 구성

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **전자 보고 매개 변수** 를 선택합니다.
3. **전자 보고 매개변수** 페이지의 **일반** 탭에서 **디자인 모드 활성화** 옵션을 **네** 로 설정합니다.
4. **첨부** 탭에서 다음 매개 변수를 설정합니다.

    - **구성** 필드에서 **USMF** 회사의 **파일** 유형을 선택하십시오.
    - **작업 아카이브**, **임시**, **기준선** 및 **기타** 필드에서 **파일** 유형을 선택합니다.

ER 매개 변수에 대한 자세한 내용은 [ER 프레임워크 구성](electronic-reporting-er-configure-parameters.md)을 참조하세요.

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>ER 구성 공급자 활성화

추가된 모든 ER 구성은 ER 구성 공급자가 소유한 것으로 표시됩니다. 이 목적으로 **전자 보고** 작업 영역에서 활성화된 ER 구성 공급자가 사용됩니다. 따라서 ER 구성을 추가하거나 편집하기 전에 **전자 보고** 작업 영역에서 ER 구성 공급자를 활성화해야 합니다.

> [!NOTE]
> ER 구성은 구성 소유자만 편집할 수 있습니다. ER 구성을 편집하려면 먼저 **전자 보고** 작업 공간에서 적절한 ER 구성 공급자를 활성화해야 합니다.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>ER 구성 제공자 목록 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자 테이블** 페이지에서 각 공급자 레코드에는 고유한 이름과 URL이 있습니다. 이 페이지의 내용을 검토하세요. **Litware, Inc.**(`https://www.litware.com`)의 레코드가 이미 존재하는 경우 다음 절차를 건너뛰고, [새 ER 구성 공급자를 추가](#AddProvider)합니다.

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>새 ER 구성 공급자 추가

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자** 페이지에서 **새로 만들기** 를 선택합니다.
4. **이름** 필드에서 **Litware, Inc.** 를 입력합니다.
5. **인터넷 주소** 필드에 `https://www.litware.com`을 입력합니다.
6. **저장** 을 선택합니다.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>새 ER 구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Litware, Inc.** 타일을 선택한 다음 **활성으로 설정** 을 선택합니다.

ER 구성 공급자에 대한 자세한 내용은 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하세요.

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>표준 ER 형식 구성 가져오기

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>표준 ER 구성 가져오기

Dynamics 365 Finance의 현재 인스턴스에 표준 ER 구성을 추가하려면 해당 인스턴스에 대해 구성된 ER [저장소](general-electronic-reporting.md#Repository)에서 가져와야 합니다.

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성 공급자** 섹션에서 **Microsoft** 타일을 선택한 다음 **리포지토리** 를 선택하여 **Microsoft** 공급자의 리포지토리 목록을 봅니다.
3. **구성 저장소** 페이지에서 **글로벌** 유형의 저장소를 선택한 다음 **열기** 를 선택합니다. [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md)에 연결할 권한을 묻는 메시지가 표시되면 권한 부여 지침을 따르십시오.
4. **구성 리포지토리** 페이지의 왼쪽 창에 있는 구성 트리에서 **자유 텍스트 송장(Excel)** 형식 구성을 선택합니다.
5. **버전** FastTab에서 선택한 ER 형식 구성의 최신 버전(예: **240.112**)을 선택합니다.
6. **가져오기** 를 선택하여 글로벌 리포지토리에서 현재 재무 인스턴스로 선택한 버전을 다운로드합니다.

![구성 리포지토리 페이지에서 표준 ER 구성을 가져옵니다.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> [글로벌 리포지토리](er-download-configurations-global-repo.md) 접속에 문제가 있는 경우 Microsoft Dynamics Lifecycle Services(LCS)에서 [구성을 다운로드](download-electronic-reporting-configuration-lcs.md)할 수 있습니다.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>가져온 ER 구성 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **현지화 구성** 페이지의 **구성** 섹션에서 **보고 구성** 타일을 선택합니다.
3. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **송장 모델** 을 확장합니다.
4. 선택한 **자유 텍스트 송장(Excel)** ER 형식 외에 다른 필수 ER 구성을 가져왔습니다. 구성 트리에서 다음 ER 구성을 사용할 수 있는지 확인하십시오.

    - **송장 모델** – 이 구성에는 송장 발행 비즈니스 도메인의 데이터 구조를 나타내는 데이터 모델 ER 구성 요소가 포함되어 있습니다.
    - **송장 모델 매핑** – 이 구성에는 런타임 시 데이터 모델이 애플리케이션 데이터로 채워지는 방법을 설명하는 모델 매핑 ER 구성 요소가 포함됩니다.
    - **자유 텍스트 송장(Excel)** – 이 구성에는 ER 구성 요소를 매핑하는 형식 및 형식이 포함되어 있습니다. 형식 구성 요소는 Excel 형식의 템플릿을 기반으로 보고서 레이아웃을 지정합니다. 형식 매핑 구성 요소는 모델 데이터 원본을 포함하고 데이터 원본이 런타임 시 보고서 레이아웃을 채우는 데 사용되는 방법을 지정합니다.

![구성 페이지에서 가져온 ER 구성.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>표준 ER 형식을 사용하여 무료 텍스트 송장 인쇄

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>인쇄 관리 설정

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **무료 텍스트 송장** 페이지에서 **FTI-00000002** 송장을 선택한 다음 작업 창의 **송장** 탭에 있는 **인쇄 관리** 그룹에서 **인쇄 관리** 를 선택합니다.
3. **인쇄 관리 설정** 페이지의 왼쪽 트리에서 **모듈 - 미수금 \> 문서 \> 무료 텍스트 송장** 을 확장한 다음 **원본 \<Default\>항목** 을 선택합니다.
4. **보고서 형식** 필드에서 **자유 텍스트 송장(Excel)** 을 선택합니다.
5. **Esc** 키를 선택하여 **인쇄 관리 설정** 페이지를 종료하고 **무료 텍스트 송장** 페이지로 돌아갑니다.

![인쇄 관리 설정 페이지에서 표준 ER 형식의 자유 텍스트 송장에 대한 인쇄 관리 설정입니다.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>무료 텍스트 송장 인쇄

1. **무료 텍스트 송장** 페이지에서 **FTI-00000002** 송장이 여전히 선택되어 있는지 확인한 다음 작업 창의 **송장** 탭에 있는 **문서** 그룹에서 **선택 항목** \> **인쇄** 를 선택합니다.
2. 생성된 송장을 Excel 형식으로 다운로드하고 미리 보기 위해 엽니다.
3. 제공된 ER 형식에 대한 Excel 템플릿의 구조에 따라 생성된 송장의 페이지 바닥글에는 보고서의 현재 페이지 번호와 총 페이지 수에 대한 정보가 포함됩니다.

![무료 텍스트 송장이 생성되었습니다.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>표준 ER 형식 사용자 지정

이 섹션의 예시에서는 Microsoft에서 제공하는 ER 구성을 사용하여 Excel 형식의 무료 텍스트 송장을 생성할 수 있습니다. 그러나 생성된 송장의 페이지 바닥글에 회사 로고 이미지를 삽입하려면 사용자 지정을 추가해야 합니다.

이 경우 귀하는 Litware, Inc.의 대표자로서 Microsoft에서 제공하는 **무료 텍스트 송장(Excel)** 구성을 기반으로 하는 새로운 ER 형식 구성을 생성(파생)해야 합니다.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>사용자 지정 형식 만들기

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **송장 모델** 을 확장한 다음 **자유 텍스트 송장(Excel)** 을 선택합니다. Litware, Inc.는 이 ER 형식 구성의 가져온 버전(예: **240.112**)을 사용자 지정 버전의 기반으로 사용합니다.
3. **구성 만들기** 를 선택하여 드롭다운 대화 상자를 엽니다. 이 대화 상자를 사용하여 사용자 지정 지급 형식에 대한 새 구성을 생성하십시오.
4. **새** 필드 그룹에서 이름에서 파생을 선택합니다. **무료 텍스트 송장(Excel), Microsoft** 옵션.
5. **이름** 필드에 **자유 텍스트 송장(Excel)** 사용자 지정을 입력합니다.
6. **구성 만들기** 를 선택합니다.

![구성 생성 드롭다운 대화 상자에서 사용자 지정 지급 형식에 대한 구성 생성.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

**자유 텍스트 송장(Excel) 사용자 지정** ER 형식 구성의 버전 240.112.1이 생성됩니다. 이 버전은 **초안** [상태](general-electronic-reporting.md#component-versioning)이며 편집할 수 있습니다. 사용자 지정 ER 형식의 현재 내용은 Microsoft에서 제공하는 형식의 내용과 일치합니다.

![구성 페이지에서 생성된 ER 형식 구성의 새 버전입니다.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>사용자 지정 형식 편집

회사 로고 이미지가 보고서의 모든 페이지에 있는 바닥글에 삽입되도록 사용자 지정 형식을 구성하십시오.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 왼쪽 창에 있는 구성 트리에서 **결제 모델** 을 확장한 다음 **무료 텍스트 송장(Excel)** 사용자 지정을 선택합니다.
3. **버전** FastTab에서 선택한 구성의 버전 **240.112.1** 을 선택합니다.
4. **디자이너** 를 선택합니다.
5. **형식 디자이너** 페이지에서 **세부 정보 표시** 를 선택하여 형식 요소에 대한 자세한 정보를 봅니다.
6. 다음 요소를 확장하고 검토합니다.

    - **Excel** 유형의 **자유 텍스트 송장** 요소입니다. 이 요소는 Excel 통합 문서 형식의 송장을 생성하는 데 사용됩니다.
    - **시트** 유형의 **자유 텍스트 송장 \\ 송장** 요소입니다. 이 요소는 생성된 Excel 통합 문서의 워크시트를 생성하는 데 사용됩니다.
    - **바닥글** 유형의 **자유 텍스트 \\ 송장 \\ 바닥글** 요소입니다. 이 요소는 송장 바닥글을 채우는 데 사용됩니다.

7. **자유 텍스트 송장 \\ 송장 \\ 바닥글** 요소를 선택합니다.

    ![ER Operations 디자이너의 바닥글 요소입니다.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > 생성된 송장의 모든 페이지 바닥글에는 보고서의 현재 페이지 번호와 총 페이지 수에 대한 정보가 포함됩니다. 보시다시피 **자유 텍스트 송장 \\ 송장 \\ 바닥글** 요소에는 하위 요소가 없습니다. 따라서 사용 중인 Excel 템플릿은 모든 보고서 바닥글 중앙에 페이징 세부 정보를 표시하도록 구성됩니다.

8. **추가** 를 선택한 다음 추가하려는 서식 요소의 **Excel \\ 그림** 유형을 선택합니다.

    1. **정렬** 필드에서 **오른쪽** 을 선택합니다.
    2. **높이 조정** 필드에서 **상대** 를 선택합니다.
    3. **Scale in 백분율** 필드에 **70** 을 입력합니다.
    4. **확인** 을 선택합니다.

        > [!NOTE]
        > **Excel \\ 그림** 요소는 회사 로고 이미지를 추가하고 페이지 바닥글의 오른쪽에 정렬하는 데 사용됩니다.

    ![구성 요소 속성 대화 상자에 있는 그림 요소의 속성입니다.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. 왼쪽의 형식 구조 트리에서 방금 추가한 **그림** 요소를 선택한 다음 **매핑** 탭에서 **모델** 데이터 원본을 확장합니다.
10. **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo** 를 확장한 다음 **model.InvoiceBase.CompanyInfo.Logo** 데이터 원본 필드를 선택합니다. [Container](er-formula-supported-data-types-composite.md#container) 유형의 데이터 소스 필드는 회사 로고 이미지를 미디어 콘텐츠로 노출합니다.
11. **바인딩** 을 선택합니다. 이제 **Picture** 형식 요소가 **model.InvoiceBase.CompanyInfo.Logo** 데이터 소스 필드와 바인딩됩니다. 따라서 런타임에 회사 로고 이미지가 생성된 송장의 바닥글에 표시됩니다.

    ![ER Operations Designer의 model.InvoiceBase.CompanyInfo.Logo 데이터 소스 필드와 결합된 그림 형식 요소입니다.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. **저장** 을 선택한 다음 **디자이너** 페이지를 닫습니다.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>사용자 지정 형식을 실행 가능한 것으로 표시

사용자 지정 형식의 첫 번째 버전이 만들어지고 상태가 **초안** 이므로 테스트 목적으로 형식을 실행할 수 있습니다. 보고서를 실행하려면 사용자 지정 ER 형식을 참조하는 지급 방법을 사용하여 공급 업체 지급을 처리하십시오. 기본적으로 애플리케이션에서 ER 형식을 호출할 때 상태가 **완료됨** 또는 **공유됨** 인 버전만 [고려됩니다](general-electronic-reporting.md#component-versioning). 이 동작은 미완성 디자인이 사용되는 ER 형식을 방지하는 데 도움이 됩니다. 그러나 테스트 실행의 경우 애플리케이션에서 상태가 **초안** 인 ER 형식 버전을 사용하도록 강제할 수 있습니다. 이러한 방식으로 수정이 필요한 경우 현재 형식 버전을 조정할 수 있습니다. 자세한 내용은 [적용 가능성](electronic-reporting-destinations.md#applicability)을 참조하십시오.

ER 형식의 초안 버전을 사용하려면 ER 형식을 명시적으로 표시해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개 변수** 대화 상자에서 **실행 설정** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
4. **편집** 을 선택하여 현재 페이지를 편집 가능하게 만든 다음 왼쪽 창의 구성 트리에서 **자유 텍스트 송장(Excel)** 사용자 지정을 선택합니다.
5. **초안 실행** 옵션을 **예** 로 설정합니다.

![구성 페이지에서 사용자 지정 형식을 실행 가능한 것으로 표시합니다.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>사용자 지정 ER 형식을 사용하여 무료 텍스트 송장 인쇄

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>인쇄 관리 설정

1. **미수금** \> **송장** \> **모든 무료 텍스트 송장** 으로 이동합니다.
2. **무료 텍스트 송장** 페이지에서 **FTI-00000002** 송장을 선택한 다음 작업 창의 **송장** 탭에 있는 **인쇄 관리** 그룹에서 **인쇄 관리** 를 선택합니다.
3. **인쇄 관리** 설정 페이지의 왼쪽 트리에서 **모듈 - 미수금** \> **문서** \> **무료 텍스트 송장** 을 확장한 다음 **원본** **\<Default\>** 항목을 선택합니다.
4. **보고서 형식** 필드에서 **자유 텍스트 송장(Excel)** 사용자 지정을 선택합니다.
5. **Esc** 를 선택하여 **인쇄 관리 설정** 페이지를 종료하고 **무료 텍스트 송장** 페이지로 돌아갑니다.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>무료 텍스트 송장 인쇄

1. **무료 텍스트 송장** 페이지에서 **FTI-00000002** 송장이 여전히 선택되어 있는지 확인한 다음 작업 창의 **송장** 탭에 있는 **문서** 그룹에서 **선택 항목** \> **인쇄** 를 선택합니다.
2. 생성된 송장을 Excel 형식으로 다운로드하고 미리 보기 위해 엽니다.
3. 사용자 지정 ER 형식의 구조에 따라 생성된 송장의 페이지 바닥글에는 보고서 페이징에 대한 정보 외에 회사 로고 이미지가 포함됩니다.

![페이지 바닥글에 회사 로고 이미지가 있는 무료 텍스트 송장을 생성했습니다.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>추가 리소스

- [Excel 형식의 문서 생성을 위한 구성 설계](er-fillable-excel.md)
- [ER을 사용하여 생성한 문서에 이미지 및 모양 포함](electronic-reporting-embed-images-shapes.md)
