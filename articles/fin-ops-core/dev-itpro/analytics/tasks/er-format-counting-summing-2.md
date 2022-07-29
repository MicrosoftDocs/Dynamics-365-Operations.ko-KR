---
title: ER 계산 및 합산을 수행하기 위한 형식 구성(2부 - 계산 구성)
description: 이번에는 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고 형식을 구성하는 방법에 대해 설명합니다. (2부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66b911a7cec6bc1506edb0e4cd6757cb6834a9e977c5e43052725cfa58c1342e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460887"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>ER 계산 및 합산을 수행하기 위한 형식 구성(2부 - 계산 구성)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER Configure format to do counting and summing(파트 1: 형식 만들기)' 절차를 따르십시오.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>계산 및 합계 세부 정보를 추가하는 형식 구성 만들기
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.
3. 트리에서 'Intrastat 모델'을 확장합니다.
4. 트리에서 'Intrastat 모델\Intrastat(DE)'를 선택합니다.
    * Intrastat 보고서 끝에 요약 세부 정보가 있는 행을 추가하여 Microsoft에서 제공하는 형식을 사용자 지정해야 한다고 가정합니다. 수정하려면 Microsoft 인스턴스에서 Intrastat 구성의 자체 인스턴스를 파생하여 이를 수행해야 합니다.  
5. 구성 만들기를 클릭하여 드롭 대화 상자를 엽니다.
6. 새로 만들기 필드에 '이름에서 파생: Intrastat(DE), 마이크로소프트'.
7. 이름 필드에 'Intrastat(DE) with counting & summing'을 입력합니다.
8. 구성 만들기를 클릭합니다.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>출력 세부 정보를 기반으로 계산 및 합계를 수행하도록 이 보고서를 구성합니다.
1. 디자이너를 클릭합니다.
2. 출력 세부 정보 수집 필드에서 예를 선택합니다.
    * 이 플래그는 Intrastat 파일을 생성하기 위한 출력 세부 정보를 수집하는 프로세스가 런타임에 활성화됩니다.  
    * 다양한 Intrastat 방향에 대해 계산을 수행해야 하므로 이 형식 구성의 데이터 소스 목록에 전용 모델 열거를 추가하십시오.  
3. 매핑 탭을 클릭합니다.
4. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
5. 트리에서 '데이터 모델\열거'를 선택합니다.
6. 이름 필드에 '방향'을 입력합니다.
7. 모델 열거 필드에서 값을 입력하거나 선택합니다.
    * 방향 값을 선택합니다.  
8. '확인'을 클릭합니다.
9. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
10. 트리에서 'Functions\Calculated field'를 선택합니다.
11. 이름 필드에 '$BlockName'을 입력합니다.
12. 수식 편집을 클릭합니다.
13. 수식 필드에 ''차단''을 입력합니다.
14. 저장을 클릭합니다.
15. 페이지를 닫습니다.
16. '확인'을 클릭합니다.
17. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
18. 트리에서 'Functions\Calculated field'를 선택합니다.
19. 이름 필드에 '$RecName'을 입력합니다.
20. 수식 편집을 클릭합니다.
21. 수식 필드에 ''기록''을 입력합니다.
22. 저장을 클릭합니다.
23. 페이지를 닫습니다.
24. '확인'을 클릭합니다.
25. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
26. 트리에서 'Functions\Calculated field'를 선택합니다.
27. 이름 필드에 '$InvName'을 입력합니다.
28. 수식 편집을 클릭합니다.
29. 수식 필드에 ''InvoicedAmountEUR''을 입력합니다.
30. 저장을 클릭합니다.
31. 페이지를 닫습니다.
32. '확인'을 클릭합니다.
33. 트리에서 'Intrastat\Data'를 선택합니다.
34. '수집된 데이터 키 이름' 필드의 편집 버튼 클릭
35. 데이터 소스 추가를 클릭합니다.
    * $BlockName  
36. 저장을 클릭합니다.
37. 페이지를 닫습니다.
38. 수집된 데이터 키 값 필드에 대해 편집 버튼을 클릭합니다.
39. 수식 필드에 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, 'Import', 'Export')'를 입력합니다.
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, '가져오기', '내보내기')  
40. 저장을 클릭합니다.
41. 페이지를 닫습니다.
    * 이 시퀀스의 행을 세십시오. 결과는 다른 방향에 대해 'block'이라는 이름으로 별도로 사용됩니다. 값 'Import'는 모든 도착 Intrastat 거래에 사용됩니다. '내보내기' 값은 모든 Intrastat 디스패치 트랜잭션에 사용됩니다. 이것을 가상 Excel 스프레드시트라고 생각하십시오. 각 트랜잭션에 대해 첫 번째 열 '블록'이 '가져오기' 및 '내보내기' 값으로 채워지는 행입니다.  
42. 트리에서 'Intrastat\Data: 순서
43. 트리에서 'Intrastat\Data: 시퀀스\도착?'.
44. '수집된 데이터 키 이름' 필드에 대해 편집 버튼을 클릭합니다.
    * 이 시퀀스의 행을 세십시오. 결과는 '기록'이라는 이름을 사용하여 기억됩니다.  
45. 트리에서 '아카이브'를 선택합니다.
46. 데이터 소스 추가를 클릭합니다.
47. 저장을 클릭합니다.
48. 페이지를 닫습니다.
49. '수집된 데이터 키 값' 필드에 대한 편집 버튼 클릭
50. 수식 필드에 'Intrastat.CommodityRecord.CommodityCode'를 입력합니다.
51. 저장을 클릭합니다.
52. 페이지를 닫습니다.
    * 이 시퀀스의 행을 세십시오. 결과는 다른 상품 코드에 대해 별도로 '기록'라는 이름과 함께 사용됩니다. 이것을 가상 Excel 스프레드시트라고 생각하십시오. 각 거래에 대해 첫 번째 열 '블록'이 '가져오기' 및 '내보내기' 값으로 채워지고 두 번째 블록 '기록'가 상품 코드 값으로 채워지는 행입니다.  
53. 트리에서 'Intrastat\Data: 시퀀스\디스패치?'.
54. '수집된 데이터 키 이름' 필드의 편집 버튼 클릭
55. 트리에서 '아카이브'를 선택합니다.
56. 데이터 소스 추가를 클릭합니다.
57. 저장을 클릭합니다.
58. 페이지를 닫습니다.
59. '수집된 데이터 키 값' 필드의 편집 버튼을 클릭합니다.
60. 수식 필드에 'Intrastat.CommodityRecord.CommodityCode'를 입력합니다.
61. 저장을 클릭합니다.
62. 페이지를 닫습니다.
63. 트리에서 'Intrastat\Data: 시퀀스\디스패치: 순서
64. 트리에서 'Intrastat\Data: 시퀀스\디스패치: 시퀀스?\Record = Intrastat.CommodityRecord'.
65. 형식 탭을 클릭합니다.
66. 트리에서 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'를 선택합니다.
67. 매핑 탭을 클릭합니다.
68. '수집된 데이터 키 이름' 필드의 편집 버튼을 클릭합니다.
69. 트리에서 '$InvName'을 선택합니다.
70. 데이터 소스 추가를 클릭합니다.
71. 저장을 클릭합니다.
72. 페이지를 닫습니다.
    * 이 순번의 라인에 대한 송장 금액 값을 요약합니다. 결과는 다양한 Intrastat 방향 및 상품 코드에 대해 'InvoicedAmountEUR'이라는 이름으로 별도로 사용됩니다. 이것을 Excel 스프레드시트의 가상 생성으로 간주합니다. 각 트랜잭션에 대해 첫 번째 열 '블록'이 '가져오기' 및 '내보내기' 값으로 채워지는 행입니다. 두 번째 블록 '기록'는 상품 코드 값으로 채워지고 세 번째 열 'InvoicedAmountEUR'은 송장 금액 값으로 채워집니다.  
73. 트리에서 'Intrastat\Data\Arrivals?'를 확장합니다.
74. 트리에서 'Intrastat\Data\Arrivals?\Record = Intrastat.CommodityRecord'를 확장합니다.
75. 형식 탭을 클릭합니다.
76. 트리에서 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'를 선택합니다.
77. 매핑 탭을 클릭합니다.
78. '수집된 데이터 키 이름' 필드의 편집 버튼을 클릭합니다.
79. 트리에서 '$InvName'을 선택합니다.
80. 데이터 소스 추가를 클릭합니다.
81. 저장을 클릭합니다.
82. 페이지를 닫습니다.
83. 저장을 클릭합니다.
84. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]