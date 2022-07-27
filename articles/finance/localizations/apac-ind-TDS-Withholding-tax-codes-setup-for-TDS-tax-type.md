---
title: TDS 세금 유형에 대한 원천징수세 코드 설정
description: 이 토픽에서는 원천공제세(TDS)에 대한 세금 코드를 설정하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 03d8b7d4992fbb49a873f14e1ce1f0c816cef202
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451771"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>TDS 세금 유형에 대한 원천징수세 코드 설정

[!include [banner](../includes/banner.md)]

이 토픽에서는 원천공제세(TDS)에 대한 세금 코드를 설정하는 방법에 대해 설명합니다.

1. **세금 \> 간접세 \> 원천징수세 \> 원천징수세 코드** 로 이동합니다.

    [![원천징수세 코드 페이지.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. 작업 창에서 **새로 만들기** 를 선택하여 TDS에 대한 원천징수세 코드를 만들고 필요한 세부 정보를 입력합니다.
3. **일반** 빠른 탭의 **세금 유형** 필드에서 **TDS** 를 선택하여 세금 코드를 TDS 세금 코드로 분류합니다.
4. **정산 기간** 필드에서 TDS 세금 코드에 대한 TDS 정산 기간을 선택합니다.
5. **주 계정** 필드에서 TDS 금액을 전기해야 하는 원장 계정을 선택합니다.
6. **미수금 계정** 필드에서 판매 트랜잭션에서 공제되는 TDS 금액이 전기되어야 하는 미수금 계정을 선택합니다.

    **오리진** 필드는 **총액의 비율** 로 자동 설정되며 값은 변경할 수 없습니다.

    > [!NOTE]
    > TDS 세금 유형의 세금 코드에 대해 오리진을 **순액 비율** 로 설정할 수 없습니다.

7. **원천징수세 구성요소** 필드에서 TDS 세금 코드에 대한 TDS 세금 구성요소를 선택합니다.
8. 작업 창에서 **값** 을 선택하여 **원천징수세 값** 페이지를 엽니다.
9. **시작 날짜** 필드에 TDS 값의 시작 날짜를 입력합니다. **종료 날짜** 필드에 종료 날짜를 입력합니다.

    > [!NOTE]
    > **최소 한도**, **상한** 및 **제외 %** 필드는 TDS 세금 유형의 세금 코드에 사용할 수 없습니다.

10. **값** 필드에 TDS 세금 코드에 대한 TDS 비율을 입력합니다.
11. **원천징수세 값** 페이지를 닫고 **원천징수세 코드** 페이지로 돌아갑니다.

    > [!NOTE]
    > **원천징수세 코드** 페이지의 **한도** 버튼은 TDS 세금 유형의 세금 코드에 사용할 수 없습니다.

12. 페이지를 닫습니다.
