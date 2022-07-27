---
title: 고급 은행 조정 가져오기 프로세스 설정
description: 고급 은행 조정 기능으로 전자 은행 거래 내역서를 가져와 Microsoft Dynamics 365 Finance에서 은행 거래와 자동으로 조정할 수 있습니다. 이 문서에서는 은행 거래 내역서 가져오기 기능을 설정하는 방법을 설명합니다.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0efe960bee8f5c2c0b683ad641379345ce6d470180d29893b373acc6e1de8aa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450247"
---
# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>고급 은행 조정 가져오기 프로세스 설정

[!include [banner](../includes/banner.md)]

고급 은행 조정 기능으로 전자 은행 거래 내역서를 가져와 Dynamics 365 Finance에서 은행 거래와 자동으로 조정할 수 있습니다. 이 문서에서는 은행 거래 내역서 가져오기 기능을 설정하는 방법을 설명합니다. 

은행 거래 내역서 가져오기 설정은 전자 은행 거래 내역서의 형식에 따라 다릅니다. Finance는 기본적으로 ISO20022, MT940 및 BAI2의 세 가지 은행 거래 내역서 형식을 지원합니다.

## <a name="set-time-zone-preference"></a>표준 시간대 기본 설정
은행 거래 내역서 가져오기 설정을 구성할 때 가져올 은행 거래 내역서 파일 내 날짜-시간 데이터의 표준 시간대를 고려하는 것이 중요할 수 있습니다. 기본값은 모든 날짜 및 시간 값이 이미 협정 세계시(UTC)라고 가정하므로 데이터를 가져올 때 표준 시간대 변환이 적용되지 않습니다. 

데이터 가져오기에 사용할 표준 시간대를 지정하는 옵션이 있습니다. 이 옵션은 각 **원본 데이터 형식 세부 정보** 페이지의 **표준 시간대 기본 설정** 필드에서 사용할 수 있습니다(**데이터 관리 작업 영역 > 데이터 원본 구성 > 데이터 형식 선택 > 국가별 설정** 빠른 탭). 입력한 이 표준 시간대 기본 설정은 해당 원본 데이터 형식을 사용하는 모든 가져오기에 적용됩니다. 여러 표준 시간대에서 데이터를 가져오는 데 필요한 만큼 데이터 원본 형식을 만들 수 있습니다.  

이 표준 시간대는 사용자 또는 회사의 시간대와 다를 수 있으므로 날짜 및 시간 데이터의 표준 시간대를 명확히 해야 합니다. 표준 시간대 기본 설정을 설정할 때 다음 사항을 고려하는 것이 좋습니다. 

 - 표준 시간대 기본 설정은 해당 원본 데이터 형식을 사용하는 모든 가져오기에 적용됩니다. 여러 표준 시간대에서 데이터 가져오기를 처리하는 데 필요한 만큼 데이터 원본 형식을 만들 수 있습니다. 
 
 - 표준 시간대 기본 설정은 가져오기 파일에 있는 날짜 및 시간 데이터의 현지 표준 시간대여야 합니다. 
 
 - 날짜 및 시간 데이터의 표준 시간대는 사용자 또는 회사의 표준 시간대와 다를 수 있습니다.
 
 - 사용자는 **사용자 옵션** 을 사용하여 자신의 표준 시간대를 조정할 수 있습니다.

다음 조치는 은행 거래 내역서를 가져올 때 잠재적인 날짜 및 시간 충돌을 최소화하는 데 도움이 될 수 있습니다. 

 - 이미 내역서를 가져온 은행 계좌의 표준 시간대 기본 설정을 변경하지 마세요. 표준 시간대 기본 설정을 변경하면 표준 시간대 조정으로 인해 기존 내역서와 관련된 새 내역서의 순서에 영향을 미칠 수 있습니다. 
 
 - 선택한 데이터 원본 형식을 사용하는 모든 가져오기를 검토합니다. 형식에 대해 표준 시간대 기본 설정은 지정하면 해당 형식을 사용하는 모든 가져오기 프로젝트에 적용됩니다. 표준 시간대 기본 설정이 해당 형식을 사용하는 모든 가져오기 프로젝트에 적합한지 확인합니다.

## <a name="sample-files"></a>샘플 파일
세 가지 형식 모두에 대해 전자 은행 거래 내역서를 원래 형식에서 Finance에서 사용할 수 있는 형식으로 변환하는 파일이 있어야 합니다. Microsoft Visual Studio의 애플리케이션 탐색기에 있는 **리소스** 노드에서 필요한 리소스 파일을 찾을 수 있습니다. 파일을 찾은 후 설정 프로세스 중에 더 쉽게 업로드할 수 있도록 알려진 단일 위치에 파일을 복사합니다.

| 리소스 이름                                           | 파일 이름                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>은행 거래 내역서 형식 및 기술 레이아웃의 예
다음은 고급 은행 조정 가져오기 파일 기술 레이아웃 정의 및 세 가지 관련 은행 거래 내역서 예제 파일의 예입니다. [가져오기 파일 예](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| 기술 레이아웃 정의                             | 은행 거래 내역서 예제 파일          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |



## <a name="set-up-the-import-of-iso20022-bank-statements"></a>ISO20022 은행 거래 내역서 가져오기 설정
먼저 데이터 엔터티 프레임워크를 사용하여 ISO20022 은행 거래 내역서에 대한 은행 거래 내역서 형식 처리 그룹을 정의해야 합니다.

1.  **작업 영역** &gt; **데이터 관리** 로 이동합니다.
2.  **가져오기** 를 클릭합니다.
3.  형식의 이름(예: **ISO20022**)을 입력합니다.
4.  **원본 데이터 형식** 필드를 **XML-Element** 로 설정합니다.
5.  **엔터티 이름** 필드를 **은행 거래 내역서** 로 설정합니다.
6.  가져오기 파일을 업로드하려면 **업로드** 를 클릭한 다음 이전에 저장한 **SampleBankCompositeEntity.xml** 파일을 찾아 선택합니다.
7.  은행 거래 내역서 엔터티가 업로드되고 매핑이 완료된 후 엔터티에 대한 **맵 보기** 작업을 클릭합니다.
8.  은행 거래 내역서 엔터티는 4개의 개별 엔터티로 구성된 복합 엔터티입니다. 목록에서 **BankStatementDocumentEntity** 를 선택한 다음 **맵 보기** 작업을 클릭합니다.
9.  **변환** 탭에서 **새로 만들기** 를 클릭합니다.
10. 시퀀스 번호 1에는 **파일 업로드** 를 클릭하고 이전에 저장한 **ISO20022XML-to-Reconciliation.xslt** 파일을 선택합니다. **참고:** 변환 파일은 표준 형식으로 빌드됩니다. 은행은 종종 이 형식과 다르므로 은행 거래 내역서 형식에 매핑하도록 변환 파일을 업데이트해야 할 수도 있습니다. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. **새로 만들기** 를 클릭합니다.
12. 시퀀스 번호 2에는 **파일 업로드** 를 클릭하고 이전에 저장한 **BankReconciliation-to-Composite.xslt** 파일을 선택합니다.
13. **변환 적용** 을 클릭합니다.

형식 처리 그룹이 설정된 후 다음 단계는 ISO20022 은행 거래 내역서에 대한 은행 거래 내역서 형식 규칙을 정의하는 것입니다.

1.  **현금 및 은행 관리** &gt; **설정** &gt; **고급 은행 조정 설정** &gt; **은행 거래 내역서 형식** 으로 이동합니다.
2.  **새로 만들기** 를 클릭합니다.
3.  거래 내역서 형식(예: **ISO20022**)을 지정합니다.
4.  형식의 이름을 입력합니다.
5.  **처리 그룹** 필드를 이전에 정의한 그룹(예: **ISO20022**)으로 설정합니다.
6.  **XML 파일** 확인란을 선택합니다.

마지막 단계는 고급 은행 조정을 활성화하고 은행 계좌의 내역서 형식을 설정하는 것입니다.

1.  **현금 및 은행 관리** &gt; **은행 계좌** 로 이동합니다.
2.  은행 계좌를 선택하고 열면 세부 정보가 표시됩니다.
3.  **조정** 탭에서 **고급 은행 조정** 옵션을 **예** 로 설정합니다.
4.  **내역서 형식** 필드를 이전에 만든 형식(예: **ISO20022**)으로 설정합니다.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>MT940 은행 거래 내역서 가져오기 설정
먼저 데이터 엔터티 프레임워크를 사용하여 MT940 은행 거래 내역서에 대한 은행 거래 내역서 형식 처리 그룹을 정의해야 합니다.

1.  **작업 영역** &gt; **데이터 관리** 로 이동합니다.
2.  **가져오기** 를 클릭합니다.
3.  형식의 이름(예: **MT940**)을 입력합니다.
4.  **원본 데이터 형식** 필드를 **XML-Element** 로 설정합니다.
5.  **엔터티 이름** 필드를 **은행 거래 내역서** 로 설정합니다.
6.  가져오기 파일을 업로드하려면 **업로드** 를 클릭한 다음 이전에 저장한 **SampleBankCompositeEntity.xml** 파일을 찾아 선택합니다.
7.  은행 거래 내역서 엔터티가 업로드되고 매핑이 완료된 후 엔터티에 대한 **맵 보기** 작업을 클릭합니다.
8.  은행 거래 내역서 엔터티는 4개의 개별 엔터티로 구성된 복합 엔터티입니다. 목록에서 **BankStatementDocumentEntity** 를 선택한 다음 **맵 보기** 작업을 클릭합니다.
9.  **변환** 탭에서 **새로 만들기** 를 클릭합니다.
10. 시퀀스 번호 1에는 **파일 업로드** 를 클릭하고 이전에 저장한 **MT940TXT-to-MT940XML.xslt** 파일을 선택합니다.
11. **새로 만들기** 를 클릭합니다.
12. 시퀀스 번호 2에는 **파일 업로드** 를 클릭하고 이전에 저장한 **MT940XML-to-Reconciliation.xslt** 파일을 선택합니다. **참고:** 변환 파일은 표준 형식으로 빌드됩니다. 은행은 종종 이 형식과 다르므로 은행 거래 내역서 형식에 매핑하도록 변환 파일을 업데이트해야 할 수도 있습니다. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. **새로 만들기** 를 클릭합니다.
14. 시퀀스 번호 3에는 **파일 업로드** 를 클릭하고 이전에 저장한 **BankReconciliation-to-Composite.xslt** 파일을 선택합니다.
15. **변환 적용** 을 클릭합니다.

형식 처리 그룹이 설정된 후 다음 단계는 MT940 은행 거래 내역서에 대한 은행 거래 내역서 형식 규칙을 정의하는 것입니다.

1.  **현금 및 은행 관리** &gt; **설정** &gt; **고급 은행 조정 설정** &gt; **은행 거래 내역서 형식** 으로 이동합니다.
2.  **새로 만들기** 를 클릭합니다.
3.  거래 내역서 형식(예: **MT940**)을 지정합니다.
4.  형식의 이름을 입력합니다.
5.  **처리 그룹** 필드를 이전에 정의한 그룹(예: **MT940**)으로 설정합니다.
6.  **파일 유형** 필드를 **txt** 로 설정합니다.

마지막 단계는 고급 은행 조정을 활성화하고 은행 계좌의 내역서 형식을 설정하는 것입니다.

1.  **현금 및 은행 관리** &gt; **은행 계좌** 로 이동합니다.
2.  은행 계좌를 선택하고 열면 세부 정보가 표시됩니다.
3.  **조정** 탭에서 **고급 은행 조정** 옵션을 **예** 로 설정합니다.
4.  선택을 확인하고 고급 은행 조정을 활성화하라는 메시지가 표시되면 **확인** 을 클릭합니다.
5.  **내역서 형식** 필드를 이전에 만든 형식(예: **MT940**)으로 설정합니다.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>BAI2 은행 거래 내역서 가져오기 설정
먼저 데이터 엔터티 프레임워크를 사용하여 BAI2 은행 거래 내역서에 대한 은행 거래 내역서 형식 처리 그룹을 정의해야 합니다.

1.  **작업 영역** &gt; **데이터 관리** 로 이동합니다.
2.  **가져오기** 를 클릭합니다.
3.  형식의 이름(예: **BAI2**)을 입력합니다.
4.  **원본 데이터 형식** 필드를 **XML-Element** 로 설정합니다.
5.  **엔터티 이름** 필드를 **은행 거래 내역서** 로 설정합니다.
6.  가져오기 파일을 업로드하려면 **업로드** 를 클릭한 다음 이전에 저장한 **SampleBankCompositeEntity.xml** 파일을 찾아 선택합니다.
7.  은행 거래 내역서 엔터티가 업로드되고 매핑이 완료된 후 엔터티에 대한 **맵 보기** 작업을 클릭합니다.
8.  은행 거래 내역서 엔터티는 4개의 개별 엔터티로 구성된 복합 엔터티입니다. 목록에서 **BankStatementDocumentEntity** 를 선택한 다음 **맵 보기** 작업을 클릭합니다.
9.  **변환** 탭에서 **새로 만들기** 를 클릭합니다.
10. 시퀀스 번호 1에는 **파일 업로드** 를 클릭하고 이전에 저장한 **BAI2CSV-to-BAI2XML.xslt** 파일을 선택합니다.
11. **새로 만들기** 를 클릭합니다.
12. 시퀀스 번호 2에는 **파일 업로드** 를 클릭하고 이전에 저장한 **BAI2XML-to-Reconciliation.xslt** 파일을 선택합니다. **참고:** 변환 파일은 표준 형식으로 빌드됩니다. 은행은 종종 이 형식과 다르기 때문에 은행 거래 내역서 형식에 매핑하도록 변환 파일을 업데이트해야 할 수도 있습니다. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. **새로 만들기** 를 클릭합니다.
14. 시퀀스 번호 3에는 **파일 업로드** 를 클릭하고 이전에 저장한 **BankReconciliation-to-Composite.xslt** 파일을 선택합니다.
15. **변환 적용** 을 클릭합니다.

형식 처리 그룹이 설정된 후 다음 단계는 BAI2 은행 거래 내역서에 대한 은행 거래 내역서 형식 규칙을 정의하는 것입니다.

1.  **현금 및 은행 관리** &gt; **설정** &gt; **고급 은행 조정 설정** &gt; **은행 거래 내역서 형식** 으로 이동합니다.
2.  **새로 만들기** 를 클릭합니다.
3.  거래 내역서 형식(예: **BAI2**)을 지정합니다.
4.  형식의 이름을 입력합니다.
5.  **처리 그룹** 필드를 이전에 정의한 그룹(예: **BAI2**)으로 설정합니다.
6.  **파일 유형** 필드를 **txt** 로 설정합니다.

마지막 단계는 고급 은행 조정을 활성화하고 은행 계좌의 내역서 형식을 설정하는 것입니다.

1.  **현금 및 은행 관리** &gt; **은행 계좌** 로 이동합니다.
2.  은행 계좌를 선택하고 열면 세부 정보가 표시됩니다.
3.  **조정** 탭에서 **고급 은행 조정** 옵션을 **예** 로 설정합니다.
4.  선택을 확인하고 고급 은행 조정을 활성화하라는 메시지가 표시되면 **확인** 을 클릭합니다.
5.  **내역서 형식** 필드를 이전에 만든 형식(예: **BAI2**)으로 설정합니다.

## <a name="test-the-bank-statement-import"></a>은행 거래 내역서 가져오기 테스트
마지막 단계는 은행 거래 내역서를 가져올 수 있는지 테스트하는 것입니다.

1.  **현금 및 은행 관리** &gt; **은행 계좌** 로 이동합니다.
2.  고급 은행 조정 기능이 활성화된 은행 계좌를 선택합니다.
3.  **조정** 탭에서 **은행 거래 내역서** 를 클릭합니다.
4.  **은행 거래 내역서** 페이지에서 **내역서 가져오기** 를 클릭합니다.
5.  **은행 계좌** 필드를 선택한 은행 계좌로 설정합니다. **내역서 형식** 필드가 은행 계좌의 설정에 따라 자동으로 설정됩니다.
6.  **찾아보기** 를 클릭하고 전자 은행 거래 내역서 파일을 선택합니다.
7.  **업로드** 를 클릭합니다.
8.  **확인** 을 클릭합니다.

가져오기에 성공하면 내역서를 가져왔다는 메시지가 표시됩니다. 가져오기에 성공하지 못한 경우 **자료 관리** 작업 영역의 **작업 기록** 섹션에서 작업을 찾습니다. 작업에 대한 **실행 세부 정보** 를 클릭하여 **실행 요약** 페이지를 연 다음 **실행 로그 보기** 를 클릭하여 가져오기 오류를 확인합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
