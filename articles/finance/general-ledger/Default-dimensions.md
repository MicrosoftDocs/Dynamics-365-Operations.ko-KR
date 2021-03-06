---
title: 재무 차원 및 게시
description: 계정 차트를 계획하고 설정할 때, 문서 또는 분개장을 게시할 때 다양한 구성 요소가 함께 작동하는 방식을 고려해야 합니다. 이러한 구성 요소에는 계정 구조, 고급 규칙, 균형 조정, 고정 차원이 포함됩니다. 이 항목에서는 각 구성 요소가 무엇이며 구성 요소가 어떻게 조합되어 동작하는지 설명합니다.
author: aprilolson
ms.date: 08/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9e7416c1ed69fa9783694e2adee7ada4e25e14054daeb1761428855690eb522f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450859"
---
# <a name="financial-dimensions-and-posting"></a>재무 차원 및 게시 

[!include [banner](../includes/banner.md)]

계정 차트를 계획하고 설정할 때, 문서 또는 분개장을 게시할 때 다양한 구성 요소가 함께 작동하는 방식을 고려해야 합니다. 이러한 구성 요소에는 계정 구조, 고급 규칙, 균형 조정, 고정 차원이 포함됩니다. 이 항목에서는 각 구성 요소가 무엇이며 구성 요소가 어떻게 조합되어 동작하는지 설명합니다.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>계정 차트 및 재무 차원 구성 요소

기능이 풍부한 규칙 기반 시스템을 사용하여 주요 계정과 재무 차원 값의 유효한 조합을 정의합니다. 이 섹션에서는 각 구성 요소의 기능에 대한 간략한 개요와 구성 요소를 찾을 수 있는 위치를 설명합니다.

### <a name="account-structures"></a>계정 구조

원장을 설정할 때 계정 구조가 필요합니다. 하나 이상의 계정 구조를 정의 및 활성화하고 원장에 할당해야 합니다. 계정 구조에는 주 계정이 있어야 합니다. 비즈니스에 가장 적합한 세그먼트의 순서를 정의할 수 있습니다. 주 계정이 정의되면 시스템이 사용되는 계정 구조를 결정할 수 있습니다. 주 계정을 구조의 첫 번째 또는 앞쪽에 배치함으로써 값을 제한하고 마지막으로 알려진 유효한 값을 기본값으로 적용할 수 있습니다. 계정 구조에는 최대 10개의 추가 재무 차원을 포함할 수 있습니다. 계정 구조는 어떤 차원 값이 다른 값과 조합되었을 때 유효한지 정의합니다. 또한 차원 값을 입력해야 하는지도 정의합니다.

### <a name="advanced-rules"></a>고급 규칙

고급 규칙은 계정 차트를 설정할 때 선택적 구성 요소입니다. 계정 구조에 고급 규칙을 원하는 수만큼 추가할 수 있습니다. 고급 규칙은 특정 기준을 충족했을 때 추가 재무 차원을 추적해야 하는 경우를 처리하기 위해 종종 사용됩니다. 예를 들어 출장 경비 계정을 사용하는 경우 직원이 출장 중인 이벤트와 같은 추가 정보를 추적할 수 있습니다. 고급 규칙이 여러 개 있는 경우 규칙 이름에 따라 알파벳 순으로 적용됩니다. 규칙이 추가하는 세그먼트는 계정 구조의 세그먼트 뒤에만 적용할 수 있습니다.

### <a name="balancing-dimension"></a>차원 균형 조정

선택적으로 재무 차원 균형 조정을 정의할 수 있습니다. **원장** 페이지에서 균형을 맞춰야 하는 재무 차원을 정의할 수 있습니다. 그런 다음 트랜잭션이 그 재무 차원에 게시될 때마다 시스템이 자동적으로 게시 항목을 생성하고 게시해 재무 차원의 균형을 잡습니다.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>주 계정의 기본/고정 재무 차원

기본 차원은 마스터 레코드(예: 고객 또는 공급업체 레코드), 문서 헤더, 주 계정과 같은 다양한 위치에서 가져옵니다. 이 항목에서는 주 계정의 법인별 기본 차원을 중점적으로 설명합니다. 원장의 모든 계정 구조에서 사용되는 각 재무 차원에 대해 주 계정에 **고정 안 됨** 또는 **고정됨** 값이 있는지 정의할 수 있습니다. 재무 차원이 **고정 안 됨** 인 경우 기본값을 사용하지만 이 값은 덮어쓸 수 있습니다. 이는 시스템의 모든 기본값에 적용됩니다. 마스터 레코드에서 가져온 기본값도 마찬가지입니다. 재무 차원이 **고정됨** 값으로 설정되어 있는 경우, 그 값은 기본값이 어디에서 왔든, 사용자가 입력한 것이든 관계없이 항상 적용됩니다.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>게시 중 기본 차원이 적용되는 순서

종종 다양한 구성 요소가 실행되는 순서에 대해 질문하는 경우가 있습니다. 기본 차원이 적용되는 순서를 이해하는 것은 아주 중요합니다. 이 동작이 설정 방법에 영향을 미치기 때문입니다.

> [!NOTE]
> 이 정보는 애플리케이션의 기본 차원에만 적용됩니다. Microsoft Excel 또는 Data Management Framework를 사용하여 데이터를 가져오는 경우 동작이 달라집니다.

### <a name="example-1"></a>예 1

**계정 구조**

| 주 계정            | 사업부           | 부서              | Cost center             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| 모든 값이 허용됩니다. | 모든 값이 허용됩니다. | 모든 값이 허용됩니다. | 모든 값이 허용됩니다. |

**주 계정**

| 주 계정 | 이름          | 법인 | 부서                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | 제품 판매 | USMF         | 고정 – 022 영업 및 마케팅 부서 |

다음 그림은 주 계정 401100에 설정된 고정 기본 차원을 보여 줍니다.

[![기본 재무 차원.](./media/default-dimensions.png)](./media/default-dimensions.png)

이 매우 기본적인 예에서는 부서 차원이 기본값 **023**(운영)을 사용하도록 설정되어 있는 일반 분개장을 입력합니다. 원장 계정을 입력해서 게시할 것입니다. 다음 그림은 총계정원장 헤더의 기본 재무 차원을 보여줍니다.

[![일반 분개장.](./media/general-journal.png)](./media/general-journal.png)

분개장 헤더의 기본 차원으로 인해 부서 023을 판매 계정 라인이 기본으로 적용됩니다. 다음 그림은 헤더의 **023** 기본 차원 값이 적용되는 일반 분개장 라인을 보여 줍니다.

[![분개장 바우처.](./media/journal-voucher.png)](./media/journal-voucher.png)

단, 라인이 게시되면 고정 차원이 적용되어 부서 022에 게시됩니다. 다음 그림은 영업 계정에 고정 차원이 적용된 게시된 바우처를 보여 줍니다.

[![고정 차원이 적용된 바우처 트랜잭션.](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>예 2

이 예에서는 첫 번째 예와 동일한 설정을 사용합니다. 단, 두 번째 구성 요소를 추가하고 부서 차원을 차원 균형 조정으로 사용합니다. 다음 그림에서 USMF 원장의 재무 차원 균형 조정으로 **부서** 가 설정됩니다.

[![부서를 재무 차원 균형 조정으로 사용한 것을 보여주는 그림.](./media/ledger.png)](./media/ledger.png)

동일한 분개장 헤더 설정이 사용되고 동일한 트랜잭션이 게시되며 고정 차원이 먼저 적용됩니다. 그런 다음 균형 조정 논리를 적용하여 모든 부서에 균형 잡힌 항목이 있도록 합니다. 다음 그림은 고정 차원이 적용된 후 균형 조정 항목이 포함된 바우처 트랜잭션을 보여 줍니다.

[![균형 조정 항목이 적용된 후 바우처 트랜잭션.](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>예 3

이 예에서는 고급 규칙을 추가합니다. 고급 규칙에서 영업 계정 401100 및 부서 022(영업 및 마케팅)를 지정하면 고객이라는 이름의 추가 세그먼트를 추적해야 합니다.

이 예는 순서 때문에 중요합니다. 계정 구조는 주 계정 입력 후 결정됩니다. 계정 구조 설정을 참조하면 시스템은 주 계정, 사업부, 부서, 비용 센터가 관련이 있다고 판단할 수 있습니다. 이 시점에서는 게시 중에 분개장 바우처에 기본 차원이 적용될 때까지 고정 차원이 적용되지 않기 때문에 고급 규칙이 트리거되지 않습니다. 다음 그림에서는 고급 규칙의 기준이 충족되지 않았기 때문에 고객 세그먼트가 없습니다.

[![원장 계정.](./media/drop-down.png)](./media/drop-down.png)

프로세스의 끝에 고정 차원이 적용되었기 때문에 게시에 성공하지 못합니다. 차원 유효성 검사에서 주 계정이 401100이고 부서가 022인 경우 고객 세그먼트가 필요한 것으로 판단합니다. 유효성 검사 오류로 인해 게시할 수 없습니다. 다음 그림은 차원 유효성 검사에서 고객이 필수 세그먼트임을 확인한 후 표시되는 메시지를 보여줍니다.

[![메시지 세부 정보.](./media/message.png)](./media/message.png)

이 예에서는 고급 규칙이 트리거되어 고급 세그먼트를 입력할 수 있도록 기본값을 덮어쓸 필요가 있습니다. 그러나 이 해결책이 항상 가능한 것은 아니며 일부 사용자는 게시 규칙을 인식하지 못합니다. 따라서 계정 차트를 설정할 때 기본 차원이 적용되는 순서를 이해하는 것이 중요합니다.

이 예에서 원하는 결과를 위해 여러 가지 방법으로 설정을 변경할 수 있습니다. 예를 들어, 영업 계정에 대한 새 계정 구조를 만들고 이 구조에 고객 세그먼트를 포함할 수 있습니다. 기존 계정 구조에 행을 더 추가하고 주 계정 및 유효한 부서 값을 지정할 수도 있습니다. 그런 다음 추가 고객 구조에서, 고객 세그먼트가 있는 영업 계정의 개별 계정 구조를 가지는 것이 편리할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스 

다음 리소스 중 일부는 이전 버전의 소프트웨어를 참조합니다. 그러나 기본 차원의 적용에 대한 여러 정보와 많은 개념은 이전 버전과 동일하며, 참조 내용도 여전히 유효합니다.

[부서 간 회계를 위한 균형 잡힌 분개장](example-balanced-journals-interunit-accounting.md)

[계정 차트 계획](plan-chart-of-accounts.md) 

[AX 2012 블로그의 계정 차트 계획](/archive/blogs/axsa/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7) – 이 링크는 7부작 시리즈의 1부로 이동합니다.

[회계 분포의 차원 기본값 설정](/archive/blogs/ax_gfm_framework_team_blog/dimension-defaulting-in-accounting-distributions-part-1-introduction)

[차원 프레임워크의 차원 기본값 설정](/archive/blogs/ax_gfm_framework_team_blog/dimension-defaulting-part-1-financial-dimensions-discovery)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
