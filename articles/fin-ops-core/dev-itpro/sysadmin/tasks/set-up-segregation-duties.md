---
title: 직무 분리 설정
description: 다른 사용자가 수행해야 하는 작업을 구분하는 규칙을 설정할 수 있습니다.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c06ce9325d7b0894ba53d6b9782f495a48280d45e538b048d883ab86f05dabf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460985"
---
# <a name="set-up-segregation-of-duties"></a>직무 분리 설정

[!include [banner](../../includes/banner.md)]

다른 사용자가 수행해야 하는 작업을 구분하는 규칙을 설정할 수 있습니다. 이 개념을 직무 분리라고 합니다. 예를 들어, 동일한 사람이 상품 수령을 확인하고 공급업체에 대한 지불을 처리하는 것을 원하지 않을 수 있습니다. 업무 분리는 사기 위험을 줄이는 데 도움이 되며 오류나 부정 행위를 감지하는 데도 도움이 됩니다. 업무 분리를 사용하여 내부 통제 정책을 시행할 수도 있습니다. 규칙을 생성하려면 다음 절차를 완료하세요. 절차를 완료하려면 시스템 관리자여야 합니다.

1. **시스템 관리** > **보안** > **직무 분리** > **직무 분리 규칙** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **이름** 필드에 규칙의 값을 입력합니다.
4. **첫 의무** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
5. 목록에서 원하는 기록을 찾아 선택합니다. 규칙에 의해 제어되는 첫 번째 의무를 선택합니다.
6. **두 번째 의무** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다. 
7. 목록에서 원하는 기록을 찾아 선택합니다. 규칙에 의해 제어되는 두 번째 의무를 선택합니다.
10. **심각도** 필드에서 옵션을 선택합니다. 동일한 사용자 또는 역할이 두 가지 작업을 모두 수행할 때 발생하는 위험의 심각도를 선택합니다.  
11. **보안 위험** 필드에 값을 입력합니다. 보안 위험의 설명을 입력합니다.  
12. **보안 완화** 필드에 값을 입력합니다. 보안 위험을 완화하기 위해 취하는 조치에 대한 설명을 입력합니다. 예를 들어, 프로세스에 대한 보다 자세한 검토를 수행하거나, 월별 관리 검토를 수행하거나, 다른 부서와 리소스를 공유하여 위험을 완화할 수 있습니다.     
13. **저장** 을 클릭합니다.

> [!IMPORTANT] 
> 규칙을 생성할 때 직무 분리 규칙 준수 여부는 확인되지 않습니다. 기존 역할에 대한 충돌을 생성하는 규칙을 생성할 수 있습니다. 기존 사용자 역할 할당이 새 규칙과 충돌할 수도 있습니다. 규칙을 생성하거나 수정한 후에는 규정 준수를 검증해야 합니다. 자세한 내용은 [직무 분담의 갈등 파악 및 해결](identify-resolve-conflicts-segregation-duties.md)을 참조하세요


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]