---
title: 지급 계정 및 수취 계정에서 TDS 매개 변수 설정
description: 이 토픽에서는 원천공제세(TDS) 공제를 지원하기 위해 지급 계정 및 수취 계정에서 매개 변수를 설정하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 6d5258d3f2f9dd32f73ba7dec9c57ab896461f7e
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451840"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>지급 계정 및 수취 계정에서 TDS 매개 변수 설정

[!include [banner](../includes/banner.md)]

이 토픽에서는 원천공제세(TDS) 공제를 지원하기 위해 지급 계정 및 수취 계정에서 매개 변수를 설정하는 방법에 대해 설명합니다.

1. **세금 \> 설정 \> 매개 변수 \> 수취 계정 매개 변수** 로 이동합니다.
2. **업데이트** 탭에서 **주문 라인 업데이트** 를 선택하여 **주문 라인 업데이트** 대화 상자를 엽니다.
3. **TDS 그룹** 섹션의 **TDS 그룹 업데이트** 필드, 라인 수준에서 TDS 그룹을 업데이트하는 데 사용할 방법을 지정합니다. 이 설정은 주문 헤더에서 TDS 그룹이 업데이트될 때 사용됩니다. 다음 옵션을 사용할 수 있습니다.

    - **없음** – TDS 그룹은 주문 헤더에서 업데이트될 때 주문 라인에서 업데이트되지 않습니다.
    - **항상** – TDS 그룹은 주문 헤더에서 업데이트될 때 주문 라인에서 자동으로 업데이트됩니다.
    - **메시지 표시** – 사용자는 주문 라인에서 TDS 그룹을 업데이트하라는 메시지를 받습니다.
4. **확인** 을 선택합니다.

    [![주문 라인 업데이트 대화 상자.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. **세금 \> 설정 \> 매개 변수 \> 지급 계정 매개 변수** 로 이동합니다.
6. **일반** 탭의 **배송 정보에 따라 분할** 빠른 탭에서 **제품 영수증** 옵션을 **예** 로 설정하여 배송 주소와 세금 계정 번호(TAN)가 다른 제품 영수증을 게시하고 분할합니다. 이 옵션이 **아니요** 로 설정된 경우 배송 주소 및 TAN이 다른 구매 포장 전표를 전기할 수 없습니다.
7. 배송 주소와 TAN이 다른 구매 송장을 전기하고 분할하려면 **송장** 옵션을 **예** 로 설정합니다.

    [![배송 정보에 따라 분할 빠른 탭.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. 페이지를 닫습니다.
