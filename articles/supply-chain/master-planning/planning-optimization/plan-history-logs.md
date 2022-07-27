---
title: 계획 기록 및 계획 로그 보기
description: 이 항목에서는 계획 최적화 기능에 의해 트리거된 계획 작업의 기록을 보는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 757d2103bd629c0107a3f29599196a56ea56d431a66cf1e69c7b3cf3d817c087
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446731"
---
# <a name="view-plan-history-and-planning-logs"></a>계획 기록 및 계획 로그 보기

[!include [banner](../../includes/banner.md)]

이 항목에서는 Microsoft Dynamics 365 Supply Chain Management에서 계획 최적화 기능에 의해 트리거된 계획 작업의 기록을 보는 방법에 대해 설명합니다.

계획에 대한 기록을 보려면 **기준 계획** \> **설정** \> **계획** \> **기준 계획** 으로 이동하고 **기록** 을 선택하여 계획을 엽니다. 기록에는 선택한 계획에 대한 모든 작업이 나열됩니다. 목록에는 완료된 작업과 활성 작업이 포함됩니다.

계획 최적화 기준 계획 실행에 대한 작업 기록은 기준 계획당 최대 60개의 레코드만 유지합니다. 새 기준 계획 계산을 실행할 때마다 해당 계획의 가장 오래된 기록 레코드가 삭제됩니다.

작업의 시작 시간과 상태를 보는 것 외에도 특정 작업에 대한 로그를 볼 수 있습니다. 로그에는 추가 정보와 경고가 포함됩니다. 모든 작업에 로그가 있는 것은 아닙니다. 작업에 대한 로그를 보려면 **로그** 를 선택합니다. 로그 항목은 작업이 완료된 날짜로부터 30일 동안만 저장되며 그 이후에는 자동으로 삭제됩니다.

**백그라운드에서 실행** 빠른 탭의 **일괄 처리** 옵션이 기준 계획 처리가 설정될 때 활성화되었으며 배치 작업 로그는 기준 계획 실행 중에 생성된 경고 및 오류에 대한 추가 정보를 표시합니다. 예를 들어 자동 확정 오류는 일괄 작업 로그에만 캡처됩니다. **기록** 페이지의 로그에는 표시되지 않습니다.

자동 확정 오류 및 기준 계획 실행 중에 발생한 기타 경고 또는 오류를 보려면 다음 단계를 따르십시오.

1. **시스템 관리 \> 문의 \> 일괄 작업** 으로 이동합니다.
1. 관심 있는 기준 계획 실행을 나타내는 레코드를 찾아 선택합니다. (예를 들어, **직무 설명** 필드의 값은 *기준 계획* 으로 시작할 수 있습니다.)
1. **일괄 작업** 페이지에 *향상된 양식* 또는 *레거시(향되지 않은) 양식* 을 사용 중인지 여부에 따라 다음 단계 중 하나를 따릅니다.

    - 향상된 양식을 사용하는 경우 작업 창에서 **일괄 작업 기록** 을 선택합니다. 그런 다음 **일괄 작업 기록** 페이지의 작업 창에서 **로그** 를 선택합니다.
    - 레거시 양식을 사용하는 경우 작업 창의 **일괄 작업** 에서 **로그** 를 선택합니다.

1. **메시지 세부 정보** 를 선택하여 **메시지 세부 정보** 페이지를 열어 처리하는 동안 캡처된 모든 경고 및 오류를 볼 수 있습니다.

## <a name="related-resources"></a>관련 리소스

- [계획 최적화 개요](planning-optimization-overview.md)
- [계획 최적화 시작하기](get-started.md)
- [계획 최적화 적합 분석](planning-optimization-fit-analysis.md)
- [계획에 필터 적용](plan-filters.md)
- [계획 작업 취소](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
