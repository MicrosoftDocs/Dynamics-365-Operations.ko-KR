---
title: 조직 보고서 계층 구조 만들기
description: 이 절차를 사용하여 조직 보고를 위한 보고서 계층 구조를 만듭니다.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e9d5cc6fd6188c988a433fcd7f2bf81bf31668edf762c0ed3bcbf67477a4e35
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450181"
---
# <a name="create-an-organization-report-hierarchy"></a>조직 보고서 계층 구조 만들기

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 조직 보고를 위한 보고서 계층 구조를 만듭니다. 이 레코딩의 목적은 전체 조직 보고 구조가 만들어질 때까지 계속할 수 있도록 차원 계층 구조를 안내하는 것입니다. 이 레코딩은 USP2 데모 데이터 회사를 사용합니다.

1. 원가 회계 > 차원 > 차원 계층으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. HierarchyTypeComboBox 필드에서 '차원 분류 계층'을 선택합니다.
    * 차원 분류 계층을 선택합니다. 차원 분류 계층 유형은 규칙 정의와 보고서 생성에 사용됩니다. 비용 개체, 비용 요소 및 통계 차원과 같은 모든 차원을 지원합니다.  
4. 만들기를 클릭합니다.
5. 차원 계층 이름 필드에 '조직 USP2'를 입력합니다.
6. 차원 필드에서 값을 입력하거나 선택합니다.
    * 비용 센터를 선택합니다.  
7. 저장을 클릭합니다.
8. 계층 보기를 클릭합니다.
9. 새로 만들기를 클릭합니다.
10. Node 이름 필드에 'CEO'를 입력합니다.
11. 저장을 클릭합니다.
12. 새로 만들기를 클릭합니다.
13. Node 이름 필드에 'CEO cost centers'를 입력합니다.
14. 저장을 클릭합니다.
15. 새로 만들기를 클릭합니다.
16. Node 이름 필드에 'Region West'를 입력합니다.
17. 저장을 클릭합니다.
18. 새로 만들기를 클릭합니다.
19. 목록에서 선택한 행을 표시합니다.
20. 원본 차원 구성원 필드에서 값을 입력하거나 선택합니다.
    * 노드에 해당하는 차원 구성원을 선택합니다.  
21. 저장을 클릭합니다.
22. 트리에서 '조직 USP2\CEO\CEO 비용 센터'를 선택합니다.
23. 새로 만들기를 클릭합니다.
24. Node 이름 필드에 'Region West'를 입력합니다.
25. 저장을 클릭합니다.
26. 새로 만들기를 클릭합니다.
27. 목록에서 선택한 행을 표시합니다.
28. 원본 차원 구성원 필드에서 값을 입력하거나 선택합니다.
    * 노드에 해당하는 차원 구성원을 선택합니다.  
29. 저장을 클릭합니다.
30. 트리에서 'Oganization USP2\CEO'을 선택합니다.
31. 새로 만들기를 클릭합니다.
32. Node 이름 필드에 'CFO cost centers'를 입력합니다.
33. 저장을 클릭합니다.
34. 새로 만들기를 클릭합니다.
35. Node 이름 필드에 'Marketing campa'를 입력합니다.
36. Node 이름 필드에 'Marketing campaign'을 입력합니다.
37. 저장을 클릭합니다.
38. 새로 만들기를 클릭합니다.
39. 목록에서 선택한 행을 표시합니다.
40. 원본 차원 구성원 필드에서 값을 입력하거나 선택합니다.
    * 노드에 해당하는 차원 구성원을 선택합니다.  
41. 저장을 클릭합니다.
42. 트리에서 '조직 USP2\CEO\CFO 비용 센터'를 선택합니다.
43. 새로 만들기를 클릭합니다.
44. Node 이름 필드에 'Trade shows'를 입력합니다.
45. 저장을 클릭합니다.
46. 새로 만들기를 클릭합니다.
47. 목록에서 선택한 행을 표시합니다.
48. 원본 차원 구성원 필드에서 값을 입력하거나 선택합니다.
    * 노드에 해당하는 차원 구성원을 선택합니다.  
49. 저장을 클릭합니다.
50. 트리에서 'Oganization USP2\CEO'을 선택합니다.
51. Node 이름 필드에 'CIO cost centers'를 입력합니다.
52. 저장을 클릭합니다.
53. 새로 만들기를 클릭합니다.
54. Node 이름 필드에 'Call centers'를 입력합니다.
55. 저장을 클릭합니다.
56. 새로 만들기를 클릭합니다.
57. 목록에서 선택한 행을 표시합니다.
58. 원본 차원 구성원 필드에서 값을 입력하거나 선택합니다.
    * 노드에 해당하는 차원 구성원을 선택합니다.  
59. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]