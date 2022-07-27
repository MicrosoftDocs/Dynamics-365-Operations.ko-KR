---
title: 계획 최적화 확장성
description: 이 토픽에서는 계획 최적화에서 지원되는 확장성 시나리오에 대해 설명합니다.
author: ChristianRytt
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e18801a02ae9e904eb5bc597f9f61ed42c537ab9
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "8449389"
---
# <a name="planning-optimization-extensibility"></a>계획 최적화 확장성

[!include [banner](../../includes/banner.md)]

이 토픽에서는 기준 계획과 관련되고 계획 최적화에서 지원되는 확장성 시나리오에 대해 설명합니다. 이러한 기능은 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.13부터 사용할 수 있습니다.

## <a name="custom-processing-when-master-planning-is-completed"></a>기준 계획 완료 시 사용자 지정 처리

계획 최적화의 가장 일반적인 확장성 시나리오에서 사용자 지정 처리는 계획이 업데이트된 후에 수행됩니다. 예를 들어 계획 주문 테이블(``ReqPO`)에 열을 추가하거나 생성된 계획에서 일부 통계 정보를 파생할 수 있습니다. 이러한 시나리오를 가능하게 하는 주요 확장성 지점은 `MpsMasterPlanningEvents` 클래스의 `jobCompletedSuccessfully` 메서드입니다.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

다음은 계획 주문에 사용자 정의 `CstmOrderPriority` 필드를 설정하는 확장의 예입니다.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

사용자 지정 논리를 추가할 때 다음 제약 조건 및 모범 사례를 고려하세요.

- `jobCompletedSuccessfully` 메서드가 트랜잭션 범위 외부에서 호출됩니다. 따라서 사용자 지정 논리가 실행되기 시작할 때 계획이 이미 사용자에게 표시됩니다. 사용자 지정이 계획 주문에 대한 추가 필드를 설정하는 경우 해당 필드의 값이 결국에는 일관성을 갖게 될 것임을 사용자에게 알리는 것이 중요합니다(즉, 계획 작업이 완료된 직후 이 값이 최신이 아닐 수 있음).
- 다른 기준 계획 작업은 `jobCompletedSuccessfully` 메서드가 호출될 때 시작할 수 있습니다. 새 작업은 전체 계획 또는 계획의 일부에 영향을 미칠 수 있습니다. 새 작업은 `jobCompletedSuccessfully`에서 처리된 계획 작업의 일부로 생성되거나 업데이트된 동일한 계획 주문 또는 요구 사항 트랜잭션을 업데이트하거나 삭제할 수 있습니다. 이 이벤트가 확장될 때 업데이트 충돌 예외를 처리해야 합니다.
- 이 방법을 확장할 때 단일 트랜잭션 범위를 사용하지 마세요. 단일 기준 계획 실행은 수백만 개의 요구 사항 트랜잭션과 수십만 개의 계획 주문을 생성할 수 있습니다. 이러한 모든 트랜잭션과 계획된 주문이 단일 트랜잭션의 범위에서 처리되면 많은 SQL 잠금이 발생하여 다른 계획 프로세스를 차단합니다. 또한 트랜잭션이 장기간 유지되면 SQL 데이터베이스에 "고스트 레코드"가 생성됩니다. 유령 기록은 시스템의 모든 프로세스에 부정적인 영향을 미칩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]