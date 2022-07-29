---
title: 직무 분담의 갈등 파악 및 해결
description: 이 항목에서는 직무 분리에서 충돌을 식별하고 해결하는 방법에 대해 설명합니다.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0638699c0e569bbe67024a87d6c55729642557cb085ee899aa98aa0022b12840
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460988"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>직무 분담의 갈등 파악 및 해결

[!include [banner](../../includes/banner.md)]

이 항목에서는 직무 분리에서 충돌을 식별하고 해결하는 방법에 대해 설명합니다. 다른 사용자가 수행해야 하는 작업을 구분하는 규칙을 설정할 수 있습니다. 이 개념을 직무 분리라고 합니다. 보안 역할의 정의 또는 사용자의 역할 할당이 규칙을 위반하면 충돌이 기록됩니다. 모든 충돌은 관리자가 해결해야 합니다. 충돌을 식별하고 해결하려면 다음 절차를 완료합니다.

규칙을 추가한 후 모든 기존 역할이 규정을 준수하는지 확인합니다. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>기존 역할 및 직무가 직무 분리에 대한 새로운 규칙을 준수하는지 확인
1. **시스템 관리** > **보안** > **직무 분리** > **직무 분리 규칙** 으로 이동합니다.
3. **의무 및 역할 검증** 을 선택합니다. 역할이 규칙을 위반하는 경우 규칙 이름, 역할 및 충돌하는 의무 이름이 포함된 메시지가 표시됩니다. 충돌하는 역할은 **보안 구성** 을 사용하여 수정해야 하며 충돌하는 의무를 포함할 수 없습니다. 선택한 규칙을 위반하는 역할이 없으면 모든 역할이 준수한다는 메시지가 표시됩니다.   

> [!NOTE]
> 유효성 검사는 선택한 규칙에 대해서만 수행됩니다. 각 규칙의 준수 여부를 확인하는 것이 중요합니다.   

역할을 생성하거나 수정하면 직무 분리 규칙이 자동으로 적용됩니다. 역할에 충돌하는 임무를 할당할 수 없습니다.

다음으로 모든 기존 역할 할당이 규정을 준수하는지 확인합니다.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>사용자 역할 할당이 직무 분리에 대한 새로운 규칙을 준수하는지 확인
1. **시스템 관리 > 보안 > 직무 분리 > 사용자 역할 할당 준수 여부 확인** 으로 이동합니다.
2. **확인** 을 선택합니다. 알림은 유효성 검사 결과를 표시합니다. 충돌은 **직무 분리 해결되지 않은 충돌** 페이지에 기록됩니다.   

역할에 사용자를 할당하면 직무 분리 규칙이 자동으로 적용됩니다. 충돌하는 의무가 포함된 역할에 사용자를 할당하려고 하면 오류 메시지가 나타납니다. 그런 다음 추가 역할 할당을 거부하거나 허용하여 충돌을 해결해야 합니다. 할당이 허용된 후 추가 역할이 할당됩니다. 

> [!NOTE]
> Active Directory 도메인 그룹을 기반으로 역할이 할당된 사용자에 대한 충돌은 현재 확인되지 않습니다.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>충돌하는 사용자 역할 할당 보기 및 해결
1. **시스템 관리** > **보안** > **직무 분리** > **직무 분리 미해결 갈등** 으로 이동합니다. 
2. 충돌을 선택하고 다음 작업 중 하나를 선택합니다. 

  - **거부 할당**: 추가 보안 역할에 대한 사용자 할당을 거부합니다. 자동 역할 할당을 거부하면 사용자가 역할에서 제외된 것으로 표시됩니다. 제외된 사용자에게는 역할과 연결된 액세스 권한이 부여되지 않으며 관리자가 제외를 제거할 때까지 역할에 할당될 수 없습니다. 
-  **허용 할당**: 이렇게 하면 충돌이 무시되고 사용자가 추가 보안 역할에 할당될 수 있습니다. 충돌을 무시하는 경우 **재정의 이유** 필드에 이유를 입력해야 합니다. 재정의된 모든 역할 할당은 **업무 분담 충돌** 페이지에서 볼 수 있습니다.  

> [!NOTE]
> 동일한 사용자에 대해 여러 충돌이 나열되는 경우 사용자 레코드를 선택하고 **사용자** 페이지에서 할당된 역할을 평가합니다. 이 충돌을 방지하려면 추가 또는 수정한 후 각 규칙의 유효성을 검사하세요.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]