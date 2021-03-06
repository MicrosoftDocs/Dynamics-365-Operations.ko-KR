---
title: 판매세 지불 및 반올림 규칙
description: 이 항목에서는 판매세 당국의 반올림 규칙 설정이 작동하는 방식과 판매세 정산 및 사후 판매세 작업 중 판매세 잔액을 반올림하는 방법에 관해 설명합니다.
author: kailiang
ms.date: 10/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a75d41195875c5ed48cbe8ce5f5e448f173e718
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451120"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>판매세 지불 및 반올림 규칙

[!include [banner](../includes/banner.md)]

이 항목에서는 판매세 당국의 반올림 규칙 설정이 작동하는 방식과 판매세 정산 및 사후 판매세 작업 중 판매세 잔액을 반올림하는 방법에 관해 설명합니다.

정기적으로 세무 당국에 판매세를 신고 및 납부해야 합니다. 이 작업은 **판매세** 페이지에서 판매세 정산 및 게시 프로세스를 실행하여 완료할 수 있습니다. 일정 기간의 판매세는 판매세 계정에 대해 정산되며 판매세 잔액은 판매세 정산 계정에 게시됩니다. 판매세 정산 계정에 게시되는 판매세 잔액은 **판매세** 페이지에서 반올림 규칙을 설정하여 세무 당국의 요구에 따라 반올림할 수 있습니다. 

반올림 오차는 총계정원장의 자동 거래용 계정 필드에서 선택한 판매세 반올림 계정으로 게시됩니다.

아래 예는 판매세 당국에 대한 반올림 규칙이 작동하는 방식을 보여줍니다.

## <a name="examples"></a>예

특정 기간의 총 판매세가 -98,765.43의 신용 잔액을 표시합니다. 법인이 납부한 것보다 더 많은 판매세를 징수했습니다. 따라서 법인은 세무 당국에 돈을 빚지고 있습니다. 

법인은 잔액을 가장 가까운 1.00으로 반올림하는 반올림 방법을 사용하려고 합니다. 판매세 회계를 담당하는 사용자는 다음 단계를 수행합니다.

1. **세금** > **간접세** > **판매세** > **판매세 당국** 을 클릭합니다.
2. **일반** 빠른 탭의 **반올림 형식** 필드에서 **기본** 을 선택합니다.
3. **반올림** 필드에 1.00을 입력합니다.
4. 세무서에 판매세를 납부할 때가 되면 **세금** > **신고** > **판매세** > **판매세 정산 및 게시** 로 이동합니다. 판매세 정산 계정에서 세금 부채 금액 **98,765.43** 이 **98,765** 로 반올림된 것을 볼 수 있습니다.

다음 표는 **판매세 당국** 페이지의 **반올림 형식** 필드에서 사용할 수 있는 각 반올림 방법을 사용하여 98,765.43의 금액을 반올림하는 방법을 보여줍니다.

> [!NOTE]                                                                                  
> 반올림 값이 0.00으로 설정된 경우
>
> - 기본 반올림의 경우 반올림 동작은 **반올림 = 0.01** 과 동일합니다.
> - **반올림 형식 옵션**, **하향**, **반올림** 및 **자체 이점** 의 경우 동작은 **반올림 = 1.00** 의 경우와 동일합니다.

| 반올림 형식 옵션                | 반올림 가치 = 0.01 | 반올림 가치 = 0.10 | 반올림 가치 = 1.00 | 반올림 가치 = 100.00 | 반올림 가치 = 0.00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| 기본                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| 하향                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| 반올림                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| 대변 잔액에 대한 자체 이점 | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| 차변 잔액에 대한 자체 이점  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>기본 반올림 및 반올림 정밀도는 0.01입니다

```<table>
  <tr>
    <td>Rounding
    </td>
    <td>Calculation process
    </td>
  </tr>
    <tr>
    <td>round(1.015, 0.01) = 1.02
    </td>
    <td>
      <ol>
        <li>round(1.015 / 0.01, 0) = round(101.5, 0) = 102
        </li>
        <li>102 * 0.01 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.014, 0.01) = 1.01
    </td>
    <td> <ol>
        <li>round(1.014 / 0.01, 0) = round(101.4, 0) = 101
        </li>
        <li>101 * 0.01 = 1.01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.011, 0.02) = 1.02
    </td>
    <td> <ol>
        <li>round(1.011 / 0.02, 0) = round(50.55, 0) = 51
        </li>
        <li>51 * 0.02 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.009, 0.02) = 1.00
    </td>
    <td> <ol>
        <li>round(1.009 / 0.02, 0) = round(50.45, 0) = 50
        </li>
        <li>50 * 0.02 = 1.00
        </li>
      </ol>
    </td>
  </tr>
</table>
```

> [!NOTE]                                                                                  
> 자체 이점을 선택하면 항상 법인에 유리하게 반올림됩니다. 

자세한 내용은 다음 항목을 참조하세요.
- [판매세 개요](indirect-taxes-overview.md)
- [판매세 납부 생성](tasks/create-sales-tax-payment.md)
- [문서에 대한 판매세 거래 생성](tasks/create-sales-tax-transactions-documents.md)
- [게시된 판매세 거래 보기](tasks/view-posted-sales-tax-transactions.md)
- [반올림 기능](/previous-versions/dynamics/ax-2012/reference/aa850656(v=ax.60))




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
