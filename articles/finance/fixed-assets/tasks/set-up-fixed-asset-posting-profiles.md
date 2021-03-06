---
title: 고정 자산 게시 프로필 설정
description: 이 절차는 고정 자산 게시 프로필을 설정하는 방법을 보여줍니다.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee0006c9588a22d720687e7aceb49acc756b83e1
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8451264"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>고정 자산 게시 프로필 설정

[!include [banner](../../includes/banner.md)]

이 절차는 고정 자산 게시 프로필을 설정하는 방법을 보여줍니다. 주제에 제공된 예는 기본 게시 프로필에 관한 것이지만 게시 프로필은 특정 계정 차트 및 재무 보고 요구 사항에 맞게 생성되어야 합니다.

1. 탐색 창에서 **모듈 > 고정 자산 > 설정 > 고정 자산 게시 프로필** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **게시 프로필** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다. 고정 자산 작업에 사용할 각 고정 자산 거래 유형에 대한 게시 프로필을 생성해야 합니다. 이 작업 가이드는 취득 거래 유형으로 시작합니다.  
5. 도구 모음에서 **추가** 를 클릭합니다.
6. **장부** 필드에 값을 입력하거나 선택합니다. **그룹화** 필드를 사용하면 테이블(각 고정 자산에 설정된 하나의 계정) 또는 그룹(각 고정 자산 그룹에 설정된 하나의 계정)까지 게시 프로필을 정의할 수 있습니다. 이 작업 가이드의 경우 지정된 장부가 있는 모든 고정 자산에 적용하려면 값을 "모두"로 설정된 상태로 두세요.  
7. **주 계정** 필드에서 원하는 값을 지정합니다. 취득의 경우 상쇄 계정을 입력하거나 특정 거래에 대해 채우도록 비워 둘 수 있습니다.    
8. **원장 계정** 빠른 탭의 드롭다운 메뉴에서 '취득 조정'을 선택합니다. 취득 조정 거래의 경우 취득 거래에 사용된 것과 같은 계정을 사용합니다.  
9. **추가** 를 클릭합니다.
10. **장부** 필드에 값을 입력하거나 선택합니다.
11. **주 계정** 필드에서 원하는 값을 지정합니다. 취득 조정의 경우 상쇄 계정을 입력하거나 특정 거래에 대해 채우도록 비워 둘 수 있습니다.    
12. **원장 계정** 빠른 탭의 드롭다운 메뉴에서 '감가상각'을 선택합니다.
13. **추가** 를 클릭합니다.
14. **장부** 필드에 값을 입력하거나 선택합니다.
15. **주 계정** 필드에서 원하는 값을 지정합니다.
16. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
17. **원장 계정** 빠른 탭의 드롭다운 메뉴에서 '감가상각 조정'을 선택합니다. 감가상각 조정 거래의 경우 감가상각 거래에 사용된 것과 같은 계정을 사용합니다.  
18. **추가** 를 클릭합니다.
19. **장부** 필드에 값을 입력하거나 선택합니다.
20. **주 계정** 필드에서 원하는 값을 지정합니다.
21. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
22. **원장 계정** 빠른 탭의 드롭다운 메뉴에서 '처분 - 매각'을 선택합니다.
23. **추가** 를 클릭합니다.
24. **장부** 필드에 값을 입력하거나 선택합니다.
25. **주 계정** 필드에서 원하는 값을 지정합니다. 처분의 경우 상쇄 계정을 입력하거나 특정 거래에 대해 채우도록 비워 둘 수 있습니다.  
26. **원장 계정** 빠른 탭의 드롭다운 메뉴에서 '처분 - 폐기'를 선택합니다. '처분 판매'와 '처분 폐기'에는 같은 계정을 사용하세요.  
27. **추가** 를 클릭합니다.
28. **장부** 필드에 값을 입력하거나 선택합니다.
29. **주 계정** 필드에서 원하는 값을 지정합니다. 처분의 경우 상쇄 계정을 입력하거나 특정 거래에 대해 채우도록 비워 둘 수 있습니다.  
30. **처분** 빠른 탭을 확장합니다. 판매 및 폐기 모두에 대해 처분 게시 프로필을 설정해야 합니다.  처분 판매 거래부터 시작하겠습니다.  
31. **추가** 를 클릭합니다.
32. **장부** 필드에 값을 입력하거나 선택합니다.
33. **게시 가치** 필드에 '취득 가치'를 선택합니다.
    * 취득 가치는 모든 연도에 대한 취득 및 취득 조정 가치를 다룰 것입니다. 이러한 거래 유형에 대한 계정을 별도로 정의할 수도 있습니다.  
    * 처분으로 인해 손익이 발생하는지에 따라 다른 계정을 사용하도록 처분 프로세스를 설정할 수 있습니다. 모든 유형의 처분에 대해 같은 계정을 사용하도록 판매 가치 유형을 "모두"로 설정하겠습니다.  
34. **주 계정** 필드에서 원하는 값을 지정합니다.
35. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
36. **추가** 를 클릭합니다.
37. **장부** 필드에 값을 입력하거나 선택합니다.
38. **게시 가치** 필드에 '감가상각(이전 연도)'을 선택합니다.  
38. **주 계정** 필드에서 원하는 값을 지정합니다.
39. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
40. **추가** 를 클릭합니다.
41. **장부** 필드에 값을 입력하거나 선택합니다.
42. **게시 가치** 필드에 '감가상각(올해)'을 선택합니다.
43. **주 계정** 필드에서 원하는 값을 지정합니다.
44. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
45. **추가** 를 클릭합니다.
46. **장부** 필드에 값을 입력하거나 선택합니다.
47. **게시 가치** 필드에 '감가상각 조정(이전 연도)'을 선택합니다.
48. **주 계정** 필드에서 원하는 값을 지정합니다.
49. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
50. **추가** 를 클릭합니다.
51. **장부** 필드에 값을 입력하거나 선택합니다.
52. **게시 가치** 필드에 '감가상각 조정(올해)'을 선택합니다.
53. **주 계정** 필드에서 원하는 값을 지정합니다.
54. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
55. **추가** 를 클릭합니다.
56. **장부** 필드에 값을 입력하거나 선택합니다.
57. **게시 가치** 필드에 '순 장부가액'을 선택합니다.
58. **주 계정** 필드에서 원하는 값을 지정합니다.
59. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
60. **판매 또는 폐기** 필드에서 '폐기'를 선택합니다.
61. **추가** 를 클릭합니다.
62. **장부** 필드에 값을 입력하거나 선택합니다.
63. **게시 가치** 필드에 '취득 가치'를 선택합니다.
64. **주 계정** 필드에서 원하는 값을 지정합니다.
65. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
66. **추가** 를 클릭합니다.
67. **장부** 필드에 값을 입력하거나 선택합니다.
67. **게시 가치** 필드에 '감가상각(이전 연도)'을 선택합니다.  
68. **주 계정** 필드에서 원하는 값을 지정합니다.
69. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
70. **추가** 를 클릭합니다.
71. **장부** 필드에 값을 입력하거나 선택합니다.
72. **게시 가치** 필드에 '감가상각(올해)'을 선택합니다.
73. **주 계정** 필드에서 원하는 값을 지정합니다.
74. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
75. **추가** 를 클릭합니다.
76. **장부** 필드에 값을 입력하거나 선택합니다.
77. **게시 가치** 필드에 '감가상각 조정(이전 연도)'을 선택합니다.
78. **주 계정** 필드에서 원하는 값을 지정합니다.
79. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
80. **추가** 를 클릭합니다.
81. **장부** 필드에 값을 입력하거나 선택합니다.
82. **게시 가치** 필드에 '감가상각 조정(올해)'을 선택합니다.
83. **주 계정** 필드에서 원하는 값을 지정합니다.
84. **상쇄 계정** 필드에서 원하는 값을 지정합니다.
85. **추가** 를 클릭합니다.
86. **장부** 필드에 값을 입력하거나 선택합니다.
87. **게시 가치** 필드에 '순 장부가액'을 선택합니다.
88. **주 계정** 필드에서 원하는 값을 지정합니다.
89. **상쇄 계정** 필드에서 원하는 값을 지정합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
