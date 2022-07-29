---
title: 동일한 Excel 페이지에서 행을 함께 유지하도록 ER 형식 디자인
description: 이번에는 동일한 Microsoft Excel 페이지에 행을 함께 유지하는 전자 보고(ER) 형식을 디자인하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.openlocfilehash: 711681ab38fb24b57a83f008f86a8261176aa5a5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8461045"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>동일한 Excel 페이지에서 행을 함께 유지하도록 ER 형식 디자인

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

이번에는 시스템 관리자 또는 전자 보고 함수 컨설턴트 역할의 사용자가 아웃바운드 문서를 생성하는 [전자 보고(ER)](general-electronic-reporting.md) [형식을](er-overview-components.md#format-component) 구성하고 Microsoft Excel 생성된 행이 동일한 페이지에 유지되도록 문서 페이지 매김을 관리하는 방법에 대해 설명합니다.

이 예시에서는 Excel에서 자유 텍스트 송장을 인쇄하는 데 사용되는 Microsoft 제공 ER 형식을 수정합니다. 수정 사항을 통해 생성된 자유 텍스트 송장 보고서의 페이지 매김을 관리할 수 있으므로 단일 송장 라인의 모든 행이 가능한 경우 동일한 페이지에 유지됩니다.

이 항목의 절차는 **USMF** 회사에서 완료할 수 있습니다. 코딩이 필요하지 않습니다.

이 예시에서는 **Litware, Inc.** 샘플 회사에 필요한 ER [구성](general-electronic-reporting.md#Configuration)을 생성합니다. **Litware, Inc.** (`http://www.litware.com`) 샘플 회사의 구성 공급자가 ER 프레임워크에 대해 나열되어 있고 **활성** 으로 표시되어 있는지 확인합니다. 이 구성 공급자가 나열되지 않거나 **활성** 으로 표시되지 않은 경우 구성 공급자 만들기의 단계를 따라 [활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)합니다.

## <a name="enter-a-new-free-text-invoice"></a>새 무료 텍스트 송장 입력

1. 무료 텍스트 송장을 추가하려면 [무료 텍스트 송장 만들기](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1)의 단계를 따르십시오.

    1. 송장에 한 줄을 추가합니다.
    2. 송장 라인에 대해 5개의 메모를 추가합니다.

    ![첨부 페이지에서 송장 라인 메모를 검토합니다.](./media/er-keep-excel-rows-together-notes.png)

2. [라인 복사](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines)의 단계에 따라 이전 단계에서 추가한 송장 라인을 복사하는 5개의 추가 송장 라인을 생성합니다.

    ![무료 텍스트 송장 페이지에서 무료 텍스트 송장 라인을 검토합니다.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>ER 프레임워크 구성

ER 프레임워크 구성의 단계에 따라 [ER 매개 변수의 최소 집합](er-quick-start2-customize-report.md#ConfigureFramework)을 설정합니다. ER 프레임워크를 사용하여 표준 ER 형식의 사용자 지정 버전을 디자인하기 시작하기 전에 이 설정을 완료해야 합니다.

## <a name="import-the-standard-er-format-configuration"></a>표준 ER 형식 구성 가져오기

[표준 ER 형식 구성 가져오기](er-quick-start2-customize-report.md#ImportERSolution1)의 단계에 따라 Dynamics 365 Finance의 현재 인스턴스에 표준 ER 구성을 추가합니다. 예를 들어 **무료 텍스트 송장(Excel)** 형식 구성의 버전 **252.116** 을 가져옵니다. 기본 **송장 모델** 구성의 기본 버전 **252** 는 필수 **송장 모델 매핑** 구성과 함께 저장소에서 자동으로 가져옵니다.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>표준 ER 형식을 사용하도록 인쇄 관리 설정

표준 ER 형식이 자유 텍스트 송장을 인쇄하는 데 사용되도록 [인쇄 관리 설정](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1)의 단계에 따라 **미수금** 모듈에 대한 인쇄 관리를 구성하십시오.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>표준 ER 형식에 대한 형식 대상 구성

[화면 미리 보기를 위한 형식 대상 구성](er-quick-start1-new-solution.md#ConfigureDestination)의 단계에 따라 생성된 보고서가 PDF 형식으로 변환되고 새 브라우저 탭에서 미리 볼 수 있도록 표준 ER 형식의 [화면](er-destination-type-screen.md) ER 대상을 구성합니다.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>표준 ER 형식을 사용하여 무료 텍스트 송장 인쇄

1. 표준 ER 형식을 사용하여 추가된 송장에 대해 Excel 형식의 무료 텍스트 송장 보고서를 생성하려면 [무료 텍스트 송장 인쇄](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1)의 단계를 따르십시오.
2. 생성된 Excel 통합 문서를 다운로드하고 Excel 데스크톱 애플리케이션에서 검토합니다.

    송장의 여섯 번째 행은 보고서의 첫 번째 페이지에서 시작하여 두 번째 페이지에서 계속됩니다. 마지막 메모는 두 번째 페이지에 나타나며 여섯 번째 송장 라인에 속하는지 명확하지 않습니다. 따라서 송장 라인의 내용 중간에 있는 페이지 나누기는 이 문서를 읽기 어렵게 만듭니다.

    ![Excel 데스크톱 애플리케이션에서 생성된 자유 텍스트 송장의 페이지 매김을 검토합니다.](./media/er-keep-excel-rows-together-invoice1.gif)

이 항목의 나머지 절차에서는 표준 ER 형식을 조정하여 단일 송장 라인에 대한 모든 콘텐츠를 동일한 페이지에 유지함으로써 송장 보고서의 모양과 가독성을 향상시키는 방법을 보여줍니다.

## <a name="create-a-custom-format"></a>사용자 지정 형식 만들기

[사용자 지정 형식 만들기](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat)의 단계에 따라 가져온 ER 형식에서 형식을 파생하고 편집 및 수정에 사용할 수 있는 **자유 텍스트 송장(Excel)** 사용자 지정 ER 구성을 만듭니다.

## <a name="edit-the-custom-format"></a>사용자 지정 형식 편집

1. [사용자 지정 형식 만들기](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat)의 단계에 따라 ER 형식 디자이너에서 편집할 파생된 ER 형식을 엽니다.
2. **형식 디자이너** 페이지의 왼쪽 창에 있는 형식 구성 요소 트리에서 **자유 텍스트 송장 \> 시트 \> InvoiceLines** 를 확장하고 **InvoiceLines_Values** 구성 요소를 선택합니다.
3. **서식** 탭에서 **행을 함께 유지** 옵션을 **예** 로 설정합니다.

    ![형식 디자이너 페이지에서 편집 가능한 ER 형식에 대해 행을 함께 유지 옵션을 설정합니다.](./media/er-keep-excel-rows-together-format.png)

4. **저장** 을 선택하고 페이지를 닫습니다.

## <a name="mark-the-custom-format-as-runnable"></a>사용자 지정 형식을 실행 가능한 것으로 표시

[사용자 지정 형식을 실행 가능한 것으로 표시](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable)의 단계에 따라 사용자 지정 ER 형식의 수정된 버전을 실행 가능하게 만드십시오.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>사용자 지정 ER 형식을 사용하도록 인쇄 관리 설정

[인쇄 관리 설정](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2)의 단계에 따라 **미수금** 모듈에 대한 인쇄 관리를 구성하여 사용자 지정 ER 형식을 사용하여 자유 텍스트 송장을 인쇄하도록 합니다.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>사용자 지정 ER 형식에 대한 형식 대상 구성

[화면 미리 보기를 위한 형식 대상 구성](er-quick-start1-new-solution.md#ConfigureDestination)의 단계에 따라 생성된 보고서가 PDF 형식으로 변환되고 새 브라우저 탭에서 미리 볼 수 있도록 사용자 지정 ER 형식의 **화면** ER 대상을 구성합니다.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>사용자 지정 ER 형식을 사용하여 무료 텍스트 송장 인쇄

1. 사용자 지정 ER 형식을 사용하여 추가된 송장에 대해 Excel 형식의 무료 텍스트 송장 보고서를 생성하려면 [무료 텍스트 송장 인쇄](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2)의 단계를 따르십시오.
2. 생성된 Excel 통합 문서를 다운로드하고 Excel 데스크톱 애플리케이션에서 검토합니다.

    송장의 여섯 번째 행은 두 번째 페이지에서 시작하고 이 송장 행을 나타내는 모든 Excel 행이 해당 페이지에 함께 나타납니다.

    ![Excel 데스크톱 애플리케이션에서 생성된 자유 텍스트 송장의 업데이트된 페이지 매김을 검토합니다.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>추가 리소스

[Excel 형식의 문서 생성을 위한 구성 설계](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
