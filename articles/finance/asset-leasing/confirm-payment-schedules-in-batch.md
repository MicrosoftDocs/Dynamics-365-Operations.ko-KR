---
title: 배치로 자산 임대 지불 일정 확인
description: 이 토픽에서는 배치로 지불 일정을 확인하는 방법에 대해 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82e985d3b1518a287fbf0916ab3afc71d4bd6466f93992b587942053af44cf59
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450709"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>배치로 자산 임대 지불 일정 확인

[!include [banner](../includes/banner.md)]

이 토픽에서는 배치로 지불 일정을 확인하는 방법에 대해 설명합니다. 지불 일정은 임대차 단위 또는 확인 배치 프로세스를 통해 확인됩니다. 분개장 기입은 지불 일정이 확인된 임대에 대해서만 전기할 수 있습니다. 지불 일정의 확인은 임대에 대한 재무 정보의 최종 승인 역할을 합니다. 지불 및 임대 기간과 같은 임대에 대한 재무 정보에 대한 모든 향후 변경은 임대 조정을 구성하며 그러한 방식으로 처리되어야 합니다.

여러 지불 일정을 확인하려면 다음 단계를 따르십시오.

1. **자산 임대 \> 정기 \> 확인 배치** 로 이동합니다.
2. **확인 배치** 페이지에서 **확인 배치** 를 선택합니다.
3. 표시되는 대화 상자에서 확인하려는 장부를 필터링합니다.

    - 특정 임대 그룹의 모든 장부를 확인하려면 **임대 그룹** 필드에서 해당 그룹을 선택하십시오.
    - 특정 장부를 확인하려면 **장부 ID** 필드에서 장부를 선택하십시오.
    - 모든 장부를 확인하려면 **모든 장부용** 매개 변수를 켭니다.

새로 확인된 장부에 대한 정보는 **확인된 장부** 페이지에서 확인하실 수 있습니다. 지급 일정이 확인된 후 리스에 대해 초기 인식 분개장을 전기할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
