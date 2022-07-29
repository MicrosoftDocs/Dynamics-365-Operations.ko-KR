---
title: Power BI에 데이터를 가져오도록 전자 보고(ER) 구성
description: 이 주제에서는 전자 보고(ER) 구성을 사용하여 인스턴스에서 Power BI 서비스로 데이터 전송을 정렬하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: aa9a47c9ee7c76322fd2d9bfcf5fc61a50bf421321891b3c78a782be6a9f8e6a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460660"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Power BI에 데이터를 가져오도록 전자 보고(ER) 구성

[!include [banner](../includes/banner.md)]

이 주제에서는 전자 보고(ER) 구성을 사용하여 인스턴스에서 Power BI 서비스로 데이터 전송을 정렬하는 방법에 대해 설명합니다. 예를 들어 이 항목에서는 Intrastat 트랜잭션을 전송해야 하는 비즈니스 데이터로 사용합니다. Power BI 지도 시각화는 이 Intrastat 트랜잭션 데이터를 사용하여 Power BI 보고서에서 회사 수입/수출 활동 분석을 위한 보기를 제공합니다.

## <a name="overview"></a>개요

Microsoft Power BI는 외부 데이터 소스를 일관되고 시각적으로 몰입할 수 있는 대화형 통찰력으로 전환하기 위해 함께 작동하는 소프트웨어 서비스, 앱 및 커넥터의 모음입니다. 전자 보고(ER)를 통해 사용자는 데이터 소스를 쉽게 구성하고 애플리케이션에서 Power BI로 데이터 전송을 정렬할 수 있습니다. 데이터는 OpenXML 워크시트(Microsoft Excel 통합 문서 파일) 형식의 파일로 전송됩니다. 전송된 파일은 해당 용도로 구성된 Microsoft SharePoint 서버에 저장됩니다. 저장된 파일은 시각화(표, 차트, 지도 등)를 포함하는 보고서를 만들기 위해 Power BI에서 사용됩니다. Power BI 보고서는 Power BI 사용자와 공유되며 Power BI 대시보드 및 애플리케이션 페이지에서 액세스합니다. 이 항목에서는 다음 작업에 대해 설명합니다.

- Microsoft Dynamics 365 Finance를 구성합니다.
- 재무 애플리케이션에서 데이터를 가져오려면 ER 형식 구성을 준비합니다.
- Power BI에 데이터를 전송할 ER 환경을 구성합니다.
- 전송된 데이터를 사용하여 Power BI 보고서를 만듭니다.
- 재무에서 Power BI 보고서에 액세스할 수 있게 합니다.

## <a name="prerequisites"></a>전제 조건
이 주제의 예를 완료하려면 다음 액세스 권한이 있어야 합니다.

- 다음 역할 중 하나에 대한 액세스:

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 애플리케이션과 함께 사용하도록 구성된 SharePoint 서버에 액세스
- Power BI 프레임워크에 액세스

## <a name="configure-document-management-parameters"></a>문서 관리 매개 변수 구성
1. **문서 관리 매개 변수** 페이지에서 로그인한 회사(이 예에서는 DEMF 회사)에서 사용할 SharePoint 서버에 대한 액세스를 구성합니다.
2. SharePoint 서버에 대한 연결을 테스트하여 액세스 권한이 부여되었는지 확인합니다.

    [![문서 관리 매개 변수 페이지.](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. 구성된 SharePoint 사이트를 엽니다. ER이 Power BI보고서가 Power BI 데이터세트의 소스로 필요한 비즈니스 데이터가 있는 Excel 파일을 저장할 새 폴더를 만듭니다.
4. **문서 유형** 페이지에서 방금 만든 SharePoint 폴더에 액세스하는 데 사용할 새 문서 유형을 만듭니다. **그룹** 필드에 **파일** 을 입력하고 **위치** 필드에 **SharePoint** 를 입력한 다음 SharePoint 폴더의 주소를 입력합니다.

    [![문서 유형 페이지.](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>ER 매개 변수 구성
1. **전자 보고** 작업 영역에서 **전자 보고 매개 변수** 링크를 클릭합니다.
2. **첨부 파일** 탭에서 모든 필드에 **파일** 문서 유형을 선택합니다.
3. **전자 보고** 작업 영역에서 **활성으로 설정** 을 클릭하여 필요한 공급자를 활성화합니다. 자세한 내용은 **ER 서비스 제공업체 선택** 작업 가이드를 재생하세요.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>ER 데이터 모델을 데이터 소스로 사용
Power BI 보고서에 사용될 비즈니스 데이터의 소스로 ER 데이터 모델이 있어야 합니다. 이 데이터 모델은 ER 구성 저장소에서 업로드됩니다. 자세한 내용은 [Lifecycle Services에서 전자 보고 구성 다운로드](download-electronic-reporting-configuration-lcs.md)를 참조하거나 **ER Lifecycle Services에서 구성 가져오기** 작업 안내를 재생하세요. **Intrastat** 을 선택한 ER 구성 리포지토리에서 업로드될 데이터 모델로 선택합니다. (이 예에서는 모델의 버전 1이 사용됩니다.) 그런 다음 **구성** 페이지에서 **Intrastat** ER 모델 구성에 액세스할 수 있습니다.

[![구성 페이지의 Intrastat ER 모델 구성입니다.](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>ER 형식 구성 디자인
**Intrastat** 데이터 모델을 비즈니스 데이터의 소스로 사용하는 새 ER 형식 구성을 생성해야 합니다. 이 형식 구성은 출력 결과를 OpenXML(Excel 파일) 형식의 전자 문서로 생성해야 합니다. 자세한 내용은 **ER OPENXML 형식의 보고서에 대한 구성 생성** 작업 가이드를 재생하세요. 다음 그림과 같이 새 구성 이름 **활동 가져오기/내보내기** 를 지정합니다. ER 형식을 디자인할 때 [ER 데이터 - 가져오기 및 내보내기 세부 정보](https://download.microsoft.com/download/f/7/5/f755c0fd-025c-4aa9-920b-909abb8302ad/ER-data-import-and-export-details.xlsx) Excel 파일을 템플릿으로 사용합니다. (형식 템플릿을 가져오는 방법에 대한 정보는 작업 가이드를 재생하세요.)

[![가져오기/내보내기 활동 구성.](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

**내보내기/가져오기 활동** 형식 구성을 수정하려면 다음 단계를 따르세요.

1. **디자이너** 를 클릭합니다.
2. **형식** 탭에서 이 형식 **Excel 출력 파일** 의 파일 요소 이름을 지정합니다.

    [![Excel 출력 파일 요소입니다.](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. **매핑** 탭에서 이 형식이 실행될 때마다 생성될 Excel 파일의 이름을 지정합니다. 관련 표현식을 구성하여 **세부 정보 가져오기 및 내보내기**(.xlsx 파일 이름 확장자는 자동으로 추가됨) 값을 반환합니다.

    [![형식 디자이너.](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. 이 형식에 대한 새 데이터 소스 항목을 추가합니다. (이 열거는 추가 데이터 바인딩에 필요합니다.)

    1. 데이터 원본 **방향\_enum** 이름을 지정합니다.
    2. **데이터 모델 열거** 데이터 소스 유형으로 선택합니다.
    3. **방향** 데이터 모델 열거를 참조합니다.

    [![방향 열거형.](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. **Intrastat** 데이터 모델의 요소 및 다음 그림과 같이 설계된 형식의 데이터 모델 바인딩을 완료합니다.

    [![바인딩을 완료합니다.](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

실행 후 ER 형식은 출력 결과를 Excel 형식으로 생성합니다. Intrastat 트랜잭션의 세부 정보를 출력 결과로 보내고 가져오기 활동 또는 내보내기 활동을 설명하는 트랜잭션으로 분리합니다. **실행** 을 클릭하여 **Intrastat** 페이지의 Intrastat 거래 목록에 대해 새로운 ER 형식을 테스트합니다(**세금** &gt; **선언** &gt; **대외 무역** &gt; **Intrastat**).

[![Intrastat 페이지.](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

다음 출력 결과가 생성됩니다. 형식 설정에서 지정한 대로 파일 이름이 **가져오기 및 내보내기 details.xlsx** 가 됩니다.

[![가져오기 및 내보내기 details.xlsx.](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>ER 대상 구성
새로운 ER 형식 구성의 출력 결과를 특별한 방식으로 보내도록 ER 프레임워크를 구성해야 합니다.

- 출력 결과는 선택한 SharePoint 서버의 폴더로 보내야 합니다.
- 형식 구성을 실행할 때마다 동일한 Excel 파일의 새 버전이 생성되어야 합니다.

**전자 보고** 페이지에서(**조직 관리** &gt; **전자 보고**) **전자 보고 대상** 항목을 클릭하고 새 대상을 추가합니다. **참조** 필드에서 이전에 만든 **가져오기/내보내기 활동** 형식 구성을 선택합니다. 참조용으로 새 파일 대상 레코드를 추가하려면 다음 단계를 따르세요.

1. **이름** 필드에 파일 대상의 제목을 입력합니다.
2. **파일 이름** 필드에서 Excel 파일 형식 구성 요소의 **Excel 출력 파일** 이름을 선택합니다.

새 대상 레코드에 대한 **설정** 버튼을 클릭합니다. 그런 다음 **대상 설정** 대화 상자에서 다음 단계를 따르세요.

1. **Power BI** 탭에서 **활성화됨** 옵션을 **네** 로 설정합니다.
2. **SharePoint** 필드에서 이전에 만든 **공유됨** 문서 유형을 선택합니다.

## <a name="schedule-execution-of-the-configured-er-format"></a>구성된 ER 형식의 실행 예약
1. **구성** 페이지에서(**조직 관리** &gt; **전자 보고** &gt; **구성**) 구성 트리에서 이전에 만든 **가져오기/내보내기 활동** 구성을 선택합니다.
2. 버전 1.1의 상태를 **초안** 에서 **완료** 로 변경하여 이 형식을 사용할 수 있도록 합니다.

    [![구성 페이지에서 활동 구성 가져오기/내보내기.](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. 완성된 버전의 **가져오기/내보내기 활동** 구성을 선택한 다음 **실행** 을 클릭합니다. 설정한 대상은 Excel 형식으로 생성된 출력 결과에 적용된다는 점에 유의하세요.
4. **일괄 처리** 옵션을 **네** 로 설정하여 무인 모드에서 이 보고서를 실행합니다.
5. **되풀이** 를 클릭하여 이 일괄 실행의 필수 반복을 예약합니다. 반복은 업데이트된 데이터가 Power BI로 전송되는 빈도를 정의합니다.

    [![전자 보고서 매개변수 대화 상자.](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. 구성된 후 **일괄 작업** 페이지에서 ER 보고서 실행 작업을 찾을 수 있습니다(**시스템 관리 &gt; 문의 &gt; 일괄 작업**).

    [![일괄 작업 페이지.](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. 이 작업을 처음 실행할 때 대상은 선택한 SharePoint 폴더에서 구성된 이름을 가진 새 Excel 파일을 만듭니다. 이후에 작업이 실행될 때마다 대상은 이 Excel 파일의 새 버전을 생성합니다.

    [![Excel 파일의 새 버전.](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>ER 형식의 출력 결과를 사용하여 Power BI 데이터 세트 만들기
1. Power BI에 로그인하고 기존 Power BI 그룹(작업 공간)을 열거나 새 그룹을 만듭니다. **가져오기 또는 데이터에 연결** 의 **파일** 에서 **추가** 를 클릭하거나 왼쪽 창의 **데이터세트** 옆의 더하기 기호(**+**)를 클릭합니다.

    [![데이터 세트 만들기.](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. **SharePoint 선택 – 팀 사이트** 옵션을 선택한 다음 사용 중인 SharePoint 서버의 경로를 입력합니다(이 예이서 `https://ax7partner.litware.com`).
3. **/Shared Documents/GER data/PowerBI** 폴더를 찾고 생성한 Excel 파일을 새로운 Power BI 데이터 세트에 대한 데이터 원본으로 선택합니다.

    [![Excel 파일을 선택합니다.](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. **연결** 을 클릭한 다음 **가져오기** 를 클릭합니다. 선택한 Excel 파일을 기반으로 하는 새 데이터 세트가 생성됩니다. 데이터 세트는 새로 생성된 대시보드에 자동으로 추가될 수도 있습니다.

    [![대시보드의 데이터세트입니다.](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. 이 데이터 세트에 대한 새로 고침 일정을 구성하여 주기적 업데이트를 강제 실행합니다. 주기적 업데이트를 통해 SharePoint 서버에서 생성된 새 버전의 Excel 파일을 통해 ER 보고서의 주기적 실행을 통해 제공되는 새로운 비즈니스 데이터를 사용할 수 있습니다.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>새 데이터세트를 사용하여 Power BI 보고서 만들기
1. 생성한 **세부 정보 가져오기 및 내보내기** Power BI 데이터세트를 클릭합니다.
2. 시각화를 구성합니다. 예를 들어 **등치 지역도** 시각화를 선택하고 다음과 같이 구성합니다.

    - **CountryOrigin** 데이터 세트 필드를 지도 시각화의 **위치** 필드에 할당합니다.
    - **금액** 데이터 세트 필드를 지도 시각화의 **색 채도** 필드에 할당합니다.
    - **활동** 및 **연도** 데이터세트 필드를 지도 시각화의 **필터** 필드 컬렉션에 추가합니다.

3. Power BI 보고서를 **세부 정보 보고서 가져오기 및 내보내기** 로 저장합니다.

    [![가져오기 및 내보내기 세부정보 보고서.](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    지도는 Excel 파일에 언급된 국가/지역을 보여줍니다(이 예에서는 오스트리아와 스위스). 이러한 국가/지역은 색상이 지정되어 각각에 대해 청구된 금액의 비율을 보여줍니다.

4. Intrastat 거래 목록을 업데이트합니다. 이탈리아에서 시작된 수출 거래가 추가됩니다.

    [![Intrastat 거래 목록.](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. ER 보고서의 다음 예약된 실행 및 Power BI 데이터 세트의 다음 예약 업데이트를 기다립니다. 그런 다음 Power BI 보고서를 검토합니다(가져오기 거래만 표시하려면 선택). 업데이트된 지도에는 이제 이탈리아가 표시됩니다.

    [![업데이트된 지도.](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>재무에서 Power BI 보고서에 액세스
Power BI와 통합 설정 자세한 내용은 [작업 영역용 Power BI 통합](configure-power-bi-integration.md)을 참조하세요.

1. Power BI 통합을 지원하는 **전자 보고** 작업 공간 페이지에서(**조직 관리** &gt; **작업 공간** &gt; **전자 보고 작업 공간**) **옵션** &gt; **보고서 카탈로그 열기** 를 클릭합니다.
2. 생성한 **세부 정보 가져오기 및 내보내기** Power BI 보고서를 선택하여 선택한 페이지에서 해당 보고서를 작업 항목으로 표시합니다.
3. 작업 항목을 클릭하여 Power BI에서 디자인한 보고서를 표시하는 페이지를 엽니다.

    [![Power BI에서 디자인한 가져오기 및 내보내기 세부정보 보고서.](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>추가 리소스

[전자 보고(ER) 대상](electronic-reporting-destinations.md)

[전자 보고(ER) 개요](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
