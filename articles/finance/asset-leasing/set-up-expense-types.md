---
title: 경비 유형 설정
description: 이 항목에서는 자산 임대에서 경비 유형을 설정하는 방법을 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1e5af18921314061ba3256559d7fc7ceacef606a9b3d5cc3a8047c83494074fc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450157"
---
# <a name="set-up-expense-types"></a>경비 유형 설정

[!include [banner](../includes/banner.md)]

이 항목에서는 자산 임대에서 경비 유형을 설정하는 방법을 설명합니다. 지불 일정에 표시되지 않는 비용을 *경비 비용* 이라고 합니다. 이러한 비용의 예로는 재산세, 공용 구역 유지 관리 비용 및 보험 경비가 있습니다.

## <a name="add-an-administrative-expense-type"></a>관리 경비 유형 추가

1. **자산 임대 \> 설정 \> 경비 유형** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 해당 필드에 새 경비 유형과 설명을 입력합니다.

## <a name="assign-accounts-to-administrative-costs"></a>관리 비용에 계정 할당

다음은 경비 유형과 계정을 연결해야 합니다. 이 계정은 경비 일정 항목이 게시될 때 출금됩니다. 상쇄 계정은 각 임대의 **집행 비용 지불 일정** 라인에 지정됩니다.

1. **자산 임대 \> 설정 \> 자산 임대 매개 변수** 로 이동합니다.
2. **계정** 탭의 **집행 비용** 빠른 탭에 있는 **경비 유형** 필드에서 경비 유형을 선택합니다.
3. **추가** 를 선택합니다.
4. **장부 유형** 필드에서 관리 비용을 연결할 장부 유형을 선택합니다.

    > [!NOTE]
    > 여러 장부 유형을 같은 경비 계정에 연결할 수 있습니다.

5. **계정 코드** 필드에 장부를 적용해야 하는 임대를 지정합니다.

    - **모두** – 장부를 모든 임대에 적용합니다.
    - **그룹** – 장부를 특정 임대 그룹에 적용합니다.
    - **테이블** – 장부를 특정 임대에 적용합니다.

6. **계정 코드** 필드에서 **그룹** 또는 **테이블** 을 선택한 경우 **계정/그룹 번호** 필드에서 계정 번호 또는 그룹 번호를 선택합니다.
7. 해당 필드에서 금융 리스 주 계정과 운용 리스 주 계정을 선택합니다.

이 단계를 완료하면 선택한 임대의 **임대 세부 정보** 페이지에 있는 **집행 비용 지불 일정** 라인을 통해 경비를 추가할 수 있습니다. 또는 새 임대를 생성할 때 경비를 추가할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
