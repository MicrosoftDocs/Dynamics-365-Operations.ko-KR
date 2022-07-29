---
title: PDF 템플릿을 채우기 위한 ER 구성 설계
description: 이번에는 PDF 템플릿을 채우기 위해 전자 보고(ER) 형식을 디자인하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: a568ddd93bfbc7d536e951a13470b3dedb796e1b
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460624"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>PDF 템플릿을 채우기 위한 ER 구성 설계

[!include[banner](../includes/banner.md)]

이 항목의 절차는 **시스템 관리자** 역할 또는 **전자 보고 개발자** 역할의 사용자가 채울 수 있는 PDF 문서를 보고서 템플릿으로 사용하여 보고서를 PDF 파일로 생성하는 전자 보고(ER) 형식을 구성하는 방법을 보여주는 예입니다. 이러한 단계는 Dynamics 365 Finance RCS(Regulatory Configuration Services)의 모든 회사에서 수행할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

시작하기 전에 이 항목의 절차를 완료하는 데 사용하는 서비스에 따라 다음 액세스 유형 중 하나가 있어야 합니다.

- 다음 역할 중 하나에 대한 재무 액세스:

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 다음 역할 중 하나에 대한 RCS 액세스:

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

또한 [구성 공급자 생성을 완료하고 활성 절차로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)해야 합니다.

마지막으로 다음 파일을 다운로드합니다.

| 콘텐츠 설명                       | 파일 이름                                     |
|-------------------------------------------|-----------------------------------------------|
| 보고서의 첫 페이지 템플릿 | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| 보고서의 다른 페이지용 템플릿    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| 샘플 ER 형식 - PDF                          | [통계 내 보고서(PDF).version.1.1.xml](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| 샘플 ER 형식 - Excel                          | [Intrastat(Excel에서 가져오기).version.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| 샘플 데이터세트                            | [통계 내 샘플 데이터.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>형식 구성 디자인

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Microsoft에서 제공하는 구성 목록에 액세스

1. **조직 관리 \> 작업 영역 \> 전자 보고** 로 이동합니다.
2. **Litware, Inc.** 공급자가 사용 가능하고 활성으로 표시되어 있는지 확인합니다.
3. **Microsoft** 공급자에 대한 타일에서 **리포지토리** 를 선택합니다.

    > [!NOTE]
    > **LCS** 유형의 저장소가 이미 있는 경우 이 절차의 나머지 단계를 건너뜁니다.

4. **추가** 를 선택합니다.
5. 드롭다운 대화 상자의 **구성 리포지토리 유형** 필드 그룹에서 **LCS** 옵션을 선택합니다.
6. **리포지토리 만들기** 를 선택합니다.
7. **확인** 을 선택합니다.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Microsoft에서 제공하는 모델 구성 가져오기

1. **구성 리포지토리** 페이지 왼쪽에서 **필터 표시** 버튼(깔때기 기호)을 선택합니다.
2. **유형** 필드에 **LCS** 값에 대한 필터를 추가하고 **시작** 연산자를 사용합니다.
3. **적용** 을 선택합니다.
4. **열기** 를 선택합니다.
5. 트리에서 **Intrastat 모델** 을 선택합니다.
6. **버전** FastTab에서 버전 **1** 을 선택합니다.

    > [!NOTE]
    > **버전** FastTab의 **가져오기** 버튼을 사용할 수 없는 경우 이 절차의 나머지 단계를 건너뜁니다.

7. **가져오기** 를 선택합니다.
8. **예** 를 선택하여 선택한 버전의 **Intrastat 모델** 모델 구성 가져오기를 확인합니다.

### <a name="create-a-new-format-configuration"></a>새 형식 구성 만들기

1. **전자 보고** 작업 영역에서 **보고 구성** 타일을 선택합니다.
2. 트리에서 **Intrastat 모델** 을 선택합니다.
3. **구성 만들기** 를 선택합니다.

    > [!NOTE]
    > **구성 생성** 버튼을 사용할 수 없는 경우 **전자 보고** 작업 공간에서 열 수 있는 **전자 보고** 매개 변수 페이지에서 디자인 모드를 켜야 합니다.

4. 드롭다운 대화 상자의 **새로 만들기** 필드 그룹에서 **데이터 모델 기반 형식 Intrastat** 옵션을 선택합니다.
5. **이름** 필드에 **Intrastat 보고서(PDF)** 를 입력합니다.
6. **설명** 필드에 **Intrastat 보고서를 PDF 형식** 으로 입력합니다.

    > [!NOTE]
    > 활성 구성 공급자가 자동으로 입력됩니다. 이 공급자는 이 구성을 유지할 수 있습니다. 다른 공급자가 이 구성을 사용할 수 있지만 유지 관리할 수는 없습니다.

7. 선택 과목: **형식 유형** 필드에서 전자 문서의 특정 형식을 선택할 수 있습니다. **PDF** 를 선택하면 디자인 타임에 ER Operations 디자이너가 PDF 형식(**PDF\File**, **PDF\PDF 병합** 등)으로 생성된 문서에만 적용할 수 있는 형식 요소만 제공합니다. 이 필드를 비워두면 첫 번째 형식 요소가 추가될 때 ER Operations 디자이너에서 디자인 타임에 전자 문서 형식이 지정됩니다. 예를 들어 **Excel\File** 을 첫 번째 형식 요소로 추가하면 ER Operations 디자이너는 Excel 형식(**Excel\Cell**, **Excel\Range** 등)으로 생성된 문서에만 적용할 수 있는 형식 요소만 제공합니다. 형식,
8. **구성 만들기** 를 선택합니다.

새 ER 형식 구성이 생성됩니다. 이 구성의 초안 버전을 사용하여 전자 문서를 PDF 형식으로 생성하도록 설계된 ER 형식 구성 요소를 저장할 수 있습니다.

### <a name="design-the-format-of-an-electronic-document"></a>전자 문서 형식 디자인

다음으로 생성한 ER 형식 구성에서 PDF 형식의 **Intrastat 제어** 보고서를 생성하는 ER 형식을 디자인합니다. 이 보고서의 첫 페이지에는 보고서의 요약과 보고된 대외 무역 거래의 세부 사항이 표시되어야 합니다. 다른 페이지에는 보고된 대외 무역 거래의 세부 사항만 표시되어야 합니다. 생성되는 보고서 페이지의 레이아웃이 달라야 하기 때문에 PDF 형식의 서로 다른 두 템플릿이 ER 형식으로 사용됩니다.

PDF 뷰어에서 다운로드한 PDF 템플릿을 엽니다. 각 템플릿에는 채워야 하는 여러 필드가 포함되어 있습니다. 각 템플릿에는 대외 무역 거래 기록이 42행으로 표시되며 각 행에는 9개의 필드가 있습니다. 행 번호는 각 필드 이름 끝에 나타납니다(예: **날짜 1**… **날짜 42** 및 **상품 1**… **상품 42**).

다음 그림은 보고서의 첫 페이지에 대한 PDF 템플릿을 보여줍니다.

![템플릿 1:](media/rcs-ger-filloutpdf-template1.png)

다음 그림은 보고서의 다른 페이지에 대한 PDF 템플릿을 보여줍니다.

![템플릿 2:](media/rcs-ger-filloutpdf-template2.png)

1. **구성** 페이지에서 **디자이너** 를 선택합니다.
2. **루트 추가** 를 선택합니다.
3. 드롭다운 대화 상자의 트리에서 **PDF \> PDF 병합** 을 선택합니다.

    **PDF 병합** 요소를 형식의 루트 요소로 선택하면 런타임에 생성된 모든 PDF 문서가 단일 최종 PDF 문서로 병합됩니다. 디자인한 ER 형식을 사용하여 필요한 모든 문서를 생성하기 위해 하나의 PDF 템플릿만 필요한 경우 루트 요소로 **PDF 파일** 을 선택할 수 있습니다.

4. **이름** 필드에 **출력** 을 입력합니다.
5. **언어 기본 설정** 필드에서 **사용자 기본 설정** 을 선택합니다. 보고서는 보고서를 실행하는 사용자가 선호하는 언어로 생성됩니다.
6. **문화권 기본 설정** 필드에서 **사용자 기본 설정** 을 선택하십시오. 보고서 페이지에 표시되는 값과 날짜는 보고서를 실행하는 사용자가 선호하는 로캘에 따라 형식이 지정됩니다.
7. **확인** 을 선택합니다.
8. 작업 창의 **가져오기** 탭에서 **PDF에서 가져오기** 를 선택합니다.

    채울 수 있는 PDF 문서를 이 ER 형식의 템플릿으로 가져오면 필요한 모든 ER 형식 요소(**PDF 파일**, **필드 그룹** 및 **필드** 요소)가 PDF 문서의 구조를 기반으로 설계된 형식으로 자동 생성됩니다. 수입되는 것입니다.

9. **찾아보기** 를 선택합니다. 이전에 전제 조건으로 다운로드한 **IntrastatReportTemplate1.pdf** 파일로 이동하여 선택합니다.
10. **확인** 을 선택합니다.

    선택한 파일이 로드되고 **PDF에서 가져오기** 대화 상자의 **템플릿** 필드가 채워집니다.

11. **그룹 필드** 옵션을 **예** 로 설정합니다. 선택한 PDF 문서에 필드 그룹이 포함되어 있으면 생성된 ER 형식 요소를 그룹화하는 데 사용됩니다. 이를 위해 **필드 그룹** 형식 요소가 생성됩니다.

    이 옵션을 **아니오** 로 설정하면 필수 ER 형식 요소가 생성된 **PDF 파일** 형식 요소 아래에 중첩된 단순 요소 목록으로 생성됩니다.

12. **확인** 을 선택합니다.

    ![PDF에서 가져오기 대화 상자.](media/rcs-ger-filloutpdf-importtemplate.png)

13. 트리에서 **출력** 을 확장합니다.

    **PDF 파일** 구성 요소는 런타임에 생성되는 보고서의 첫 번째 페이지 생성을 관리하기 위해 자동으로 생성되었습니다.

14. 트리에서 **PDF 파일 \> 출력** 을 확장합니다.

    형식 요소의 구조화된 목록은 이전에 가져온 채울 수 있는 PDF 문서의 구조를 기반으로 이 ER 형식으로 자동 생성되었습니다.

15. 트리에서 **PDF 파일 \> 출력** 을 선택합니다.
16. **이름** 필드에 **페이지 1** 을 입력합니다.

    이 형식 요소는 **Intrastat 제어** 보고서의 첫 번째 페이지를 생성하는 데 사용됩니다. 해당 페이지에는 보고서 요약 및 대외 무역 거래 세부 정보가 표시됩니다.

    **언어 기본 설정** 필드를 비워 두면 상위 **PDF 병합** 요소의 **언어 기본 설정** 에 따라 이 형식 요소를 사용하여 생성되는 보고서의 언어가 결정됩니다. 다른 값을 선택하여 상위 요소의 설정을 재정의할 수 있습니다.

    **문화권 기본 설정** 필드를 비워 두면 **상위 PDF 병합** 요소의 문화권 기본 설정에 따라 이 **형식 요소** 를 사용하여 생성되는 보고서의 로케일이 결정됩니다. 로캘은 보고서 페이지의 값 및 날짜 형식을 결정합니다. 다른 값을 선택하여 상위 요소의 설정을 재정의할 수 있습니다.

17. 작업 창에서 **가져오기** 탭을 선택합니다. **선택한 형식 요소인 PDF 파일에 대해 PDF에서 업데이트** 버튼을 **사용할** 수 있습니다.

    이 버튼을 사용하여 업데이트된 PDF 템플릿을 편집된 형식으로 가져올 수 있습니다. 업데이트된 PDF 템플릿을 가져오면 형식 요소 목록이 그에 따라 변경됩니다.

    - 업데이트된 PDF 템플릿의 새 필드에 대해 새 형식 요소가 편집된 ER 형식으로 생성됩니다.
    - 업데이트된 PDF 템플릿에 편집된 ER 형식의 기존 형식 요소에 해당하는 필드가 더 이상 포함되지 않으면 해당 형식 요소가 ER 형식에서 삭제됩니다.

18. **형식** 탭에서 **첨부 파일** 을 선택합니다.

    가져온 PDF 문서는 편집된 ER 형식에 첨부됩니다.

    ![PDF 첨부 파일 미리보기.](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. 두 번째 PDF 템플릿을 가져오고 데이터 소스에 필요한 바인딩을 추가하는 등의 방식으로 이 형식을 계속 디자인합니다.
20. **저장** 을 선택합니다.
21. 페이지를 닫습니다.
22. **삭제** 를 선택합니다.
23. **예** 를 선택합니다.

새로운 **PDF 병합**, **PDF 파일**, **필드 그룹** 및 **필드** 형식 요소를 사용하여 PDF 형식의 문서를 생성하는 방법을 배우려면 샘플 ER 형식을 가져와서 분석할 수 있습니다.

### <a name="import-the-format-configuration"></a>형식 구성 가져오기

다음으로 PDF 형식의 **Intrastat 제어** 보고서를 생성하기 위해 이전에 다운로드한 샘플 ER 형식을 가져옵니다. 보고서의 첫 페이지에는 보고서의 요약과 보고된 대외 무역 거래의 세부 사항이 표시되어야 합니다. 다른 페이지에는 보고된 대외 무역 거래의 세부 사항만 표시되어야 합니다.

1. **구성** 페이지에서 **XML 파일에서 \> Exchange 로드** 를 선택합니다.
2. **찾아보기** 를 선택합니다. 이전에 필수 구성 요소로 다운로드한 **Intrastat 보고서(PDF).version.1.1.xml** 파일로 이동하여 선택합니다.
3. **확인** 을 선택합니다.

## <a name="analyze-the-format-configuration"></a>형식 구성 분석

### <a name="format-layout"></a>형식 레이아웃

1. **구성** 페이지의 트리에서 **Intrastat 모델 \> Intrastat 보고서(PDF)** 를 선택합니다.
2. **디자이너** 를 선택합니다.
3. **세부 정보 표시** 를 선택합니다.
4. 트리에서 출력을 확장합니다. **PDF 합병**.

    이 ER 형식에는 각각 다른 PDF 템플릿을 사용하는 두 개의 **PDF 파일** 요소가 포함되어 있습니다. 하나의 템플릿은 보고서의 첫 페이지를 PDF 형식으로 생성하는 데 사용되고 다른 템플릿은 다른 페이지를 생성하는 데 사용됩니다.

5. 트리에서 출력을 확장합니다. **PDF 병합 \> 페이지 1: PDF 파일(IntrastatReportTemplate1)**.
6. 트리에서 출력을 확장합니다. **PDF 병합 \> 페이지 N: PDF 파일(IntrastatReportTemplate2)**.

    두 PDF 템플릿의 내용이 다르기 때문에 두 **PDF 파일** 요소에 대한 중첩 형식 요소의 구조도 다릅니다.

### <a name="format-mapping"></a>형식 매핑

1. **형식 디자이너** 페이지에서 **매핑** 탭을 선택합니다.
2. 트리에서 **페이징 \> 페이지** 를 확장합니다.

    ![모델 트리가 확장된 공식 디자이너 페이지입니다.](media/rcs-ger-filloutpdf-reviewformat.png)

    다음 세부정보를 참고하십시오.

    - **PDF 파일** 형식의 **출력 \> 페이지 1** 형식 요소는 데이터 소스에 바인딩되지 않으며 이 형식 요소의 **사용** 식은 비어 있습니다. 따라서 런타임 시 **IntrastatReportTemplate1** PDF 템플릿은 개별 PDF 문서가 생성될 때 한 번만 채워집니다.
    - **PDF 파일** 형식의 **출력 \> 페이지 N** 형식 요소는 **기록 목록** 형식의 **Paging.PageN** 데이터 소스에 바인딩되며 이 형식 요소의 **사용** 식은 비어 있습니다. 따라서 런타임 시 개별 PDF 문서가 생성될 때 바인딩된 기록 목록의 각 기록에 대해 **IntrastatReportTemplate2** PDF 템플릿이 채워집니다.
    - 왜냐하면 **1페이지: PDF 파일** 및 **페이지 N: PDF 파일** 형식 요소는 출력의 하위 요소입니다. **PDF 병합 형식** 요소, 채워진 모든 PDF 문서는 하나의 최종 PDF 문서로 병합됩니다.
    - **Paging.Page1** 및 **Paging.PageN** 데이터 원본은 **Paging.Pages** 데이터 원본의 기록 필터로 구성됩니다. 이 데이터 소스는 전체 대외 무역 거래를 일괄 처리로 분할하도록 구성됩니다. 각 배치에는 최대 42개의 기록이 포함됩니다. 다음 ER 표현식은 트랜잭션을 배치로 분할하는 데 사용됩니다.

        SPLITLIST(Totals.CommodityRecord,42)

    - **Paging.Pages** 데이터 원본에는 일괄 처리에 포함된 각 기록의 세부 정보를 반환하는 **Paging.Pages.Enumerated** 요소가 포함되어 있습니다. 이러한 세부 정보에는 현재 일괄 처리의 기록 시퀀스(**Paging.Pages.Enumerated.Number** 필드)가 포함됩니다. **Paging.Pages.Enumerated.Number** 필드는 일괄 처리의 트랜잭션 번호를 기반으로 하는 필드 **이름** 을 동적으로 생성하기 위해 **PDF 필드** 형식 요소의 이름 표현식에 사용됩니다. 생성된 필드 이름은 사용되는 PDF 템플릿의 올바른 PDF 필드를 채우는 데 사용됩니다.
    - **PDF 그룹** 유형의 **출력 \> 페이지 N \> 세부 사항 2** 형식 요소는 **기록 목록** 유형의 **Paging.PageN.Enumerated** 데이터 소스(또는 **상대 경로** 보기 모드가 사용되는 경우 **\@.Enumerated**)에 바인딩됩니다. 따라서 런타임에 이 PDF 그룹의 중첩 요소가 바인딩된 기록 목록의 각 기록에 대해 채워집니다. 이러한 방식으로 **Paging.PageN.Enumerated** 목록의 42개 기록 중 N번째 각각에 대해 다음 PDF 필드가 채워지면 개별 PDF 라인이 가상으로 생성됩니다. 날짜 N, 방향 N, 상품 N 등. 따라서 이 점에서 이 **필드 그룹** 형식 요소의 동작은 **XML \> 시퀀스** 및 **텍스트 \> 시퀀스** 형식 요소의 동작과 유사합니다.

3. 트리에서 **Output \> Page N \> Details2** 를 확장합니다.
4. 트리에서 **Output \> Page N \> Details2 \> PageFooter** 를 선택합니다.

    이 형식 요소의 **Name** 속성은 **PageFooter** 로 정의되어 있습니다. 또한 형식 요소의 **이름** 표현식이 비어 있음을 확인하십시오.

5. 트리에서 **출력 \> 페이지 N \> 세부 정보2 \> 수정 1** 을 선택합니다.

    이 형식 요소의 **이름** 속성은 **수정 1** 로 정의되어 있습니다. 또한 형식 요소의 **이름** 표현식이 **Paging.FldName('Correction',\@.Number)** 로 정의되어 있음을 주목하십시오.

![매핑이 선택된 형식 디자이너입니다.](media/rcs-ger-filloutpdf-reviewformat2.png)

**필드** 형식 요소는 상위 PDF 파일 형식 요소의 템플릿으로 정의된 채울 수 있는 **PDF 문서** 의 개별 필드를 채우는 데 사용됩니다. **PDF 파일** 형식 요소 또는 중첩된 요소의 바인딩은 중첩된 요소가 있는 경우 해당 PDF 필드에 입력되는 값을 지정합니다. **Field** 형식 요소의 다른 속성을 사용하여 개별 형식 요소로 채워지는 PDF 필드를 지정할 수 있습니다.

- **형식** 탭에서 형식 요소의 **이름** 속성
- **매핑** 탭에서 형식 요소의 **이름** 식

두 속성 모두 **필드** 형식 요소에 대해 선택 사항이므로 대상 PDF 필드를 지정하기 위해 다음 규칙이 적용됩니다.

- **Name** 속성이 비어 있고 **Name** 식이 런타임에 빈 스트링을 반환하는 경우 런타임에 예외가 발생하여 채우는 데 사용되는 PDF 템플릿에서 PDF 필드를 찾을 수 없음을 사용자에게 알립니다. PDF 문서.
- **Name** 속성이 정의되어 있고 **Name** 표현식이 비어 있으면 format 요소의 **Name** 속성과 이름이 같은 PDF 필드가 채워집니다.
- **Name** 속성이 정의되고 **Name** 표현식이 설정되면 format 요소의 **Name** 표현식이 반환하는 값과 동일한 이름의 PDF 필드가 채워진다.

> [!NOTE]
> PDF 확인란은 다음과 같은 방법으로 선택한 대로 채울 수 있습니다.
>
> - 해당 **Field** 형식 요소가 **True** 값을 갖는 **Boolean** 데이터 유형의 데이터 소스 필드에 바인딩된 경우
> - 해당 **필드** 형식 요소에 텍스트 값이 **1**, **True** 또는 **Yes** 인 데이터 소스 필드에 바인딩된 중첩된 **스트링** 형식 요소가 포함된 경우

## <a name="run-the-format-configuration"></a>형식 구성 실행

### <a name="import-the-format-configuration"></a>형식 구성 가져오기

다음으로 **Intrastat(Excel에서 가져오기)** 샘플 ER 형식을 로드합니다. 이 형식은 대외 무역 거래를 시뮬레이션하는 사용자 선택 Microsoft Excel 통합 문서를 구문 분석하도록 설계되었습니다.

1. **구성** 페이지에서 **XML 파일에서 \> Exchange 로드** 를 선택합니다.
2. **찾아보기** 를 선택합니다. 이전에 필수 구성 요소로 다운로드한 **Intrastat(Excel에서 가져오기).version.1.1.xml** 파일로 이동하여 선택합니다.
3. **확인** 을 선택합니다.
4. 트리에서 **Intrastat 모델 \> Intrastat(Excel에서 가져오기)** 를 선택합니다.
5. **편집** 을 선택합니다.
6. **모델 매핑에 대한 기본값** 옵션을 **예** 로 설정합니다.

    > [!NOTE]
    > 이전에 **Intrastat 모델** 구성 또는 **Intrastat 모델** 구성 아래에 중첩된 다른 구성에 대해 **모델 매핑에 대한 기본값** 옵션을 **예** 로 설정한 경우 이 옵션을 **아니요** 로 설정합니다.

    **모델 매핑에 대한 기본값** 옵션을 **예** 로 설정하면 가져온 **Intrastat(Excel에서 가져오기)** ER 형식이 **Intrastat 보고서(PDF)** 형식 구성에 대한 기본 데이터 소스로 할당됩니다. 이후 **Intrastat 보고서(PDF)** 형식 구성이 실행될 때 **Intrastat(Excel에서 가져오기)** ER 형식으로 구문 분석되는 Excel 통합 문서의 내용은 보고해야 하는 대외 무역 거래를 시뮬레이션합니다. 다음 그림은 Excel 통합 문서의 예를 보여줍니다.

    ![샘플 데이터가 있는 Excel 통합 문서.](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>형식 구성 실행

1. **구성** 페이지의 트리에서 **Intrastat 모델 \> Intrastat 보고서(PDF)** 를 선택합니다.
2. **실행** 을 선택합니다.
3. **찾아보기** 를 선택합니다. 이전에 전제 조건으로 다운로드한 **Intrastat 샘플 data.xlsx** 파일로 이동하여 선택합니다.
4. **확인** 을 선택합니다.
5. **보고서 방향** 필드에서 **모두** 를 선택하여 생성된 PDF 보고서에서 가져온 Excel 통합 문서의 모든 트랜잭션을 채웁니다.
6. **확인** 을 선택합니다.
7. 생성된 PDF 문서를 검토하십시오.

다음 그림은 생성된 보고서의 첫 번째 페이지에 대한 예를 보여줍니다.

![생성된 보고서의 첫 번째 페이지입니다.](media/rcs-ger-filloutpdf-generatedreport.png)

다음 그림은 생성된 보고서의 다른 페이지에 대한 예를 보여줍니다.

![생성된 보고서의 다른 페이지입니다.](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>한계

채울 수 있는 필드의 이름은 보고서 템플릿으로 사용하려는 PDF 양식에서 고유해야 합니다. 이러한 모든 필드에 대해 PDF 양식을 가져올 때 해당 이름을 가진 개별 형식 요소가 편집 가능한 ER 형식으로 생성됩니다. PDF 양식에 동일한 이름의 필드가 여러 개 포함되어 있는 경우 런타임에 개별적으로 입력할 수 없는 필드에 대해 단일 형식 요소가 생성됩니다.

## <a name="frequently-asked-questions"></a>자주 하는 질문

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>ER 형식을 실행하여 PDF 형식의 보고서를 생성할 때 다음 오류가 발생하는 이유는 무엇입니까?  **iref 스트림을 처리할 수 없습니다. 현재 구현된 PDFSharp에서는 Acrobat 6에 도입된 이 PDF 기능을 처리할 수 없습니다.** **PDF 이름은 슬래시(/)로 시작해야 합니다**.

ER 프레임워크는 PDFSharp 라이브러리 버전 1.5를 사용하여 이러한 PDF 보고서를 생성합니다. PDF 1.5(Adobe Reader 6.0)의 일부 기능은 아직 이 라이브러리에서 구현되지 않습니다. 따라서 PDFSharp는 아직 **PDF 1.5 이상** 으로 표시된 일부 파일을 열 수 없으며 수신된 오류가 발생할 수 있습니다. 다음 해결 방법 중 하나를 사용하여 문제를 해결하십시오.

-   자신의 PDF 템플릿을 사용하는 경우: 템플릿을 이전 Adobe 버전으로 다운그레이드하고 ER 형식의 새 템플릿 사용을 시작합니다.
-   ER 솔루션의 일부로 다른 구성 제공자가 공유한 ER 형식 템플릿을 사용하는 경우: 이 ER 솔루션의 소유자에게 연락하여 문제에 대한 설명을 제공하십시오.
-   이전 버전의 PDFSharp 라이브러리가 포함된 ISV 솔루션을 사용하는 경우: 솔루션 소유자에게 연락하여 최신 PDFSharp 버전으로의 업그레이드를 제안하십시오.

## <a name="additional-resources"></a>추가 리소스

- [ER OPENXML 형식의 보고서 생성을 위한 구성 설계(2016년 11월)](tasks/er-design-reports-openxml-2016-11.md)
- [Word 형식으로 보고서를 생성하도록 ER 구성 설계](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
