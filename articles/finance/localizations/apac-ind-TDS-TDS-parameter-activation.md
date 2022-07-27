---
title: TDS 매개 변수 설정
description: 이 토픽에서는 지정된 트랜잭션에서 원천공제세(TDS) 기능을 활성화하기 위해 매개 변수를 설정하는 방법에 대해 설명합니다. 원천공제세 TDS 기능을 사용하기 위해 필요한 단계입니다.
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
ms.openlocfilehash: ca98a74753ca0de3b376cb89ef47862bc1bfb30e
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451777"
---
# <a name="set-the-tds-parameters"></a>TDS 매개 변수 설정

[!include [banner](../includes/banner.md)]

이 토픽에서는 지정된 트랜잭션에서 원천공제세(TDS) 기능을 활성화하기 위해 매개 변수를 설정하는 방법에 대해 설명합니다. 원천공제세 TDS 기능을 사용하기 위해 필요한 단계입니다.

1. **총계정원장 \> 원장 설정 \> 총계정원장 매개 변수** 으로 이동합니다.
2. **직접세** 탭의 **원천공제세** 섹션에서 **TDS 활성화** 옵션을 **예** 로 설정하여 TDS 기능과 이 기능에 사용되는 페이지와 필드를 활성화합니다.
3. **송장** 옵션을 **예** 로 설정하여 송장 수준에서 TDS를 계산하고 공제하는 데 사용되는 필드를 활성화합니다.
4. **지불** 옵션을 **예** 로 설정하여 지불 수준에서 TDS를 계산하고 공제하는 데 사용되는 필드를 활성화합니다.

    [![직접세 탭.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. **번호 시퀀스** 탭에서 **참조** 필드가 **원천징수세 납부** 로 설정된 행을 찾습니다. 행의 **번호 시퀀스 코드** 필드에서 번호 시퀀스 코드를 선택합니다. 번호 시퀀스 코드는 정기 TDS 정산 프로세스에 대한 바우처 번호를 생성하는 데 사용됩니다.

    > [!NOTE]
    > 정기 TDS 정산 프로세스를 실행하려면 **세금 \> 신고 \> 원천징수세 \> 원천징수세 납부** 로 이동하십시오.

    [![번호 시퀀스 탭.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. 페이지를 닫습니다.
