---
title: ER 계산 및 합산을 수행하는 형식 구성(3부 - 계산을 사용하여 출력 만들기)
description: 이번에는 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고 형식을 구성하는 방법에 대해 설명합니다. (3부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a59dc2ff4e4e2092911e0aec092ae8182f7601413fc220fda47766a3a0bc061
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460884"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>ER 계산 및 합산을 수행하는 형식 구성(3부 - 계산을 사용하여 출력 만들기)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER Configure format to do counting and summing(파트 2: 계산 구성)' 절차를 따르십시오.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>계산 및 합산 정보를 사용하도록 이 보고서를 구성합니다.
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.
3. 트리에서 'Intrastat 모델'을 확장합니다.
4. 트리에서 'Intrastat model\Intrastat(DE)'를 확장합니다.
5. 트리에서 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'을 선택합니다.
6. 디자이너를 클릭합니다.
7. 매핑 탭을 클릭합니다.
8. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
    * 새 데이터 소스를 추가하여 기억된 블록 목록을 가져옵니다.  
9. 트리에서 'Functions\Calculated field'를 선택합니다.
10. 이름 필드에 '$BlocksList'를 입력합니다.
    * $BlocksList  
11. 수식 편집을 클릭합니다.
12. 트리에서 '데이터 수집 함수\COLLECTEDLIST'를 선택합니다.
13. 함수 추가를 클릭합니다.
14. 데이터 소스 추가를 클릭합니다.
15. 수식 필드에 'COLLECTEDLIST('$BlockName', '.
    * COLLECTEDLIST('$BlockName',  
16. 수식 필드에 'COLLECTEDLIST('$BlockName', '*')'를 입력합니다.
    * COLLECTEDLIST('$BlockName', '*')  
17. 저장을 클릭합니다.
    * '*' 패턴은 모든 블록이 이 기록의 목록에 포함됨을 의미합니다.  
18. 페이지를 닫습니다.
19. '확인'을 클릭합니다.
20. 형식 탭을 클릭합니다.
21. 트리에서 'Intrastat\Data'를 선택합니다.
22. 추가를 클릭하여 드롭 대화 상자를 엽니다.
23. 트리에서 '텍스트\시퀀스'를 선택합니다.
24. 이름 필드에 '블록별 합계'를 입력합니다.
    * 블록별 합계  
25. 특수 문자 필드에서 '새 줄 - Windows(CR LF)'를 선택합니다.
26. '확인'을 클릭합니다.
27. 트리에서 'Intrastat\Data\Totals by block'을 선택합니다.
28. 추가를 클릭하여 드롭 대화 상자를 엽니다.
29. 트리에서 '텍스트\문자열'을 선택합니다.
30. 이름 필드에 '차단 코드'를 입력합니다.
    * 블록 코드  
31. '확인'을 클릭합니다.
32. 스트링 추가를 클릭합니다.
33. 이름 필드에 '라인 계산'을 입력합니다.
    * 라인 카운팅  
34. '확인'을 클릭합니다.
35. 스트링 추가를 클릭합니다.
36. 이름 필드에 '총 금액'을 입력합니다.
    * 총액  
37. '확인'을 클릭합니다.
38. 매핑 탭을 클릭합니다.
39. 트리에서 '$BlocksList'를 선택합니다.
40. 바인딩을 클릭합니다.
    * 암기된 각 블록에 대한 요약 줄을 만듭니다.  
41. 형식 탭을 클릭합니다.
42. 트리에서 'Intrastat\Data\Totals by blocks\Block code'를 선택합니다.
43. 매핑 탭을 클릭합니다.
44. 수식 편집을 클릭합니다.
45. 수식 필드에 ''차단 ID: " & '.
    * "블록 ID: " &  
46. 트리에서 'ArchiveRelations'를 확장합니다.
47. 트리에서 '$BlocksList\Value'를 선택합니다.
48. 데이터 소스 추가를 클릭합니다.
49. 저장을 클릭합니다.
50. 페이지를 닫습니다.
51. 형식 탭을 클릭합니다.
52. 트리에서 'Intrastat\Data\Totals by blocks\Block code'를 선택합니다.
53. 매핑 탭을 클릭합니다.
54. 수식 편집을 클릭합니다.
    * 이 보고서에 표시된 각 블록에 대해 송장 금액의 합계가 될 출력을 생성합니다.  
55. 수식 필드에 ''이 블록의 줄 수: " & '.
    * "이 블록의 줄 수: " &  
56. 수식 필드에 ''이 블록의 줄 수: " & TEXT('.
    * "이 블록의 줄 수: “ & TEXT(  
57. 트리에서 '데이터 수집 함수\COUNTIFS'를 선택합니다.
58. 함수 추가를 클릭합니다.
59. 데이터 소스 추가를 클릭합니다.
60. 수식 필드에 ''이 블록의 줄 수: " & TEXT(COUNTIFS('$BlockName', '.
    * "이 블록의 줄 수: " & TEXT(COUNTIFS('$BlockName',  
61. 트리에서 'ArchiveRelations'를 확장합니다.
62. 트리에서 '$BlocksList\Value'를 선택합니다.
63. 데이터 소스 추가를 클릭합니다.
64. 수식 필드에 ''이 블록의 줄 수 '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.
    * "이 블록의 줄 수: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. 트리에서 '아카이브'를 선택합니다.
66. 데이터 소스 추가를 클릭합니다.
67. 수식 필드에 ''이 블록의 줄 수: & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', *'))'.
    * "이 블록의 줄 수: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. 저장을 클릭합니다.
69. 페이지를 닫습니다.
70. 형식 탭을 클릭합니다.
71. 트리에서 'Intrastat\Data\Totals by blocks\Total amount'를 선택합니다.
72. 매핑 탭을 클릭합니다.
73. 수식 편집을 클릭합니다.
    * 이 보고서에 표시된 각 블록에 대해 송장 금액의 합계가 될 출력을 생성합니다.  
74. 공식 필드에 ''송장 금액 합계: & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', *'))'.
    * "송장 금액 합계: & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', *'))'.  
75. 저장을 클릭합니다.
76. 페이지를 닫습니다.
77. 저장을 클릭합니다.
78. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]