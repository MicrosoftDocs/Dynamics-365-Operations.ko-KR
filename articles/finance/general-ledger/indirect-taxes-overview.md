---
title: 판매세 개요
description: 이 항목에서는 판매세 체계에 대한 개요를 제공합니다. 판매세 설정의 요소와 함께 작동하는 방식에 대해 설명합니다.
author: kailiang
ms.date: 10/28/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 021692e0b599731db1d991405fcb4632080582bf
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451411"
---
# <a name="sales-tax-overview"></a>판매세 개요

[!include [banner](../includes/banner.md)]

이 항목에서는 판매세 체계에 대한 개요를 제공합니다. 판매세 설정의 요소와 함께 작동하는 방식에 대해 설명합니다.

## <a name="overview"></a>개요

판매세 프레임워크는 판매세, 부가가치세(VAT), 물품용역세(GST), 단위당 수수료 및 원천징수세와 같은 다양한 유형의 간접세를 지원합니다. 이러한 세금은 구매 및 판매 거래 중에 계산되고 문서화됩니다. 정기적으로 세무 당국에 신고 및 납부해야 합니다. 

다음 다이어그램은 세금 설정의 엔터티와 이들 간의 관계를 보여줍니다.

[![세금 설정 엔터티의 개요를 보여주는 다이어그램.](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

회사가 관리해야 하는 모든 판매세에 대해 판매세 코드를 정의해야 합니다. 판매세 코드는 판매세의 세율과 계산 규칙을 저장합니다. 

모든 판매세 코드는 판매세 정산 기간에 연결되어야 합니다. 판매세 정산 기간은 판매세를 판매세 당국에 보고하고 지불해야 하는 간격을 정의합니다. 모든 판매세 정산 기간은 판매세 당국에 할당되어야 합니다. 판매세 당국은 판매세가 보고되고 지불되는 법인을 나타냅니다. 또한 판매세 보고서의 레이아웃을 정의합니다. 판매세 당국은 공급업체 계정과 연결될 수 있습니다. 자세한 내용은 [판매세 정산 기간 설정](tasks/set-up-sales-tax-settlement-periods.md)을 참조하세요.

모든 판매세 코드는 원장 게시 그룹에도 연결되어야 합니다. 원장 게시 그룹은 판매세 코드 금액이 게시될 주 계정을 지정합니다. 

선택적 판매세 보고 코드도 정의할 수 있습니다. 판매세 코드에 대해 계산되는 다양한 금액 유형에 대해 판매세 코드에 할당할 수 있습니다. **코드별 판매세 납부** 보고서는 지정된 판매세 정산 기간 및 간격에 대한 판매세 보고 코드별 총액을 보여줍니다. 

판매세가 계산되고 게시되어야 하는 모든 거래에는 판매세 그룹과 품목 판매세 그룹이 있어야 합니다. 판매세 그룹은 거래 당사자(예: 고객 또는 공급업체)와 관련되지만 품목 판매세 그룹은 거래의 리소스(예: 품목 또는 조달 범주)와 관련됩니다. 세금 그룹에는 세금 코드 목록이 포함되어 있습니다. 거래에 대한 판매세 그룹과 품목 판매세 그룹 모두에 있는 세금 코드는 해당 거래에 적용되는 세금 코드입니다. 

다음 테이블은 세금 설정에 대한 엔터티 및 순서를 설명합니다.

| 설정 활동                                                  | 필수/선택 및 설명                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 주 계정 만들기.                                           | 필수. 판매세 기능을 설정하려면 먼저 회사에서 세금을 납부하고 기록하는 데 사용하는 주 계정을 만들어야 합니다.                                                                                                                                                                             |
| 판매세에 대한 원장 게시 그룹 설정.                     | 필수. 원장 게시 그룹은 판매세를 기록하고 납부하기 위한 주 계정을 정의합니다.   자세한 내용은 [판매세에 대한 원장 게시 그룹 설정](tasks/set-up-ledger-posting-groups-sales-tax.md)을 참조하세요.                                                                                 |
| 판매세 당국 설정.                                   | 필수. 판매세 당국은 세금을 신고하고 납부해야 하는 기관입니다.    자세한 내용은 [판매세 당국 설정](tasks/set-up-sales-tax-authorities.md)을 참조하세요.                                                                                                                                          |
| 판매세 정산 기간 설정.                            | 필수. 판매세 정산 기간에는 판매세를 신고하고 납부해야 하는 시기와 빈도에 대한 정보가 포함됩니다. 판매세 당국과 관련이 있습니다.                                                                                                                                                       |
| 판매세 보고 코드 설정.                               | 선택 사항. 판매세 보고 코드를 판매세 코드에 할당하여 하나의 판매세 보고 코드로 여러 판매세 코드에 대한 금액을 보고할 수 있습니다. 자세한 내용은 [판매세 보고 코드 설정](tasks/set-up-sales-tax-reporting-codes.md)을 참조하세요.                                         |
| 판매세 코드 설정.                                         | 필수. 판매세 코드에는 각 판매세에 대한 세율과 계산 규칙이 포함됩니다. 판매세 코드는 판매세 정산 기간 및 원장 게시 그룹과 관련이 있습니다. 자세한 내용은 [판매세 코드 설정](tasks/set-up-sales-tax-codes.md)을 참조하세요.                                |
| 판매세 그룹 설정.                                        | 필수. 판매세 그룹에는 거래 당사자(고객 또는 공급업체)에 적용되는 판매 코드 목록이 포함됩니다. 주어진 거래에서 판매세 그룹과 품목 판매세 그룹의 판매세 코드 교차에 따라 해당 거래에 적용되는 판매세 코드가 결정됩니다.                  |
| 품목 판매세 그룹 설정.                                   | 필수. 품목 판매세 그룹에는 거래되는 리소스(제품, 서비스 등)에 적용되는 판매 코드 목록이 포함됩니다. 주어진 거래에서 판매세 그룹과 품목 판매세 그룹의 판매세 코드 교차에 따라 해당 거래에 적용되는 판매세 코드가 결정됩니다. 자세한 내용은 [판매세 그룹 및 품목 판매세 그룹 설정](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md)을 참조하세요. |
| 애플리케이션 매개 변수 페이지에서 판매세 매개 변수 설정. | 필수. 총계정원장, 수취 계정 및 지급 계정과 같은 다른 영역은 간접세의 정확한 계산을 위해 매개 변수를 설정해야 합니다. 이러한 매개 변수는 대부분 기본값이 있지만 각 회사의 요구 사항에 맞게 수정해야 합니다.                                          |

## <a name="sales-tax-on-transactions"></a>거래 시 판매세
모든 거래(판매/구매 문서 라인, 분개장 등)에서 판매세를 계산하려면 판매세 그룹과 품목 판매세 그룹을 입력해야 합니다. 기본 그룹은 마스터 데이터(예: 고객, 공급업체, 품목 및 조달 범주)에 지정되지만 필요한 경우 거래에서 그룹을 수동으로 변경할 수 있습니다. 두 그룹 모두 판매세 코드 목록을 포함하고 두 판매세 코드 목록의 교차에 따라 거래에 적용 가능한 판매세 코드 목록이 결정됩니다. 

모든 거래에 대해 **판매세 거래** 페이지를 열어 계산된 판매세를 조회할 수 있습니다. 문서 라인 또는 전체 문서에 대한 판매세를 조회할 수 있습니다. 특정 문서(예: 공급업체 송장 및 일반 분개장)의 경우 원본 문서에 잘못된 금액이 표시되면 계산된 판매세를 조정할 수 있습니다.

## <a name="sales-tax-settlement-and-reporting"></a>판매세 정산 및 보고
판매세는 규정된 간격(월별, 분기별 등)으로 세무 당국에 신고 및 납부해야 합니다. 원장 게시 그룹에 지정된 대로 간격에 대한 세금 계정을 정산하고 잔액을 세금 정산 계정으로 상계할 수 있습니다. **판매세 정산 및 게시** 페이지에서 이 기능에 액세스할 수 있습니다. 판매세를 정산해야 하는 판매세 정산 기간을 지정해야 합니다. 

판매세를 납부한 후 판매세 정산 계좌의 잔액과 은행 계좌의 잔액이 일치해야 합니다. 판매세 정산 기간에 지정된 판매세 당국이 공급업체 계정과 관련된 경우 판매세 잔액은 미결 공급업체 송장으로 게시되고 일반 지불 제안에 포함될 수 있습니다.

## <a name="conditional-sales-tax"></a>조건부 판매세
조건부 판매세는 청구서에 지불된 실제 금액에 비례하여 지불되는 판매세입니다. 반대로 표준 판매세는 송장 발행 시 계산됩니다. 조건부 판매세는 송장이 게시될 때가 아니라 지급이 게시될 때 판매세 당국에 납부해야 합니다. 송장이 게시되면 거래는 판매세 장부 보고서에 보고되어야 합니다. 단, 판매세 납부 보고서에서 해당 거래를 제외하여야 합니다. 

총계정원장 매개 변수 양식에서 조건부 판매세 확인란을 선택하면 송장을 지불할 때까지 판매세가 공제되지 않습니다. 이는 일부 국가/지역의 법적 요구 사항입니다.

> [!NOTE]
> 조건부 판매세 확인란을 선택한 경우 기능을 지원하기 위해 판매세 코드 및 판매세 그룹을 설정하고 원장 게시 그룹도 만들어야 합니다. |

###  <a name="example"></a>예

매월 판매세를 정산합니다. 6월 15일에 판매세가 포함된 10,000의 고객 송장을 만듭니다.
-   판매세는 25% 또는 2,500입니다.
-   송장 결제는 7월 30일까지입니다.

고객으로부터 대금을 받지 못하더라도 6월에 송장이 게시될 때 일반적으로 2,500을 정산하여 세무 당국에 납부해야 합니다. 

단, 조건부 판매세를 사용하는 경우 7월 30일에 고객으로부터 대금을 수령하는 시점에 세무당국과 정산합니다.

### <a name="postdated-check"></a>사후입금 수표

지불 방법으로 사후입금 수표를 사용하는 경우 지불이 생성될 때 은행 계좌가 반제되지 않습니다. 일부 국가에서는 결제가 은행에서 결제되면 VAT가 '실현' 책임이 되며, 이는 사후입금 수표가 결제됨을 의미합니다. **현금 및 은행 관리 > 설정 > 현금 및 은행 관리 매개 변수 > 사후입금 수표** 에서 **사후입금 수표 발행 시 조건부 세금 실현** 을 선택하여 이를 활성화할 수 있습니다.

자세한 내용은 [원천징수세 설정](tasks/set-up-withholding-tax.md)을 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]