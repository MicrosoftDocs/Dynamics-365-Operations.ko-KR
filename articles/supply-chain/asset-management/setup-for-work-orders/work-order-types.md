---
title: 작업 주문 유형
description: 이 토픽에서는 자산 관리의 작업 주문 유형에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d77effbfe329a449318d6942918245917f22cdc23defadcb5e85f02c6c786f6d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447055"
---
# <a name="work-order-types"></a>작업 주문 유형

[!include [banner](../../includes/banner.md)]

 

작업 주문 유형은 작업 주문을 분류하는 데 사용됩니다. 예를 들어 예방 유지 관리 또는 수정 유지 관리와 관련된 작업 주문이 있을 수 있습니다.

작업 주문 유형은 작업 주문 수명 주기 모델과의 제휴를 정의합니다. 작업 주문 수명 주기 모델은 작업 주문에 설정할 수 있는 작업 주문 수명 주기 상태를 정의합니다. (작업 주문 수명 주기 상태의 예로는 **생성됨**, **처리 중** 및 **완료됨** 이 있습니다.)

작업 주문 수명 주기 상태 및 프로젝트 단계에 대한 자세한 내용은 [작업 주문 수명 주기 상태](work-order-lifecycle-states.md)를 참조하세요.

1. **자산 관리** \> **설정** \> **작업 주문** \> **작업 주문 유형** 을 선택합니다.
2. **새로 만들기** 를 선택하여 작업 주문 유형을 만듭니다.
3. **작업 주문 유형** 필드에 작업 주문 유형의 ID를 입력합니다.
4. **이름** 필드에 이름을 입력합니다.
5. **작업 주문 수명 주기 모델** 필드에서 수명 주기 모델을 선택합니다.
5. 이 유형의 작업 주문과 관련된 모든 작업 주문 작업을 동일한 유지 관리 작업자에게 예약해야 하는 경우 **한 유지 관리 작업자** 옵션을 **예** 로 설정합니다.
6. **비용 유형** 필드에서 **수정**, **예방** 또는 **투자** 를 적절하게 선택합니다. 작업 주문의 모든 작업 주문 작업은 비용 유형이 동일해야 합니다.
7. **필수** 섹션에서 관련 옵션을 **예** 로 설정하여 이 유형의 작업 주문에 추가할 오류 관련 정보 또는 유지 관리 가동 중지 시간관련 정보를 지정합니다.

    > [!NOTE]
    > **필수** 섹션의 옵션은 **작업 주문 수명 주기 상태** 페이지(**자산 관리** \> **설정** \> **작업 주문** \> **수명 주기 상태**)의 **유효성 확인** 빠른 탭에 있는 옵션과 관련이 있습니다.

8. **저장** 을 선택합니다.

![작업 주문 유형.](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]