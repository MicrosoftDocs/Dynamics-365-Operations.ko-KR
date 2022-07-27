---
title: 계획 최적화 시작하기
description: 이 토픽에서는 계획 최적화 기능 사용을 시작하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 8e6328902cec840b98b401fe8dd46c2a6f18cb54
ms.sourcegitcommit: 88f8a0369ce66b82314db9639491b695e18a7e5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449554"
---
# <a name="get-started-with-planning-optimization"></a>계획 최적화 시작하기

[!include [banner](../../includes/banner.md)]

[이전에 발표](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios)한 바와 같이 계획 최적화는 기존 기본 제공 기준 계획 엔진을 대체할 예정입니다.

현재 기본 제공 기준 계획 엔진을 사용하는 경우 지금 계획 최적화로의 마이그레이션 계획을 시작해야 합니다. 지원 중단이 시행되면 작업에 영향을 미칠 수 있으므로 마이그레이션 프로세스를 즉시 시작하는 것이 중요합니다. 지원 중단이 시행될 때 막바지 문제를 방지하려면 2020년 12월 1일 이전에 마이그레이션을 완료하는 것이 좋습니다. 

계획 최적화 기능은 현재 Supply Chain Management에 내장된 계획 엔진에서 사용할 수 있는 모든 기능을 지원하지 않습니다. 따라서 현재 계획 최적화에서 사용할 수 있는 기능 집합이 요구 사항을 충족하는지 평가하는 것이 중요합니다. 계획 최적화 기능은 현재 Dynamics Lifecycle Services(LCS)에서 기본적으로 설정되어 있지 않으므로 기능이 설정되기 전에 평가를 수행할 수 있습니다.

> [!NOTE]
> 기준 계획 프로세스에 생산이 포함되지 않고(기준 계획 생성 계획 생산 주문) 버전 10.0.15 이상의 기본 제공 기준 계획 엔진이 필요한 경우 계획 최적화로의 마이그레이션 예외를 요청해야 합니다. 버전 10.0.16부터 계획된 생산 주문을 생성하지 않고 기본 제공 기준 계획을 실행할 때 환경에 오류가 표시됩니다. 계획 최적화는 기준 계획 중에 계획된 생산 주문을 생성하지 않는 모든 신규 배포에 사용해야 합니다. 계획된 생산 주문을 생성하지 않고 기본 제공 기준 계획 엔진을 실행하는 기존 환경의 소유자는 예외 프로세스에 대한 세부 정보가 포함된 메일을 받게 됩니다. 파트너와 협력하여 계획 최적화로의 마이그레이션을 평가하고 계획하는 것이 좋습니다.

계획 최적화를 켜기 전에 계획 최적화 적합성 분석 결과를 평가하는 것이 좋습니다. 자세한 내용은 [계획 최적화 적합 분석](planning-optimization-fit-analysis.md)을 참조하세요.

## <a name="availability"></a>가용성

계획 최적화는 현재 미국, 캐나다, 유럽, 영국, 호주, 아시아 태평양, 일본 및 인도와 같은 Azure 지역에서 사용할 수 있습니다. 다른 지역에서 추가 기능을 설치하려고 하면 LCS에서 이 지역이 지원되지 않는다는 메시지를 표시합니다. Azure 지역 및 관련 지역에 대한 자세한 내용은 [Azure 지역](https://azure.microsoft.com/global-infrastructure/geographies/#geographies)을 참조하세요.

계획 최적화는 Dynamics 365 Supply Chain Management의 온-프레미스 배포를 지원하지 않습니다.

## <a name="licensing"></a>라이선싱

현재 라이선스를 사용하여 기준 계획을 실행할 수 있는 경우 계획 최적화 사용을 시작하기 위해 추가 라이선스를 구입할 필요가 없습니다.

## <a name="install-and-enable-planning-optimization"></a>계획 최적화 설치 및 활성화

계획 최적화를 사용하려면 시스템에 모든 필수 구성 요소가 있는지 확인한 다음 라이선스 키를 활성화하고 Dynamics 365 Supply Chain Management용 계획 최적화 추가 기능을 설치해야 합니다.

### <a name="prerequisites"></a>전제 조건

계획 최적화 추가 기능을 설치하기 전에 다음 전제 조건이 충족되어야 합니다.

- Dynamics 365 Supply Chain Management 버전 10.0.7 이상이 포함된 LCS 지원 고가용성 환경, 계층 2 이상(OneBox 환경 아님)에서 Supply Chain Management를 실행해야 합니다. OneBox 환경에서 추가 기능을 설치하려고 하면 설치가 완료되지 않으며 설치를 취소해야 합니다.

- Power Platform 통합을 위해 시스템을 설정해야 합니다. 자세한 내용은 [금융 및 운영 앱과 Microsoft Power Platform 통합](../../../fin-ops-core/dev-itpro/power-platform/overview.md)을 참조하세요.

### <a name="enable-the-planning-optimization-license"></a>계획 최적화 라이선스 활성화

계획 최적화를 사용하려면 구성 키를 활성화해야 합니다. 이렇게 하려면:

1. [유지 관리 모드](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)에 설명된 대로 시스템을 유지 관리 모드로 설정합니다.
1. **시스템 관리 \> 설정 \> 라이선스 구성** 으로 이동합니다.
1. **구성 키** 탭에서 **계획 최적화** 확인란을 선택합니다.
1. [유지 관리 모드](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)에 설명된 대로 유지 관리 모드를 끕니다.

### <a name="install-the-planning-optimization-add-in"></a>계획 최적화 추가 기능 설치

LCS 프로젝트에서 추가 기능을 설치한 다음 Supply Chain Management 사용자 인터페이스에서 계획 최적화 기능을 켜야 합니다.

계획 최적화 추가 기능을 설치하려면:

1. LCS에 로그인하여 원하는 환경을 엽니다.
1. **전체 세부 정보** 로 이동합니다.
1. **환경 추가 기능** 빠른 탭까지 아래로 스크롤합니다.
1. **새 추가 기능 설치** 를 선택합니다.
1. **계획 최적화** 를 선택합니다.
1. 설치 가이드를 따르고 이용 약관에 동의합니다.
1. **설치** 를 선택합니다.
1. **환경 추가 기능** 빠른 탭에서 계획 최적화가 설치 중임을 확인해야 합니다.
1. 몇 분 후 **설치 중** 이 **설치됨** 으로 변경되어야 합니다(페이지를 새로 고쳐야 할 수 있음). 설치되면 Dynamics 365 Supply Chain Management에서 계획 최적화를 활성화할 준비가 된 것입니다.

계획 최적화 추가 기능을 설치하는 주요 목적은 서비스와 환경을 연결하는 것입니다. 따라서 환경 간에 이동된 코드에 관계없이 계획 최적화를 사용할 각 환경에 추가 기능을 별도로 설치해야 합니다.

## <a name="integrate-planning-optimization-with-your-system"></a>시스템과 계획 최적화 통합

계획 최적화 추가 기능을 기준 계획에 사용해야 하는지 여부를 구성하려면 **기준 계획** \> **설정** \> **계획 최적화 매개 변수** 로 이동합니다.

### <a name="connection-status"></a>연결 상태

연결 상태는 Supply Chain Management와 Planning Optimization 서비스 간의 현재 연결 상태를 나타냅니다. 다음 테이블은 가능한 값을 보여줍니다.

| 연결 상태 | 설명 | 계획 최적화를 사용할 수 있나요? |
|---|---|---|
| 연결됨 | 계획 최적화 서비스와 Supply Chain Management 간에 연결이 설정되었습니다. | 예 |
| 연결 사용 | 계획 최적화 서비스에 대한 연결을 켜기 위한 요청이 현재 진행 중입니다. | 아니요 |
| 연결 끊김 | 계획 최적화 서비스에 연결되어 있지 않습니다. 이 토픽의 앞부분에서 설명한 대로 LCS에서 연결을 켤 수 있습니다. | 아니요 |
| 연결 사용 중지 | 계획 최적화 서비스에 대한 연결을 끄기 위한 요청이 현재 진행 중입니다. | 아니요 |
| 상태 가져오기 | 시스템이 계획 최적화 서비스의 상태 정보를 기다리고 있습니다. | 아니요 |

### <a name="the-use-planning-optimization-option"></a>계획 최적화 사용 옵션

**계획 최적화 사용** 옵션의 설정은 기준 계획에 사용되는 계획 엔진을 결정합니다.

- **예** – 계획 최적화는 기준 계획에 사용됩니다.
- **아니요** – 기본 제공 Supply Chain Management 계획 엔진이 기준 계획에 사용됩니다.

이 설정은 모든 법인(회사)에 적용됩니다. 일부 법인에서는 계획 최적화를 사용하고 다른 법인에서는 기본 제공 기준 계획을 사용할 수 없습니다.

> [!NOTE]
> 기본 제공 Supply Chain Management 계획 엔진에 대해 생성된 기존 계획 배치 작업이 **계획 최적화 사용** 옵션이 **예** 로 설정되어 있는 동안 트리거되는 경우 해당 작업은 실패합니다.

### <a name="integration-with-the-setup"></a>설정과의 통합

계획 최적화가 켜져 있으면 계획 최적화 추가 기능을 사용하여 기준 계획이 수행됩니다. 이 경우 기준 계획 결과 및 기능이 영향을 받습니다.

## <a name="additional-resources"></a>추가 리소스

[프리뷰 이용약관](https://go.microsoft.com/fwlink/?linkid=2015274)

[계획 최적화 개요](planning-optimization-overview.md)

[계획 최적화 적합 분석](planning-optimization-fit-analysis.md)

[계획 기록 및 계획 로그 보기](plan-history-logs.md)

[계획에 필터 적용](plan-filters.md)

[계획 작업 취소](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
