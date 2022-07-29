---
title: Excel에서 생성된 문서의 페이지를 매기기 위한 ER 형식 디자인
description: 이 항목에서는 Microsoft Excel에서 생성된 문서의 페이지를 매기는 전자 보고(ER) 형식을 디자인하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: Version 10.0.22
ms.openlocfilehash: ce29225c4bce24adc2abefc3d3d6f20774852af4
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "8461033"
---
# <a name="design-an-er-format-to-paginate-generated-documents-in-excel"></a>Excel에서 생성된 문서의 페이지를 매기기 위한 ER 형식 디자인

[!include [banner](../includes/banner.md)]

이 항목에서는 시스템 관리자 또는 전자 보고 기능 컨설턴트 역할의 사용자가 [전자 보고(ER)](general-electronic-reporting.md) 형식을 구성하여 Microsoft Excel에서 아웃바운드 문서를 생성하고 문서 페이지 매김을 관리하는 방법을 설명합니다.

이 예에서는 Intrastat 선언이 [생성](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md)되었을 때 제어 보고서를 인쇄하는 데 사용되는 Microsoft 제공 ER 형식을 수정합니다. 이 보고서를 통해 보고된 통계 내 거래를 관찰할 수 있습니다. 수정 사항을 통해 생성된 제어 보고서의 페이지 매김을 관리할 수 있습니다.

이 항목의 절차는 **DEMF** 회사에서 완료할 수 있습니다. 코딩이 필요하지 않습니다. 시작하기 전에 다음 파일을 다운로드하여 저장합니다.

| 설명       | 파일 이름 |
|-------------------|-----------| 
| 보고서 템플릿 1 | [ERIntrastatReportDemo1.xlsx](https://download.microsoft.com/download/7/2/a/72ae292a-8bb2-4b9d-8397-9764218f6fa8/ERIntrastatReportDemo1%20.xlsx) |
| 보고서 템플릿 2 | [ERIntrastatReportDemo2.xlsx](https://download.microsoft.com/download/7/d/1/7d15858d-6260-4afa-9dda-d8b955e59b1a/ERIntrastatReportDemo2.xlsx) |

## <a name="configure-the-er-framework"></a>ER 프레임워크 구성

ER 프레임워크 구성의 단계에 따라 [ER 매개 변수의 최소 집합](er-quick-start2-customize-report.md#ConfigureFramework)을 설정합니다. ER 프레임워크를 사용하여 표준 ER 형식의 사용자 지정 버전을 디자인하기 시작하기 전에 이 설정을 완료해야 합니다.

## <a name="import-the-standard-er-format-configuration"></a>표준 ER 형식 구성 가져오기

[표준 ER 형식 구성 가져오기](er-quick-start2-customize-report.md#ImportERSolution1)의 단계에 따라 Dynamics 365 Finance의 현재 인스턴스에 표준 ER 구성을 추가합니다. **Intrastat 보고서** 형식 구성의 버전 **1.9** 를 가져옵니다. 기본 **Intrastat 모델** 구성의 버전 1을 저장소에서 자동으로 가져옵니다.

## <a name="customize-the-standard-er-format"></a>표준 ER 형식 사용자 지정

### <a name="create-the-custom-er-format"></a>사용자 정의 ER 형식 만들기

이 시나리오에서 귀하는 현재 활성 ER 구성 제공자로 선택된 Litware, Inc.의 대표입니다. **통계 내 보고서** 구성을 기본으로 사용하여 새 ER 형식 구성을 생성해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **Intrastat 모델** 을 확장하고 **Intrastat 보고서** 를 선택합니다. Litware, Inc.는 이 ER 형식 구성의 버전 1.9를 사용자 지정 버전의 기반으로 사용합니다.
3. **구성 만들기** 를 선택하여 드롭다운 대화 상자를 엽니다. 이 대화 상자를 사용하여 사용자 지정 지불 형식에 대한 새 구성을 만들 수 있습니다.
4. **새로 만들기** 필드 그룹에서 **이름에서 파생: Intrastat 보고서, Microsoft** 를 선택합니다.
5. **이름** 필드에서 **Intrastat 보고서 Litware** 를 입력합니다.
6. **구성 만들기** 를 선택하여 새 형식을 생성합니다.

**Intrastat 보고서 Litware** ER 형식 구성의 버전 1.9.1이 생성됩니다. 이 버전은 **초안** [상태](general-electronic-reporting.md#component-versioning)이며 편집할 수 있습니다. 사용자 지정 ER 형식의 현재 내용은 Microsoft에서 제공하는 형식의 내용과 일치합니다.

### <a name="make-the-custom-format-runnable"></a>사용자 정의 형식을 실행 가능하게 만들기

이제 사용자 정의 형식의 첫 번째 버전이 만들어지고 상태가 **초안** 이 되었으므로 테스트 목적으로 형식을 실행할 수 있습니다. 보고서를 실행하려면 사용자 지정 ER 형식을 참조하는 지급 방법을 사용하여 공급 업체 지급을 처리하십시오. 기본적으로 애플리케이션에서 ER 형식을 호출할 때 상태가 **완료됨** 또는 **공유됨** 인 버전만 [고려됩니다](general-electronic-reporting.md#component-versioning). 이 동작은 미완성 디자인이 사용되는 ER 형식을 방지하는 데 도움이 됩니다. 그러나 테스트 실행의 경우 애플리케이션에서 상태가 **초안** 인 ER 형식 버전을 사용하도록 강제할 수 있습니다. 이러한 방식으로 수정이 필요한 경우 현재 형식 버전을 조정할 수 있습니다. 자세한 내용은 [적용 가능성](electronic-reporting-destinations.md#applicability)을 참조하십시오.

ER 형식의 초안 버전을 사용하려면 ER 형식을 명시적으로 표시해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **사용자 매개 변수** 대화 상자에서 **실행 설정** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
4. **편집** 을 선택하여 필요에 따라 현재 페이지를 편집 가능하게 만듭니다.
5. 왼쪽 창의 구성 트리에서 **Intrastat 보고서 Litware** 를 선택합니다.
6. **초안 실행** 옵션을 **네** 로 설정한 다음 **저장** 을 선택합니다.

    ![구성 페이지에서 초안 옵션을 실행합니다.](./media/er-paginate-excel-reports-derived-format-configuration.png)

## <a name="set-up-foreign-trade-parameters-to-use-the-custom-er-format"></a>사용자 정의 ER 형식을 사용하도록 대외 무역 매개변수 설정

사용자 정의 형식을 사용할 수 있도록 대외 무역 매개변수를 구성하려면 다음 단계를 따르세요.

1. **세금** \> **설정** \> **대외 무역** \> **대외 무역 매개 변수** 로 이동합니다.
2. **대외 무역 매개 변수** 페이지의 **전자 보고** 빠른 탭에서 **파일 형식 매핑** 필드의 **Intrastat 보고서 Litware** 를 선택합니다.
3. **보고서 형식 매핑** 필드에서 **Intrastat 보고서 Litware** 를 선택합니다.
4. **저장** 을 선택합니다.

## <a name="configure-the-custom-format-to-use-the-downloaded-report-template"></a>다운로드한 보고서 템플릿을 사용하도록 사용자 지정 형식 구성

### <a name="review-the-first-downloaded-excel-template"></a>첫 번째 다운로드한 Excel 템플릿 검토

1. Excel 데스크톱 응용 프로그램에서 이전에 다운로드한 **ERIntrastatReportDemo1.xlsx** 템플릿 파일을 엽니다.
2. 템플릿에 생성된 문서에 보고서 머리글, 보고서 세부 정보 및 보고서 바닥글 섹션을 만들기 위한 명명된 범위가 포함되어 있는지 확인합니다.

    ![데스크톱 응용 프로그램에서 Excel 템플릿 1의 레이아웃입니다.](./media/er-paginate-excel-reports-template1.gif)

### <a name="replace-the-current-excel-template-in-the-custom-er-format"></a><a id="replace-template"></a>사용자 지정 ER 형식의 현재 Excel 템플릿 바꾸기

사용자 지정 ER 형식에 새 Excel 템플릿을 추가해야 합니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지에서 왼쪽 창의 구성 트리에서 **Intrastat 모델** \> **Intrastat 보고서** 를 확장하고 **Intrastat 보고서 Litware** 구성을 선택합니다.
3. **디자이너** 를 선택합니다.
4. **형식 디자이너** 페이지의 작업 창에서 **세부 정보 표시** 를 선택합니다.
5. **Intrastat: Excel** 루트 형식 구성 요소를 선택했는지 확인한 다음 작업 창에서 **가져오기** 탭의 **가져오기** 그룹에서 **Excel에서 업데이트** 를 선택합니다.
6. **Excel에서 업데이트** 대화 상자에서 **템플릿 업데이트** 를 선택합니다.
7. **열기** 대화 상자에서 이전에 다운로드한 **ERIntrastatReportDemo1.xlsx** 파일을 찾아 선택한 다음 **열기** 를 선택합니다.
8. **확인** 을 선택합니다.
9. **저장** 을 선택합니다.

![새 Excel 템플릿이 추가된 후 ER 형식 디자이너의 형식 구조입니다.](./media/er-paginate-excel-reports-format1.png)

## <a name="change-the-data-binding-to-show-the-item-description-on-a-generated-report"></a>생성된 보고서에 항목 설명을 표시하도록 데이터 바인딩 변경

1. **형식 디자이너** 페이지에서 **매핑** 탭을 선택합니다.
2. **Intrastat** \> **보고서 라인** 을 확장하고 **상품 코드** 구성 요소를 선택합니다.
3. **수식 편집** 을 선택합니다.
4. 바인딩 수식을 `@.CommodityCode`에서 `CONCATENATE(@.CommodityCode, " ", @.ProductName)`로 변경합니다.
5. **저장** 을 선택합니다.

![ER 형식 디자이너에서 항목 설명을 표시하기 위해 구성된 바인딩입니다.](./media/er-paginate-excel-reports-format1a.png)

## <a name="generate-an-intrastat-declaration-control-report"></a><a id="generate-intrastat-control-report"></a>Intrastat 선언 제어 보고서 생성

먼저, **Intrastat** 페이지에서 보고를 위한 Intrastat 트랜잭션이 있는지 확인합니다.

![Intrastat 페이지의 거래.](./media/er-paginate-excel-reports-transactions1.gif)

그런 다음 사용자 정의 ER 형식을 사용하여 Intrastat 선언의 제어 보고서를 생성합니다.

1. **세금** \> **신고** \> **해외 무역** \> **Intrastat** 으로 이동합니다.
2. **Intrastat** 페이지의 작업 창에서 **출력** \> **보고서** 를 선택합니다.
3. **Intrastat 보고서** 대화 상자에서 보고서를 실행하려면 다음 단계를 따르세요.

    1. 보고서에 특정 Intrastat 거래를 포함하도록 **시작 날짜** 및 **종료 날짜** 필드를 설정합니다.
    2. **파일 생성** 옵션을 **아니요** 로 설정합니다.
    3. **보고서 생성** 옵션을 **예** 로 설정합니다.
    4. **확인** 을 선택합니다.

4. 생성된 문서를 다운로드하여 저장합니다.
5. Excel에서 문서를 열고 검토합니다.

    ![데스크톱 애플리케이션에서 생성된 Excel 문서.](./media/er-paginate-excel-reports-document1.png)

## <a name="configure-the-custom-format-to-paginate-generated-documents"></a>생성된 문서에 페이지를 매기기 위한 사용자 정의 형식 구성

### <a name="review-the-second-downloaded-excel-template"></a>두 번째 다운로드한 Excel 템플릿 검토

1. Excel에서 이전에 다운로드한 **ERIntrastatReportDemo2.xlsx** 템플릿 파일을 엽니다.
2. 이 템플릿을 **ERIntrastatReportDemo1.xlsx** 템플릿과 비교하고 생성된 문서에서 페이지별 섹션을 만들고 채우기 위한 몇 가지 새 Excel 이름이 포함되어 있는지 확인합니다.

    - **ReportPageHeader** 범위가 추가되어 페이지 헤더를 생성합니다.
    - **ReportPageFooter** 범위가 추가되어 페이지 바닥글을 생성합니다.
    - **ReportPageFooter\_PageLines** 셀은 페이지당 트랜잭션 수를 표시하도록 구성됩니다.
    - **ReportPageFooter\_PageAmount** 셀은 페이지당 트랜잭션의 총 금액을 표시하도록 구성됩니다.
    - **ReportPageFooter\_PageWeight** 셀은 페이지당 트랜잭션의 총 무게를 표시하도록 구성됩니다.
    - **ReportPageFooter\_RunningCounterLines** 셀은 보고서 시작부터 현재 페이지까지 트랜잭션의 실행 카운터를 표시하도록 구성됩니다.
    - **ReportPageFooter\_RunningTotalAmount** 셀은 보고서 시작부터 현재 페이지까지 모든 트랜잭션에 대한 실행의 총 금액을 표시하도록 구성됩니다.
    - **ReportPageFooter\_RunningTotalWeight** 셀은 보고서 시작부터 현재 페이지까지 트랜잭션에 대한 실행의 총 무게를 표시하도록 구성됩니다.

    ![데스크톱 응용 프로그램에서 Excel 템플릿 2의 레이아웃입니다.](./media/er-paginate-excel-reports-template2a.gif)

    이 템플릿의 **CommodityCode** 셀은 셀 텍스트를 줄 바꿈하도록 구성되어 있습니다. 트랜잭션 세부 정보 행은 자동으로 행 높이에 맞게 구성되어 있기 때문에 **CommodityCode** 셀의 텍스트가 래핑될 때 전체 행 높이가 자동으로 변경되어야 합니다.

    ![셀 텍스트를 래핑하도록 구성된 CommodityCode 셀입니다.](./media/er-paginate-excel-reports-template2b.gif)

### <a name="repeat-the-replacement-of-the-current-excel-template-in-the-custom-er-format"></a>사용자 지정 ER 형식의 현재 Excel 템플릿 바꾸기 반복

1. 이 토픽의 [사용자 지정 ER 형식의 현재 Excel 템플릿 바꾸기](#replace-template) 섹션에 있는 단계를 따르세요. 그러나 7단계에서 **ERIntrastatReportDemo2.xlsx** 파일을 선택합니다.
2. **형식 디자이너** 페이지에서 **Intrastat** 을 확장합니다.
3. 적용된 Excel 템플릿의 구조와 구조를 동기화하기 위해 편집 가능한 ER 형식에 추가된 [범위](er-fillable-excel.md#range-component) 형식 구성 요소의 이름을 지정합니다.

    1. Excel 이름 **ReportPageHeader** 와 연결된 **범위** 구성 요소를 선택합니다.
    2. **형식** 탭의 **이름** 필드에 **보고서 페이지 헤더** 를 입력합니다.
    3. Excel 이름 **ReportPageFooter** 와 연결된 **범위** 구성 요소를 선택합니다.
    4. **형식** 탭의 **이름** 필드에 **보고서 페이지 바닥글** 을 입력합니다.

4. **저장** 을 선택합니다.

![Excel 템플릿이 바뀐 후 ER 형식 디자이너의 형식 구조입니다.](./media/er-paginate-excel-reports-format2.png)

### <a name="change-the-format-structure-to-implement-document-pagination"></a>문서 페이지 매김을 구현하도록 형식 구조 변경

1. **형식 디자이너** 페이지의 왼쪽 창에 있는 형식 트리에서 **Intrastat** 루트 구성 요소를 선택합니다.
2. **추가** 를 선택합니다.
3. **추가** 대화 상자에서 구성 요소의 **Excel** 그룹에 있는 [페이지](er-fillable-excel.md#page-component) 구성 요소를 선택합니다.
4. **구성 요소 속성** 대화 상자의 **이름** 필드에 **보고서 페이지** 를 입력합니다. 그런 다음 **확인** 을 선택합니다.
5. **보고서 페이지 헤더** 구성 요소를 생성된 모든 페이지의 페이지 헤더로 사용하려면 다음 단계를 따르세요.

    1. **보고서 페이지 헤더** 구성 요소를 선택한 다음 **자르기** 를 선택합니다.
    2. **보고서 페이지** 구성 요소를 선택한 다음 **붙여넣기** 를 선택합니다.
    3. **보고서 페이지** 를 확장합니다.
    4. **페이지** 구성 요소가 이 범위를 페이지 헤더로 [고려](er-fillable-excel.md#page-component-structure)하도록 하려면 **보고서 페이지 헤더** 를 선택한 다음 **형식** 탭의 **복제 방향** 필드에서 **복제 없음** 을 선택합니다.

6. 보고서 라인의 내용이 고려되도록 생성된 문서에 페이지를 매기려면 다음 단계를 따르세요.

    1. **보고서 라인** 구성 요소를 선택한 다음 **자르기** 를 선택합니다.
    2. **보고서 페이지** 구성 요소를 선택한 다음 **붙여넣기** 를 선택합니다.

7. 보고서 라인 뒤에 보고서 바닥글을 포함하되 마지막 페이지 바닥글 앞에 포함하려면 다음 단계를 따르세요.

    1. **보고서 바닥글** 구성 요소를 선택한 다음 **자르기** 를 선택합니다.
    2. **보고서 페이지** 구성 요소를 선택한 다음 **붙여넣기** 를 선택합니다.

8. **보고서 페이지 바닥글** 구성 요소를 생성된 모든 페이지의 페이지 바닥글로 사용하려면 다음 단계를 따르세요.

    1. **보고서 페이지 바닥글** 구성 요소를 선택한 다음 **자르기** 를 선택합니다.
    2. **보고서 페이지** 구성 요소를 선택한 다음 **붙여넣기** 를 선택합니다.
    3. **페이지** 구성 요소가 이 범위를 페이지 바닥글로 [고려](er-fillable-excel.md#page-component-structure)하도록 하려면 **보고서 페이지 바닥글** 을 선택한 다음 **형식** 탭의 **복제 방향** 필드에서 **복제 없음** 을 선택합니다.

![문서 페이지 매김이 구현된 후 ER 형식 디자이너의 형식 구조입니다.](./media/er-paginate-excel-reports-format3.png)

### <a name="add-data-sources-to-calculate-page-footer-totals"></a>페이지 바닥글 합계를 계산하기 위해 데이터 소스 추가

페이지 합계, 누적 카운터 및 누적 합계 값을 계산하고 페이지 바닥글 섹션에 표시하려면 새 데이터 원본을 구성해야 합니다. 이 목적으로 [데이터 수집](er-data-collection-data-sources.md) 데이터 원본을 사용하는 것이 좋습니다.

1. **형식 디자이너** 페이지에서 **매핑** 탭을 선택합니다.
2. **루트 추가** 를 선택하고 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **일반** 섹션에서 **빈 컨테이너** 를 선택합니다.
    2. **'빈 컨테이너' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **합계** 를 입력합니다.
    3. **확인** 을 선택합니다.

3. **합계** 데이터 원본을 선택하고 **추가** 를 선택한 후 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **일반** 섹션에서 **빈 컨테이너** 를 선택합니다.
    2. **'빈 컨테이너' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **페이지** 를 입력합니다.
    3. **확인** 을 선택합니다.

4. **추가** 를 다시 선택하고 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **일반** 섹션에서 **빈 컨테이너** 를 선택합니다.
    2. **'빈 컨테이너' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **실행 중** 을 입력합니다.
    3. **확인** 을 선택합니다.

5. **Total.Page** 데이터 원본을 선택하고 **추가** 를 선택한 후 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **함수** 섹션에서 **데이터 수집** 을 선택합니다.
    2. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **금액** 을 입력합니다.
    3. **항목 유형** 필드에서 **실제** 를 선택하십시오.
    4. **모든 값 수집** 옵션을 **네** 로 설정합니다.
    5. **확인** 을 선택합니다.

6. **추가** 를 다시 선택하고 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **함수** 섹션에서 **데이터 수집** 을 선택합니다.
    2. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **무게** 를 입력합니다.
    3. **항목 유형** 필드에서 **실제** 를 선택하십시오.
    4. **모든 값 수집** 옵션을 **네** 로 설정합니다.
    5. **확인** 을 선택합니다.

7. **Total.Running** 데이터 원본을 선택하고 **추가** 를 선택한 후 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **함수** 섹션에서 **데이터 수집** 을 선택합니다.
    2. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **금액** 을 입력합니다.
    3. **항목 유형** 필드에서 **실제** 를 선택하십시오.
    4. **모든 값 수집** 필드를 **네** 로 설정합니다.
    5. **확인** 을 선택합니다.

8. **추가** 를 다시 선택하고 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **함수** 섹션에서 **데이터 수집** 을 선택합니다.
    2. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **무게** 를 입력합니다.
    3. **항목 유형** 필드에서 **실제** 를 선택하십시오.
    4. **모든 값 수집** 필드를 **네** 로 설정합니다.
    5. **확인** 을 선택합니다.

9. **추가** 를 다시 선택하고 다음 단계를 따르세요.

    1. **데이터 원본 추가** 대화 상자의 **함수** 섹션에서 **데이터 수집** 을 선택합니다.
    2. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **라인** 을 입력합니다.
    3. **항목 유형** 필드에서 **정수** 를 선택합니다.
    4. **모든 값 수집** 필드를 **네** 로 설정합니다.
    5. **확인** 을 선택합니다.

10. **저장** 을 선택합니다.

### <a name="add-data-sources-to-control-page-footer-visibility"></a>페이지 바닥글 공개 설정을 제어하기 위해 데이터 소스 추가

페이지 바닥글 가시성을 제어할 계획이고 마지막 페이지에 트랜잭션이 포함된 경우 바닥글을 포함하지 않으려는 경우 필요한 실행 카운터를 계산하도록 새 데이터 원본을 구성합니다.

1. **형식 디자이너** 페이지에서 **매핑** 탭을 선택합니다.
2. **Total.Running** 데이터 원본을 선택하고 **추가** 를 선택합니다.
3. **데이터 원본 추가** 대화 상자의 **함수** 섹션에서 **데이터 수집** 을 선택합니다.
4. **'데이터 수집' 데이터 원본 속성** 대화 상자의 **이름** 필드에 **라인2** 를 입력합니다.
5. **항목 유형** 필드에서 **정수** 를 선택합니다.
6. **모든 값 수집** 옵션을 **네** 로 설정합니다.
7. **확인** 을 선택합니다.
8. **저장** 을 선택합니다.

![ER 형식 디자이너에 데이터 소스를 추가했습니다.](./media/er-paginate-excel-reports-format4.png)

### <a name="configure-bindings-to-collect-total-values"></a>총 값을 수집하도록 바인딩 구성

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서 라인** 구성 요소를 확장하고 중첩된 **송장 값** 구성 요소를 선택합니다.
2. **수식 편집** 을 선택합니다.
3. 바인딩 수식을 `NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", "")`에서 `Total.Page.Amount.Collect(NUMBERVALUE(NUMBERFORMAT(@.InvoiceValue, "F"&TEXT(model.Parameters.IntrastatAmountDecimals)), ".", ""))`로 변경합니다.

    > [!NOTE]
    > 모든 반복 트랜잭션에 대해 Excel 셀에 금액 값을 넣는 것 외에도 이 바인딩은 데이터 컬렉션 **Total.Page.Amount** 데이터 원본의 값을 수집합니다.

4. 중첩된 **무게** 구성 요소를 선택합니다.
5. **수식 편집** 을 선택합니다.
6. 바인딩 수식을 `@.'$RoundedWeight'`에서 `Total.Page.Weight.Collect(@.'$RoundedWeight')`로 변경합니다.

    > [!NOTE]
    > 모든 반복 트랜잭션에 대해 Excel 셀에 무게 값을 넣는 것 외에도 이 바인딩은 **Total.Page.Weight** 데이터 원본의 값을 수집합니다.

![ER 형식 디자이너에서 총 값을 수집하기 위해 구성된 바인딩입니다.](./media/er-paginate-excel-reports-format5.png)

### <a name="configure-bindings-to-fill-in-page-footer-totals"></a>페이지 바닥글 합계를 채우도록 바인딩 구성

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서 페이지 바닥글** 구성 요소를 확장하고 Excel **ReportPageFooter\_PageAmount** 셀을 참조하는 중첩된 **범위** 구성 요소를 선택하고 다음 단계를 따르세요.

    1. 오른쪽 창의 데이터 소스 트리에서 **Total.Page.Amount.Sum()** 항목을 선택합니다.
    2. **바인딩** 을 선택합니다.
    3. **수식 편집** 을 선택합니다.
    4. 수식을 `Total.Page.Amount.Sum(false)`으로 업데이트합니다.

    > [!NOTE]
    > 이 함수의 인수를 **거짓** 으로 지정하여 현재 페이지에 대해 수집된 데이터를 유지해야 합니다. 이 데이터는 누적 총량, 페이지당 총 라인 수 및 라인의 실행 카운터를 계산하기 위해 필요하기 때문입니다.

2. 형식 트리에서 Excel **ReportPageFooter\_PageWeight** 셀을 참조하는 중첩된 **범위** 구성 요소를 선택하고 다음 단계를 따르세요.

    1. 오른쪽 창의 데이터 소스 트리에서 **Total.Page.Weight.Sum()** 항목을 선택합니다.
    2. **바인딩** 을 선택합니다.
    3. **수식 편집** 을 선택합니다.
    4. 수식을 `Total.Page.Weight.Sum(false)`으로 업데이트합니다.

### <a name="configure-bindings-to-fill-in-page-running-totals"></a>실행 중인 페이지 합계를 채우도록 바인딩 구성

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서 페이지 바닥글** 구성 요소를 확장하고 Excel **ReportPageFooter\_RunningTotalAmount** 셀을 참조하는 중첩된 **범위** 구성 요소를 선택하고 다음 단계를 따르세요.

    1. 오른쪽 창의 데이터 소스 트리에서 **Total.Running.Amount.Collect()** 항목을 선택합니다.
    2. **바인딩** 을 선택합니다.
    3. **수식 편집** 을 선택합니다.
    4. 수식을 `Total.Running.Amount.Sum(false)+Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))`으로 업데이트합니다.

    > [!NOTE]
    > `Total.Running.Amount.Sum(false)` 피연산자는 이전에 수집된 누적 합계를 반환합니다. `Total.Running.Amount.Collect(Total.Page.Amount.Sum(true))` 피연산자는 현재 페이지의 총량을 반환합니다. 두 번째 피연산자의 중첩 함수 인수를 **True** 로 지정하여 이 값이 `Total.Running.Amount` 실행 중인 총 컬렉션에 입력되는 즉시 `Total.Page.Amount` 데이터 수집을 재설정해야 합니다. 지정된 인수는 0(영) 값에서 다음 페이지 합계를 수집하기 시작해야 합니다.
    >
    > `Total.Running.Amount.Sum(false)` 함수는 현재 페이지의 Excel **ReportPageFooter\_RunningTotalAmount** 셀에서 실행 중인 총 금액을 입력하도록 호출됩니다.

2. 형식 트리에서 Excel **ReportPageFooter\_RunningTotalWeight** 셀을 참조하는 중첩된 **범위** 구성 요소를 선택하고 다음 단계를 따르세요.

    1. 오른쪽 창의 데이터 소스 트리에서 **Total.Running.Weight.Collect()** 항목을 선택합니다.
    2. **바인딩** 을 선택합니다.
    3. **수식 편집** 을 선택합니다.
    4. 수식을 `Total.Running.Weight.Sum(false)+Total.Running.Weight.Collect(Total.Page.Weight.Sum(true))`으로 업데이트합니다.

### <a name="configure-bindings-to-fill-in-the-page-running-counter"></a>실행 중인 페이지 카운터를 채우도록 바인딩 구성

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서 페이지 바닥글** 구성 요소를 확장하고 Excel **ReportPageFooter\_RunningCounterLines** 셀을 참조하는 중첩된 **범위** 구성 요소를 선택합니다.
2. **수식 편집** 을 선택합니다.
3. 수식 `Total.Running.Lines.Collect(COUNT(Total.Page.Amount.Result))`를 추가합니다.

    > [!NOTE]
    > 이 수식은 전체 보고서에 대해 수집된 금액 값의 수를 반환합니다. 이 숫자는 현재 순간에 반복된 트랜잭션의 수와 같습니다. 동시에 수식은 **Total.Running.Lines** 컬렉션에서 반환된 값을 수집합니다.

### <a name="configure-bindings-to-fill-in-the-page-footer-counter"></a>페이지 바닥글 카운터를 채우도록 바인딩 구성

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서 페이지 바닥글** 구성 요소를 확장하고 Excel **ReportPageFooter\_PageLines** 셀을 참조하는 중첩된 **범위** 구성 요소를 선택합니다.
2. **수식 편집** 을 선택합니다.
3. 수식 `COUNT(Total.Page.Amount.Result)-Total.Running.Lines.Sum(false)`를 추가합니다.

    > [!NOTE]
    > 이 공식은 전체 보고서의 **Total.Page.Amount.Result** 에서 수집된 거래 수와 **Total.Running.Lines.Sum** 의 이 단계에 저장된 거래 수 사이의 차이로 현재 페이지의 거래 수를 계산합니다. 현재 페이지에 대한 트랜잭션 수가 Excel **ReportPageFooter\_RunningCounterLines** 셀을 참조하는 **범위** 구성 요소의 바인딩에서 **Total.Running.Lines** 에 저장되므로 현재 페이지의 트랜잭션 수가 아직 포함되지 않았습니다. 따라서 이 차이는 현재 페이지의 트랜잭션 수와 같습니다.

![ER 형식 디자이너에서 페이지 바닥글 카운터를 채우기 위해 구성된 바인딩입니다.](./media/er-paginate-excel-reports-format6.png)

### <a name="configure-component-visibility"></a>구성 요소 가시성 구성

생성된 문서의 특정 페이지에서 페이지 머리글 및 바닥글의 가시성을 변경하여 다음 요소를 숨길 수 있습니다.

- 보고서 머리글에 이미 열 제목이 포함되어 있으므로 첫 번째 페이지의 페이지 머리글
- 마지막 페이지에서 발생할 수 있는 트랜잭션이 없는 페이지의 페이지 헤더
- 마지막 페이지에서 발생할 수 있는 트랜잭션이 없는 페이지의 페이지 바닥글

가시성을 변경하려면 **보고서 페이지 헤더** 및 **보고서 페이지 바닥글** 구성 요소의 **활성화됨** 특성을 업데이트합니다.

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서 페이지** 구성 요소를 확장하고 중첩된 **보고서 페이지 헤더** 구성 요소를 선택하고 다음 단계를 따르세요.

    1. **활성화됨** 필드에서 **편집** 을 선택합니다.
    2. **수식 디자이너** 페이지의 **수식** 필드에 다음 표현식을 입력합니다.

        `AND(`<br>
        `COUNT(Total.Page.Amount.Result)<>0,`<br>
        `COUNT(Total.Page.Amount.Result)<>COUNT(model.CommodityRecord)`<br>
        `)`

2. 형식 트리에서 중첩된 **보고서 페이지 바닥글** 구성 요소를 선택하고 다음 단계를 따르세요.

    1. **활성화됨** 필드에서 **편집** 을 선택합니다.
    2. **수식 디자이너** 페이지의 **수식** 필드에 다음 표현식을 입력합니다.

        `(`<br>
        `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)+`<br>
        `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result))`<br>
        `)<>0`

    > [!NOTE]
    > `COUNT(Total.Page.Amount.Result)-Total.Running.Lines2.Sum(false)` 구성은 현재 페이지의 트랜잭션 수를 계산하는 데 사용됩니다. `0*Total.Running.Lines2.Collect(COUNT(Total.Page.Amount.Result)` 구성은 다음 페이지 바닥글의 가시성을 올바르게 처리하기 위해 현재 페이지의 트랜잭션 수를 컬렉션에 추가하는 데 사용됩니다.
    >
    > `Total.Running.Lines` 컬렉션은 중첩된 구성 요소의 바인딩이 처리 **후** 에 기본 구성 요소의 **활성화됨** 속성이 처리되므로 여기에서 다시 사용할 수 없습니다. **활성화됨** 속성이 처리되면 `Total.Running.Lines` 컬렉션은 현재 페이지의 트랜잭션 수만큼 이미 증가했습니다.

3. **저장** 을 선택합니다.

## <a name="generate-an-intrastat-declaration-control-report-updated"></a>Intrastat 선언 제어 보고서 생성(업데이트됨)

1. **Intrastat** 페이지에서 24 트랜잭션이 있는지 확인합니다. 이 토픽의 [Intrastat 선언 제어 보고서 생성](#generate-intrastat-control-report)의 단계를 반복하여 제어 보고서를 생성하고 검토하려면 이 항목의 섹션을 참조하세요.

    모든 거래는 첫 페이지에 표시됩니다. 페이지 합계 및 카운터는 보고서 합계 및 카운터와 같습니다. 보고서 머리글에 이미 열 제목이 포함되어 있으므로 첫 번째 페이지의 페이지 머리글 범위가 숨겨집니다. 페이지 머리글과 바닥글은 해당 페이지에 트랜잭션이 없기 때문에 두 번째 페이지에서 숨겨집니다.

    ![데스크톱 애플리케이션에서 생성된 Excel 문서.](./media/er-paginate-excel-reports-document2.gif)

2. **D00006** 에서 **L0010** 으로 **품목 번호** 코드를 변경하여 **Intrastat** 페이지의 거래 두 개를 업데이트합니다. 새 항목의 제품 이름 **액티브 스테레오 스피커 쌍** 이 원래 항목의 제품 이름 **표준 스피커** 보다 깁니다. 이 상황은 생성된 문서의 해당 셀에서 텍스트 줄 바꿈을 강제 실행합니다. 문서 페이지 매김, 페이지 관련 합계 및 계산은 이제 업데이트되어야 합니다. [Intrastat 선언 제어 보고서 생성](#generate-intrastat-control-report)의 단계를 반복하여 제어 보고서를 생성하고 검토하려면 이 항목의 섹션을 참조하세요.

    현재 거래는 두 페이지에 표시되며 페이지 총계와 카운터가 올바르게 계산됩니다. 페이지 헤더 범위는 첫 번째 페이지에서 올바르게 숨겨지고 두 번째 페이지에서 보입니다. 페이지 바닥글은 트랜잭션을 포함하기 때문에 두 페이지 모두에서 볼 수 있습니다.

    ![데스크톱 애플리케이션에서 생성된 Excel 문서 업데이트됨.](./media/er-paginate-excel-reports-document3.gif)

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="is-there-any-way-to-recognize-when-the-final-page-is-processed-by-the-page-format-component"></a>페이지 형식 구성 요소에서 최종 페이지를 처리하는 시점을 알 수 있는 방법이 있습니까?

**페이지** 구성 요소는 처리된 페이지 수와 생성된 문서의 총 페이지 수에 대한 정보 [공개하지 않습니다](er-fillable-excel.md#page-component-limitations). 그럼에도 불구하고 ER [수식](er-formula-language.md)을 구성하여 마지막 페이지를 인식할 수 있습니다. 다음은 예입니다.

- **보고서 페이지** 구성 요소를 사용하여 이미 처리된 총 트랜잭션 수를 계산합니다. 수식 `COUNT(Total.Page.Amount.Result)`를 사용하여 이 계산을 수행할 수 있습니다. 
- **보고서 라인** 구성 요소에 구성된 `model.CommodityRecord` 바인딩을 기반으로 처리해야 하는 총 트랜잭션 수를 계산합니다. 수식 `COUNT(model.CommodityRecord)`를 사용하여 이 계산을 수행할 수 있습니다.
- 두 숫자를 비교하여 마지막 페이지를 인식합니다. 두 값이 같으면 최종 페이지가 생성됩니다.

> [!NOTE]
> **보고서 라인** 구성 요소의 **활성화됨** 속성이 바인딩된 [레코드 목록](er-formula-supported-data-types-composite.md#record-list)의 반복된 [레코드](er-formula-supported-data-types-composite.md#record) 중 일부에 대해 런타임 시 [거짓](er-formula-supported-data-types-primitive.md#boolean)ㅇ르 반환할 수 있는 수식을 포함하지 않은 경우에만 이 방식을 사용하는 것이 좋습니다.

## <a name="additional-resources"></a>추가 리소스

- [Excel 형식의 문서 생성을 위한 구성 설계](er-fillable-excel.md)
- [전자 보고(ER) 형식의 데이터 수집 데이터 원본 사용](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
