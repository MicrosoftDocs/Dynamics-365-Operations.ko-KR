---
title: 유지 관리 요청 유형
description: 이 토픽에서는 자산 관리에서 유지 관리 요청 유형을 설정하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f51c90f72120d236ae9acf3fbcb8ac98fdc8cdf3d3bd032b3a3a3d317483b070
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446698"
---
# <a name="maintenance-request-types"></a>유지 관리 요청 유형

[!include [banner](../../includes/banner.md)]

 

유지 관리 요청 유형은 유지 관리 요청을 분류하는 데 사용됩니다. 예를 들어 예방 유지 관리 및 수정 유지 관리와 관련된 유지 관리 요청 유형이 있을 수 있습니다. 또는 자산 수리를 관리하는 데 사용되는 특별한 유지 관리 요청 유형이 있을 수 있습니다(수리 창고).

유지 관리 요청 유형은 유지 관리 요청 수명 주기 상태 그룹(유지 관리 수명 주기 모델)과의 제휴를 정의합니다. 유지 관리 요청 수명 주기 모델은 유지 관리 요청에 대해 설정할 수 있는 수명 주기 상태를 정의합니다. (유지 관리 요청 수명 주기 상태의 예로는 **생성됨**, **활성** 및 **종료됨** 이 있습니다.)

1. **자산 관리** \> **설정** \> **유지 관리 요청** \> **유지 관리 요청 유형** 을 선택합니다.
2. **새로 만들기** 를 선택하여 유지 관리 요청 유형을 만듭니다.
3. **유지 관리 요청 유형** 필드에 유지 관리 요청 유형의 ID를 입력합니다.
4. **이름** 필드에 이름을 입력합니다.
5. **일반** 빠른 탭의 **유지 관리 요청 수명 주기 모델** 필드에서 유지 관리 요청 수명 주기 모델을 선택합니다.
6. **작업 주문 유형** 필드에서 작업 주문 유형을 선택합니다. 유지 관리 요청이 작업 주문으로 변환되면 작업 주문은 유지 관리 요청 유형과 관련된 작업 주문 유형을 자동으로 가져옵니다.

다음 그림은 **유지 관리 요청 유형** 페이지의 예를 보여줍니다.

![유지 관리 요청 유형 페이지.](media/07-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]