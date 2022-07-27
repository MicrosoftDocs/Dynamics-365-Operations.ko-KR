---
title: TaxTrans 레코드가 생성되지 않음
description: 이 항목에서는 TaxTrans 레코드가 생성되지 않을 때 도움이 될 수 있는 문제 해결 정보를 제공합니다.
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
ms.openlocfilehash: 82b00387e39b88e1ab2bc27d9dbc4e36aac3a7a605c04669171997ba236ae39a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450541"
---
# <a name="taxtrans-record-isnt-generated"></a>TaxTrans 레코드가 생성되지 않음

[!include [banner](../includes/banner.md)]

거래에 대해 **게시된 판매세** 를 선택했지만 **게시된 판매세** 페이지에 세금 라인이 표시되지 않거나 세금 라인이 누락된 경우 **TaxTrans** 레코드가 생성되지 않았을 수 있습니다.

[![라인 항목이 없이 게시된 판매세 페이지.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

이 문제를 해결하려면 필요에 따라 다음 섹션의 단계를 따르세요.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>거래를 게시하기 전에 판매세 확인

1. 거래를 게시하기 전에 **송장 게시** 페이지에서 **판매세** 를 선택하여 계산을 확인합니다.

    [![송장 게시 페이지의 판매세 버튼.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. **임시 판매세 거래** 페이지에서 계산 결과를 검토합니다. 세금이 계산되지 않으면 [세금이 계산되지 않거나 세액이 0임](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md)을 참조하세요.

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>모든 게시된 판매세에서 TaxTrans 레코드 찾기

1. **세금** \> **문의 및 신고** \> **판매세 조회** > **게시된 판매세** 로 이동합니다.
2. **전표** 열 머리글에서 필터 기호를 선택하여 **TaxTrans** 레코드를 찾습니다.
3. 찾고 있는 판매세 기록을 찾으면 날짜를 확인합니다. 날짜가 분기장 헤더의 날짜와 다른 경우 추가 지원을 위해 Microsoft 서비스 요청을 작성하세요.

    [![게시된 판매세 페이지.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>디버그로 세부 사항 확인

1. 디버그 및 **TmpTaxWorkTrans** 및 **TaxUncommitted** 가 올바르게 생성되었는지 확인하는 방법에 대한 자세한 내용은 [TaxTrans의 잘못된 필드 값 찾기](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md)를 참조하세요.
2. **TaxTmpWorkTrans** 또는 **TaxUncommitted** 가 올바르게 생성되면 **TaxPost::SaveAndPost()** 및 **Tax::SaveAndPost** 에 중단점을 추가하여 **TaxTrans** 가 삽입되지 않은 이유를 디버그하세요.

    [![코드에 추가된 중단점.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![중단점 추가 결과.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>사용자 지정이 있는지 확인

이전 섹션의 단계를 완료했지만 문제가 발견되지 않는 경우 사용자 지정이 있는지 확인하세요. 사용자 지정이 없으면 Microsoft 서비스 요청을 작성하여 추가 지원을 받으세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
