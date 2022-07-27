---
title: 이전 주문의 창고 설정
description: 이 토픽에서는 이전 주문에 대한 창고를 설정하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6de9df2749836c68bc4e9f92a6934516ff9c1d469374f0d63173a209c841ba38
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447073"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>이전 주문의 창고 설정 

[!include [banner](../includes/banner.md)]

창고 레벨을 사용하여 창고 간 이전 주문을 지원하는 계층 구조를 작성할 수 있습니다. 이 설정을 기반으로 기준 일정 계획이 개별 창고 수준에서 항목 소요량을 계산하고 이를 이행하기 위해 지정된 출처 창고에서 계획된 이전 주문을 생성합니다.

1.  **재고 관리 > 설정 > 재고 분석 > 창고** 를 클릭합니다.

2.  리필할 창고를 선택합니다.

3.  **기준 계획** 빠른 탭에서 **리필** 확인란을 선택합니다.

4.  **기본 창고** 필드에서 리필 창고로 지정할 창고를 선택합니다. 기준 일정 계획은 선택한 창고에 대한 이전 소요량을 계산하고 지정된 **기본 창고** 에서 계획된 이전 주문을 생성합니다.
   
    > [!NOTE]
    > <P><STRONG>리필</STRONG> 확인란을 선택하지 않으면 두면 선택한 창고가 <STRONG>주요 창고</STRONG>와(과) 관련된 창고 레벨로 지정되지만, <STRONG>주요 창고</STRONG>은(는) 리필 창고로 설정되지 않습니다.</P>

5.  새 설정을 적용하려면 페이지를 닫습니다.


> [!TIP]
> <P>리필을 위해 창고를 지정하려면 먼저 <STRONG>재고 규모 그룹</STRONG> 페이지에서 창고를 재고 규모로 설정해야 합니다. 이 페이지에서 창고에 대한 <STRONG>활성</STRONG> 필드 및 <STRONG>차원별 적용 범위 계획</STRONG> 필드를 선택합니다.</P>

## <a name="set-up-transport-lead-time"></a>운송 리드 타임 설정

또한 **운송일** 페이지에서 창고 간의 운송 리드 타임을 설정해야 합니다. 
1. **재고 관리 > 설정 > 유통 > 운송일** 로 이동합니다.
2. **입고 지점** 필드에서 **창고** 를 선택합니다.
3. **배송 창고**, **입고 창고** 및 **운송일** 을 선택합니다. 
4. (선택 사항) **배송 모드별 운송일** 탭에서 배송 모드에 따라 운송 시간을 설정할 수도 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]