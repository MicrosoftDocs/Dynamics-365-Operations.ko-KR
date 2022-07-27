---
title: 기준 계획을 위한 계획 최적화로 마이그레이션
description: 이 항목에서는 새 기준 계획 엔진인 계획 최적화 및 기존 엔진에서 마이그레이션에 대한 정보를 제공합니다.
author: ChristianRytt
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8d3edeefca2e2194a8d5484afbfabf2091da4a1c1538d238351a5d389177ccfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446761"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>기준 계획을 위한 계획 최적화로 마이그레이션

[!include [banner](../includes/banner.md)]

기본 제공 기준 계획 엔진은 더 이상 사용되지 않을 예정입니다(더 이상 사용되지 않음). Microsoft Dynamics 365 Supply Chain Management용 계획 최적화 추가 기능으로 대체됩니다. 이 항목에서는 신규 및 기존 배포에 대한 영향에 대한 정보를 제공합니다. 여기에는 필요한 조치에 대한 정보가 포함됩니다.

계획 최적화를 사용하면 Supply Chain Management 및 해당 Azure SQL 데이터베이스 외부에서 기준 계획 계산을 수행할 수 있습니다. 계획 최적화와 관련된 이점에는 기준 계획 실행 중 성능 향상 및 SQL 데이터베이스에 대한 영향 최소화가 포함됩니다. 근무 시간 중에도 신속한 계획 실행이 가능하기 때문에 계획자는 수요 또는 매개 변수 변경에 즉시 대응할 수 있습니다.

최적화 계획에 대한 자세한 내용은 [계획 최적화 개요](planning-optimization/planning-optimization-overview.md)를 참조하세요.

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>기존 기준 계획 엔진의 노후화

Microsoft는 계획 최적화를 위해 기본 제공 계획 엔진을 구식으로 만드는 과정에 있습니다. 이 변경 사항은 모든 클라우드 환경에 영향을 미칩니다. 온-프레미스 설치는 영향을 받지 않습니다. 버전 10.0.16 이상에서 계획된 생산 주문을 생성하지 않고 기본 제공 기준 계획을 실행하면 오류 메시지가 표시됩니다. 그러나 오류 메시지에도 불구하고 기준 계획 실행은 성공적으로 완료됩니다.

기본 제공 계획 엔진의 단종에 대한 자세한 내용은 [Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](../get-started/removed-deprecated-features-scm-updates.md)의 공지를 참조하세요.

## <a name="migration-messages-and-exceptions"></a>마이그레이션, 메시지 및 예외

계획된 생산 주문을 생성하지 않고 기본 제공 기준 계획 엔진을 실행하는 기존 환경의 소유자는 예외 프로세스에 대한 세부 정보를 제공하는 이메일을 받게 됩니다. 파트너와 협력하여 계획 최적화로의 마이그레이션을 평가하고 계획하는 것이 좋습니다.

언급한 바와 같이 계획 생산 주문을 생성하지 않고 기본 제공 기준 계획을 실행하면 버전 10.0.16 이상에서 오류 메시지를 받게 됩니다. 이 오류 메시지에는 마이그레이션에 대한 지침과 예외 요청 지침이 포함되어 있습니다.

### <a name="new-deployments"></a>새로운 배포

계획 최적화는 클라우드의 모든 새 배포에 대한 기본 기준 계획 엔진으로 간주되어야 합니다. 일반적으로 계획 최적화는 기준 계획 중에 계획된 생산 주문을 생성하지 않는 모든 신규 배포에 사용해야 합니다. 새 배포가 계획 최적화에서 현재 지원하지 않는 기능에 의존하는 경우 기본 제공 기준 계획 엔진을 계속 사용할 수 있도록 예외를 요청할 수 있습니다.

### <a name="existing-deployments"></a>기존 배포

기준 계획에 의존하는 기존 클라우드 기반 배포의 소유자는 계획 최적화로 마이그레이션을 계획해야 합니다. 구현이 계획 최적화에서 현재 지원하지 않는 기능에 의존하는 경우 기본 제공 기준 계획 엔진을 계속 사용할 수 있도록 예외를 요청할 수 있습니다.

현재 사용되지 않는 기준 계획 프로세스를 사용하는 환경의 경우 Microsoft는 환경 관리자에게 이메일을 보냅니다. 이 이메일은 마이그레이션 또는 예외 요청에 필요한 작업에 대한 정보를 제공합니다.

## <a name="the-exception-process"></a>예외 프로세스

비즈니스 프로세스가 현재 계획 최적화에서 구현되지 않은 하나 이상의 기능에 크게 의존하기 때문에 기본 제공 기준 계획 엔진을 계속 사용해야 하는 경우 예외를 요청할 수 있습니다. 사용 가능한 기능 목록은 [계획 최적화 적합 분석](planning-optimization/planning-optimization-fit-analysis.md)을 참조하세요.

현재 계획 최적화 마이그레이션에 대한 예외는 기준 계획 프로세스에 생산(즉, 기준 계획에 의해 생성된 계획 생산 주문)이 포함되지 않고 버전 10.0.15 이상의 기본 제공 기준 계획 엔진이 필요한 경우에만 관련이 있습니다.

필요한 기능을 사용할 수 있게 되면 Microsoft는 예외가 만료될 때까지 유예 기간을 제공합니다. 필요한 기능을 사용할 수 있게 되고 유예 기간이 시작되면 환경 관리자에게 알림이 전송됩니다.

다음 순서도는 예외를 요청해야 하는지 여부를 빠르게 찾을 수 있도록 이 항목에서 제공하는 정보를 요약합니다. 예외를 요청해야 하는 경우 [계획 최적화 마이그레이션 및 예외 질문](https://go.microsoft.com/fwlink/?linkid=2144962)을 작성하여 제출하세요.

![예외 흐름도.](media/exception-diagram.png "예외 흐름도")

> [!NOTE]
> 샌드박스 환경만 있는 테넌트가 아니라 현재 프로덕션 환경을 포함하거나 포함할 테넌트에 대해서만 예외를 요청할 수 있습니다. IaaS(Infrastructure as a Service) 샌드박스 환경에서 계획 최적화 예외 오류를 비활성화해야 하는 경우 [샌드박스 환경](#faq-sandbox)에 제공된 SQL 쿼리를 실행합니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>샌드박스 환경

내 샌드박스 환경에서 기본 제공 기준 계획을 사용할 수 있습니까? 예외가 필요합니까?

**답변:** 계획 최적화 예외 오류는 기본 제공 기준 계획 엔진이 성공적으로 실행되는 것을 방해하지 않기 때문에 예외는 일반적으로 샌드박스 환경과 관련이 없습니다. 그러나 오류 메시지가 방해가 되는 경우 데이터베이스에서 다음 쿼리를 실행하여 IaaS(Service Fabric 아님) 샌드박스 환경에서 비활성화할 수 있습니다.

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>온프레미스 환경

내 환경은 온프레미스입니다. 예외가 필요합니까?

**답변:** 아니요. 온프레미스 환경에는 예외가 필요하지 않습니다. 기본 제공 기준 계획을 계속 사용할 수 있습니다. 조치가 필요한 경우 환경 관리자에게 알립니다.

### <a name="production-scenarios"></a>생산 시나리오

우리는 계획된 생산 주문을 사용하지만 버전 10.0.16으로 업그레이드하면 어떻게 될지 걱정됩니다. 조치를 취해야 합니까?

**답변:** 걱정하지 않으셔도 됩니다. 버전 10.0.16에서는 기본 제공 기준 계획을 계속 사용할 수 있습니다. 그러나 계획 최적화로의 마이그레이션을 현재 기능으로 시작할 수 있는지 여부를 평가하는 것이 좋습니다. 또한 새로운 기능에 대한 정보를 계속 받아두는 것이 좋습니다.

### <a name="email-from-microsoft"></a>Microsoft의 이메일

환경 관리자가 Microsoft로부터 이메일을 받았습니다. 이 이메일에는 계획 최적화로 마이그레이션하거나 예외를 요청해야 한다고 명시되어 있습니다. 조치를 취해야 합니까?

**답변:** 예. 이메일의 지침을 따르지 않으면 환경이 영향을 받습니다. 지정된 날짜까지 계획 최적화로 마이그레이션하거나 이메일의 링크를 사용하여 예외를 요청할 수 있습니다. 이 링크는 설문지를 엽니다. 이 설문지를 작성하여 제출하면 이메일을 통해 답변을 받게 됩니다. 이 프로세스는 수동이지만 Microsoft는 질문이 제출된 후 일주일 이내에 응답을 시도합니다.

### <a name="error-messages"></a>오류 메시지

버전 10.0.16 이상을 사용하고 있으며 기준 계획을 실행할 때 다음 오류 메시지가 나타납니다. 기준 계획이 차단됩니까?

> 기본 제공 기준 계획 엔진이 계획 최적화에서 지원하는 시나리오에 사용되었기 때문에 이 오류 메시지가 나타납니다. 현재 기본 제공되는 기준 계획이 더 이상 사용되지 않으므로 지금 계획 최적화로 마이그레이션해야 합니다. 이 기준 계획 실행이 성공적으로 완료되었습니다.
>
> 마이그레이션이 보류 중인 기능에 강한 종속성을 갖는 경우 기본 제공 기준 계획 엔진의 지속적인 사용에 대한 예외를 요청할 수 있습니다.
>
> 시작하려면 다음 설문지를 작성하고 해당되는 경우 계획 최적화로의 마이그레이션에서 예외를 요청하세요.

**답변:** 아니요. 기준 계획은 차단되지 않습니다. 기준 계획 실행이 성공적으로 완료되었으며 결과를 일반적인 방식으로 사용할 수 있습니다. 그러나 향후 기준 계획 실행 중에 이 오류 메시지를 받지 않으려면 즉시 계획 최적화로 마이그레이션하거나 오류 메시지의 링크를 사용하여 예외를 요청해야 합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
