---
title: 조달 범주 계층에 대한 정책 설정
description: 이 절차를 사용하여 범주에서 제품을 주문하기 위한 규칙을 설정하세요.
author: Henrikan
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee056d7c2a8bdc9bcd2f5a0f4b96a7bf69c8c862
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448972"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>조달 범주 계층에 대한 정책 설정

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 범주에서 제품을 주문하기 위한 규칙을 설정하세요. 규칙은 특정 구매 정책에 대해 정의됩니다. 범주 액세스 규칙은 직원이 구매 요청을 생성할 때 액세스할 수 있는 조달 범주를 제어합니다. 요청이 생성될 때 적용해야 하는 구매 정책 및 범주 액세스 규칙은 직원이 속한 법인 및 운영 단위에 의해 결정됩니다. 데모 데이터 회사 USMF에서 이 절차를 사용할 수 있습니다. 이 작업은 일반적으로 구매 관리자가 수행합니다.


## <a name="find-the-procurement-policy"></a>조달 정책 찾기
1. 탐색 창에서 **모듈 > 조달 및 소싱 > 설정 > 정책 > 구매 정책** 으로 이동합니다.
2. '조달 정책 USMF' 정책에 대한 링크를 클릭합니다. 이것은 규칙을 추가할 정책입니다. 활성 정책이어야 합니다.  

## <a name="create-a-category-access-rule"></a>범주 액세스 규칙 만들기
1. **정책 규칙** 빠른 탭을 확장합니다.
2. **정책 규칙 유형** 목록에서 **범주 액세스 정책 규칙** 을 선택합니다. **정책 규칙 만들기** 단추가 흐리게 표시되면 범주 액세스에 대한 활성 정책 규칙이 이미 있기 때문입니다. **유효** 및 **만료** 필드를 확인하여 어떤 항목인지 확인한 다음 선택하고 **정책 규칙 폐기** 를 클릭합니다. **정책 규칙 만들기** 단추를 사용할 수 있다면 아무 것도 할 필요가 없습니다.  
3. **정책 규칙 만들기** 를 클릭합니다.
4. **적용 날짜** 필드에 날짜와 시간을 입력합니다. 시간은 이미 활성화된 다른 규칙과 겹치지 않아야 합니다.  
5. 규칙을 적용할 범주를 선택합니다. 이것이 어떤 범주인지 기록해 두세요. 나중에 필요합니다. 카테고리를 선택하면 상위 카테고리도 선택된 카테고리 목록에 추가됩니다. 선택한 범주의 모든 하위 범주에 규칙을 적용하려면 **하위 범주 포함** 확인란을 선택합니다.
6. 오른쪽 화살표를 클릭하여 **선택한 범주** 목록에 추가합니다.  
4. **확인** 을 클릭합니다. **상위 규칙 포함** 옵션을 예로 설정하면 하위 범주에 대해 정의된 정책 규칙이 없는 경우 상위 범주에 대해 정의한 정책 규칙이 하위 범주에도 할당됩니다.

## <a name="create-a-category-policy-rule"></a>범주 정책 규칙 만들기
1. **정책 규칙 유형** 목록에서 **범주 정책 규칙** 을 선택합니다. **정책 규칙 생성** 버튼이 흐리게 표시되면 활성 정책 규칙을 선택한 다음 **정책 규칙 폐기** 를 클릭합니다.  
2. **정책 규칙 만들기** 를 클릭합니다.
3. **적용 날짜** 필드에 날짜와 시간을 입력합니다.
4. **추가** 를 클릭합니다.
5. **범주** 필드에서 **범주 액세스 규칙** 에 사용한 것과 동일한 범주를 선택합니다.
6. **공급업체 선택** 필드에서 옵션을 선택합니다. 요청이 생성될 때 범주에 대해 선택할 수 있는 공급업체 종류를 제어하는 규칙을 선택합니다.  
7. **닫기** 를 클릭합니다. 정의한 정책 규칙은 소비 유형의 요청에 대한 것입니다. 보충 유형의 요청에 대한 정책을 정의하려면 "보충 범주 액세스 정책 규칙"이라는 정책 규칙 유형에 대한 규칙을 생성합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]