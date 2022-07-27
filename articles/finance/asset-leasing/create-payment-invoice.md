---
title: 지불 송장 만들기
description: 이 토픽에서는 월별 임대 송장을 만드는 방법에 대해 설명합니다. 개별 임대에 대한 송장을 생성하거나 배치 프로세스를 사용하여 여러 임대에 대한 송장을 생성할 수 있습니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bc87c329f6f5dd9532b1319f8d88fbc41dcd4d14
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "8450898"
---
# <a name="create-payment-invoices"></a>지불 송장 만들기

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


개별 임대에 대한 월별 송장을 생성하거나 배치 프로세스를 사용하여 여러 임대에 대한 송장을 생성할 수 있습니다. 다음 절차는 **임대 장부 설정** 페이지의 **공급업체에 지불** 매개 변수가 켜져 있을 때 개별 임대 지불 항목을 만드는 방법을 보여줍니다.

1. **임대 요약** 페이지에서 임대를 선택한 후 **장부 \> 지불 일정** 을 선택합니다.
2. 지불해야 할 지불을 선택한 다음 **분개장 만들기** 를 선택합니다. 선택한 지불에 대해 분개장이 생성되었다는 메시지를 받습니다.
3. **송장 분개장** 을 선택한 다음 지불해야 하는 송장을 선택합니다.
4. **라인** 탭에서 총계정원장에 전기하기 전에 분개장 기입을 검토하십시오.

    > [!NOTE]
    > 기본적으로 생성된 공급업체 송장 라인은 **지급 계정 매개 변수** 페이지의 공급업체 전기 프로필을 사용합니다.

5. 정확한 분개를 선택한 다음 지불해야 하는 송장을 선택하십시오.

    이 예에서는 임대 장부의 **공급업체에 지불** 매개 변수가 켜져 있습니다. 따라서 송장은 송장 분개장에 있습니다. **개요** 섹션에는 분개장 기입의 요약이 표시되고 **라인** 섹션에는 실제 분개장 라인에 대한 세부 정보가 표시됩니다.
    
   시스템은 트랜잭션과 일정 간의 차이를 방지하기 위해 특정 재무 필드를 편집하지 못하도록 잠급니다. 잠긴 필드에는 **계정**, **금액,** **재무 차원**, **통화**, **트랜잭션 유형** 입니다. 또한, 일정과 거래 간에 차이가 발생할 수 있으므로 자산 임대 분개에 분개 라인을 추가하거나 삭제할 수 없습니다.

    > [!NOTE]
    > **공급업체에 지불** 매개 변수가 꺼져 있으면 지불 분개장이 임대 장부에 대한 **자산 임대** 페이지에 나열되고 시스템은 송장 대신 자산 임대 항목을 생성합니다. 임대 지불 항목은 **월간 임대 분개장** 필드에 지정된 분개장 이름으로 전기됩니다.

6. 거래가 전기된 후 임대 장부에서 **부채 거래** 를 선택하면 거래 정보와 임대 부채의 장부금액을 확인할 수 있습니다.

    지불 일정에서 **분개장 게시** 확인란이 선택되고 라인에 송장 분개 번호가 표시됩니다. 지불 분개와 해당 분개에 대한 항목이 생성된 후 항목을 다시 생성하려면 먼저 항목을 취소해야 합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
