---
title: 작업 기록을 위한 보안 진단
description: 이 항목에서는 작업 기록을 기반으로 보안 권한 요구 사항을 분석하고 관리하는 방법에 대한 정보를 제공합니다.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 44af35f16f6e9ff89b30bc10eef3f16ecdfaf907c4c6e22aa5775d1941fb6a5d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460986"
---
# <a name="security-diagnostics-for-task-recordings"></a>작업 기록을 위한 보안 진단

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>시작하기 전에

이 항목에서는 작업 기록을 기반으로 보안 권한 요구 사항을 분석하고 관리하는 방법에 대한 정보를 제공합니다. 이 항목의 단계를 완료하기 전에 분석할 비즈니스 프로세스의 작업 기록이 있어야 합니다. 비즈니스 프로세스를 기록하려면 [작업 레코더 리소스](../../user-interface/task-recorder.md)를 참조하세요. 

## <a name="manage-security-for-a-task-recording"></a>작업 기록에 대한 보안 관리

1. **시스템 관리** > **보안** > **작업 기록을 위한 보안 진단** 으로 이동합니다.
2. 해당 위치에서 작업 기록을 엽니다. **이 PC에서 열기** 또는 **Lifecycle Services에서 열기** 를 선택한 다음 **닫기** 를 선택합니다.
3. 이렇게 하면 **보안 메뉴 항목 세부 정보** 페이지가 열리고 프로세스에 필요한 보안 개체가 나열됩니다.

 > [!NOTE]
 > **동작** 및 **산출** 메뉴 항목은 목록에 포함되지 않습니다.

4. **사용자 ID** 필드에서 사용자를 선택합니다. 사용자에게 일부 메뉴 항목에 대한 권한이 없으면 **권한 누락** 필드가 **예** 로 업데이트됩니다.
  
  ![보안 메뉴 항목 세부 정보 페이지.](../media/Security-Menu-Item-Details.png)

5. **참조 추가** 를 선택하여 누락된 권한을 부여하는 역할, 의무 및 권한을 포함하여 보안 개체 목록을 확인합니다.
6. 목록에서 보안 개체를 선택합니다.

    - **역할** 이 선택디어 있으면 **사용자에게 역할 추가** 를 선택합니다. 이렇게 하면 **역할에 사용자 할당** 페이지가 열립니다. 자세한 내용은 [보안 역할에 사용자 할당](assign-users-security-roles.md) 페이지를 참조하세요.
    - **의무** 가 선택되어 있으면 **역할에 의무 추가** 를 선택하고 임무를 추가해야 하는 역할을 선택한 다음 **확인** 을 선택합니다.
    - **권한** 이 선택되어 있으면 **의무에 권한 추가** 를 선택하고 임무를 추가해야 하는 역할을 선택한 다음 **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]