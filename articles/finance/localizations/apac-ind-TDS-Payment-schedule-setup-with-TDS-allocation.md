---
title: TDS 할당으로 지불 일정 설정
description: 이 토픽에서는 원천 공제 세금(TDS) 할당으로 지급 일정을 설정하는 방법에 대해 설명합니다.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 31ecf2e6fa4d3d37c3d5332dc1d5592bf1a99bad
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451819"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>TDS 할당으로 지불 일정 설정

[!include [banner](../includes/banner.md)]

이 토픽에서는 원천 공제 세금(TDS) 할당으로 지급 일정을 설정하는 방법에 대해 설명합니다.

1. **지급 계정 \> 지불 설정 \> 지불 일정** 으로 이동합니다.

    [![지불 일정 페이지.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. 작업 창에서 **새로 만들기** 를 선택하여 지불 일정을 만들고 필요한 세부 정보를 입력합니다.
3. **할당** 필드에서 지급 일정에 대한 지급을 할당하는 데 사용할 방법을 선택합니다.

    - 합계
    - 고정 금액
    - 고정 수량
    - 지정됨

    **원천징수세 할당** 필드에는 지급 일정에 대한 TDS 할당 방법이 표시됩니다. **할당** 필드에서 **합계** 를 선택하면 **원천징수세 할당** 필드가 자동으로 **합계** 로 설정됩니다. **할당** 필드에서 **고정 금액**, **고정 수량** 또는 **지정** 을 선택하면 **원천징수세 할당** 필드가 자동으로 **비례** 로 설정됩니다.

    > [!NOTE]
    > **원천징수세 할당** 필드가 **합계** 로 설정된 경우 분할 지불은 TDS 금액을 포함하는 총액을 기준으로 계산됩니다. **원천징수세 할당** 필드가 **비례** 로 설정된 경우 분할 지불은 TDS 금액을 차감한 후 순 송장 금액을 기준으로 계산됩니다.

4. 기타 필수 세부 정보를 입력한 다음 페이지를 닫습니다.
