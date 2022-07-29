---
title: 워크플로 시스템 개요
description: 이 항목에서는 워크플로 시스템에 대해 설명합니다.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "56381"
- intro-internal
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70776ba0a0461998d2c1f62ba05b55cd4307a0f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460953"
---
# <a name="workflow-system-overview"></a>워크플로 시스템 개요

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

이 항목에서는 워크플로 시스템에 대해 설명합니다.

## <a name="what-is-workflow"></a>워크플로란 무엇입니까?

*워크플로* 라는 용어는 시스템과 비즈니스 프로세스의 두 가지 방식으로 정의할 수 있습니다.

### <a name="workflow-is-a-system"></a>워크플로는 시스템입니다

워크플로는 AOS(Application Object Server)에서 실행되는 시스템입니다. 워크플로 시스템은 개별 워크플로 또는 비즈니스 프로세스를 만드는 데 사용할 수 있는 기능을 제공합니다.

### <a name="workflow-is-a-business-process"></a>워크플로는 비즈니스 프로세스입니다

워크플로는 비즈니스 프로세스를 나타냅니다. 작업을 완료하거나 결정을 내리거나 문서를 승인해야 하는 사람을 표시하여 시스템을 통해 문서가 어떻게 흐르거나 이동하는지 정의합니다. 예를 들어 다음 그림은 비용 보고서의 워크플로를 보여줍니다.

![사용자에게 할당된 요소의 워크플로.](./media/workflow_user.gif)

이 워크플로를 더 잘 이해하기 위해 Sam이 USD 7,000에 대한 경비 보고서를 제출했다고 가정합니다. 이 시나리오에서 Ivan은 Sam이 자신에게 보낸 영수증을 검토해야 합니다. 그런 다음 Frank와 Sue는 경비 보고서를 승인해야 합니다. 이제 Sam이 USD 11,000에 대한 경비 보고서를 제출했다고 가정합니다. 이 시나리오에서 Ivan은 영수증을 검토하고 Frank, Sue 및 Ann은 경비 보고서를 승인해야 합니다.

## <a name="benefits-of-using-the-workflow-system"></a>워크플로 시스템 사용의 이점

조직에서 워크플로 시스템을 사용하면 다음과 같은 몇 가지 이점이 있습니다.

- **일관된 프로세스** — 구매 요청 및 경비 보고서와 같은 특정 문서가 처리되는 방식을 정의할 수 있습니다. 워크플로 시스템을 사용하면 문서가 일관되고 효율적인 방식으로 처리되고 승인되도록 할 수 있습니다.
- **프로세스 가시성** — 워크플로 인스턴스의 상태, 기록 및 성능 메트릭을 추적할 수 있습니다. 이는 효율성을 개선하기 위해 워크플로를 변경해야 하는지 여부를 결정하는 데 도움이 됩니다.
- **중앙 집중식 작업 목록** — 사용자는 중앙 집중식 작업 목록을 보고 자신에게 할당된 워크플로 작업 및 승인을 볼 수 있습니다.


## <a name="workflow-content"></a>워크플로 콘텐츠

+ [워크플로 시스템 아키텍처](workflow-system-architecture.md)
+ [워크플로 요소](workflow-elements.md)
+ [워크플로 승인 프로세스의 작업](workflow-actions.md)
+ [워크플로 만들기 개요](create-workflow.md)
+ [워크플로 속성 구성](configure-workflow-properties.md)
+ [워크플로에서 수동 작업 구성](configure-manual-task-workflow.md)
+ [워크플로에서 자동화된 작업 구성](configure-automated-task-workflow.md)
+ [워크플로에서 승인 프로세스 구성](configure-approval-process-workflow.md)
+ [워크플로에서 승인 단계 구성](configure-approval-step-workflow.md)
+ [워크플로에서 수동 결정 구성](configure-manual-decision-workflow.md)
+ [워크플로에서 조건부 결정 구성](configure-conditional-decision-workflow.md)
+ [워크플로에서 병렬 활동 구성](configure-parallel-activity-workflow.md)
+ [워크플로에서 병렬 브랜치 구성](configure-parallel-branch-workflow.md)
+ [광고 항목 워크플로 구성](configure-line-item-workflow.md)
+ [워크플로 FAQ](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]