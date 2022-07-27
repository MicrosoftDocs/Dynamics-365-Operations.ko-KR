---
title: 품목 또는 원자재 추적
description: 이 절차에서는 항목 추적을 사용하여 항목 또는 원자재가 사용되었거나 사용 중인 위치를 식별하는 방법을 보여줍니다.
author: yufeihuang
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c01cabf32542798f70720ab0db7d055fc54cf345
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448846"
---
# <a name="trace-an-item-or-raw-material"></a>품목 또는 원자재 추적

[!include [banner](../../includes/banner.md)]

이 절차에서는 항목 추적을 사용하여 항목 또는 원자재가 사용되었거나 사용 중인 위치를 식별하는 방법을 보여줍니다. 이 절차를 통해 품목을 식별하고 소스를 역추적한 다음 완제품의 생산 및 판매를 추적할 수 있습니다. 이 프로세스는 영향을 받는 고객, 영향을 받는 판매 주문 등을 조사하는 데 사용할 수 있습니다. 이 절차는 데모 데이터 회사 USP2를 사용합니다.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>알려진 배치 번호를 사용하여 항목을 거꾸로 추적
1. **탐색** 창에서 **모듈 > 재고 관리 > 문의 및 보고서 > 추적 규모 > 항목 추적** 으로 이동합니다.
2. **품목 번호** 필드에서 'P9100'을 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. **앞으로 또는 뒤로** 필드에서 '뒤로'를 선택합니다.
5. **배치 번호** 필드에서 'as-12-344-01'을 선택합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.
7. **확인** 을 클릭합니다.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>항목 식별, 정방향 추적 및 분석

트리의 상단 노드는 선택한 품목 및 배치의 현재고 수량을 나타냅니다. 정방향 추적이 실행되어야 하는 항목을 찾으려면 트리의 노드를 확장해야 합니다.   
1. 트리에서 아래에 설명된 노드를 확장한 다음 마지막 노드를 선택합니다.
    
    확장: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal \P9100 ● Picked ● 판매 주문 000072 ● 12/22/2015 ● -1 keg ● -4.00 gal ● Site=1, 창고 =10, 배치 번호=as-12-344-01 \P9100 ● 생산 B-000050 ● 12/9/2015● 7 keg ● 27.00gal ● 사이트=1,창고=10,배치 번호=as-12-344- 01 ● Co-products: P9101' 그런 다음 해당 노드를 선택합니다.     
2. 트리에서 아래에 설명된 노드를 확장한 다음 해당 노드를 선택합니다.
    
    방금 선택한 노드에서 시작하여 'M9103 ● 생산 라인 B-000050 ● 12/9/2015 ● -160.00lb ● 크기=70, 색상=OK, 사이트=1, 창고=10, 배치 번호=App01'을 확장한 다음 해당 노드를 선택합니다.  
3. **노드에서 추적** 을 클릭합니다.
4. **앞으로** 를 클릭합니다.
5. **작업 창** 에서 **추적** 을 클릭합니다.
    
    추적 중인 항목의 영향을 받는 고객에 대한 정보와 배송된 항목과 배송되지 않은 항목과 관련된 판매 주문에 대한 정보를 제공하는 몇 가지 추적 옵션이 있습니다.   
6. **고객** 을 클릭합니다.
7. 페이지를 닫습니다.
8. **작업 창** 에서 **추적** 을 클릭합니다.
9. **배송된 판매 주문** 을 클릭합니다.
10. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]