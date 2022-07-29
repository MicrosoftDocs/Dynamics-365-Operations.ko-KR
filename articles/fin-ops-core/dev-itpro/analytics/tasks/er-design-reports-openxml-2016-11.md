---
title: ER OPENXML 형식의 보고서 생성을 위한 구성 설계(2016년 11월)
description: 이번에는 OPENXML 형식의 전자 문서를 생성하기 위한 템플릿이 포함된 새 전자 보고 구성을 만드는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c3dfe6ce9c918b5fccbd7097096fa359facdf41bbf6fd0fab6c61153171484cd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460719"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER OPENXML 형식의 보고서 생성을 위한 구성 설계(2016년 11월)

[!include [banner](../../includes/banner.md)]

이번에는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 OPENXML 형식의 전자 문서를 생성하기 위한 템플릿이 포함된 새 전자 보고(ER) 구성을 만드는 방법에 대해 설명합니다. 이 구성은 공급 업체 지급 처리에 사용됩니다.

이 예시에서는 샘플 회사 Litware, Inc.에 대한 구성을 생성합니다. 이러한 단계는 GBSI 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 '구성 공급자를 만들고 활성으로 표시' 절차의 단계를 완료해야 합니다. 템플릿을 만들 때 가져올 Excel 파일도 있어야 합니다. 이 파일은 [지급 보고서 템플릿](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx)에서 액세스할 수 있습니다.


## <a name="upload-the-payments-data-model-configuration"></a>결제 데이터 모델 구성 업로드
1. 탐색 분할창에서 **모듈 > 조직 관리 > 작업공간 > 전자 보고** 로 이동하십시오.
2. 목록에서 샘플 회사 Litware, Inc.의 구성 공급자를 표시합니다. 이 구성 공급자가 표시되지 않으면 먼저 [구성 공급자 만들기의 단계를 완료하고 활성으로 표](er-configuration-provider-mark-it-active-2016-11.md)시해야 합니다.
3. **활성 설정** 을 선택합니다.
4. **저장소** 를 선택합니다. 사용 가능한 경우 작업 리소스 유형에 대한 리포지토리를 선택합니다. 사용 가능한 경우 새 리포지토리 생성에 대한 다음 단계를 건너뜁니다.  
5. **추가** 를 선택하여 드롭 대화 상자를 엽니다.
6. **구성 저장소 유형** 필드에 `Operations resourcesdd`를 입력하십시오.
7. **리포지토리 만들기** 를 선택합니다.
8. **확인** 을 선택합니다.
9. **열기** 를 선택합니다.
10. 트리에서 **결제 모델** 을 선택합니다.
11. **가져오기** 를 선택합니다. 이 데이터 모델을 가져옵니다. 새로운 형식 구성에서 데이터 소스로 사용됩니다. 이 구성을 이미 가져온 경우 이 단계를 건너뜁니다.  
12. **예** 를 선택합니다.
13. 전자 보고 페이지로 돌아갈 때까지 페이지를 닫습니다.

## <a name="create-a-new-format-configuration"></a>새 형식 구성 만들기
1. **보고 구성** 을 선택합니다.
2. 트리에서 **결제 모델** 을 선택합니다.
3. **구성 만들기** 를 선택하여 드롭 대화 상자를 엽니다.
4. **수량** 필드에 `Format based on data model PaymentModel`을(를) 입력합니다. PaymentModel 데이터 모델을 기반으로 하는 형식을 작성하십시오.
5. **이름** 필드에 `Sample worksheet report`를 입력하십시오. 샘플 워크시트 보고서  
6. **설명** 필드에 `Sample worksheet report for vendors' payments`를 입력합니다. 공급 업체 지급에 대한 샘플 워크시트 보고서.  
7. **데이터 모델 정의** 필드에서 값을 입력하거나 선택하십시오. **CustomerCreditTransferInitiation** 정의를 선택하십시오.  
8. **구성 만들기** 를 선택합니다.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>OPENXML 워크시트 형식으로 새 문서 디자인
1. 트리에서 **지급 모델\샘플 워크시트 보고서** 를 선택합니다.
2. **디자이너** 를 선택합니다.
3. 작업 창에서 **송장** 을 선택합니다.
4. **Excel에서 가져오기** 를 선택합니다.
5. **첨부 파일** 을 선택합니다. 기존 Excel 문서를 템플릿으로 첨부합니다.  
6. **새로 만들기** 를 선택합니다.
7. **파일** 선택 기존 Excel 파일을 가리킵니다.  
8. 페이지를 닫습니다.
9. **템플릿** 필드에서 값을 입력하거나 선택합니다. 템플릿으로 사용할 첨부된 엑셀 파일을 선택합니다.  
10. **확인** 을 선택합니다. ER 형식 구성 요소는 참조 MS Excel 문서(명명 범위)의 구조를 기반으로 하는 설계 형식으로 생성되었습니다.  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>통화 코드별로 합계를 계산하는 새 데이터 소스 만들기
1. **매핑** 탭을 선택합니다.
2. **루트 추가** 를 선택하여 드롭 대화 상자를 엽니다.
3. 트리에서 **Functions\Group by** 를 선택합니다.
4. **이름** 필드에 `PaymentByCurrency`를 입력하십시오.
5. **그룹화 기준 편집** 을 선택합니다.
6. 트리에서 **모델** 을 확장한 다음 **model\Payments** 를 선택합니다.
7. **필드 추가** 를 선택합니다.
8. **그룹화할 대상** 을 선택합니다.
9. 트리에서 **model\Payments** 를 확장한 다음 **model\Payments\Currency** 를 선택합니다.
10. **필드 추가** 를 선택합니다.
11. **그룹화된 필드** 를 선택합니다.
12. 트리에서 **model\Payments\Instructed Amount(InstructedAmount)** 를 선택합니다.
13. **필드 추가** 를 선택한 다음 **집계 필드** 를 선택합니다.
14. **방법** 필드에서 옵션을 선택합니다. **SUM 집계** 함수를 선택합니다.  
15. **이름** 필드에 `TotalInstructuredAmount`를 입력하십시오.
16. **저장** 을 선택합니다.
17. 페이지를 닫습니다.
18. **확인** 을 선택합니다.

## <a name="map-format-components-to-data-sources"></a>데이터 소스에 형식 구성 요소 매핑
1. 트리에서 **model\Payments\Initiating Party(InitiatingParty)\Name** 및 **Excel\ReportHeader\CompanyName** 을 선택합니다.
2. **바인딩** 을 선택합니다.
3. 트리에서 **model\Payments\Creditor\Identification\Source ID(SourceID)** 및 **Excel\PaymLines\VendAccountName** 을 선택합니다.
4. **바인딩** 을 선택합니다.
5. 트리에서 **model\Payments\Creditor\Name** 및 **Excel\PaymLines\VendName** 을 선택합니다.
6. **바인딩** 을 선택합니다.
7. 트리에서 **model\Payments\Creditor Agent(CreditorAgent)\Name** and **Excel\PaymLines\Bank** 를 선택합니다.
8. **바인딩** 을 선택합니다.
9. 트리에서 **model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)** 및 **Excel\PaymLines\RoutingNumber** 를 선택합니다.
10. **바인딩** 을 선택합니다.
11. 트리에서 **model\Payments\Creditor Account(CreditorAccount)\Identification\Number** 및 **Excel\PaymLines\AccountNumber** 를 선택합니다.
12. **바인딩** 을 선택합니다.
13. 트리에서 **model\Payments\Instructed Amount(InstructedAmount)** 및 **Excel\PaymLines\Debit** 를 선택합니다.
14. **바인딩** 을 선택합니다.
15. 트리에서 **model\Payments\Currency** 및 **Excel\PaymLines\Currency** 를 선택합니다.
16. **바인딩** 을 선택합니다.
17. 트리에서 **PaymentByCurrency\grouped\Currency** 및 **Excel\SummaryLines\SummaryCurrency** 를 선택합니다.
18. **바인딩** 을 선택합니다.
19. 트리에서 **PaymentByCurrency\aggregated\TotalInstructuredAmount** 및 **Excel\SummaryLines\SummaryAmount** 를 선택합니다.
20. **바인딩** 을 선택합니다.
21. 트리에서 **PaymentByCurrency** 및 **Excel\SummaryLines** 를 선택합니다.
22. **바인딩** 을 선택합니다.
23. 트리에서 **model\Payments** 및 **Excel\PaymLines** 를 선택합니다.
24. **바인딩** 을 선택합니다.
25. **저장** 을 선택한 다음 페이지를 닫습니다.

## <a name="use-the-created-configuration-for-payments-processing"></a>결제 처리를 위해 생성된 구성 사용
1. **상태 변경** 을 선택합니다.
2. **완료** 를 선택합니다.
3. **확인** 을 선택합니다.
4. 탐색 창에서 **모듈 > 미지급금 > 지급 설정 > 지급 방법** 으로 이동합니다.
5. 빠른 필터를 사용하여 **전자** 값으로 **지급 방법** 필드를 필터링합니다.
6. **편집** 을 선택합니다.
7. **파일 형식** 섹션을 확장합니다.
8. **일반 전자 보고** 필드에서 **예** 를 선택합니다.
9. **내보내기 형식 구성** 필드에서 값을 입력하거나 선택합니다. **샘플 워크시트 보고서** 구성을 선택합니다.  
10. **저장** 을 선택합니다.
11. 페이지를 닫습니다.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>지급 분개 처리 테스트를 위해 생성된 구성 사용
1. 탐색 창에서 **모듈 > 미지급금 > 지급 > 지급 분개** 로 이동합니다.
2. **새로 만들기** 를 선택하여 신규 라인을 생성합니다.
3. **이름** 필드에 **VendPay** 를 입력합니다.
4. **라인** 을 선택합니다.
5. **계정** 필드에서 `GB_SI_000001` 값을 지정합니다.
6. **차변** 을 `1000`로 설정합니다.
7. **새로 만들기** 를 선택합니다.
8. **계정** 필드에서 `GB_SI_000005` 값을 지정합니다.
9. **차변** 을 `2000`로 설정합니다.
10. **통화** 필드에 `EUR`를 입력합니다.
11. **오프셋 계정** 필드에서 `GBSI OPER` 값을 지정합니다.
12. **지급 방법** 필드에 `Electronic`를 입력합니다.
13. **저장** 을 선택합니다.
14. **결제 생성** 을 선택합니다.
15. **지급 방법** 필드에 `Electronic`를 입력합니다.
16. **파일 이름** 필드에 `Payments`.
17. **은행 계좌** 필드에 `GBSI OPER`를 입력합니다.
18. **확인** 을 선택한 다음 다시 **확인** 을 선택합니다. 이 지급 메시지에 사용된 각 통화 코드에 대한 합계뿐만 아니라 지급 라인의 세부 사항을 포함하여 생성된 워크시트를 검토하십시오.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
