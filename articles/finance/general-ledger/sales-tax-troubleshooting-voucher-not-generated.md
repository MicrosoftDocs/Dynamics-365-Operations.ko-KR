---
title: 전표가 생성되지 않음
description: 이 항목에서는 전표가 생성되야 하지만 그렇지 않을 때 도움이 될 수 있는 문제 해결 정보를 제공합니다.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1fbd5b5bb4a1d2a0c498b2abac82bd6f5ff3f1d2ed9960885eb8f44cbb17884d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450628"
---
# <a name="voucher-isnt-generated"></a>전표가 생성되지 않음

[!include [banner](../includes/banner.md)]

전표가 생성되어야 하지만 **전표 거래** 페이지에 전표가 표시되지 않는 경우 다음 섹션의 단계에 따라 이 문제를 해결하세요.

[![전표가 표시되지 않는 전표 거래 페이지.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>세금 적용 여부 확인

1. **세금** \> **정기 작업** \> **보조 원장 분개장이 아직 이전되지 않음** 으로 이동합니다.
2. 분개장 기록이 있으면 선택한 다음 **지금 이동** 을 선택합니다.

    [![보조 원장 분개장이 아직 이전되지 않음 페이지의 지금 이동 버튼.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. **전표 거래** 페이지를 다시 열어 전표가 생성되었는지 확인합니다.

## <a name="determine-whether-customization-exists"></a>사용자 지정이 있는지 확인

이전 섹션의 단계를 완료했지만 문제가 발견되지 않는 경우 사용자 지정이 있는지 확인하세요. 사용자 지정이 없으면 Microsoft 서비스 요청을 작성하여 추가 지원을 받으세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
