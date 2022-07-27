---
title: 계정 구조 만들기
description: 이 절차는 계정 구조를 만드는 과정을 안내합니다.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9ba43e243df4ba4b7c0eb6188629686206ff09b
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2021
ms.locfileid: "8450919"
---
# <a name="create-account-structures"></a>계정 구조 만들기

[!include [banner](../../includes/banner.md)]

이 절차는 계정 구조를 만드는 과정을 안내합니다. 단계에서는 데모 데이터 회사 USMF를 사용합니다.

1. **탐색 창 > 모듈 > 총계정원장 > 계정 차트 > 구조> 계정 구조 구성** 으로 이동합니다.
2. **작업 창** 에서 **새로 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.
3. **계정 구조** 필드에 계정 구조의 목적을 설명하는 이름을 입력합니다.
4. **설명** 필드에 계정 구조의 목적을 지정하는 설명을 입력합니다.
5. **만들기** 를 클릭합니다.
6. **세그먼트 및 허용 값** 에서 **세그먼트 추가** 를 클릭합니다.
7. 차원 목록에서 계정 구조에 추가할 차원을 선택합니다.
8. 목록 끝에서 **세그먼트 추가** 를 클릭합니다.
9. 필요에 따라 6~9단계를 반복합니다.
10. **허용 값 세부 정보** 섹션에서 허용된 값을 편집할 세그먼트를 선택합니다.
    예를 들어 **주 계정** 필드를 클릭합니다.  
11. **연산자** 필드에서 is between 및 included와 같은 옵션을 선택합니다.
12. **값** 필드에 값을 입력합니다. 예: 600000.  
13. **through** 필드에 값을 입력합니다. 예: 699999.  
14. **허용 값 세부 정보** 섹션에서 **적용** 을 클릭합니다.
15. 필요에 따라 10~15단계를 반복합니다.  
16. **허용 값 세부 정보** 섹션에서 **새 기준 추가** 를 클릭합니다.
17. 연산자 필드에서 is between 및 included와 같은 옵션을 선택합니다.
18. **값** 필드에 값을 입력합니다. 예: 033.  
19. **through** 필드에 값을 입력합니다. 예: 034.  
20. **적용** 을 클릭합니다.
21. 그리드에서 허용된 값을 편집할 세그먼트를 선택합니다. 예: 비용 센터.  
22. **CostCenter 필드** 에 값을 입력합니다. 예: 007..021.  
23. **세그먼트 및 허용 값** 에서 **추가** 를 클릭합니다.
24. **MainAccount** 필드에 값을 입력합니다. 예: 600000..699999  
25. 그리드에서 허용된 값을 편집할 세그먼트를 선택합니다. 예: 부서.  
26. 부서 필드에 값을 입력합니다. 예: 032.  
27. CostCenter 필드에 값을 입력합니다. 예: 086.  
28. **작업 창** 에서 **확인** 을 클릭합니다.
29. **작업 창** 에서 **활성화** 를 클릭합니다.
30. **활성화** 를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
