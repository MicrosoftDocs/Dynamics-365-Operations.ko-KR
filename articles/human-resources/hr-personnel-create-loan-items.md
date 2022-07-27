---
title: 대여 항목 만들기
description: 대여 항목은 회사에서 직원에게 빌려주는 전화나 컴퓨터와 같은 실제 물건을 추적하는 데 도움이 되는 기록입니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21127c46615015c30e06465b390f67b835e746cb
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452416"
---
# <a name="create-loan-items"></a>대여 항목 만들기


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



대여 항목은 회사에서 직원에게 빌려주는 전화나 컴퓨터와 같은 실제 물건을 추적하는 데 도움이 되는 기록입니다. 각 실제 항목에는 해당하는 대여 항목이 있어야 합니다. 각 대여 항목 레코드에는 대여 대상, 대여 책임자, 항목 대여 가능 일수가 설명되어 있어야 합니다. 열쇠, 출입카드, 유니폼 등 여러 대여 항목을 동시에 만들 수 있습니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="create-loan-types"></a>대여 유형 만들기
1. **Human Resources** > **작업자** > **대여 항목** > **대여 유형** 을 선택합니다.
2. **새로 만들기** 를 클릭합니다.
3. **대여 유형** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. 이 대여 유형에 할당된 항목이 연체될 수 있는 일수를 입력합니다. 
6. **저장** 을 클릭합니다.
7. 페이지를 닫습니다.
8. 페이지를 새로 고칩니다.

## <a name="create-loan-items"></a>대여 항목 만들기
1. **Human Resources** > **작업자** > **대여 항목** > **대여 항목** 을 선택합니다.
2. **대여 항목 만들기** 를 클릭합니다.
3. **수량** 필드에 숫자를 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **대여 유형** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. 항목을 대여할 수 있는 일수를 입력합니다.
    * 대여된 장비 페이지의 계획된 반환 필드에 대한 기본값은 현재 날짜에 이 숫자를 더한 값으로 계산됩니다.  
9. **담당자** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
10. **선택** 을 클릭합니다.
11. **시작 값** 필드에 숫자를 입력합니다.
12. **간격** 필드에 숫자를 입력합니다.
13. **형식** 필드에 값을 입력합니다.
    * 예를 들어, 대여 항목의 시작 번호가 10인 경우 **형식** 필드에 두 개의 숫자 기호를 입력합니다.  
14. **확인** 을 클릭합니다.
15. 페이지를 새로 고칩니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
