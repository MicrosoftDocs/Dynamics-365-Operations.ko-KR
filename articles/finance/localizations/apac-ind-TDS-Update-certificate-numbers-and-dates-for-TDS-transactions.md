---
title: TDS 트랜잭션에 대한 인증서 번호 및 날짜 업데이트
description: 이 토픽에서는 원천공제세(TDS)에 대해 공급업체, 고객 및 원장 계정에 대해 기록된 회수 가능한 인증서 번호 및 날짜를 업데이트하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: b23f01f110009ba2f0cfe71c7bb995a4dc21ca3b
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451837"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>TDS 트랜잭션에 대한 인증서 번호 및 날짜 업데이트

[!include [banner](../includes/banner.md)]

이 토픽에서는 원천공제세(TDS)에 대해 공급업체, 고객 및 원장 계정에 대해 기록된 회수 가능한 인증서 번호 및 날짜를 업데이트하는 방법에 대해 설명합니다. **회수 가능한 인증서** 페이지에서 TDS 트랜잭션에 대한 인증서를 볼 수 있습니다. **인증서 업데이트** 페이지를 사용하여 인증서를 업데이트할 수 있습니다.

TDS 트랜잭션에 대한 인증서 번호와 날짜를 업데이트하려면 다음 단계를 따르십시오.

1. **세금 \> 신고 \> 원천징수세 \> 인증서 업데이트** 로 이동합니다.

    [![인증서 업데이트 페이지.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. **인증서 업데이트** 페이지의 **선택** 섹션, **세금 유형** 필드에서 **TDS** 를 선택합니다.
3. **인증서 번호** 필드에서 고객 또는 공급업체의 TDS 인증서 번호를 선택합니다.

    > [!NOTE]
    > **인증서 번호** 필드에는 **회수 가능한 인증서** 페이지에서 **닫힘** 확인란이 선택 취소된 TDS 인증서 번호만 나열됩니다.

    **인증서 날짜** 필드는 인증서 날짜를 보여줍니다. **계정 유형** 필드는 TDS 인증서 번호를 받은 계정 유형을 표시하고 **이름** 필드는 계정 이름을 보여줍니다.

5. **시작 날짜** 및 **종료 날짜** 필드에서 TDS 트랜잭션을 표시할 기간의 시작 날짜와 종료 날짜를 선택합니다.
6. **데이터 표시** 를 선택하여 선택한 기간 동안 전기된 TDS 트랜잭션을 봅니다.

    **개요** 탭의 위쪽 창의 그리드에는 선택한 기간 동안 공급업체 또는 고객에 대해 전기된 각 TDS 트랜잭션에 대한 다음 정보가 표시됩니다.

    - **바우처** TDS 트랜잭션의 바우처 번호.
    - **날짜** – TDS 트랜잭션 날짜.
    - **금액** – TDS가 계산된 송장 금액입니다.
    - **세액** – 트랜잭션에 대해 계산된 TDS 세액입니다.

7. 특정 TDS 트랜잭션을 상단 그리드에서 하단 그리드로 이동하려면 트랜잭션을 선택한 후 **포함** 을 선택합니다. 또는 **모두 포함** 을 선택하여 모든 TDS 트랜잭션을 상단 그리드에서 하단 그리드로 이동합니다.

    특정 TDS 트랜잭션 또는 모든 TDS 트랜잭션을 하단 그리드에서 상단 그리드로 이동하려면 **제외** 또는 **모두 제외** 버튼을 사용합니다.

8. **업데이트** 를 선택하여 하단 그리드의 TDS 트랜잭션에 대한 **인증서 번호** 및 **인증서 날짜** 필드를 업데이트합니다.
10. **세금 \> 간접세 \> 원천징수세 \> 회수 가능한 인증서** 로 이동하고 **인증서 트랜잭션** 페이지에서 새 인증서 번호가 있는 업데이트된 트랜잭션 라인을 보려면 **조회** 를 선택하십시오.

    [![인증서 트랜잭션 페이지.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
