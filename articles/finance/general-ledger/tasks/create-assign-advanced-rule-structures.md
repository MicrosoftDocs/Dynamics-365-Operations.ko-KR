---
title: 고급 규칙 구조 만들기 및 할당
description: 이 토픽에서는 고급 규칙 구조를 만들고 계정 구조에 할당하는 방법에 대해 설명합니다.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 769f3cb44830a4bc9ef48e5bcfda5a47b87954c20f65d1d3eef5d02af9ed5bd1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450535"
---
# <a name="create-and-assign-advanced-rule-structures"></a>고급 규칙 구조 만들기 및 할당

[!include [banner](../../includes/banner.md)]

이 토픽에서는 고급 규칙 구조를 만들고 계정 구조에 할당하는 방법에 대해 설명합니다. 이 가이드는 USMF 데모 회사를 사용합니다.

## <a name="create-an-advanced-rule-structure"></a>고급 규칙 구조 만들기
1. **탐색 창 > 모듈 > 총계정원장 > 계정 차트 > 구조> 고급 규칙 구조** 로 이동합니다.
2. **새로 만들기** 를 선택하여 드롭 대화 상자를 엽니다.
3. **고급 규칙 구조** 필드에 규칙 구조를 설명하는 이름을 입력합니다.
4. **확인** 을 선택합니다.
5. **세그먼트 추가** 를 선택합니다.
6. 세그먼트 목록에서 재무 차원을 선택합니다. 예: **스토어**.  
7. **세그먼트 추가** 를 선택합니다.
8. **활성화** 를 선택합니다.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>계정 구조에 고급 규칙 구조 적용
1. **탐색 창 > 모듈 > 총계정원장 > 계정 차트 > 구조> 계정 구조 구성** 으로 이동합니다.
2. 목록에서 고급 규칙을 적용할 계정 구조를 찾아 선택합니다.
3. **편집** 을 선택합니다. **고급 규칙** 을 선택하면 계정 구조를 **초안 모드** 로 설정하라는 메시지가 표시됩니다.  
4. **고급 규칙** 을 선택합니다.
5. **새로 만들기** 를 선택하여 드롭 대화 상자를 엽니다.
6. **고급 규칙** 필드에 값을 입력합니다.
7. **이름** 필드에 값을 입력합니다.
8. **만들기** 를 선택합니다.
9. **새 기준 추가** 를 선택합니다.
10. **위치** 필드에서 주 계정 또는 재무 차원을 선택합니다.
11. **연산자** 필드에서 **is between** 및 **includes** 와 같은 옵션을 선택합니다.
12. **값** 필드에 값을 입력합니다.
13. **through** 필드에 값을 입력합니다.
14. **추가** 를 선택하여 드롭 대화 상자를 엽니다.
15. 목록에서 입력한 기준이 충족될 때 사용할 고급 규칙 구조를 찾습니다.
16. **추가** 를 선택합니다.
17. 페이지를 닫습니다.
18. **활성화** 를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]