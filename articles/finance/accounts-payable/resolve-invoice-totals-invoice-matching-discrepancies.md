---
title: 송장 합계 매칭 중 불일치 해결 개요
description: 송장 합계 매칭을 사용하여 송장 총액이 예상 금액에서 허용 가능한 차이보다 크게 벗어나지 않도록 할 수 있습니다.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "63413"
- intro-internal
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f15edb0423bba2a6fe01f4b3ef1ba1be4e463d4
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451450"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a>송장 합계 매칭 중 불일치 해결 개요

[!include [banner](../includes/banner.md)]

송장 매칭 유효성 검사의 한 유형이 송장 합계 매칭입니다. 시스템이 송장 총액 매칭을 수행하도록 지정하려면 **지급 계정 매개 변수** 페이지의 **송장 유효성 검사** 탭에서 **송장 총액 매칭** 옵션을 **예** 로 설정합니다. 

송장 합계 매칭을 사용하여 송장 총액이 예상 금액에서 허용 가능한 차이보다 크게 벗어나지 않도록 할 수 있습니다. **송장 총액 매칭 세부 정보** 페이지에서 6개의 총액이 비교됩니다. 합계 중 하나라도 예상되는 해당 구매 주문 합계에서 벗어나면 매칭 불일치 플래그가 지정됩니다. 

총액 매칭 불일치가 있는 송장을 검토하려면 **공급업체 송장 항목** 영역 공간에서 **보류 중인 송장** 타일을 클릭합니다. 그런 다음 작업 창의 **검토** 탭에서 **매칭 세부 정보** 를 클릭합니다. 매칭 불일치가 감지되면 송장 금액 옆에 경고 아이콘이 나타납니다. 송장 총액 매칭 세부 정보를 보면 총액에 대한 더 자세한 내용을 볼 수 있다. 

불일치를 식별한 후 송장의 정보가 올바르지 않다고 생각되면 공급업체에 문의해야 할 수 있습니다. 공급업체와의 계약 결과에 따라 다음 작업 중 하나를 수행할 수 있습니다.

-   가격 차이를 수락하고 매칭 불일치가 있는 송장을 게시합니다. 매칭 불일치가 있는 경우 게시하기 전에 승인이 필요하도록 시스템을 설정할 수 있습니다. 이 경우 매칭 불일치를 승인해야 하며 선택적으로 승인 주석을 입력할 수 있습니다. 그런 다음 송장 게시를 선택할 수 있습니다.
-   송장 금액을 예상 금액으로 수정하고 송장을 게시합니다.
-   공급업체에 전체 신용 거래와 수정된 새 송장을 요청합니다.

자세한 내용은 [예외 조사/해결](tasks/research-resolve-exceptions.md)을 참조하세요.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]