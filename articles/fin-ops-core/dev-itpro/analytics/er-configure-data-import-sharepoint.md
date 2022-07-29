---
title: 다음에서 데이터 가져오기 구성 SharePoint
description: 이번에는 Microsoft SharePoint에서 데이터를 가져오는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 9ac328e660c7a8a3b4a4f34a650062a0fa974771
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460696"
---
# <a name="configure-data-import-from-sharepoint"></a>다음에서 데이터 가져오기 구성 SharePoint

[!include[banner](../includes/banner.md)]

ER(전자 보고) 프레임워크를 사용하여 들어오는 파일에서 데이터를 가져오려면 가져오기를 지원하는 ER 형식을 구성한 다음 해당 형식을 데이터 원본으로 사용하는 **대상** 유형의 모델 매핑을 실행해야 합니다. 데이터를 가져오려면 가져올 파일로 이동해야 합니다. 들어오는 파일은 사용자가 수동으로 선택할 수 있습니다. Microsoft SharePoint에서 데이터 가져오기를 지원하는 새로운 ER 기능을 사용하면 이 프로세스를 무인으로 구성할 수 있습니다. ER 구성을 사용하여 Microsoft SharePoint 폴더에 저장된 파일에서 데이터 가져오기를 수행할 수 있습니다. 이번에는 SharePoint에서 가져오기를 완료하는 방법에 대해 설명합니다. 이 예시에서는 공급 업체 트랜잭션을 비즈니스 데이터로 사용합니다.

## <a name="prerequisites"></a>전제 조건
이 주제의 예를 완료하려면 다음 액세스 권한이 있어야 합니다.

- 다음 역할 중 하나에 액세스합니다.

    - 전자 보고 개발자
    - 전자 보고 기능 컨설턴트
    - 시스템 관리자

- 애플리케이션과 함께 사용하도록 구성된 Microsoft SharePoint Server 인스턴스에 대한 액세스.
- 1099 지급을 위한 ER 형식 및 모델 구성.

### <a name="create-required-er-configurations"></a>필요한 ER 구성 생성
**7.5.4.3 IT 서비스/솔루션 구성 요소 획득/개발(10677)** 비즈니스 프로세스의 일부인 **Microsoft Excel 파일 작업 가이드에서 ER 가져오기** 데이터를 재생합니다. 이 작업 가이드는 ER 구성을 설계하고 사용하여 Microsoft Excel 파일에서 공급 업체 트랜잭션을 대화식으로 가져오는 프로세스를 안내합니다. 자세한 내용은 [Excel 형식으로 수신 문서 구문 분석](parse-incoming-documents-excel.md)을 참조하십시오. 작업 가이드를 완료하면 다음과 같은 설정이 됩니다.

#### <a name="er-configurations"></a>ER 구성,

- ER 모델 구성, **1099 지급 모델**
- ER 형식 구성, **Excel에서 벤더 거래를 가져오기 위한 형식**

![SharePoint에서 데이터를 가져오기 위한 ER 구성.](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>데이터 가져오기를 위한 수신 파일 샘플

- 가져와야 하는 공급 업체 트랜잭션이 포함된 Excel 파일 **1099import-data.xlsx**.

![SharePoint에서 가져오기 위한 샘플 Excel 파일입니다.](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> 공급 업체 트랜잭션 가져오기 형식이 기본 모델 매핑으로 선택됩니다. 따라서 **1099 지급 모델** 의 모델 매핑을 실행하고 해당 모델 매핑이 **대상** 유형인 경우 모델 매핑은 이 형식을 실행하여 외부 파일에서 데이터를 가져옵니다. 이후 해당 데이터를 사용하여 애플리케이션 테이블을 업데이트합니다.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>파일 저장소 SharePoint에 대한 액세스 구성
전자 보고서 파일을 특정 SharePoint 위치에 저장하려면 현재 회사에서 사용할 SharePoint 서버 인스턴스에 대한 액세스를 구성해야 합니다. 이 예시에서 회사는 USMF입니다. 지침은 [SharePoint 스토리지 구성](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage)을 참조하십시오.

1. [SharePoint 스토리지 구성](../../fin-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage)의 단계를 완료하십시오.
2. 구성된 SharePoint 사이트를 엽니다.
3. 들어오는 전자 보고 파일을 저장할 수 있는 다음 폴더를 만듭니다.

     - 파일 가져오기 소스(기본)(아래 스크린샷에 표시된 예)
     - 파일 가져오기 소스(대안)

    ![파일 가져오기 소스(기본).](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (선택 사항) 가져오기 후 파일을 저장할 수 있는 다음 폴더를 만듭니다. 

    - 파일 보관 폴더 - 이 폴더는 성공적으로 가져온 파일을 위한 것입니다.
    - 파일 경고 폴더 - 이 폴더는 경고와 함께 가져온 파일을 위한 것입니다.
    - 파일 오류 폴더 - 이 폴더는 가져오기에 실패한 파일을 위한 것입니다.

4. **조직 관리 > 문서 관리 > 문서 유형** 으로 이동합니다.
5. 생성한 SharePoint 폴더에 액세스하는 데 사용할 다음 문서 유형을 생성합니다. 지침은 [문서 유형 구성](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types)을 참조하십시오.

|문서 유형       | 그룹              | 위치      | SharePoint 폴더      |
|--------------------|--------------------|---------------|------------------------|
|SP 메인             |파일                |SharePoint     |파일 가져오기 소스(기본)|
|SP 대안             |파일                |SharePoint     |파일 가져오기 소스(대안)|
|SP 아카이브             |파일                |SharePoint     |파일 아카이브 폴더|
|SP 경고             |파일                |SharePoint     |파일 경고 폴더|
|참여 예약 오류입니다.             |파일                |SharePoint     |파일 오류 폴더|

![SharePoint 설정 – 새 문서 유형.](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>ER 형식에 대한 ER 소스 구성
1. **조직 관리** \> **전자 보고** \> **전자 보고 소스** 를 클릭합니다.
2. **전자 보고 원본** 페이지에서 구성된 ER 형식을 사용하여 데이터 가져오기를 위한 원본 파일을 구성합니다.
3. 확장자가 .xlsx인 파일만 가져오도록 파일 이름 마스크를 정의합니다. 파일 이름 마스크는 선택 사항이며 정의된 경우에만 사용됩니다. 각 ER 형식에 대해 하나의 마스크만 정의할 수 있습니다.
4. 가져올 파일이 여러 개 있고 가져오기 순서가 중요하지 않은 경우 **가져오기 전에 파일 정렬** 을 **정렬 안함** 으로 변경합니다.
5. 이전에 생성한 모든 SharePoint 폴더를 선택합니다.

    [![ER 파일 소스 설정.](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - ER *소스* 는 애플리케이션 회사별로 개별적으로 정의됩니다. 대조적으로 ER *구성* 은 회사 간에 공유됩니다.
> - ER 형식에 대한 ER 소스 설정을 삭제하면 연결된 모든 파일 상태(아래 참조)도 확인으로 삭제됩니다.

## <a name="review-the-files-states-for-the-er-format"></a>ER 형식에 대한 파일 상태 검토
1. **전자 보고 소스** 페이지에서 **소스에 대한 파일 상태** 를 선택하여 현재 ER 형식에 대해 구성된 파일 소스의 내용을 검토합니다.
2. **파일** 섹션에서 파일 목록을 검토합니다. 이 목록은 다음을 제공합니다.

    - 파일 이름 마스크(파일 이름 마스크가 정의된 경우)를 기반으로 적용 가능하고 데이터 가져오기가 준비된 소스 파일입니다. 이러한 파일의 경우 가져오기 **형식 섹션에 대한 소스 로그** 가 비어 있습니다.
    - 이전에 가져온 파일. 이러한 각 파일의 가져오기 **형식 섹션에 대한 소스 로그** 에서 이 파일의 가져오기 기록을 검토할 수 있습니다.

**조직 관리** \> **전자 보고** \> **소스에 대한 파일 상태** 를 선택하여 **소스 페이지에 대한 파일 상태** 를 열 수도 있습니다. 이 경우 페이지는 현재 로그인한 회사에서 파일 소스가 구성된 모든 ER 형식의 파일 소스에 대한 정보를 제공합니다.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>SharePoint 폴더에 있는 Excel 파일에서 데이터 가져오기
1. SharePoint에서 공급 업체 트랜잭션이 포함된 **1099import-data.xlsx** Microsoft Excel 파일을 이전에 생성한 **Files 가져오기 소스(기본)** SharePoint 폴더에 업로드합니다.

    [![SharePoint 콘텐츠 – 가져올 Microsoft Excel 파일입니다.](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. **소스 페이지의 파일 상태** 에서 **새로 고침** 을 선택하여 페이지를 새로 고칩니다. 업로드된 Excel 파일이 **준비** 상태로 SharePoint 이 페이지에 나타납니다. 현재 지원되는 상태는 다음과 같습니다.

    - **준비** – SharePoint 폴더에 있는 각각의 새 파일에 대해 자동으로 할당됩니다. 이 상태는 파일을 가져올 준비가 되었음을 의미합니다.
    - **가져오기** – 다른 프로세스(많은 프로세스가 동시에 실행 중인 경우)에서 파일을 사용하지 못하도록 가져오기 프로세스에서 파일을 잠글 때 ER 보고서에 의해 자동으로 할당됩니다.
    - **가져오기** – 파일 가져오기가 성공적으로 완료되면 ER 보고서에 의해 자동으로 할당됩니다. 이 상태는 가져온 파일이 구성된 파일 소스(SharePoint 폴더)에서 삭제되었음을 의미합니다.
    - **실패** – 오류 또는 예외와 함께 파일 가져오기가 완료되면 ER 보고서에 의해 자동으로 할당됩니다.
    - **보류 중** – 이 페이지에서 사용자가 수동으로 할당했습니다. 이 상태는 파일을 지금은 가져올 수 없음을 의미합니다. 이 상태는 일부 파일의 가져오기를 연기하는 데 사용할 수 있습니다.

    [![선택한 소스에 대한 새로 고친 ER 파일 상태 페이지.](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>SharePoint 파일에서 데이터 가져오기
1. ER 구성 트리를 열고 **1099 지급 모델** 을 선택한 다음 ER 모델 구성 요소 목록을 확장합니다.
2. 모델 매핑의 이름을 선택하여 선택한 ER 모델 구성의 모델 매핑 목록을 엽니다.

    [![구성 페이지.](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. **실행** 을 선택하여 선택한 모델 매핑을 실행합니다. ER 형식에 대한 파일 소스를 구성했으므로 필요한 경우 **파일 소스** 옵션의 설정을 변경할 수 있습니다. 이 옵션의 설정을 유지하면 구성된 소스(이 예시에서는 SharePoint 폴더)에서 .xslx 파일을 가져옵니다.

    이 예시에서는 하나의 파일만 가져옵니다. 그러나 파일이 여러 개 있는 경우 SharePoint 폴더에 추가된 순서대로 가져오기를 위해 선택됩니다. ER 형식을 실행할 때마다 선택한 단일 파일을 가져옵니다.

    [![SharePoint ER 모델 매핑에서 가져오고 실행합니다.](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. 모델 매핑은 배치 모드에서 [무인으로](#limitations) 실행할 수 있습니다. 이 경우 배치에서 이 ER 형식을 실행할 때마다 구성된 파일 소스에서 단일 파일을 가져옵니다.

    SharePoint 폴더에서 파일을 성공적으로 가져오면 해당 폴더에서 삭제되고 성공적으로 가져온 파일의 폴더로 이동하거나 경고와 함께 가져온 파일이 있는 폴더로 이동합니다. 그렇지 않으면 실패한 파일의 폴더로 이동하거나 실패한 파일의 폴더가 설정되지 않은 경우 이 폴더에 유지됩니다. 

5. **V-00001** 과 같은 바우처 ID를 입력한 후 **확인** 을 선택합니다.

    [![ER 모델 매핑을 실행합니다.](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. **소스 페이지의 파일 상태** 에서 **새로 고침** 을 선택하여 페이지를 새로 고칩니다.

    [![소스 페이지에 대한 ER 파일 상태.](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. **파일** 섹션에서 파일 목록을 검토합니다. **가져오기 형식 섹션의 소스 로그** 는 Excel 파일 가져오기 기록을 제공합니다. 이 파일을 성공적으로 가져왔기 때문에 SharePoint 폴더에서 **삭제됨으로** 표시됩니다.
8. **파일 가져오기 소스(기본)** SharePoint 폴더를 검토합니다. 성공적으로 가져온 Excel 파일이 이 폴더에서 삭제되었습니다.
9. **미지급금을 선택하십시오.** \> **정기 작업** \> **세금 1099** \> **1099에 대한 공급 업체 정산**.
10. **시작 날짜** 및 **종료 날짜** 필드에 적절한 값을 입력합니다. 이후 **수동 1099 트랜잭션** 을 선택합니다.

    **V-00001** 바우처에 대한 SharePoint Excel 파일에서 가져온 공급 업체 거래가 페이지에 표시됩니다.

    [![1099 벤더 거래 페이지.](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>가져올 Excel 파일 준비
1. 이전에 사용한 Excel 파일을 엽니다. 3행 1열에 애플리케이션에 없는 공급 업체 코드를 추가합니다. 행에 잘못된 공급 업체 정보를 추가합니다.

    [![SharePoint에서 가져오기 위한 샘플 Microsoft Excel 파일입니다.](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. 공급 업체 트랜잭션이 포함된 업데이트된 Excel 파일을 **파일 가져오기 소스(기본)** SharePoint 폴더에 업로드합니다.
3. ER 구성 트리를 열고 **1099 지급 모델** 을 선택한 다음 ER 모델 구성 요소 목록을 확장합니다.
4. 데이터 가져오기 프로세스 중에 잘못된 공급 업체 코드가 오류로 간주되도록 모델 매핑을 업데이트하려면 모델 매핑의 이름을 선택합니다.
5. **디자이너** 를 선택합니다.
6. **유효성 검사** 탭에서 가져온 공급 업체 계정이 애플리케이션에 있는지 여부를 평가하도록 구성된 유효성 검사 규칙에 대한 사후 유효성 검사 작업을 변경해야 합니다. **사후 검증 작업** 필드의 값을 **실행 중지** 로 업데이트하고 변경 사항을 저장하고 페이지를 닫습니다.

    [![ER 모델 매핑 디자이너 페이지.](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. 변경 사항을 저장하고 ER 모델 매핑 디자이너를 닫습니다.
8. **실행** 을 선택하여 수정된 ER 모델 매핑을 실행합니다.
9. **V-00002** 와 같은 바우처 ID를 입력한 후 **확인** 을 선택합니다.

    Infolog에는 SharePoint 폴더에 잘못된 공급 업체 계정이 포함되어 있어 가져올 수 없다는 알림이 포함되어 있습니다.

    [![Run ER 모델 매핑을 완료했습니다.](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. **원본 페이지의 파일 상태** 에서 **새로 고침** 을 선택한 다음 **파일** 섹션에서 파일 목록을 검토합니다.

    [![선택한 소스에 대한 ER 파일 상태 페이지.](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   **가져오기 형식 섹션의 소스 로그** 는 가져오기 프로세스가 실패했으며 파일이 SharePoint 파일 오류 폴더에 있음을 나타냅니다(**삭제됨** 확인란이 선택되지 않음). 적절한 공급 업체 코드를 추가하여 이 파일을 SharePoint 수정한 다음 파일 가져오기 소스(메인) SharePoint 폴더로 이동하면 파일을 다시 가져올 수 있습니다.

11. 1099에 대한 **미지급금** \> **정기 작업** \> **세금 1099** \> **공급 업체 결제** 를 선택하고 **시작 날짜** 및 **종료 날짜** 필드에 적절한 값을 입력한 다음 **수동 1099 거래** 를 선택합니다.

    상품권 V-00001 거래만 가능합니다. 마지막으로 가져온 거래에 대한 오류가 Excel 파일에서 발견되었지만 바우처 V-00002에 대한 거래를 사용할 수 없습니다.

## <a name=""></a><a name="limitations">한계</a>

Dynamics 365 Finance 버전 10.0.25 이전 버전에서 ER 프레임워크의 UI(사용자 인터페이스)는 무인 모드에서 데이터 가져오기를 위한 모델 매핑을 실행할 새 일괄 작업을 시작하는 기능을 제공하지 않습니다. 대신 구성된 ER 모델 매핑을 애플리케이션 UI에서 호출하여 인바운드 파일에서 데이터를 가져올 수 있도록 새 논리를 개발해야 합니다. 이 논리를 개발하려면 약간의 엔지니어링 작업이 필요합니다. 

관련 ER API에 대한 자세한 내용은 [애플리케이션 업데이트 7.3에 대한 ER 프레임워크 API 변경 사항](er-apis-app73.md#code-to-run-a-format-mapping-for-data-import)의 [데이터 가져오기에 대한 형식 매핑을 실행하는 코드 섹션](er-apis-app73.md)을 참조하십시오. `Application Suite` 모델 클래스의 `BankImport_RU` 코드를 검토하여 사용자 지정 논리를 구현하는 방법을 확인하십시오. `BankImport_RU` 클래스는 `RunBaseBatch` 클래스를 확장합니다. 특히, `runER()` ER 모델 매핑의 러너로 `ERIModelMappingDestinationRun` 객체를 생성하는 방법을 검토합니다.

Finance 버전 10.0.25 이상에서 ER 프레임워크 UI는 무인 모드에서 데이터 가져오기를 위한 모델 매핑을 실행하는 새 일괄 작업을 시작하는 기능을 제공합니다. 이 프로세스에 대한 자세한 내용은 [수동으로 선택한 파일에서 일괄 모드로 데이터 가져오기](er-configure-data-import-batch.md)를 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[애플리케이션 업데이트 7.3에 대한 ER 프레임워크 API 변경](er-apis-app73.md)

[애플리케이션 업데이트 10.0.23에 대한 ER 프레임워크 API 변경](er-apis-app10-0-23.md)

[애플리케이션 업데이트 10.0.25에 대한 ER 프레임워크 API 변경](er-apis-app10-0-25.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
