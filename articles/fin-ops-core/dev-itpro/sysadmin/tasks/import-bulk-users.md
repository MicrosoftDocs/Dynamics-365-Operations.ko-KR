---
title: Azure Active Directory에서 사용자 가져오기
description: 이 절차는 시스템 관리자가 선택한 사용자를 수동으로 가져오거나 Azure Active Directory에서 많은 사용자를 가져오는 데 사용할 수 있습니다.
author: peakerbl
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce8c98add0c6d5fb07b3ba5338037d9a12b1d8e50a2d2039b0231d3d305c9ebe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460987"
---
# <a name="import-users-from-azure-active-directory"></a>Azure Active Directory에서 사용자 가져오기

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>선택한 사용자 가져오기

이 절차는 시스템 관리자가 Azure Active Directory(Azure AD)에서 선택한 사용자를 가져오는 데 사용할 수 있습니다.

1. 현재 세션 회사를 기본 회사로 사용하여 사용자를 가져옵니다. 사용자를 가져오기 전에 해당하는 경우 현재 회사를 변경합니다.
2. **시스템 관리 > 사용자 > 사용자** 로 이동합니다.
3. **사용자 가져오기** 를 클릭합니다.
4. 가져와야 하는 사용자를 선택하고 **사용자 가져오기** 를 선택합니다.

가져오기가 완료되면 사용자에게 역할을 할당해야 합니다.

## <a name="import-users-in-bulk"></a>대량으로 사용자 가져오기

이 절차는 시스템 관리자가 Azure Active Directory에서 대량의 사용자를 가져오는 데 사용할 수 있습니다.
일괄 가져오기 옵션을 사용하는 경우 사용자를 선택할 수 없습니다.

## <a name="run-the-import-as-a-batch-job"></a>가져오기를 일괄 작업으로 실행
1. 현재 세션 회사를 기본 회사로 사용하여 사용자를 가져옵니다. 사용자를 가져오기 전에 해당하는 경우 현재 회사를 변경합니다.
2. **시스템 관리 > 사용자 > 사용자** 로 이동합니다.
3. **일괄 가져오기** 를 클릭합니다.
4. **백그라운드에서 실행** 섹션을 확장합니다.
4. **일괄 처리** 필드에서 **예** 를 선택합니다.
6. **일괄 그룹** 필드에 값을 입력하거나 선택합니다. 이는 선택적 단계입니다.  
7. **비공개** 필드에서 **예** 를 선택합니다. 이는 선택적 단계입니다.  
8. **위험 작업** 필드에서 **예** 를 선택합니다. 이는 선택적 단계입니다.  
9. **모니터링 범주** 필드에서 옵션을 선택합니다.
10. **확인** 을 클릭합니다.

가져오기가 완료되면 사용자에게 역할을 할당해야 합니다.

## <a name="run-in-a-sandbox-environment"></a>샌드박스 환경에서 실행
1. **일괄 가져오기** 를 선택합니다.
2. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]