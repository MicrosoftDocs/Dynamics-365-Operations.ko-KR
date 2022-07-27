---
title: 품질 관리 항목 샘플링
description: 이 항목에서는 항목 샘플링을 설정하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea749c470ab1d80f1f3974596a2cd4a1f5b7b32d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449119"
---
# <a name="quality-management-item-sampling"></a>품질 관리 항목 샘플링

[!include [banner](../includes/banner.md)]

항목 샘플링은 품질 협회의 일부로 사용됩니다. 검사해야 하는 현재 총실사량을 정의합니다. 샘플링은 고정 수량, 백분율 또는 전체 번호판을 기반으로 할 수 있습니다.

## <a name="set-up-item-sampling"></a>항목 샘플링 설정

항목 샘플링을 설정하려면 다음 단계를 따르십시오.

1. **재고 관리 \> 설정 \> 품질 관리 \> 항목 샘플링** 으로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **항목 샘플링** 필드에 값을 입력합니다.
1. **설명** 필드에 값을 입력합니다.
1. **값** 필드에 숫자를 입력합니다. 이 값은 인접 필드에서 선택한 수량 사양 값과 관련됩니다.
1. 테스트에 실패한 경우 전체 로트 또는 주문 라인 수량을 차단해야 하는 경우 **프로세스** 섹션에서 **전체 차단** 확인란을 선택합니다. 이 확인란의 선택을 취소하면 테스트가 실패한 경우 품질 순서의 항목만 차단됩니다.
1. **저장** 을 선택합니다.
1. 페이지를 닫습니다

> [!NOTE]
> *창고 공정을 위한 품질 관리* 기능은 추가 항목 샘플링 기능을 제공합니다. *항목 샘플링 범위* 개념을 추가하고 전체 번호판을 수량 사양으로 정의할 수 있습니다. 이 기능을 사용 설정한 경우 [창고 프로세스 품질 관리](quality-management-for-warehouses-processes.md)를 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
