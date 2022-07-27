---
title: 은행 거래 내역서 파일 가져오기 문제 해결
description: 은행의 은행 거래 명세서 파일이 Microsoft Dynamics 365 Finance에서 지원하는 레이아웃과 일치하는 것이 중요합니다. 은행 거래 내역서에 대한 엄격한 표준으로 인해 대부분의 통합이 올바르게 작동합니다. 그러나 거래 내역서 파일을 가져올 수 없거나 잘못된 결과가 나오는 경우가 있습니다. 일반적으로 이러한 문제는 은행 거래 내역서 파일의 작은 차이로 인해 발생합니다. 이 문서에서는 이러한 차이점을 수정하고 문제를 해결하는 방법을 설명합니다.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc5b9cf3449b48767a27891a019f8fe8df2a900559898e3cb1849d25bec7c987
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450595"
---
# <a name="bank-statement-file-import-troubleshooting"></a>은행 거래 내역서 파일 가져오기 문제 해결

[!include [banner](../includes/banner.md)]

은행의 은행 거래 명세서 파일이 Microsoft Dynamics 365 Finance에서 지원하는 레이아웃과 일치하는 것이 중요합니다. 은행 거래 내역서에 대한 엄격한 표준으로 인해 대부분의 통합이 올바르게 작동합니다. 그러나 거래 내역서 파일을 가져올 수 없거나 잘못된 결과가 나오는 경우가 있습니다. 일반적으로 이러한 문제는 은행 거래 내역서 파일의 작은 차이로 인해 발생합니다. 이 문서에서는 이러한 차이점을 수정하고 문제를 해결하는 방법을 설명합니다.

## <a name="what-is-the-error"></a>오류가 무엇입니까?

은행 거래 내역서 파일 가져오기를 시도한 후 데이터 관리 작업 내역 및 실행 세부 정보로 이동하여 오류를 찾습니다. 오류를 찾으면 문제가 된 거래 내역서, 잔액 또는 거래 내역서 라인을 파악하는 데 도움이 될 수 있습니다. 그러나 문제를 일으키는 필드나 요소를 식별하는 데 도움이 되는 정보를 충분히 얻기는 어렵습니다.

> [!NOTE]
> 가져온 은행 거래 내역서는 단일 시점에 대해서만 겹칠 수 있습니다.  예를 들어 거래 내역서가 2021년 1월 1일 오전 12시에 끝나는 경우 다음 거래 내역서의 시작 날짜는 2021년 1월 1일 오전 12시(12:00:00 AM)가 될 수 있습니다.

## <a name="what-are-the-differences"></a>차이점은 무엇입니까?
은행 파일 레이아웃 정의를 Finance 가져오기 정의와 비교하고 필드와 요소의 차이점을 확인합니다. 은행 거래 내역서 파일을 관련 샘플 Finance 파일과 비교합니다. ISO20022 파일에서 차이점을 쉽게 볼 수 있을 것입니다.

## <a name="time-zone-differences-on-imported-bank-statements"></a>가져온 은행 거래 내역의 표준 시간대 차이
가져온 파일의 날짜-시간 값이 금융 및 운영에 표시된 날짜-시간 값과 다를 수 있습니다. 이러한 불일치를 방지하려면 **데이터 원본 구성** 페이지에서 표준 시간대 기본 설정을 입력합니다. 표준 시간대 기본 설정을 입력하는 방법에 대한 자세한 내용은 [고급 은행 조정 가져오기 프로세스 설정](set-up-advanced-bank-reconciliation-import-process.md)을 참조하세요.

## <a name="transformations"></a>변환
일반적으로 세 가지 변환 중 하나로 변경해야 합니다. 각 변환은 특정 표준에 맞게 작성되었습니다.

| 리소스 이름                                         | 파일 이름                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>변환 디버깅
### <a name="adjust-the-bai2-and-mt940-files"></a>BAI2 및 MT940 파일 조정

BAI2 및 MT940 파일은 텍스트 기반 파일이며 XSLT(Extensible Stylesheet Language Transformations) 디버깅을 사용하려면 조정이 필요합니다. 프로그램은 파일을 가져올 때 이 조정을 수행합니다.

1.  XML 파일을 만들고 다음 텍스트를 파일에 복사합니다.

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  은행 거래 내역서 파일의 내용을 복사하여 **PASTESTATEMENTFILEHERE** 를 대체하도록 XML 파일에 붙여넣습니다.

### <a name="debug-the-xslt"></a>XSLT 디버그

자세한 내용은 <https://msdn.microsoft.com/library/ms255605.aspx>를 참조하세요.

1.  Microsoft Visual Studio를 시작합니다.
2.  콘솔 애플리케이션을 만듭니다.
3.  적절한 XSLT를 엽니다.
4.  XLST 및 해당 속성 페이지를 클릭합니다.
5.  은행 거래 내역서 파일의 위치에 입력을 설정합니다.
6.  출력의 위치와 파일 이름을 정의합니다.
7.  필요한 중단점을 설정합니다.
8.  메뉴에서 **XML** &gt; **XSLT 디버깅 시작** 을 클릭합니다.

### <a name="format-the-xslt-output"></a>XSLT 출력 형식 지정

변환이 실행되면 Visual Studio에서 볼 수 있는 출력 파일이 생성됩니다. Ctrl+A, Ctrl+K 및 Ctrl+D를 사용하여 출력 파일의 서식을 빠르게 지정합니다.

### <a name="adjust-the-transformation"></a>변환 조정

은행 거래 내역서 파일에서 적절한 필드나 요소를 가져오도록 변환을 조정합니다. 그런 다음 해당 필드 또는 요소를 적절한 Finance 요소에 매핑합니다.

### <a name="debitcredit-indicator"></a>차변/대변 표시기

경우에 따라 차변을 대변으로 가져오고 대변을 차변으로 가져올 수 있습니다. 이 문제를 해결하려면 적절한 XSLT를 변경해야 합니다. 은행 거래 내역서가 여러 은행에서 제공되는 경우 모두 동일한 차변/대변 접근 방식을 사용하거나 별도의 변환을 생성해야 합니다.

-   BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator 템플릿
-   ISO20022XML-to-Reconcilation.xslt GetCreditDebit 템플릿
-   MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator 템플릿

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>은행 거래 내역서 형식 및 기술 레이아웃의 예
다음 표에는 고급 은행 조정 가져오기 파일 및 세 가지 관련 은행 거래 내역서 예제 파일에 대한 기술 레이아웃 정의의 예가 나열되어 있습니다. 예제 파일과 기술 레이아웃을 [파일 가져오기 예](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)에서 다운로드할 수 있습니다  

| 기술 레이아웃 정의                             | 은행 거래 내역서 예제 파일          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
