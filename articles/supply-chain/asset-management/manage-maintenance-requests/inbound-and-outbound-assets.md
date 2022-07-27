---
title: 인바운드 및 아웃바운드 자산
description: 이 토픽에서는 자산 관리에서 인바운드 및 아웃바운드 자산을 등록하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0bd3127df1b583acc6841c3e115d3beceabcab2756098e567b2269c1dcc94004
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447109"
---
# <a name="inbound-and-outbound-assets"></a>인바운드 및 아웃바운드 자산

[!include [banner](../../includes/banner.md)]

 

회사가 다른 위치나 고객으로부터 받은 자산에 대해 수리 작업이나 유지 관리 작업을 수행하는 경우 자산 관리는 회사로 이동 중인 인바운드 자산과 반환되는 아웃바운드 자산을 모두 추적할 수 있습니다.

> [!NOTE]
> 인바운드 및 아웃바운드 수명 주기 상태를 사용하여 들어오고 반환되는 자산을 관리하려면 이러한 작업을 지원하도록 유지 관리 요청 수명 주기 상태와 수명 주기 모델을 설정해야 합니다. 자세한 내용은 [유지 관리 요청](../setup-for-maintenance-requests/requests.md)을 참조하세요.

자산 관리 설정은 인바운드 및 아웃바운드 자산으로 작업할 수 있는지 여부를 결정합니다.

## <a name="register-assets-as-inbound"></a>인바운드로 자산 등록

1. **자산 관리** \> **공통** \> **유지 관리 요청** \> **활성 유지 관리 요청** 을 선택합니다.
2. 유지 관리 요청을 선택합니다.
3. **유지 관리 요청 상태 업데이트** 를 선택합니다.
4. **인바운드**(또는 인바운드 자산에 대해 생성한 다른 수명 주기 상태)를 선택한 다음 **확인** 을 선택합니다.

![인바운드로 자산을 등록합니다.](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>수신된 인바운드 자산 등록

1. **자산 관리** \> **공통** \> **인바운드/아웃바운드** \> **인바운드 자산** 을 선택합니다.
2. 자산 또는 유지 관리 요청을 선택합니다.
3. **자산 수령** 을 선택합니다.
4. **수령됨** 필드에 날짜와 시간을 입력합니다. 그런 다음 **확인** 을 선택합니다. 레코드가 **인바운드 자산** 목록 페이지에서 제거됩니다.

![수신된 인바운드 자산을 등록합니다.](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>아웃바운드로 자산 등록

유지 보수 또는 수리 작업을 완료하면 자산을 반환된 것으로 등록할 수 있습니다.

1. **자산 관리** \> **공통** \> **유지 관리 요청** \> **활성 유지 관리 요청** 을 선택합니다.
2. 유지 관리 요청을 선택합니다.
3. **유지 관리 요청 상태 업데이트** 를 선택합니다.
4. **아웃바운드**(또는 아웃바운드 자산에 대해 생성한 다른 수명 주기 상태)를 선택한 다음 **확인** 을 선택합니다.

## <a name="register-outbound-assets-as-delivered"></a>배송됨으로 아웃바운드 자산 등록

1. **자산 관리** \> **공통** \> **인바운드/아웃바운드** \> **아웃바운드 자산** 을 선택합니다.
2. 자산 또는 유지 관리 요청을 선택합니다.
3. **자산 배달** 을 선택합니다.
4. **배달됨** 필드에 날짜와 시간을 입력합니다. 그런 다음 **확인** 을 선택합니다. 레코드가 **아웃바운드 자산** 목록 페이지에서 제거됩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]