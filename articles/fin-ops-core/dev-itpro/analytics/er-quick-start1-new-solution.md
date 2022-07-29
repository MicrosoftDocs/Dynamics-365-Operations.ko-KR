---
title: 맞춤형 보고서를 인쇄하기 위한 새로운 ER 솔루션 설계
description: 이 항목에서는 사용자 지정 보고서를 인쇄하기 위한 전자 보고(ER) 솔루션을 설계하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "220314"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 36998d299e166709778bfaa7bfd0d8980890d4fe
ms.sourcegitcommit: d5d6b81bd8b08de20cc018c2251436065982489e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8460675"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>맞춤형 보고서를 인쇄하기 위한 새로운 ER 솔루션 설계

[!include[banner](../includes/banner.md)]

다음 단계는 시스템 관리자, 전자 보고 개발자 또는 전자 보고 기능 컨설턴트 역할의 사용자가 ER 프레임워크의 매개변수를 구성하고 특정 비즈니스 도메인의 데이터에 액세스하기 위해 새 ER 솔루션의 필수 ER 구성을 설계하는 방법 및 Microsoft Office 형식으로 사용자 정의 보고서를 생성하는 방법을 설명합니다. 이 단계는 **USMF** 회사에서 완료할 수 있습니다.

- [ER 프레임워크 구성](#ConfigureFramework)

    - [ER 매개 변수 구성](#ConfigureParameters)
    - [ER 구성 공급자 활성화](#ActivateProvider)

        - [ER 구성 제공자 목록 검토](#ReviewProvidersList)
        - [새 ER 구성 공급자 추가](#AddProvider)
        - [ER 구성 공급자 활성화](#ActivateAddedProvider)

- [도메인별 데이터 모델 설계](#DesignModel)

    - [새 데이터 모델 구성 가져오기](#ImportDataModel)
    - [새 데이터 모델 구성 만들기](#DesignDataModel)

        - [데이터 모델 이름 지정](#NameDataModel)
        - [데이터 모델 필드 추가](#FieldsEntry)
        - [데이터 모델 설계 완료](#CompleteDataModel)

- [구성된 데이터 모델에 대한 모델 매핑 설계](#DesignMapping)

    - [새 모델 매핑 구성 가져오기](#ImportModelMapping)
    - [새 모델 매핑 구성 만들기](#CreateModelMapping)

        - [새 모델 매핑 구성 요소 설계](#DesignMappingComponent)
        - [애플리케이션 테이블에 액세스할 데이터 소스 추가](#AddMmDataSource1)
        - [애플리케이션 열거에 액세스할 데이터 소스 추가](#AddMmDataSource2)
        - [ER 레이블을 추가하여 지정된 언어로 보고서 생성](#AddMmLabels)
        - [열거형 값을 텍스트 값과 비교한 결과를 변환하는 데이터 소스 추가](#AddMmDataSource3)
        - [데이터 모델 필드에 데이터 소스 바인딩](#AddMmBindings1)
        - [모델 매핑 설계 완료](#CompleteModelMapping)

- [사용자 지정 보고서용 템플릿 디자인](#DesignReportTemplate)
- [형식 디자인](#DesignFormat)

    - [디자인된 형식 구성 가져오기](#FormatImport)
    - [새 형식 구성 만들기](#FormatCreate)

        - [보고서 템플릿 가져오기](#ImportReportTemplate)
        - [형식 구성](#ConfigureFormat)
        - [보고서 제목에 대한 데이터 바인딩 정의](#DefineFormatBindings)
        - [모델 데이터 소스 검토](#ReviewModelDataSource)
        - [데이터 소스 필드에 형식 요소 바인딩](#BindFormatElements)

    - [ER에서 디자인된 형식 실행](#RunFormatFromER)

- [디자인된 형식 조정](#TuneFormat)

    - [생성된 문서의 이름을 변경하는 형식 수정](#ModifyToChangeName)
    - [질문 순서를 변경하는 형식 수정](#ModifyToOrder)
    - [ER에서 수정된 형식 실행](#RunFormatFromER2)
    - [형식 디자인 완료](#CompleteFormat)

- [설계된 보고서를 호출하는 애플리케이션 아티팩트 개발](#DevelopCustomCode)

    - [소스 코드 수정](#ModifySourceCode)

        - [데이터 계약 클래스 추가](#DataContractClass)
        - [UI 빌더 클래스 추가](#UIBuilderClass)
        - [데이터 공급자 클래스 추가](#DataProviderClass)
        - [레이블 파일 추가](#LabelsFile)
        - [보고서 서비스 클래스 추가](#ServiceClass)
        - [보고서 컨트롤러 클래스 추가](#ControllerClass)
        - [메뉴 항목 추가](#MenuItem)
        - [메뉴에 메뉴 항목 추가](#Menu)
        - [Visual Studio 프로젝트 빌드](#BuildVSProject)

    - [응용 프로그램에서 형식 실행](#RunFormatFromApp)

- [설계된 ER 솔루션 조정](#TuneSolution)

    - [모델 매핑 수정](#ModifyModelMapping)

        - [데이터 계약 개체에 액세스할 데이터 소스 추가](#AddDataSource1)
        - [ER 형식 매핑 레코드에 액세스하기 위한 데이터 소스 추가](#AddDataSource2)
        - [실행 중 ER 형식의 형식 매핑 레코드에 액세스하기 위한 데이터 소스 추가](#AddDataSource3)
        - [데이터 모델에 실행 중인 ER 형식의 이름 입력](#AddBinding)
        - [모델 매핑 설계 완료](#CompleteModelMapping2)

    - [형식 수정](#ModifyFormat)

        - [새 형식 요소 추가](#AddFormatElement)
        - [추가된 형식 요소 바인딩](#BindAddedFormatElement)
        - [형식 디자인 완료](#CompleteFormat2)

    - [응용 프로그램에서 형식 실행](#RunFormatFromApp2)
    - [ER에서 형식 실행](#RunFormatFromER3)
    - [화면 미리 보기를 위한 형식 대상 구성](#ConfigureDestination)
    - [응용 프로그램에서 형식을 실행하여 PDF 문서로 미리 보기](#RunFormatFromApp3)

- [추가 리소스](#References)

이 예에서는 [설문지](../../../human-resources/hr-learning-questionnaires.md) 모듈에 대한 새 ER 솔루션을 생성합니다. 이 새로운 ER 솔루션을 사용하면 Microsoft Excel 워크시트를 템플릿으로 사용하여 보고서를 디자인할 수 있습니다. 그런 다음 기존 SSRS(SQL Server Reporting Services) 보고서를 생성하는 것 외에도 Excel 또는 PDF 형식으로 **설문지** 보고서를 작성할 수 있습니다. 요청 시 나중에 새 보고서를 수정할 수도 있습니다. 코딩이 필요하지 않습니다.

1. 기존 보고서를 실행하려면 **설문지** \> **설계** \> **설문 보고서** 로 이동합니다.

    ![설문 모듈에서 설문 보고서 메뉴 항목을 선택하여 기존 SSRS 보고서를 실행합니다.](./media/er-quick-start1-application-menu-origin.png)

2. **설문 보고서** 대화 상자에서 선택 기준을 지정합니다. 보고서에 **SBCCrsExam** 설문지만 포함되도록 필터를 적용합니다.

    ![설문 보고서 대화 상자에서 선택 기준 지정.](./media/er-quick-start1-ssrs-report-dialog.png)

다음 그림은 **SBCCrsExam** 설문지에 대해 생성된 버전의 SSRS 보고서를 보여줍니다.

![생성된 SSRS 보고서.](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>ER 프레임워크 구성

전자 보고 개발자 역할의 사용자는 ER 프레임워크를 사용하여 새 ER 솔루션을 설계하기 시작하기 전에 최소 ER 매개변수 집합을 구성해야 합니다.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>ER 매개 변수 구성

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **전자 보고** 작업 영역에서 **전자 보고 매개 변수** 를 선택합니다.
3. **전자 보고 매개변수** 페이지의 **일반** 탭에서 **디자인 모드 활성화** 옵션을 **네** 로 설정합니다.
4. **첨부** 탭에서 다음 매개 변수를 설정합니다.

    - **구성** 필드를 **USMF** 회사의 **파일** 로 설정합니다.
    - **작업 아카이브**, **임시**, **기준선** 및 **기타** 필드를 **파일** 로 설정합니다.

ER 매개 변수에 대한 자세한 내용은 [ER 프레임워크 구성](electronic-reporting-er-configure-parameters.md)을 참조하세요.

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>ER 구성 공급자 활성화

모든 ER 구성은 ER 구성 공급자가 소유한 것으로 표시됩니다. 따라서 ER 구성을 추가하거나 편집하기 전에 **전자 보고** 작업 영역에서 ER 구성 공급자를 활성화해야 합니다.

> [!NOTE]
> ER 구성의 소유자만 편집할 수 있습니다. 따라서 ER 구성을 편집하기 전에 **전자 보고** 작업 영역에서 적절한 ER 구성 공급자를 활성화해야 합니다.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>ER 구성 공급자 목록 검토

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **전자 보고** 작업 영역의 **관련 링크** 섹션에서 **구성 공급자** 를 선택합니다.
3. **구성 공급자** 페이지에서 각 구성 공급자 레코드에는 고유한 이름과 URL이 있습니다. 이 페이지의 내용을 검토하세요. **Litware, Inc.**(`https://www.litware.com`)의 레코드가 이미 존재하는 경우 다음 절차를 건너뛰고, [새 ER 구성 공급자를 추가](#ActivateProvider)합니다.

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>새 ER 구성 공급자 추가

1. **구성 공급자** 페이지에서 **새로 만들기** 를 선택합니다.
2. **이름** 필드에서 **Litware, Inc.** 를 입력합니다.
3. **인터넷 주소** 필드에 `https://www.litware.com`을 입력합니다.
4. **저장** 을 선택합니다.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>ER 구성 공급자 활성화

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **전자 보고** 작업 공간에서 **Litware, Inc.** 구성 공급자를 선택합니다.
3. **활성으로 설정** 을 선택합니다.

ER 구성 공급자에 대한 자세한 내용은 [구성 공급자를 만들고 활성으로 표시](tasks/er-configuration-provider-mark-it-active-2016-11.md)를 참조하세요.

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>도메인별 데이터 모델 설계

**설문지** 비즈니스 도메인에 대한 데이터 모델 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 이 데이터 모델은 ER 형식을 설계하여 **설문지** 보고서를 생성하면 나중에 데이터 소스로 사용됩니다.

[새 데이터 모델 구성 가져오기](#ImportDataModel) 섹션의 단계를 완료하여 제공된 XML 파일에서 필요한 데이터 모델을 가져올 수 있습니다. 또는 [새 데이터 모델 구성 만들기](#DesignDataModel) 섹션의 단계를 완료하여 이 데이터 모델을 처음부터 설계할 수 있습니다.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>새 데이터 모델 구성 가져오기

1. [설문지 model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. 작업 창에서 **XML 파일에서** \> **Exchange 로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **설문지 model.version.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

계속하려면 다음 절차를 건너뛰고 [새 데이터 모델 구성을 만듭니다](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>새 데이터 모델 구성 만들기

1. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
2. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
3. **구성 만들기** 를 선택합니다.
4. 드롭다운 대화 상자의 **이름** 필드에 **설문지 모델** 을 입력합니다.
5. **구성 만들기** 를 선택하여 구성을 생성합니다.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>데이터 모델 이름 지정

1. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 선택합니다.
2. **디자이너** 를 선택합니다.
3. **데이터 모델 디자이너** 페이지에서 **일반** 빠른 탭의 **이름** 필드에 <a name="DataModeName"></a>**설문지** 를 입력합니다.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>새 데이터 모델 필드 추가

1. **데이터 모델 디자이너** 페이지에서 **새로 만들기** 를 선택합니다.
2. 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **모델 루트** 를 새 노드의 유형으로 선택합니다.
    2. **이름** 필드에 <a name="RootDefinitionName"></a>**루트** 를 입력합니다.
    3. **추가** 를 선택하여 새 노드를 추가합니다.

    이 루트 설명자는 **설문지** 보고서에 대한 데이터를 제공하는 데 사용됩니다. 단일 데이터 모델에는 여러 설명자가 있을 수 있습니다. 보고서를 생성하는 데 필요한 데이터를 식별하기 위해 단일 ER 형식에 대해 각 설명자를 지정할 수 있습니다.

3. **새로 만들기** 를 다시 선택한 다음 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **활성 노드의 하위** 을 새 노드의 유형으로 선택합니다.
    2. **이름** 필드에 **CompanyName** 을 입력합니다.
    3. **항목 유형** 필드에서 **스트링** 을 선택하십시오.
    4. **추가** 를 선택하여 새 필드를 추가합니다.

    이 필드는 이 데이터 모델을 데이터 소스로 사용하는 ER 보고서에 현재 회사 이름을 전달하는 데 필요합니다.

4. **새로 만들기** 를 다시 선택한 다음 데이터 모델 노드를 추가하기 위한 드롭다운 대화 상자에서 다음 단계를 수행합니다.

    1. **활성 노드의 하위** 을 새 노드의 유형으로 선택합니다.
    2. **이름** 필드에 **설문지** 를 입력합니다.
    3. **항목 유형** 필드에서 **기록 목록** 을 선택하십시오.
    4. **추가** 를 선택하여 새 필드를 추가합니다.

    이 필드는 이 데이터 모델을 데이터 소스로 사용하는 ER 보고서에 설문지 목록을 전달하는 데 사용됩니다.

5. **설문지** 노드를 선택합니다.
6. 다음 데이터 모델 구조를 완료할 때까지 동일한 방식으로 편집 가능한 데이터 모델의 필수 필드를 계속 추가합니다.

    | 필드 경로                                                    | 데이터 형식   | 필드명/반환값 |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | 루트                                                          |             | 설문 데이터를 요청하는 기준점입니다. |
    | 루트\\CompanyName                                             | 문자열      | 현재 회사 이름입니다. |
    | 루트\\ExecutionContext                                        | 레코드      | 형식 실행 세부 정보. |
    | 루트\\ExecutionContext\\FormatName                            | 문자열      | 실행 중인 ER 형식의 이름입니다. |
    | 루트\\설문지                                           | 레코드 목록 | 설문지 목록 |
    | 루트\\설문지\\활성                                   | 문자열      | 현재 설문지의 상태. |
    | 루트\\설문지\\코드                                     | 문자열      | 현재 설문지의 코드. |
    | 루트\\설문지\\설명                              | 문자열      | 현재 설문지의 설명. |
    | 루트\\설문지\\QuestionnaireType                        | 문자열      | 현재 설문지의 유형. |
    | 루트\\설문지\\QuestionOrder                            | 문자열      | 현재 설문지의 번호 순서. |
    | 루트\\설문지\\ResultsGroup                             | 레코드      | 현재 설문지의 결과 매개 변수. |
    | 루트\\설문지\\ResultsGroup\\코드                       | 문자열      | 현재 결과 그룹의 식별 코드. |
    | 루트\\설문지\\ResultsGroup\\설명                | 문자열      | 현재 결과 그룹의 설명. |
    | 루트\\설문지\\ResultsGroup\\MaxNumberOfPoints          | 실수        | 획득할 수 있는 최대 포인트 수입니다. |
    | 루트\\설문지\\질문                                 | 레코드 목록 | 현재 질문에 대한 질문 목록입니다. |
    | 루트\\설문지\\질문\\CollectionSequenceNumber       | 정수     | 현재 답변 컬렉션의 시퀀스 번호입니다. |
    | 루트\\설문지\\질문\\Id                             | 문자열      | 현재 질문의 식별 코드. |
    | 루트\\설문지\\질문\\MustBeCompleted                | 문자열      | 현재 질문에 답변해야 하는지 여부를 나타내는 플래그입니다. |
    | 루트\\설문지\\질문\\PrimaryQuestion                | 문자열      | 현재 질문이 기본인지 여부를 나타내는 플래그입니다. |
    | 루트\\설문지\\질문\\SequenceNumber                 | 정수     | 현재 질문의 시퀀스 번호입니다. |
    | 루트\\설문지\\질문\\텍스트                           | 문자열      | 현재 질문의 텍스트. |
    | 루트\\설문지\\질문\\답변                         | 레코드 목록 | 현재 질문에 대한 답변 목록입니다. |
    | 루트\\설문지\\질문\\답변\\CorrectAnswer          | 문자열      | 현재 답변이 정답인지 여부를 나타내는 플래그입니다. |
    | 루트\\설문지\\질문\\답변\\점수                 | 실수        | 현재 답변 선택 시 적립되는 포인트입니다. |
    | 루트\\설문지\\질문\\답변\\SequenceNumber         | 정수     | 현재 답변의 시퀀스 번호입니다. |
    | 루트\\설문지\\질문\\답변\\텍스트                   | 문자열      | 현재 답변의 텍스트. |

    다음 그림은 **데이터 모델 디자이너** 페이지에서 완성된 편집 가능한 데이터 모델을 보여줍니다.

    ![ER 데이터 모델 디자이너에서 구성된 데이터 모델.](./media/er-quick-start1-model2.png)

7. 변경 사항을 저장합니다.
8. **데이터 모델 디자이너** 페이지를 닫습니다.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>데이터 모델 설계 완료

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 선택합니다.
3. **버전** 빠른 탭에서 상태가 **초안** 인 구성 버전을 선택합니다.
4. **상태 변경** \> **완료** 를 선택합니다.

이 구성의 버전 1 상태가 **초안** 에서 **완료됨** 으로 변경됩니다. 버전 1은 더 이상 변경할 수 없습니다. 이 버전에는 구성된 데이터 모델이 포함되어 있으며 다른 ER 구성의 기초로 사용할 수 있습니다. 이 구성의 버전 2가 생성되었으며 상태는 **초안** 입니다. 이 버전을 편집하여 **설문지** 데이터 모델을 조정할 수 있습니다.

![구성 페이지에서 편집 가능한 구성의 버전입니다.](./media/er-quick-start1-model-configuration.png)

ER 구성의 버전 관리에 대한 자세한 내용은 [전자 보고(ER) 개요](general-electronic-reporting.md#component-versioning)를 참조하세요.

> [!NOTE]
> 구성된 데이터 모델은 **설문지** 비즈니스 도메인을 추상적으로 대표하며 Microsoft Dynamics 365 Finance와 관련된 아티팩트와 관련이 없습니다.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>구성된 데이터 모델에 대한 모델 매핑 설계

전자 보고 개발자 역할의 사용자는 **설문지** 데이터 모델에 대한 모델 매핑 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 이 구성 요소는 재무에 대해 구성된 데이터 모델을 구현하므로 재무 관련입니다. 런타임 시 구성된 데이터 모델을 애플리케이션 데이터로 채우는 데 사용해야 하는 애플리케이션 개체를 지정하도록 모델 매핑 구성 요소를 구성해야 합니다. 이 작업을 완료하려면 재무에서 **설문지** 비즈니스 도메인의 데이터 구조 구현 세부 정보를 알고 있어야 합니다.

다음의 [새 모델 매핑 구성 가져오기](#ImportModelMapping) 섹션의 단계를 완료하여 제공된 XML 파일에서 필요한 모델 매핑 구성을 가져올 수 있습니다. 또는 [새 모델 매핑 구성 만들기](#CreateModelMapping) 섹션의 단계를 완료하여 이 모델 매핑을 처음부터 설계할 수 있습니다.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>새 모델 매핑 구성 가져오기

1. [설문지 mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. 작업 창에서 **XML 파일에서** \> **Exchange 로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **설문지 mapping.version.1.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

계속하려면 다음 절차를 건너뛰고 [새 모델 매핑 구성을 만듭니다](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>새 모델 매핑 구성 만들기

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 선택합니다.
3. **구성 만들기** 를 선택합니다.
4. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. **새로 만들기** 필드에서 **데이터 모델 설문지 기반 모델 매핑** 을 선택합니다.
    2. **이름** 필드에 **설문지 매핑** 을 입력합니다.
    3. **데이터 모델 정의** 필드에서 **루트** 정의를 선택합니다.
    4. **구성 만들기** 를 선택하여 구성을 생성합니다.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>새 모델 매핑 구성 요소 설계

1. **구성** 페이지의 구성 트리에서 **설문지 매핑** 을 선택합니다.
2. **디자이너** 를 선택하여 매핑 목록을 엽니다.
3. **루트** 정의에 대해 자동으로 추가된 **설문지 매핑** 매핑을 선택합니다.
4. **디자이너** 를 선택하여 선택한 매핑 구성을 시작합니다.

새 매핑이 **루트** 정의에 대해 자동으로 추가됩니다. 이 매핑에는 **모델링** 방향이 있습니다. 따라서 이 매핑을 사용하여 필요한 데이터로 데이터 모델을 채울 수 있습니다.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>애플리케이션 테이블에 액세스할 데이터 소스 추가

질문 세부사항이 포함된 애플리케이션 테이블에 액세스하려면 데이터 소스를 구성해야 합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **Dynamics 365 for Operations\\테이블 레코드** 를 선택합니다.
2. 모든 레코드가 단일 질문을 나타내는 KMCollection 테이블에 액세스하는 데 사용할 새 데이터 원본을 추가합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **설문지** 를 입력합니다.
    3. **테이블** 필드에 **KMCollection** 을 입력합니다.
    4. **쿼리 요청** 옵션을 **예** 로 설정합니다. 그러면 런타임 시 시스템 쿼리 대화 상자에서 이 테이블에 대한 [필터링](../../fin-ops/get-started/advanced-filtering-query-options.md) 옵션을 지정할 수 있습니다.
    5. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

3. **데이터 원본 유형** 창에서 **Dynamics 365 for Operations\\테이블 레코드** 를 선택합니다.
4. 모든 레코드가 설문지의 단일 질문을 나타내는 KMQuestion 테이블에 액세스하는 데 사용할 새 데이터 원본을 추가합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **질문** 을 입력합니다.
    3. **테이블** 필드에 **KMQuestion** 을 입력합니다.
    4. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

5. **데이터 원본 유형** 창에서 **Dynamics 365 for Operations\\테이블 레코드** 를 선택합니다.
6. 모든 레코드가 설문지의 질문에 대한 단일 답변을 나타내는 KMAnswer 테이블에 액세스하는 데 사용할 새 데이터 원본을 추가합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. **이름** 필드에 **답변** 을 입력합니다.
    3. **테이블** 필드에 **KMAnswer** 를 입력합니다.
    4. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

7. **데이터 원본 유형** 창에서 **함수\\계산된 필드** 를 선택합니다.
8. 상위 KMCollection 테이블의 모든 레코드에서 KMQuestionResultGroup 테이블의 레코드에 액세스하는 데 사용할 새 계산된 필드를 추가합니다.

    1. **데이터 소스** 창에서 **설문지** 를 선택합니다.
    2. **추가** 를 선택합니다.
    3. 대화 상자의 **이름** 필드에 **\$ResultGroup** 을 입력합니다.
    4. **수식 편집** 을 선택합니다.
    5. [ER 공식 편집기](general-electronic-reporting-formula-designer.md)에서 **공식** 필드에 KMCollection과 KMQuestionResultGroup 테이블 간의 일대다 관계의 [경로](er-formula-language.md#Paths)를 사용할 **FIRSTORNULL(\@.'\<Relations'.KMQuestionResultGroup)** 을 입력합니다.
    6. **저장** 을 선택하고 수식 편집기를 닫습니다.
    7. **확인** 을 선택하여 새 계산 필드를 추가합니다.

9. **데이터 원본 유형** 창에서 **함수\\계산된 필드** 를 선택합니다.
10. 상위 KMCollectionQuestion 테이블의 모든 레코드에서 KMQuestion 테이블의 질문 레코드에 액세스하는 데 사용할 새 계산된 필드를 추가합니다.

    1. **데이터 소스** 창에서 **설문지** 를 선택합니다.
    2. KMCollection 테이블의 일대다 관계를 포함하는 **\<관계** 노드를 확장합니다.
    3. 관련 **KMCollectionQuestion** 테이블을 선택한 다음 **추가** 를 선택합니다.
    4. 대화 상자의 **이름** 필드에 **\$질문** 을 입력합니다.
    5. **수식 편집** 을 선택합니다.
    6. 수식 편집기에서 **수식** 필드에 **FIRSTORNULL(FILTER(Question, Question.kmQuestionId =\@.kmQuestionId))** 을 입력하여 KMQuestion 테이블에서 적절한 질문 레코드를 반환합니다.
    7. **저장** 을 선택하고 수식 편집기를 닫습니다.
    8. **확인** 을 선택하여 새 계산 필드를 추가합니다.

11. **데이터 원본 유형** 창에서 **함수\\계산된 필드** 를 선택합니다.
12. 상위 KMQuestion 테이블의 모든 레코드에서 KMAnswer 테이블의 답변 레코드에 액세스하는 데 사용할 새 계산된 필드를 추가합니다.

    1. **데이터 소스** 창에서 **설문지.\<Relations.KMCollectionQuestion.\$질문** 을 선택한 다음 **추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **\$답변** 을 입력합니다.
    3. **수식 편집** 을 선택합니다.
    4. 수식 편집기에서 **수식** 필드에 **FILTER (Answer, Answer.kmAnswerCollectionId = \@.kmAnswerCollectionId)** 을 입력하여 KMAnswer 테이블에서 적절한 답변 레코드를 반환합니다.
    5. **저장** 을 선택하고 수식 편집기를 닫습니다.
    6. **확인** 을 선택하여 새 계산 필드를 추가합니다.

13. **데이터 원본 유형** 창에서 **Dynamics 365 for Operations\\테이블** 을 선택합니다.
14. CompanyInfo 테이블의 메소드에 액세스하는 데 사용할 새 데이터 소스를 추가합니다. 이 테이블의 **find()** 메서드는 컨텍스트에서 이 매핑이 호출되는 현재 재무 인스턴스의 회사를 나타내는 레코드를 반환합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **CompanyInfo** 를 입력합니다.
    3. **테이블** 필드에 **CompanyInfo** 를 입력합니다.
    4. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>애플리케이션 열거에 액세스할 데이터 소스 추가

애플리케이션 열거에 액세스하고 해당 값을 애플리케이션 테이블의 **열거** 유형의 필드 값과 비교하도록 데이터 소스를 구성해야 합니다. 비교 결과를 사용하여 데이터 모델의 적절한 필드를 채워야 합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **Dynamics 365 for Operations\\열거** 를 선택합니다.
2. **EnumAppNoYes** 열거의 값에 액세스하는 데 사용할 새 데이터 소스를 추가합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **EnumAppNoYes** 를 입력합니다.
    3. **열거** 필드에 **NoYes** 를 입력합니다.
    4. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

3. **데이터 원본 유형** 창에서 **Dynamics 365 for Operations\\열거** 를 선택합니다.
4. **KMCollectionQuestionMode** 열거의 값에 액세스하는 데 사용할 새 데이터 소스를 추가합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **EnumAppQuestionOrder** 를 입력합니다.
    3. **열거** 필드에 **KMCollectionQuestionMode** 를 입력합니다.
    4. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>ER 레이블을 추가하여 지정된 언어로 보고서 생성

ER 레이블을 추가하여 모델 매핑 호출 컨텍스트에 정의된 언어에 따라 값을 반환하도록 일부 데이터 소스를 구성할 수 있습니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스** 창에서 **답변** 을 선택한 다음 **편집** 을 선택합니다.
2. **레이블** 필드를 활성화합니다.
3. **번역** 을 선택합니다.
4. **텍스트 번역** 대화 상자에서 다음 단계를 따르세요.

    1. **레이블 ID** 필드에 **PositiveAnswer** 를 입력합니다.
    2. **기본 언어의 텍스트** 필드에 **네** 를 입력합니다.
    3. **번역** 을 선택합니다.
    4. **레이블 ID** 필드에 **NegativeAnswer** 를 입력합니다.
    5. **기본 언어의 텍스트** 필드에 **아니요** 를 입력합니다.
    6. **번역** 을 선택합니다.

5. **텍스트 번역** 대화 상자를 닫습니다.
6. **취소** 를 선택합니다.

![편집 가능한 모델 매핑을 위해 ER 레이블을 추가합니다.](./media/er-quick-start1-adding-labels.png)

기본 언어에 대해서만 ER 레이블을 입력했습니다. ER 레이블을 다른 언어로 번역하는 방법에 대한 정보는 [다국어 보고서 디자인](er-design-multilingual-reports.md)을 참조하세요.

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>열거형 값을 텍스트 값과 비교한 결과를 변환하는 데이터 소스 추가

열거형 값과 텍스트 값 간의 비교 결과를 서로 다른 원본에 대해 여러 번 변환해야 하므로 이 논리를 단일 데이터 원본으로 구성하는 것이 좋습니다. 그러나 이 데이터 소스를 재사용 가능하게 하려면 매개변수화된 데이터 소스로 구성해야 합니다. 자세한 내용은 [계산된 필드 유형의 ER 데이터 소스의 매개변수화된 호출 지원](er-calculated-field-type.md)을 참조하세요.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **일반\\빈 컨테이너** 를 선택합니다.
2. 새 컨테이너 데이터 소스를 추가합니다.

    1. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
    2. 대화 상자의 **이름** 필드에 **도우미** 를 입력합니다.
    3. **확인** 을 선택하여 새 컨테이너 데이터 소스를 추가합니다.

3. **데이터 원본 유형** 창에서 **함수\\계산된 필드** 를 선택합니다.
4. 새 데이터 소스를 추가합니다.

    1. **데이터 소스** 창에서 **도우미** 를 선택합니다.
    2. **추가** 를 선택합니다.
    3. 대화 상자의 **이름** 필드에 **NoYesEnumToString** 을 입력합니다.
    4. **수식 편집** 을 선택합니다.
    5. 수식 편집기에서 **매개 변수** 를 선택합니다.
    6. 다음 단계를 따라 구성된 식의 매개 변수를 지정합니다.

        1. **새로 만들기** 를 선택합니다.
        2. 대화 상자의 **이름** 필드에 **인수** 를 입력합니다.
        3. **유형** 필드에서 **부울** 데이터 형식을 선택합니다.
        4. **확인** 을 선택합니다.

    7. **수식** 필드에 **IF (Argument = true, \@"GER\_LABEL:PositiveAnswer", \@"GER\_LABEL:NegativeAnswer")** 를 입력하여 실행 컨텍스트의 언어와 지정된 매개변수의 값에 따라 적절한 ER 레이블의 텍스트를 반환합니다.
    8. **저장** 을 선택하고 수식 편집기를 닫습니다.
    9. **확인** 을 선택하여 새 데이터 원본을 추가합니다.

![ER 모델 매핑 디자이너에서 구성된 모델 매핑.](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>데이터 모델 필드에 데이터 소스 바인딩

구성된 데이터 소스를 데이터 모델의 필드에 바인딩하여 런타임 시 데이터 모델이 애플리케이션 데이터로 채워지는 방식을 지정해야 합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 모델** 창에서 **CompanyName** 을 선택합니다.
2. **데이터 소스** 창에서 **CompanyInfo** 를 확장하고 다음 단계를 따르세요.

    1. CompanyInfo 테이블의 **find()** 메서드를 나타내는 **CompanyInfo.find()** 노드를 확장합니다.
    2. **CompanyInfo.find().Name** 을 선택합니다.
    3. **바인딩** 을 선택하여 런타임 시 컨텍스트에서 구성된 모델 매핑이 호출되는 회사 이름을 입력합니다.

3. **데이터 모델** 창에서 **설문지** 를 선택합니다.
4. **데이터 소스** 창에서 **설문지** 를 선택한 다음 **바인딩** 을 선택하여 설문지 레코드를 작성합니다.
5. **데이터 모델** 창에서 **설문지** 를 확장하고 다음 단계를 따르세요.

    1. **데이터 모델** 창에서 **활성** 을 선택합니다.
    2. **데이터 모델** 창에서 **편집** 을 선택합니다.
    3. **공식** 필드에 **Helper.NoYesEnumToString(\@.Active = EnumAppNoYes.Yes)** 를 입력하여 열거형 값 비교의 텍스트 종속 및 언어 종속 결과를 채웁니다.

6. 다음 결과를 얻을 때까지 동일한 방식으로 데이터 원본을 데이터 모델 필드에 계속 바인딩합니다.

    | 필드 경로                                              | 데이터 형식   | 작업 | 바인딩 식 |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | 문자열      | 바인딩   | CompanyInfo.'find()'.Name |
    | 설문                                           | 레코드 목록 | 바인딩   | 설문 |
    | 설문지\\활성                                   | 문자열      | 편집   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | 설문지\\코드                                     | 문자열      | 바인딩   | \@.kmCollectionId |
    | 설문지\\설명                              | 문자열      | 바인딩   | \@.설명 |
    | 설문지\\QuestionnaireType                        | 문자열      | 바인딩   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | 설문지\\QuestionOrder                            | 문자열      | 편집   | 케이스(\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Conditional",<br>EnumAppQuestionOrder.Random, "Random(질문에서 백분율)",<br>EnumAppQuestionOrder.RandomGroup, "Random(결과 그룹의 백분율)",<br>EnumAppQuestionOrder.Sequence, "Sequential",<br>"") |
    | 설문지\\ResultsGroup                             | 레코드      |        | |
    | 설문지\\ResultsGroup\\코드                       | 문자열      | 바인딩   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | 설문지\\ResultsGroup\\설명                | 문자열      | 바인딩   | \@.'\$ResultGroup'.description |
    | 설문지\\ResultsGroup\\MaxNumberOfPoints          | 실수        | 바인딩   | \@.'\$ResultGroup'.maxPoint |
    | 설문지\\질문                                 | 레코드 목록 | 바인딩   | \@.'&lt;Relations'.KMCollectionQuestion |
    | 설문지\\질문\\CollectionSequenceNumber       | 정수     | 바인딩   | \@.answerCollectionSequenceNumber |
    | 설문지\\질문\\Id                             | 문자열      | 바인딩   | \@.kmQuestionId |
    | 설문지\\질문\\MustBeCompleted                | 문자열      | 편집   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | 설문지\\질문\\PrimaryQuestion                | 문자열      | 바인딩   | \@.parentQuestionId |
    | 설문지\\질문\\SequenceNumber                 | 정수     | 바인딩   | \@.SequenceNumber |
    | 설문지\\질문\\텍스트                           | 문자열      | 바인딩   | \@.'\$Question'.text |
    | 설문지\\질문\\답변                         | 레코드 목록 | 바인딩   | \@.'\$Question'.'\$Answer' |
    | 설문지\\질문\\답변\\CorrectAnswer          | 문자열      | 편집   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | 설문지\\질문\\답변\\점수                 | 실수        | 바인딩   | \@.point |
    | 설문지\\질문\\답변\\SequenceNumber         | 정수     | 바인딩   | \@.sequenceNumber |
    | 설문지\\질문\\답변\\텍스트                   | 문자열      | 바인딩   | \@.text |

    다음 그림은 **모델 매핑 디자이너** 페이지에서 구성된 모델 매핑의 최종 상태를 보여줍니다.

    ![ER 모델 매핑 디자이너에서 전체 구성된 모델 매핑.](./media/er-quick-start1-mapping2.png)

7. 변경 사항을 저장합니다.
8. **모델 매핑 디자이너** 페이지를 닫습니다.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>모델 매핑 설계 완료

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 매핑** 을 선택합니다.
3. **버전** 빠른 탭에서 상태가 **초안** 인 구성 버전을 선택합니다.
4. **상태 변경** \> **완료** 를 선택합니다.

이 구성의 버전 1.1 상태가 **초안** 에서 **완료됨** 으로 변경됩니다. 버전 1.1은 더 이상 변경할 수 없습니다. 이 버전에는 구성된 모델 매핑이 포함되어 있으며 다른 ER 구성의 기초로 사용할 수 있습니다. 이 구성의 버전 1.2가 생성되었으며 상태는 **초안** 입니다. 이 버전을 편집하여 **설문지 매핑** 구성을 조정할 수 있습니다.

![구성 페이지에서 편집 가능한 ER 구성의 버전입니다.](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> 구성된 모델 매핑은 **설문** 비즈니스 도메인을 나타내는 추상 데이터 모델의 재무 관련 구현입니다.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>사용자 지정 보고서용 템플릿 디자인

ER 프레임워크는 사전 정의된 템플릿을 사용하여 Microsoft Office 형식(Excel 통합 문서 또는 Word 문서)으로 보고서를 생성합니다. 필수 보고서가 생성되는 동안 구성된 데이터 흐름에 따라 템플릿이 필수 데이터로 채워집니다. 따라서 먼저 사용자 정의 보고서에 대한 템플릿을 디자인해야 합니다. 이 템플릿은 사용자 지정 보고서의 레이아웃을 나타내는 구조의 Excel 통합 문서로 디자인되어야 합니다. 필수 데이터로 채우려는 모든 Excel 항목의 이름을 지정해야 합니다.

1. [설문지 보고서 템플릿.xlsx](https://download.microsoft.com/download/3/8/2/382c3cf0-87bb-473f-b7bb-3015b4facb74/Questionnaires_report_template.xlsx) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. Excel에서 파일을 열고 통합 문서의 구조를 검토합니다.

다음 그림에서 볼 수 있듯이 다운로드한 템플릿은 적절한 답변과 함께 설문지의 질문을 제시하는 지정된 설문지를 인쇄하도록 설계되었습니다.

![지정된 설문지를 인쇄하는 Excel 템플릿입니다.](./media/er-quick-start1-template-layout.png)

설문 세부 정보를 채우기 위해 이 템플릿에 Excel 이름이 추가되었습니다. 이름 관리자를 사용하여 Excel 이름을 검토할 수 있습니다.

![이름 관리자를 사용하여 제공된 Excel 템플릿에서 Excel 이름을 검토합니다.](./media/er-quick-start1-template-names.png)

보고서 레이블이 영어로 된 고정 텍스트로 추가되었습니다. 구성된 모델 매핑의 언어 종속 표현식에 대해 수행한 것처럼 ER 형식 [레이블](#AddMmLabels)을 사용하여 레이블을 언어 종속 텍스트로 채우는 새 Excel 이름으로 보고서 레이블을 바꿀 수 있습니다. 이 경우 ER 레이블은 편집 가능한 ER 형식으로 추가해야 합니다.

다음 그림에서 볼 수 있듯이 Excel에서 페이징을 수행할 수 있도록 사용자 지정 보고서 머리글이 지정되었습니다.

![제공된 Excel 템플릿의 사용자 정의 보고서 헤더입니다.](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>형식 디자인

전자 보고 함수 컨설턴트 역할의 사용자는 형식 구성 요소가 포함된 새 ER 구성을 생성해야 합니다. 런타임 시 보고서 템플릿을 필수 데이터로 채우는 방법을 지정하려면 형식 구성 요소를 구성해야 합니다.

[디자인된 형식 구성 가져오기](#FormatImport) 섹션의 단계를 완료하여 제공된 XML 파일에서 필요한 형식을 가져올 수 있습니다. 또는 [새 형식 구성 만들기](#FormatCreate) 섹션의 단계를 완료하여 이 형식을 처음부터 설계할 수 있습니다.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>디자인된 형식 구성 가져오기

1. [설문지 format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) 파일을 다운로드하고 로컬 컴퓨터에 저장합니다.
2. **조직 관리** \> **작업 영역** \> **전자 보고** 로 이동합니다.
3. **전자 보고** 작업 영역에서 **보고 구성** 을 선택합니다.
4. 작업 창에서 **교환** \> **XML 파일에서 로드** 를 선택합니다.
5. **찾아보기** 를 선택한 다음 **설문지 format.version.1.1.xml** 파일을 찾아 선택합니다.
6. **확인** 을 선택하여 구성을 가져옵니다.

계속하려면 다음 절차를 건너뛰고 [새 형식 구성을 만듭니다](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>새 형식 구성 만들기
 
1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 선택합니다.
3. **구성 만들기** 를 선택합니다.
4. 드롭다운 대화 상자에서 다음 단계를 따르십시오.

    1. **새로 만들기** 필드에서 **데이터 모델 설문지 기반 형식** 을 선택합니다.
    2. **이름** 필드에 **설문지 보고서** 를 입력합니다.
    3. **데이터 모델 버전** 필드에서 **1** 을 선택합니다.

        > [!NOTE]
        > - 기본 데이터 모델의 특정 버전을 선택하면 해당 버전의 데이터 모델 구조가 생성된 형식의 **모델** 데이터 원본의 구조로 표시됩니다.
        > - 이 필드를 비워 둘 수 있습니다. 이 경우 데이터 모델의 **초안** 버전 구조는 생성된 형식의 **모델** 데이터 원본 구조로 표시됩니다. 그런 다음 모델을 조정하고 형식에서 해당 조정을 즉시 확인할 수 있습니다. 이 접근 방식은 데이터 모델, 모델 매핑 및 형식을 동시에 구성할 때 ER 솔루션 설계의 효율성을 향상시킬 수 있습니다.
        > - 기본 데이터 모델의 특정 버전을 선택하면 나중에 형식 편집을 시작할 때 **초안** 버전을 사용하도록 전환할 수 있습니다.

    4. **데이터 모델 정의** 필드에서 **루트** 정의를 선택합니다.

5. **구성 만들기** 를 선택하여 구성을 생성합니다.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>보고서 템플릿 가져오기

1. **구성** 페이지의 구성 트리에서 **설문지 보고서** 를 선택합니다.
2. **디자이너** 를 선택하여 사용자 지정 형식 구성을 시작합니다.
3. **형식 디자이너** 페이지의 작업 창에서 **가져오기** \> **Excel에서 가져오기** 를 선택합니다.
4. 대화 상자에서 다음 단계를 따르세요.

    1. **템플릿 추가** 를 선택합니다.
    2. 로컬에 저장된 **설문 보고서 템플릿.xslx** 파일을 찾아 선택한 다음 **열기** 를 선택합니다.
    3. **확인** 을 선택하여 템플릿을 가져옵니다.

    ![보고서 템플릿 가져오기.](./media/er-quick-start1-template-import.png)

**Excel\\파일** 형식 요소는 루트 요소로 편집 가능한 형식에 자동으로 추가됩니다. 또한 **Excel\\범위** 형식 요소 또는 **Excel\\셀** 형식 요소는 가져온 템플릿의 인식된 모든 Excel 이름에 대해 자동으로 추가됩니다. 중첩된 **문자열** 요소가 있는 **Excel\\머리글** 형식은 가져온 템플릿의 헤더 설정을 반영하도록 자동으로 추가됩니다.

![ER 작업 디자이너에서 자동으로 추가된 요소를 포함하는 형식 구조입니다.](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>형식 구성

1. **형식 디자이너** 페이지의 형식 트리에서 **Excel** 루트 요소를 선택합니다.
2. 페이지 오른쪽에 있는 **형식** 탭의 **이름** 필드에 <a name="AddFormatRootElement"></a>**보고서** 를 입력합니다.
3. **언어 기본 설정** 필드에서 **사용자 기본 설정** 을 선택하여 사용자가 선호하는 언어로 보고서를 실행합니다.
4. **문화 기본 설정** 필드에서 **사용자 기본 설정** 을 선택하여 사용자가 선호하는 문화로 보고서를 실행합니다.

    ER 프로세스에 대한 언어 및 문화권 컨텍스트를 지정하는 방법에 대한 정보는 [다국어 보고서 디자인](er-design-multilingual-reports.md)을 참조하세요.

    ![ER 작업 디자이너에서 디자인된 보고서에 대한 언어 및 문화 설정 구성.](./media/er-quick-start1-template-format-structure1.png)

5. 형식 트리에서 루트 노드를 확장한 다음 **ResultsGroup** 을 선택합니다.
6. **형식** 탭의 **복제 방향** 필드에서 **복제 없음** 을 선택합니다. 단일 질문에 대해 여러 결과 그룹이 있을 것으로 예상하지 않기 때문입니다.

    ![ER 작업 디자이너에서 범위 형식 요소에 대한 복제 방향을 정의합니다.](./media/er-quick-start1-template-format-structure2.png)

7. **저장** 을 선택합니다.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>보고서 제목에 대한 데이터 바인딩 정의

생성된 보고서의 제목을 채우는 데 사용되는 형식 요소에 대한 데이터 바인딩을 지정해야 합니다.

1. **형식 디자이너** 페이지 오른쪽의 **매핑** 탭에서 **보고서\\ReportTitle** 요소를 선택합니다.
2. **수식 편집** 을 선택합니다.
3. 수식 편집기에서 **번역** 을 선택합니다.
4. **텍스트 번역** 대화 상자에서 다음 단계를 따르세요.

    1. **레이블 ID** 필드에 **ReportTitle** 을 입력합니다.
    2. **기본 언어의 텍스트** 필드에 **설문지 보고서** 를 입력합니다.
    3. **번역** 을 선택하고 **저장** 을 선택합니다.
    4. **번역** 을 선택하여 **텍스트 번역** 대화 상자를 닫습니다.

5. 수식 편집기를 닫습니다.

    ![생성된 보고서의 제목을 채우도록 바인딩을 구성합니다.](./media/er-quick-start1-add-report-title-label.png)

이 기술을 사용하여 현재 템플릿의 다른 모든 레이블을 언어 종속적으로 만들 수 있습니다. 단일 ER 구성의 추가된 레이블을 지원되는 모든 언어로 번역하는 방법에 대한 정보는 [다국어 보고서 디자인](er-design-multilingual-reports.md)을 참조하세요.

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>모델 데이터 소스 검토

1. **형식 디자이너** 페이지의 **매핑** 탭에서 이 ER 형식의 기본 데이터 모델을 나타내는 <a name="ModelDSName"></a>**모델** 데이터 원본을 선택합니다.
2. **편집** 을 선택합니다.
3. **데이터 소스 속성** 대화 상자의 정보를 검토합니다. 이 데이터 원본은 **설문지 모델** ER 구성에 있는 **설문지** 데이터 모델 구성 요소의 버전 1을 나타냅니다.

![ER 작업 디자이너의 모델 데이터 소스 속성입니다.](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>데이터 소스 필드에 형식 요소 바인딩

템플릿이 런타임에 채워지는 방법을 지정하려면 적절한 Excel 이름과 연결된 모든 형식 요소를 이 형식 데이터 소스의 단일 필드에 바인딩해야 합니다.

1. **형식 디자이너** 페이지의 형식 트리에서 **보고서\\CompanyName** 형식 요소를 선택합니다.
2. **매핑** 탭에서 **문자열** 유형의 **model.CompanyName** 데이터 원본을 선택합니다.
3. **바인딩** 을 선택하여 템플릿에 회사 이름을 입력합니다.
4. 형식 트리에서 **보고서\\설문지** 요소를 선택합니다.
5. **매핑** 탭에서 **레코드 목록** 유형의 **model.Questionnaire** 데이터 원본을 선택합니다.
6. **바인딩** 을 선택합니다.
7. **세부 정보 표시** 를 선택하여 형식 요소에 대한 자세한 내용을 봅니다.

    **설문지** 범위 형식 요소는 수직 복제로 구성됩니다. **레코드 목록** 유형의 데이터 소스에 바인딩된 경우 Excel 템플릿의 적절한 **설문지** 범위는 바인딩된 데이터 원본의 모든 레코드에 대해 반복됩니다.
 
    ![설문지 범위 형식 요소를 ER 작업 디자이너의 적절한 레코드 목록 데이터 소스에 바인딩합니다.](./media/er-quick-start1-bindings1.png)

    Excel 템플릿의 **설문지** 범위는 5행에서 14행 사이에 정의되므로 이 행은 보고된 모든 질문에 대해 반복됩니다.

    ![레코드 목록 데이터 원본의 모든 레코드에 대해 생성된 보고서에서 반복될 Excel 템플릿의 행입니다.](./media/er-quick-start1-template-questionnaire-range.png)

8. 다음 표에 설명된 대로 나머지 형식 요소에 대해 유사한 바인딩을 구성합니다.

    > [!NOTE]
    > 이 표에서 "데이터 소스 경로" 열의 정보는 [상대 경로](relative-path-data-bindings-er-models-format.md) ER 기능이 켜져 있다고 가정합니다.

    | 형식 요소 경로                                      | 데이터 원본 경로 |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\설문지                                     | **model.Questionnaire** |
    | Excel\\설문지\\활성                             | **\@.Active**, where **\@** is **model.Questionnaire** |
    | Excel\\설문지\\코드                               | **\@.Code** |
    | Excel\\설문지\\설명                        | **\@.Description** |
    | Excel\\설문지\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\설문지\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\설문지\\ResultsGroup\\코드\_               | **\@.ResultsGroup.Code** |
    | Excel\\설문지\\ResultsGroup\\설명\_        | **\@.ResultsGroup.Description** |
    | Excel\\설문지\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\설문지\\질문                           | **\@.Question** |
    | Excel\\설문지\\질문\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, **\@** 이(가) **model.Questionnaire.Question** |
    | Excel\\설문지\\질문\\Id                       | **\@.Id** |
    | Excel\\설문지\\질문\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\설문지\\질문\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\설문지\\질문\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\설문지\\질문\\텍스트                     | **\@.Text** |
    | Excel\\설문지\\질문\\답변                   | **\@.Answer** |
    | Excel\\설문지\\질문\\답변\\CorrectAnswer    | **\@.CorrectAnswer**, **\@** 이(가) **model.Questionnaire.Answer** |
    | Excel\\설문지\\질문\\답변\\점수           | **\@.Points** |
    | Excel\\설문지\\질문\\답변\\텍스트             | **\@.Text** |

9. 완료되면 **저장** 을 선택합니다.

다음 그림은 **형식 디자이너** 페이지에서 구성된 데이터 바인딩의 최종 상태를 보여줍니다.

![ER 작업 디자이너에서 구성된 데이터 바인딩.](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> 지정된 데이터 소스 및 바인딩의 전체 컬렉션은 구성된 형식의 형식 매핑 구성 요소를 나타냅니다. 이 형식 매핑은 보고서 생성을 위해 구성된 형식을 실행할 때 호출됩니다.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>ER에서 디자인된 형식 실행

이제 테스트 목적으로 설계된 형식을 **구성** 페이지에서 실행할 수 있습니다.

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 확장한 다음 **설문 보고서** 를 선택합니다.
3. 상태가 **초안** 인 형식 버전에 **디자이너** 를 선택합니다.
4. **형식 디자이너** 페이지에서 **실행** 을 선택합니다.
5. **ER 매개변수** 대화 상자의 **포함할 레코드** 빠른 탭에서 필터링 옵션을 구성하여 **SBCCrsExam** 설문지만 포함되도록 합니다.
6. **확인** 을 선택하여 필터링 옵션을 확인합니다.
7. **확인** 을 선택하여 보고서를 실행합니다.
8. 생성된 보고서를 검토합니다.

[기본](electronic-reporting-destinations.md#default-behavior)적으로 생성된 보고서는 다운로드할 수 있는 Excel 파일로 전달됩니다. 다음 그림은 Excel 형식으로 생성된 보고서의 두 페이지를 보여줍니다.

![Excel 형식으로 생성된 보고서의 예, 1페이지.](./media/er-quick-start1-report1a.png)

![Excel 형식으로 생성된 보고서의 예, 2페이지.](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>디자인된 형식 조정

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>생성된 문서의 이름을 변경하는 형식 수정

기본적으로 생성된 문서의 이름은 현재 사용자의 별칭을 사용하여 지정됩니다. 형식을 수정하여 생성된 문서의 이름이 사용자 정의 논리를 기반으로 하도록 이 동작을 변경할 수 있습니다. 예를 들어, 생성된 문서의 이름은 현재 세션 날짜 및 시간과 보고서 제목을 기반으로 할 수 있습니다.

1. **형식 디자이너** 페이지에서 **보고서** 루트 항목을 선택합니다.
2. **매핑** 탭에서 **파일 이름 수정** 을 선택합니다.
3. **수식** 필드에 **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))** 를 입력합니다.
4. **저장** 을 선택하고 수식 편집기를 닫습니다.
5. **저장** 을 선택합니다.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>질문 순서를 변경하는 형식 수정

생성된 보고서에서 질문의 순서가 올바르지 않습니다. 형식을 수정하여 순서를 변경할 수 있습니다.

1. **형식 디자이너** 페이지에서 **보고서** 루트 항목을 선택합니다.
2. **매핑** 탭의 형식 트리에서 **보고서\\설문지\\질문** 을 확장합니다.

    ![범위 유형의 질문 형식 요소는 ER 작업 디자이너입니다.](./media/er-quick-start1-bindings3.png)

3. **매핑** 탭에서 **model.Questionnaire** 를 선택합니다.
4. **추가** \> **기능\\계산 필드** 를 선택한 다음 **이름** 필드에 **OrderedQuestions** 를 입력합니다.
5. **수식 편집** 을 선택합니다.
6. 수식 편집기의 **수식** 필드에 **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** 를 입력하여 현재 설문지의 질문 목록을 시퀀스 순서 번호로 정렬합니다.
7. **저장** 을 선택하고 수식 편집기를 닫습니다.
8. **확인** 을 선택하여 새 계산된 필드의 입력을 완료합니다.
9. **매핑** 탭에서 **model.Questionnaire.OrderedQuestions** 를 선택합니다.
10. 형식 트리에서 **Excel\\설문지\\질문** 을 선택합니다.
11. **바인딩** 을 선택한 다음 중첩된 요소의 모든 바인딩에서 현재 **model.Questionnaire.Questions** 경로가 새로운 **model.Questionnaire.OrderedQuestions** 경로를 대체하는지 확인합니다.
12. **저장** 을 선택합니다.

![질문 형식 요소를 ER 작업 디자이너에서 구성된 OrderedQuestions 데이터 소스에 바인딩합니다.](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>ER에서 수정된 형식 실행

이제 ER 프레임워크에서 테스트 목적으로 수정된 형식을 실행할 수 있습니다.

1. **형식 디자이너** 페이지에서 **실행** 을 선택합니다.
2. **ER 매개변수** 대화 상자의 **포함할 레코드** 빠른 탭에서 필터링 옵션을 구성하여 **SBCCrsExam** 설문지만 포함되도록 합니다.
3. **확인** 을 선택하여 필터링 옵션을 확인합니다.
4. **확인** 을 선택하여 보고서를 실행합니다.
5. 생성된 보고서를 검토합니다.

다음 그림은 질문이 올바르게 정렬된 Excel 형식으로 생성된 보고서를 보여줍니다.

![올바르게 정렬된 질문이 있는 Excel 형식의 보고서를 생성했습니다.](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>형식 디자인 완료

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 확장한 다음 **설문 보고서** 를 선택합니다.
3. **버전** 빠른 탭에서 상태가 **초안** 인 구성 버전을 선택합니다.
4. **상태 변경** \> **완료** 를 선택합니다.

이 구성의 버전 1.1 상태가 **초안** 에서 **완료됨** 으로 변경됩니다. 버전 1.1은 더 이상 변경할 수 없습니다. 이 버전에는 구성된 형식이 포함되어 있으며 사용자 정의 보고서를 인쇄하는 데 사용할 수 있습니다. 이 구성의 버전 1.2가 생성되었으며 상태는 **초안** 입니다. 이 버전을 편집하여 **설문지** 보고서의 형식을 조정할 수 있습니다.

![구성 페이지에서 편집 가능한 ER 구성.](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> 구성된 형식은 **설문지** 보고서의 디자인이며 재무 관련 아티팩트와 관련이 없습니다.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>설계된 보고서를 호출하는 애플리케이션 아티팩트 개발

시스템 관리자 역할의 사용자는 사용자 정의 보고서를 생성하기 위해 애플리케이션 UI(사용자 인터페이스)에서 구성된 ER 형식을 호출할 수 있도록 새 논리를 개발해야 합니다. 현재 ER은 이러한 유형의 논리를 구성하는 기능을 제공하지 않습니다. 따라서 약간의 엔지니어링 작업이 필요합니다. 

새 논리를 개발하려면 연속 빌드를 지원하는 토폴로지를 배포해야 합니다. 자세한 내용은 [지속적인 빌드 및 테스트 자동화를 지원하는 토폴로지 배포](../perf-test/continuous-build-test-automation.md)를 참조하세요. 또한 이 토폴로지의 개발 환경에 대한 액세스 권한이 있어야 합니다. 사용 가능한 ER API에 대한 자세한 내용은 [ER 프레임워크 API](er-apis-app73.md)를 참조하세요.

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>소스 코드 수정

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>데이터 계약 클래스 추가

새 **QuestionnairesErReportContract** 클래스를 Microsoft Visual Studio 프로젝트에 추가하고 구성된 ER 형식을 실행하는 데 사용해야 하는 데이터 계약을 지정하는 코드를 작성합니다.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>UI 빌더 클래스 추가

새 **QuestionnairesErReportUIBuilder** 플래스를 Visual Studio 프로젝트에 추가하고 실행해야 하는 ER 형식의 형식 매핑 ID를 조회하는 데 사용할 런타임 대화 상자를 생성하는 코드를 작성합니다. 제공된 코드는 **[루트](#RootDefinitionName)** 정의를 사용하여 **[설문지](#DataModeName)** 데이터 모델을 참조하는 **데이터 모델** 유형의 데이터 원본을 포함하는 ER 형식만 조회합니다.

> [!NOTE]
> 또는 ER 통합 포인트를 사용하여 ER 형식을 필터링할 수 있습니다. 자세한 내용은 [형식 매핑 조회를 표시하는 API](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup)를 참조하세요.

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>데이터 공급자 클래스 추가

새 **QuestionnairesErReportDP** 클래스를 Visual Studio 프로젝트에 추가하고 구성된 ER 형식을 실행하는 데 사용해야 하는 데이터 공급자를 소개하는 코드를 작성합니다. 제공된 코드에는 이 데이터 공급자에 대한 데이터 계약만 포함됩니다.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>레이블 파일 추가

새 **QuestionnairesErReportLabels\_en-US** 레이블 파일을 Visual Studio 프로젝트에 추가하고 새 UI 리소스에 대해 다음 레이블을 지정합니다.

- 미국 영어(en-US)로 된 다음 텍스트가 포함된 새 메뉴 항목의 **\@QuestionnairesReport** 레이블: **설문지 보고서(ER 제공)**
- 선택한 ER 형식이 일괄 작업으로 실행되도록 예약된 경우 일괄 작업 제목에 대한 **\@QuestionnairesReportBatchJobDescription** 레이블

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>보고서 서비스 클래스 추가

새 **QuestionnairesErReportService** 클래스를 Visual Studio 프로젝트에 추가하고 ER 형식을 호출하는 코드를 작성하고 형식 매핑 ID로 식별하고 데이터 계약을 매개 변수로 제공합니다.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

애플리케이션 데이터를 실행하는 ER 형식을 사용해야 하는 경우 형식 매핑에서 **데이터 모델** 유형의 데이터 소스를 구성해야 합니다. 이 데이터 소스는 단일 루트 정의를 사용하여 지정된 데이터 모델의 특정 부분을 참조합니다. ER 형식이 실행되면 이 데이터 소스를 호출하여 주어진 모델 및 루트 정의에 대해 구성된 적절한 ER 모델 매핑에 액세스합니다.

소스 코드에서 준비하고 데이터 계약의 일부로 저장할 수 있는 모든 정보는 이 유형의 ER 모델 매핑을 사용하여 실행 중인 ER 형식으로 전달할 수 있습니다. ER 모델 매핑에서 **[QuestionnairesErReportContract](#DataContractClass)** 클래스를 참조하는 **개체** 유형의 데이터 원본을 구성해야 합니다. 모델 매핑을 식별하려면 이 모델 매핑을 호출하는 데이터 소스를 지정해야 합니다. 제공된 코드에서 이 데이터 원본은 **[모델](#ModelDSName)** 값이 있는 **ERModelDataSourceName** 상수에 의해 지정됩니다. 모델 매핑에서 데이터 계약을 노출하는 데 사용되는 데이터 원본을 식별하려면 데이터 원본 이름을 지정해야 합니다. 제공된 코드에서 이 이름은 <a name="DataContractDSName"></a>**RunTimeParameters** 값이 있는 **ParametersDataSourceName** 상수에 의해 지정됩니다.

> [!NOTE]
> 새 환경에서는 ER 모델 매핑 디자이너에서 이러한 유형의 클래스를 사용할 수 있도록 ER 메타데이터를 새로 고쳐야 할 수 있습니다. 자세한 내용은 [ER 프레임워크 구성](electronic-reporting-er-configure-parameters.md#frequently-asked-questions)을 참조하세요.

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>보고서 컨트롤러 클래스 추가

새 **QuestionnairesErReportController** 클래스를 Visual Studio 프로젝트에 추가하고 제공된 **QuestionnairesErReportUIBuilder** 클래스의 로직을 기반으로 구축된 대화 상자에서 원하는 대로 동기 모드 또는 배치 모드에서 ER 형식을 실행하는 코드를 작성합니다.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>메뉴 항목 추가

새 **QuestionnairesErReport** 메뉴 항목을 Visual Studio 프로젝트에 추가합니다. **개체** 속성에서 이 메뉴 항목은 **QuestionnairesErReportController** 클래스를 참조하며 ER 형식을 선택하고 실행할 수 있는 사용자 권한을 지정하는 데 사용됩니다. **레이블** 속성에서 이 메뉴 항목은 이전에 만든 **\@QuestionnairesReport** 레이블을 참조하므로 애플리케이션 UI에 올바른 텍스트가 표시됩니다.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>메뉴에 메뉴 항목 추가

기존 **KM** 메뉴를 Visual Studio 프로젝트에 추가합니다. 이 메뉴에 **출력** 유형의 새 **QuestionnairesErReport** 항목을 추가해야 합니다. 이 항목은 이전 섹션에서 설명한 **QuestionnairesErReport** 메뉴 항목을 참조해야 합니다.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Visual Studio 프로젝트 빌드

사용자가 새 메뉴 항목을 사용할 수 있도록 프로젝트를 빌드합니다.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>응용 프로그램에서 형식 실행

1. **설문지** \> **디자인** \> **설문지 보고서(ER 제공)** 으로 이동합니다.

    ![설문 모듈에서 설문 보고서(ER 제공) 메뉴 항목을 선택하여 구성된 ER 형식을 실행합니다.](./media/er-quick-start1-application-menu-modified.png)

2. 대화 상자의 **형식 매핑** 필드에서 **설문 보고서** 를 선택합니다.
3. **확인** 을 선택합니다.
4. **전자 보고 매개 변수** 대화 상자의 **포함할 레코드** 빠른 탭에서 필터링 옵션을 구성하여 **SBCCrsExam** 설문지만 포함되도록 합니다.
5. **확인** 을 선택하여 필터링 옵션을 확인합니다.
6. **확인** 을 선택하여 보고서를 실행합니다.

    ![전자 보고서 대화 상자에서 선택 기준 지정.](./media/er-quick-start1-report-run-dialog-page.png)

7. 생성된 보고서를 검토합니다.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>설계된 ER 솔루션 조정

실행 중인 ER 형식의 세부 정보에 액세스하기 위해 개발한 데이터 공급자 클래스를 사용하고 생성된 보고서에 이 ER 형식의 이름을 입력하도록 구성된 ER 솔루션을 수정할 수 있습니다.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>모델 매핑 수정

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>데이터 계약 개체에 액세스할 데이터 소스 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 확장한 다음 **설문 매핑** 을 선택합니다.
3. **디자이너** 를 선택하여 **데이터 소스 매핑에 대한 모델** 페이지를 엽니다.
4. **디자이너** 를 선택하여 모델 매핑 디자이너에서 선택한 매핑을 엽니다.
5. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **Dynamics 365 for Operations\\개체** 를 선택합니다.
6. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
7. 대화 상자의 **이름** 필드에 **QuestionnairesErReportService** 클래스의 소스 코드에 정의된 대로 **[RunTimeParameters](#DataContractDSName)** 를 입력합니다.
8. **클래스** 필드에 이전에 코딩된 **[QuestionnairesErReportContract](#DataContractClass)** 를 입력합니다.
9. **확인** 을 선택합니다.
10. **RunTimeParameters** 를 확장합니다.

추가된 데이터 소스는 실행 중인 ER 형식 매핑의 레코드 ID에 대한 정보를 제공합니다.

![ER 모델 매핑 디자이너에 데이터 소스를 추가했습니다.](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>ER 형식 매핑 레코드에 액세스하기 위한 데이터 소스 추가

ER 형식 매핑 레코드에 액세스할 데이터 소스를 추가하여 선택한 모델 매핑을 계속 편집합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **Dynamics 365 for Operations\\테이블 레코드** 를 선택합니다.
2. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
3. 대화 상자의 **이름** 필드에 **ER1** 을 입력합니다.
4. **테이블** 필드에 **ERFormatMappingTable** 을 입력합니다.
5. **확인** 을 선택합니다.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>실행 중 ER 형식의 형식 매핑 레코드에 액세스하기 위한 데이터 소스 추가

실행 중인 ER 형식의 형식 매핑 레코드에 액세스할 데이터 소스를 추가하여 선택한 모델 매핑을 계속 편집합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 소스 유형** 창에서 **함수\\계산 필드** 를 선택합니다.
2. **데이터 원본** 창에서 **루트 추가** 를 선택합니다.
3. 대화 상자의 **이름** 필드에 **ER2** 를 입력합니다.
4. **수식 편집** 을 선택합니다.
5. 수식 편집기의 **수식** 필드에 **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))** 을 입력합니다.
6. **저장** 을 선택하고 수식 편집기를 닫습니다.
7. **확인** 을 선택합니다.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>데이터 모델에 실행 중인 ER 형식의 이름 입력

실행 중인 ER 형식의 이름이 데이터 모델에 입력되도록 선택한 모델 매핑을 계속 편집합니다.

1. **모델 매핑 디자이너** 페이지의 **데이터 모델** 창에서 **ExecutionContext** 를 확장한 다음 **ExecutionContext\\FormatName** 을 선택합니다.
2. **데이터 모델** 창에서 **편집** 을 선택하여 선택한 데이터 모델의 필드에 대한 데이터 바인딩을 구성합니다.
3. 수식 편집기의 **수식** 필드에 **FIRSTORNULL (ER2.'\>Relations'.Format).Name** 을 입력합니다.
4. **저장** 을 선택하고 수식 편집기를 닫습니다.

**형식 이름** 필드를 사용했으므로 구성된 모델 매핑은 이제 실행 중에 이 모델 매핑을 호출하는 ER 형식의 이름을 노출합니다.

![데이터 모델 필드를 ER 모델 매핑 디자이너에서 추가된 데이터 소스의 메서드에 바인딩합니다.](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>모델 매핑 설계 완료

1. **모델 매핑 디자이너** 페이지에서 **저장** 을 선택합니다.
2. 페이지를 닫습니다.
3. 모델 매핑 페이지를 닫습니다.
4. **구성** 페이지의 구성 트리에서 **설문지 매핑** 구성이 여전히 선택되어 있는지 확인합니다. 그런 다음 **버전** 빠른 탭에서 상태가 **초안** 인 구성 버전을 선택합니다.
5. **상태 변경** \> **완료** 를 선택합니다.

이 구성의 버전 1.2 상태가 **초안** 에서 **완료됨** 으로 변경됩니다. 버전 1.2는 더 이상 변경할 수 없습니다. 이 버전에는 구성된 모델 매핑이 포함되어 있으며 다른 ER 구성의 기초로 사용할 수 있습니다. 이 구성의 버전 1.3이 생성되었으며 상태는 **초안** 입니다. 이 버전을 편집하여 **설문지** 모델 매핑을 조정할 수 있습니다.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>형식 수정

ER 형식이 실행될 때 생성되는 보고서의 바닥글에 이름이 표시되도록 구성된 ER 형식을 수정할 수 있습니다.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>새 형식 요소 추가

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 확장한 다음 **설문 보고서** 를 선택합니다.
3. **디자이너** 를 선택합니다.
4. **형식 디자이너** 페이지에서 **보고서** 루트 항목을 선택합니다.
5. **추가** 를 선택하여 선택한 **보고서** 루트 항목에 대해 새 중첩 형식 요소를 추가합니다.
6. **Excel\\바닥글** 을 선택합니다.
7. **이름** 필드에 **바닥글** 을 입력합니다.
8. **보고서\바닥글** 을 선택하고 **추가** 를 선택합니다.
9. **텍스트\\문자열** 을 선택합니다.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>추가된 형식 요소 바인딩

1. **형식 디자이너** 페이지의 **매핑** 탭에서 형식 트리의 활성 **바닥글\\문자열** 요소에 대해 **수식 편집** 을 선택합니다.
2. 수식 편집기의 **수식** 필드에 **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))** 를 입력합니다.
3. **저장** 을 선택하고 수식 편집기를 닫습니다.
4. **저장** 을 선택합니다.

구성된 형식이 이제 수정되어 **바닥글\\문자열** 요소를 사용하여 생성된 보고서의 바닥글에 이름이 입력됩니다.

![ER 작업 디자이너에서 구성된 형식에 바닥글 형식 요소를 추가합니다.](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>형식 디자인 완료

1. **형식 디자이너** 페이지를 닫습니다.
2. **구성** 페이지의 구성 트리에서 **설문지 보고서** 구성이 여전히 선택되어 있는지 확인합니다. 그런 다음 **버전** 빠른 탭에서 상태가 **초안** 인 구성 버전을 선택합니다.
3. **상태 변경** \> **완료** 를 선택합니다.

이 구성의 버전 1.2 상태가 **초안** 에서 **완료됨** 으로 변경됩니다. 버전 1.2는 더 이상 변경할 수 없습니다. 이 버전에는 구성된 형식이 포함되어 있으며 다른 ER 구성의 기초로 사용할 수 있습니다. 이 구성의 버전 1.3이 생성되었으며 상태는 **초안** 입니다. 이 버전을 편집하여 **설문지** 보고서를 조정할 수 있습니다.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>응용 프로그램에서 형식 실행

1. **설문지** \> **디자인** \> **설문지 보고서(ER 제공)** 으로 이동합니다.
2. 대화 상자의 **형식 매핑** 필드에서 **설문 보고서** 를 선택합니다.
3. **확인** 을 선택합니다.
4. **ER 매개변수** 대화 상자의 **포함할 레코드** 빠른 탭에서 필터링 옵션을 구성하여 **SBCCrsExam** 설문지만 포함되도록 합니다.
5. **확인** 을 선택하여 필터링 옵션을 확인합니다.
6. **확인** 을 선택하여 보고서를 실행합니다.
7. Excel 형식의 생성된 보고서를 검토합니다.

생성된 보고서의 바닥글에는 보고서를 생성하는 데 사용된 ER 형식의 이름이 포함되어 있습니다.

![Excel 형식의 생성된 보고서.](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>ER에서 형식 실행

1. **조직 관리** \> **전자 보고** \> **구성** 으로 이동합니다.
2. **구성** 페이지의 구성 트리에서 **설문지 모델** 을 확장한 다음 **설문 보고서** 를 선택합니다.
3. 작업 창에서 **송장** 을 선택합니다.
4. **전자 보고 매개 변수** 대화 상자의 **포함할 레코드** 빠른 탭에서 필터링 옵션을 구성하여 **SBCCrsExam** 설문지만 포함되도록 합니다.
5. **확인** 을 선택하여 필터링 옵션을 확인합니다.
6. **확인** 을 선택하여 보고서를 실행합니다.
7. Excel 형식의 생성된 보고서를 검토합니다.

생성된 보고서의 바닥글에는 보고서를 생성하는 데 사용된 ER 형식의 이름이 포함되어 있지 않습니다. ER에서 실행된 ER 형식에 의해 호출될 때 실행 중인 모델 매핑에 데이터 계약 개체가 전달되지 않았기 때문입니다.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>화면 미리 보기를 위한 형식 대상 구성

1. **조직 관리** \> **전자 보고** \> **전자 보고 대상** 으로 이동합니다.
2. **전자 보고 대상** 페이지에서 구성된 **설문 보고서** ER 형식의 대상 레코드를 추가합니다.
3. **파일 대상** 빠른 탭에서 [추가](#AddFormatRootElement)된 **보고서** 형식 구성 요소의 **화면** [대상](er-destination-type-screen.md)을  구성된 **설문 보고서** ER 형식의 루트 요소로 설정합니다.
4. **PDF 변환 설정** 빠른 탭에서 보고서를 변환할 대상을 **가로** 페이지 방향을 사용하는 [PDF 형식](electronic-reporting-destinations.md#OutputConversionToPDF)에 구성합니다.

![전자 보고 대상 페이지에서 ER 형식에 대한 사용자 정의 화면 대상 구성.](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>응용 프로그램에서 형식을 실행하여 PDF 문서로 미리 보기

1. **설문지** \> **디자인** \> **설문지 보고서(ER 제공)** 으로 이동합니다.
2. 대화 상자의 **형식 매핑** 필드에서 **설문 보고서** 를 선택합니다.
3. **확인** 을 선택합니다.
4. **전자 보고 매개 변수** 대화 상자의 **포함할 레코드** 빠른 탭에서 필터링 옵션을 구성하여 **SBCCrsExam** 설문지만 포함되도록 합니다.
5. **확인** 을 선택하여 필터링 옵션을 확인합니다.

    **대상** 빠른 탭에 **출력** 필드가 **화면** 으로 설정되어 있습니다. 구성된 대상을 변경하려면 **변경** 을 선택합니다.

    ![구성된 대상을 변경할 수 있는 ER 보고서 런타임 대화 상자.](./media/er-quick-start1-run-settings.png)

6. **확인** 을 선택하여 보고서를 실행합니다.
7. PDF 형식의 생성된 보고서를 검토합니다.

    ![PDF 형식의 생성된 보고서 화면 미리 보기.](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>추가 리소스

- [전자 보고 개요](general-electronic-reporting.md)
- [전자 보고 공식 언어](er-formula-language.md)
- [다국어 보고서 디자인](er-design-multilingual-reports.md)
- [ER 프레임워크 API](er-apis-app73.md)
- [CASE 함수](er-functions-logical-case.md)
- [CONCATENATE 함수](er-functions-text-concatenate.md)
- [DATETIMEFORMAT 함수](er-functions-datetime-datetimeformat.md)
- [FILTER 함수](er-functions-list-filter.md)
- [FIRSTORNULL 함수](er-functions-list-firstornull.md)
- [FORMAT 함수](er-functions-text-format.md)
- [IF 함수](er-functions-logical-if.md)
- [ORDERBY 함수](er-functions-list-orderby.md)
- [SESSIONNOW 함수](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
