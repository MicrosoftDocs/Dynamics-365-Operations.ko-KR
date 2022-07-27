---
title: 세금이 전표의 잘못된 원장 계정에 게시됨
description: 이 항목은 세금이 전표의 잘못된 원장 계정에 게시될 때 도움이 될 수 있는 문제 해결 정보를 제공합니다.
author: qire
ms.date: 04/12/2021
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
ms.openlocfilehash: 3d60265df7ff1f447e20866b8b8a447d88db8cc4b3dccedebc0f18ce8f0f70dc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450490"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>세금이 전표의 잘못된 원장 계정에 게시됨

[!include [banner](../includes/banner.md)]

세금이 전표의 잘못된 원장 계정으로 게시될 수 있습니다. 이 문제를 해결하려면 필요에 따라 다음 섹션의 단계를 따르세요. 이 항목의 예에서는 판매 주문을 비즈니스 문서로 사용합니다.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>잘못 게시된 세금 거래의 세금 코드 찾기

1. **전표 거래** 페이지에서 작업할 거래를 선택한 다음 **게시된 판매세** 를 선택합니다.

    [![전표 거래 페이지의 게시된 판매세 버튼.](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. **판매세 코드** 필드의 값을 검토합니다. 이 예에서는 **VAT 19** 입니다.

    [![게시된 판매세 페이지의 판매세 코드 필드.](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>세금 코드의 원장 게시 그룹 확인

1. **세금** \> **간접세** \> **판매세** \> **판매세 코드** 로 이동합니다.
2. 세금 코드를 찾아 선택한 다음 **원장 게시 그룹** 필드의 값을 검토합니다. 이 예에서는 **VAT** 입니다.

    [![판매세 코드 페이지의 원장 게시 그룹 필드.](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. **원장 게시 그룹** 필드의 값은 링크입니다. 그룹 구성의 세부 정보를 보려면 링크를 선택합니다. 또는 필드를 길게 선택하고(또는 오른쪽 버튼으로 클릭) **세부 정보 보기** 를 선택합니다.

    [![세부 정보 보기 명령.](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. **판매세 납부** 필드에서 거래 유형에 따라 계좌 번호가 올바른지 확인합니다. 올바르지 않은 경우 게시할 올바른 계정을 선택합니다. 이 예에서 판매 주문의 판매세는 판매세 납부 계정 222200에 게시되어야 합니다.

    [![원장 게시 그룹 페이지의 판매세 납부 필드.](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    다음 표는 **원장 게시 그룹** 페이지의 각 필드에 대한 정보를 제공합니다.

    | 필드                  | 설명 |
    |------------------------|-------------|
    | 판매세 납부      | 세무 당국에 납부해야 하는 판매세의 주 계정입니다. |
    | 판매세 수취   | 세무 당국에서 받는 들어오는 세금에 대한 주 계정입니다. |
    | 사용세 경비        | 공급업체가 유럽 연합(EU) 물품 용역세(GST)/조화 판매세(HST) 수신인 부담의 일부로 세무 당국에 청구하거나 보고하지 않는 공제 가능한 사용세를 게시하는 데 사용되는 주 계정입니다. **사용세** 는 거래에 사용된 판매세 그룹의 판매세 코드에 대해 선택해야 합니다. **총계정원장 매개 변수** 페이지에서 **판매세 과세 규칙 적용** 이 선택된 경우 이 필드를 사용할 수 없습니다. |
    | 사용세 납부        | 세무 당국에 납부해야 하는 수신 사용세를 게시하는 데 사용되는 주 계정입니다. |
    | 정산 계정     | **사용세 납부** 및 **판매세 수취** 필드에 지정된 원장 계정의 순 잔액을 게시하는 데 사용되는 주 계정입니다. |
    | 공급업체 현금 할인   | 이 원장 전기 그룹과 연관된 판매세 코드에 대한 현금 할인을 게시하는 데 사용되는 주 계정입니다. |
    | 고객 케이스 할인 | 이 원장 전기 그룹과 연관된 판매세 코드에 대한 현금 할인을 게시하는 데 사용되는 주 계정입니다. |

    자세한 내용은 [판매세에 대한 원장 게시 그룹 설정](tasks/set-up-ledger-posting-groups-sales-tax.md)을 참조하세요

## <a name="debug-in-code-to-check-ledger-dimensions"></a>원장 차원을 확인하기 위한 코드의 디버그

코드에서 게시 계정은 원장 차원에 의해 결정됩니다. 원장 차원은 데이터베이스에 계정의 레코드 ID를 저장합니다.

1. 판매 주문의 경우 **Tax::saveAndPost()** 및 **Tax::post()** 메서드에 중단점을 추가합니다. **\_ledgerDimension** 의 값에 주의합니다.

    [![중단점이 있는 판매 주문 코드 샘플.](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    구매 주문이 경우 **TaxPost::saveAndPost()** 및 **TaxPost::postToTaxTrans()** 메서드에 중단점을 추가합니다. **\_ledgerDimension** 의 값에 주의합니다.

    [![중단점이 있는 구매 주문 코드 샘플.](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. 다음 SQL 쿼리를 실행하여 원장 차원에서 저장한 레코드 ID를 기반으로 데이터베이스에서 계정의 표시 값을 찾습니다.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![레코드 ID의 값 표시.](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. 호출 스택을 조사하여 **_ledgerDimension** 값이 할당된 위치를 찾습니다. 일반적으로 값은 **TmpTaxWorkTrans** 에 있습니다. 이 경우 값이 할당된 위치를 찾으려면 **TmpTaxWorkTrans::insert()** 및 **TmpTaxWorkTrans::update()** 에 중단점을 추가해야 합니다.

## <a name="determine-whether-customization-exists"></a>사용자 지정이 있는지 확인

이전 섹션의 단계를 완료했지만 문제가 발견되지 않는 경우 사용자 지정이 있는지 확인하세요. 사용자 지정이 없으면 Microsoft 서비스 요청을 작성하여 추가 지원을 받으세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
