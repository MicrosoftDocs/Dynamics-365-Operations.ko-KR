---
title: BOM을 완료된 것으로 보고
description: 이 문서에서는 BOM을 완료된 것으로 보고하는 방법에 대한 정보를 제공합니다.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMReportFinish, BOMReportFinishMax, BOMSetupReportFinish
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff88622c2cbbdcff6130fb8c500ea12a1e454ecb5f33834bc0a69718038c9e89
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447175"
---
# <a name="report-boms-as-finished"></a>BOM을 완료된 것으로 보고

[!include [banner](../includes/banner.md)]

이 문서에서는 BOM을 완료된 것으로 보고하는 방법에 대한 정보를 제공합니다.

**완료로 보고** 및 **최대 완료로 보고** 페이지는 BOM(자재 명세서)을 완료로 보고하는 데 사용됩니다. 개념적으로 BOM을 완료로 보고하는 프로세스는 생산 주문을 완료로 보고하는 프로세스와 동일합니다. 이 프로세스는 예를 들어 생산 주문의 고급 기능이 필요하지 않은 간단한 조립 및 키팅 프로세스에서 사용할 수 있습니다. **완료로 보고** 페이지를 사용하면 여러 BOM을 일괄적으로 완료된 것으로 보고할 수 있습니다. **최대 완료로 보고** 페이지에서는 한 번에 하나의 BOM만 완료된 것으로 보고할 수 있습니다. **완료로 보고** 페이지는 재고 관리의 메뉴 항목에서 사용할 수 있으며 두 페이지 모두 **출시된 제품** 페이지의 메뉴 항목으로 사용할 수 있습니다.

## <a name="report-as-finished-page"></a>완료로 보고 페이지
출시된 제품에서 **완료로 보고** 페이지를 열면 페이지에서 표준 재고 기본 수량을 완료로 보고할 것을 제안합니다. 기본적으로 활성 BOM 버전이 표시되지만 승인된 다른 버전이 있는 경우 BOM 버전을 변경할 수 있습니다. 또한 이 페이지에서는 완료된 것으로 보고되어야 하는 출시된 제품에 대한 레코드를 삭제하고 새 레코드를 생성할 수 있습니다. 쿼리를 사용하여 제품을 선택하려면 **선택** 메뉴 항목을 클릭하세요. **확인** 을 클릭하여 선택한 제품에 대한 보고가 완료된 것으로 수동으로 확인할 수 있습니다. 또는 배치로 실행되도록 프로세스를 설정할 수 있습니다. 완료 프로세스로 보고가 확인되면 시스템은 재고 전기가 처리되는 BOM 분개장을 생성합니다. 이 분개장은 완제품에 대한 하나의 라인 항목과 각 BOM 라인에 대한 라인 항목으로 구성됩니다. 분개장이 자동으로 전기되는지 여부 또는 추가 조정을 위해 미결 상태로 남아 있는지 여부를 제어할 수 있습니다.

## <a name="max-report-as-finished-page"></a>최대 완료로 보고 페이지
**최대 완료로 보고** 페이지에서 각 BOM 라인은 완성된 것으로 보고될 수 있는 제품의 조각 수를 나타냅니다. 이 계산은 각 자재 라인의 실제 사용 가능한 현재고를 기반으로 합니다. 다음 예에서 품목 번호 FG 1개는 원자재 RM10 2개와 원자재 RM20 1개를 소비합니다. 수중에 RM10이 10개밖에 없기 때문에 완성된 것으로 보고할 수 있는 FG의 최대 수량은 5개입니다. 이 값은 **최대 완료된 보고** 필드에 표시됩니다.

| 수준 | 품목 번호 | 수량 | 보유 | 최대 완료로 보고 |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>여러 수준이 있는 BOM
BOM에 여러 수준이 있는 경우 **분해** 필드를 사용하여 모든 수준에서 자재를 설명하는 방법을 제어할 수 있습니다. 이 필드는 **완료로 보고** 페이지와 **최대 완료로 보고** 페이지 모두에서 사용할 수 있습니다. 다음 옵션을 사용할 수 있습니다.

-   **전혀** – 자재 부족이 있는 경우 기본 BOM이 분해되지 않습니다.
-   **언제나** – 모든 기본 BOM이 완전히 분해됩니다. 따라서 반제품 구성품 품목에 대한 무료 현재고는 사용되지 않습니다.
-   **부족** – 기본 BOM은 원하는 자재의 전체 수량을 사용할 수 없는 경우에만 전개됩니다.

### <a name="example"></a>예

이 예에서 완제품의 세 조각(품목 번호 FG)이 완제품으로 보고될 준비가 되었습니다. 여기에 표시된 것처럼 2단계 BOM이 있습니다.

| 수준 | 품목 번호 | BOM 라인 수량 | 보유 |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

다음 테이블은 **분해** 필드의 설정이 BOM 분개장 라인이 생성되는 방식에 미치는 영향을 보여줍니다. **분해: 전혀**

| 수준 | 품목 번호 | 수량 |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

앞의 표에서 볼 수 있듯이 품목 번호 COMP만 분개장에서 공제된 것으로 간주됩니다. COMP의 일부인 품목 번호 RM은 분개장 라인으로 전개되지 않으며 COMP의 두 가지 현재고는 고려되지 않습니다. **폭발: 항상**

| 수준 | 품목 번호 | 수량 |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

이 경우 품목 번호 COMP는 원자재인 품목 번호 RM으로 분해됩니다. 현재 보유하고 있는 COMP 2개는 소비할 RM 수량에 포함되지 않습니다. **분해: 부족**

| 수준 | 품목 번호 | 수량 |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

이 경우 품목 번호 COMP의 2개의 현재고가 고려됩니다. 단, 품번 FG 3개가 필요하기 때문에 COMP 1개를 추가로 만들기 위해서는 품번 RM 1개도 필요합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]