---
title: 계획 작업 취소
description: 이 항목에서는 계획 최적화 기능을 사용하는 활성 계획 작업을 취소하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 85dffae7e5484d34d0cfa4bf44649fcdd69fc36804802ad9f02c122adf5d9785
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447232"
---
# <a name="cancel-a-planning-job"></a>계획 작업 취소

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management에서는 계획 최적화 기능을 사용하는 활성 계획 작업을 취소할 수 있습니다. 계획 최적화 작업이 백그라운드에서가 아니라 사용자 인터페이스에서 직접 트리거될 때 대화 상자에서 **취소** 를 선택하면 계획 최적화 작업이 취소되지 않습니다. "작업 취소됨"과 같은 경고가 표시되더라도 계획 최적화로 계획 작업을 취소하려면 여전히 다음 단계를 사용해야 합니다.


활성 계획 작업을 취소하려면 다음 단계를 따르세요. 

> [!NOTE]
> 활성 작업만 취소할 수 있습니다.

1. **마스터 플래닝 \> 설정 \> 계획** 으로 이동합니다.
2. 계획 실행에 적합한 계획을 선택합니다.
3. **기록** 을 선택합니다.
4. 취소할 계획 작업을 선택합니다.
5. **취소** 를 선택합니다.

계획 최적화 서비스에서 작업이 취소되었음을 확인할 때까지 작업 상태는 **취소 중** 입니다. 그런 다음 상태가 **취소됨** 으로 변경됩니다.

> [!NOTE]
> 상태 변경 사항을 보려면 **새로 고침** 단추를 선택하여 페이지를 새로 고쳐야 합니다.

## <a name="additional-resources"></a>추가 리소스

[계획 최적화 개요](planning-optimization-overview.md)

[계획 최적화 시작하기](get-started.md)

[계획 최적화 적합 분석](planning-optimization-fit-analysis.md)

[계획 기록 및 계획 로그 보기](plan-history-logs.md)

[계획에 필터 적용](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]