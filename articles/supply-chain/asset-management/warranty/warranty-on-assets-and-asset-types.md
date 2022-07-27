---
title: 자산 및 자산 유형에 대한 보증
description: 이 토픽에서는 자산 관리에서 자산 및 자산 유형에 대한 보증을 설정하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/30/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bcfbd56f5fa1491f13ea65c5fb3d70659c3b945276813d7c1c922c849bf8e3a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446995"
---
# <a name="warranties-on-assets-and-asset-types"></a>자산 및 자산 유형에 대한 보증

[!include [banner](../../includes/banner.md)]

 


이 토픽에서는 자산 관리에서 자산 및 자산 유형에 대한 보증을 설정하는 방법에 대해 설명합니다.

## <a name="set-up-a-warranty-on-an-asset-type"></a>자산 유형에 대한 보증 설정

1. **자산 관리** \> **설정** \>> **자산 유형** \> **자산 유형** 을 선택합니다.
2. 왼쪽 창에서 공급업체 보증 계약을 첨부할 자산 유형을 선택한 다음 **자산 유형 기본값** 을 선택합니다.
3. **일반** 빠른 탭의 **공급업체 보증** 필드에서 계약을 선택합니다.

## <a name="set-up-a-warranty-on-an-asset"></a>자산 유형에 대한 보증 설정

1. **자산 관리** \> **공통** \> **자산** \> **모든 자산** 을 선택합니다.
2. 자산을 선택한 다음 **편집** 을 선택합니다.
3. **공급업체** 빠른 탭의 **공급업체 보증** 섹션에 있는 **보증** 필드에서 보증 계약을 선택합니다.
4. **보증 시작** 및 **보증 종료** 필드에 시작 및 종료 날짜를 선택합니다.

    > [!IMPORTANT]
    > 작업 주문의 **보증 시작** 필드에서 날짜를 선택하면 해당 날짜의 작업 주문에 대해 보증이 유효하게 됩니다. 작업 주문을 생성하면 **보증 시작** 필드가 생성 날짜로 자동 설정됩니다. 그러나 예를 들어 보증 계약의 시작 날짜와 일치하도록 날짜를 변경할 수 있습니다.
    >
    > ![작업 주문 페이지.](media/02-warranty.png)

> [!NOTE]
> 공급업체 보증이 적용되는 자산에 대한 작업 주문을 생성할 때 작업 주문에 보증 기간 동안 예상 시작 날짜가 있는 경우 보증 계약에 대한 알림을 받습니다. 그런 다음 필요에 따라 작업 주문을 취소할 수 있습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]