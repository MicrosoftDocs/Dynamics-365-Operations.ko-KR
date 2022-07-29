---
title: ER 수평으로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가(1부 - 디자인 형식)
description: 이번에는 보고서를 OPENXML 워크시트(Excel) 파일로 생성하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다. (1부)
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab360c259af37ce3995d3cd2560bc2e765e0bceb
ms.sourcegitcommit: e3290eb58ae569a59d6ae2e6922e7d8be8f1980f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "8460810"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER 수평으로 확장 가능한 범위를 사용하여 Excel 보고서에 동적으로 열 추가(1부 - 디자인 형식)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER(전자 보고) 형식을 구성하여 보고서를 OPENXML 워크시트(Excel) 파일로 생성할 수 있는 방법을 설명합니다. 여기서 필요한 열은 수평 확장 가능한 범위로 동적으로 생성될 수 있습니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 다음 세 가지 작업 가이드를 완료해야 합니다.

ER 구성 공급자를 만들고 활성으로 표시

ER 재무 차원을 데이터 소스로 사용(1부 - 모델 매핑) 디자인 데이터 모델"

ER 재무 차원을 데이터 소스로 사용(2부 - 모델 매핑) 모델 매핑

또한 [샘플 재무 차원 웹 서비스 보고서](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx)에 있는 샘플 보고서와 함께 템플릿의 로컬 복사본을 다운로드하여 저장해야 합니다.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.

## <a name="create-a-new-report-configuration"></a>새 보고서 구성 만들기

1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 `Financial dimensions sample model`을 선택합니다.
3. 구성 만들기를 클릭하여 드롭 대화 상자를 엽니다.
4. 수량 필드에 `Format based on data model Financial dimensions sample model`을(를) 입력합니다.
    * 미리 만든 모델을 새 보고서의 데이터 소스로 사용합니다.  
5. 이름 필드에 `Sample report with horizontally expandable ranges`를 입력하십시오.
    * 수평으로 확장 가능한 범위가 있는 샘플 보고서  
6. 설명 필드에 `To make Excel output with dynamically adding columns`를 입력합니다.
    * 동적으로 열을 추가하여 Excel 출력을 만들려면  
7. 데이터 모델 정의 필드에서 항목을 선택하십시오.
8. 구성 만들기를 클릭합니다.

## <a name="design-the-report-format"></a>보고서 형식 디자인

1. 디자이너를 클릭합니다.
2. `Show details` 토글 버튼을 켭니다.
3. 작업 창에서 가져오기를 클릭합니다.
4. Excel에서 가져오기를 클릭합니다.
5. 첨부 파일을 클릭합니다.
    * 보고서 템플릿을 가져옵니다. 이를 위해 다운로드 한 Excel 파일을 사용하십시오.  
6. 새로 만들기를 클릭합니다.
7. 파일을 클릭합니다.
8. 페이지를 닫습니다.
9. 템플릿 필드에서 값을 입력하거나 선택합니다.
    * 다운로드한 템플릿을 선택합니다.  
10. '확인'을 클릭합니다.
    * 재무 차원에 대해 선택한 열 수만큼(사용자 대화 상자 양식에서) Excel 출력을 동적으로 생성하려면 새 범위를 추가하십시오. 모든 열의 각 셀은 단일 재무 차원의 이름을 나타냅니다.  
11. 추가를 클릭하여 드롭 대화 상자를 엽니다.
12. 트리에서 `Excel\Range`을 선택합니다.
13. Excel 범위 필드에 `DimNames`.
    * DimNames  
14. 복제 방향 필드에서 `Horizontal`을 선택합니다.
15. '확인'을 클릭합니다.
16. 트리에서 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`을 선택합니다.
17. 위로 이동을 클릭합니다.
18. 트리에서 `Excel = "SampleFinDimWsReport"\Cell<DimNames>`을 선택합니다.
19. 잘라내기를 클릭합니다.
20. 트리에서 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`을 선택합니다.
21. 붙여넣기를 클릭합니다.
22. 트리에서 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`을 확장합니다.
23. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`을 확장합니다.
24. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`을 확장합니다.
25. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`을 선택합니다.
    * 재무 차원에 대해 선택한 열 수만큼(사용자 대화 상자 양식에서) Excel 출력을 동적으로 생성하려면 새 범위를 추가하십시오. 모든 열의 각 셀은 각 보고 트랜잭션에 대한 단일 재무 차원 값을 나타냅니다.  
26. 범위 추가를 클릭합니다.
27. Excel 범위 필드에 `DimValues`.
    * 희미한 값  
28. 복제 방향 필드에서 `Horizontal`을 선택합니다.
29. '확인'을 클릭합니다.
30. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>`을 선택합니다.
31. 잘라내기를 클릭합니다.
32. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`을 선택합니다.
33. 붙여넣기를 클릭합니다.
34. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`을 확장합니다.

## <a name="map-format-elements-to-data-sources"></a>데이터 소스에 형식 요소 매핑

1. 매핑 탭을 클릭합니다.
2. 트리에서 `model: Data model Financial dimensions sample model`을 확장합니다.
3. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list`을 확장합니다.
4. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`을 확장합니다.
5. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`을 확장합니다.
6. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>`을 선택합니다.
7. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String`을 선택합니다.
8. 바인딩을 클릭합니다.
9. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`을 선택합니다.
10. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`을 선택합니다.
11. 바인딩을 클릭합니다.
12. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>`을 선택합니다.
13. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real`을 선택합니다.
14. 바인딩을 클릭합니다.
15. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>`을 선택합니다.
16. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real`을 선택합니다.
17. 바인딩을 클릭합니다.
18. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>`을 선택합니다.
19. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String`을 선택합니다.
20. 바인딩을 클릭합니다.
21. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>`을 선택합니다.
22. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date`을 선택합니다.
23. 바인딩을 클릭합니다.
24. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>`을 선택합니다.
25. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String`을 선택합니다.
26. 바인딩을 클릭합니다.
27. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>`을 선택합니다.
28. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`을 선택합니다.
29. 바인딩을 클릭합니다.
30. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`을 선택합니다.
31. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`을 선택합니다.
32. 바인딩을 클릭합니다.
33. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>`을 선택합니다.
34. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`을 선택합니다.
35. 바인딩을 클릭합니다.
36. 트리에서 `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`을 선택합니다.
37. 트리에서 `model: Data model Financial dimensions sample model\Journal: Record list`을 선택합니다.
38. 바인딩을 클릭합니다.
39. 트리에서 `model: Data model Financial dimensions sample model\Dimensions setting: Record list`을 확장합니다.
40. 트리에서 `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String`을 선택합니다.
41. 트리에서 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>`을 선택합니다.
42. 바인딩을 클릭합니다.
43. 트리에서 `model: Data model Financial dimensions sample model\Dimensions setting: Record list`을 선택합니다.
44. 트리에서 `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`을 선택합니다.
45. 바인딩을 클릭합니다.
46. 트리에서 `Excel = "SampleFinDimWsReport"\Cell<CompanyName>`을 선택합니다.
47. 트리에서 `model: Data model Financial dimensions sample model\Company: String`을 선택합니다.
48. 바인딩을 클릭합니다.
49. 저장을 클릭합니다.
50. 페이지를 닫습니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
