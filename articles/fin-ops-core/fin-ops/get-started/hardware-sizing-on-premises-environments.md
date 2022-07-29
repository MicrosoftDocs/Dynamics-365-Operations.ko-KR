---
title: 온프레미스 환경에 대한 하드웨어 크기 조정 요구 사항
description: 이 토픽은 온-프레미스 환경에 대한 하드웨어 크기 조정 요구 사항을 나열합니다.
author: sericks007
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 443b80e44a90a68610fbb2bb5a5f4b6b7d545fa7ad772edb3672972fa82f8cbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460983"
---
# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>온프레미스 환경에 대한 하드웨어 크기 조정 요구 사항

[!include [banner](../includes/banner.md)]

온-프레미스 환경에 대한 하드웨어 및 인프라 크기 조정 프로세스를 시작하기 전에 [클라우드 배포를 위한 시스템 요구 사항](system-requirements.md) 및 [설정 및 배포 지침](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md)을 숙지하여 기본 인프라에 대한 확실한 이해를 얻으세요.

> [!NOTE]
> 최적의 성능을 위해 시스템 설정 모범 사례에 세심한 주의를 기울이세요.

설명서를 검토한 후 트랜잭션 및 동시 사용자 볼륨을 추정하고 평균 코어 처리량을 기반으로 환경 크기를 조정하는 프로세스를 시작할 수 있습니다.

## <a name="factors-that-affect-sizing"></a>크기 조정에 영향을 미치는 요소

다음 그림에 표시된 모든 요소는 크기 조정에 기여합니다. 더 자세한 정보를 수집할수록 더 정확하게 사이징을 결정할 수 있습니다. 지원 데이터가 없는 하드웨어 크기 조정은 정확하지 않을 수 있습니다. 필요한 데이터에 대한 절대 최소 요구 사항은 시간당 최대 트랜잭션 라인 로드입니다.

[![온-프레미스 환경에 대한 하드웨어 크기 조정.](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

왼쪽에서 오른쪽으로 볼 때 크기를 정확하게 추정하는 데 필요한 첫 번째이자 가장 중요한 요소는 트랜잭션 프로필 또는 트랜잭션 특성입니다. 항상 시간당 최대 거래량을 찾는 것이 중요합니다. 피크 기간이 여러 개인 경우 이러한 기간을 정확하게 정의해야 합니다.

인프라에 영향을 미치는 로드를 이해하면서 다음 요소에 대해서도 더 자세히 이해해야 합니다.

- **트랜잭션** – 일반적으로 거래는 하루/주 내내 특정 피크가 있습니다. 이것은 주로 거래 유형에 따라 다릅니다. 시간 및 비용 항목은 일반적으로 일주일에 한 번 피크를 표시하는 반면 매도 주문 항목은 종종 통합을 통해 대량으로 제공되거나 낮 동안 조금씩 유입됩니다.
- **동시 사용자 수** – 동시 사용자 수는 두 번째로 중요한 크기 조정 요소입니다. 동시 사용자 수를 기준으로 크기 추정치를 안정적으로 얻을 수 없으므로 사용할 수 있는 데이터가 이것뿐인 경우 대략적인 수를 추정한 다음 데이터가 더 있을 때 다시 방문하세요. 정확한 동시 사용자 정의는 다음을 의미합니다.

    - 기명 사용자는 동시 사용자가 아닙니다.
    - 동시 사용자는 항상 명명된 사용자의 하위 집합입니다. 
    - 피크 워크로드는 크기 조정을 위한 최대 동시성을 정의합니다.

    동시 사용자의 기준은 사용자가 다음 기준을 모두 충족하는 것입니다.

    - 로그인.
    - 계산 시 작업 트랜잭션/조회.
    - 유휴 세션이 아닙니다.

- **데이터 구성** – 이것은 주로 시스템을 설정하고 구성하는 방법에 관한 것입니다. 예를 들어, 법인 수, 품목 수, BOM 수준 수, 보안 설정이 얼마나 복잡한지 등입니다. 이러한 각 요소는 성능에 약간의 영향을 미칠 수 있으므로 인프라와 관련하여 현명한 선택을 사용하여 이러한 요소를 상쇄할 수 있습니다.
- **확장** – 사용자 정의는 단순하거나 복잡할 수 있습니다. 사용자 정의의 수와 복잡성 및 사용의 특성은 필요한 인프라의 크기에 다양한 영향을 미칩니다. 복잡한 사용자 지정의 경우 성능 평가를 수행하여 효율성에 대해 테스트될 뿐만 아니라 인프라 요구 사항을 이해하는 데 도움이 되는지 확인하는 것이 좋습니다. 확장이 성능 및 확장성에 대한 모범 사례에 따라 코딩되지 않은 경우 이는 훨씬 더 중요합니다.
- **보고 및 분석** – 이러한 요인에는 일반적으로 시스템의 다양한 데이터베이스에 대한 과도한 쿼리 실행이 포함됩니다. 값비싼 보고서가 실행되는 빈도를 이해하고 줄이면 보고서의 영향을 이해하는 데 도움이 됩니다.
- **타사 솔루션** – ISV와 같은 이러한 솔루션에는 확장과 동일한 의미와 권장 사항이 있습니다.

## <a name="sizing-your-environment"></a>환경 크기 조정

사이징 요구 사항을 이해하려면 처리해야 하는 최대 트랜잭션 볼륨을 알아야 합니다. Management Reporter 또는 SSRS와 같은 대부분의 보조 시스템은 덜 중요합니다. 결과적으로 이 문서는 주로 AOS와 SQL Server에 초점을 맞춥니다.

> [!NOTE]
> 일반적으로 컴퓨팅 계층은 확장되며 N+1 방식으로 설정되어야 합니다. 즉, 3개의 AOS를 추정하는 경우 4번째 AOS를 추가해야 합니다. 데이터베이스 계층은 Always On 고가용성 설정에서 설정해야 합니다.

## <a name="sql-server-oltp"></a>SQL Server(OLTP)

### <a name="sizing"></a>사이징

- DB 서버에서 코어당 시간당 3K ~ 15K 트랜잭션 라인.
- 기본 SQL Server에 대한 일반적인 AOS 대 SQL 코어 비율 3:1. 선택한 고가용성 구성에 따라 추가 코어가 필요합니다.

    - 데이터베이스를 많이 사용하는 작업을 처리하면 이를 2:1로 회귀할 수 있습니다.

- 변형에 영향을 미치는 요인은 다음과 같습니다.

    - 사용 중인 매개변수 설정.
    - 확장 수준.
    - 데이터베이스 로그 및 경고와 같은 추가 기능의 사용. 익스트림 데이터베이스 로깅은 코어당 시간당 처리량을 3K 라인 이하로 더욱 감소시킵니다.
    - 데이터 구성의 복잡성 – 간단한 계정 코드집과 세부적인 계정 코드집은 처리량에 영향을 미칩니다(예:).
    - 거래 특성화.
    - 코어당 2GB ~ 16GB 메모리.
    - Management Reporter 및 SSRS 데이터베이스와 같은 DB 서버의 보조 데이터베이스.
    - 임시 DB = DB 크기의 15%(실제 프로세서 수만큼 파일 포함).
    - 총 동시 트랜잭션 볼륨/사용량을 기반으로 한 SAN 크기 및 처리량.

### <a name="high-availability"></a>고가용성

클러스터 또는 미러링 설정에서 항상 SQL Server를 활용하는 것이 좋습니다. 두 번째 SQL 노드에는 기본 노드와 동일한 수의 코어가 있어야 합니다.

### <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services(AD FS)

AD FS 크기 조정은 [AD FS 서버 용량 설명서](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity)를 참조하세요.

[사이징 스프레드시트](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx)는 배포의 인스턴스 수를 계획하는 데 사용할 수 있습니다.

## <a name="aos-online-and-batch"></a>AOS(온라인 및 배치)

### <a name="sizing"></a>사이징

- 거래량/사용량별 크기 조정

    - 코어당 2K ~ 6K 라인
    - 인스턴스당 16GB
    - 표준 상자 - 4~24개 코어
    - 코어당 10~15명의 엔터프라이즈 사용자
    - 코어당 15~25명의 활동 사용자
    - 코어당 25~50명의 팀원

- 배치

    - 코어당 1~4개의 배치 스레드
    - 배치 창 특성에 따른 크기

- AOS, Data Management 및 Batch는 Service Fabric에서 동일한 역할에 있습니다. 이 세 가지 작업 부하를 결합하여 크기를 조정해야 하며 Microsoft Dynamics AX 2012에서와 같이 분리해서는 안 됩니다.
- SQL Server에 대한 동일한 가변성 요인이 여기에 적용됩니다.

### <a name="high-availability"></a>고가용성

- 예상보다 사용 가능한 AOS가 최소 1~2개 더 있는지 확인합니다.
- 최소 3~4개의 가상 호스트를 사용할 수 있는지 확인합니다.

## <a name="management-reporter"></a>Management Reporter

대부분의 경우 광범위하게 사용되지 않는 한 두 개의 노드를 사용하는 권장 최소 요구 사항이 잘 작동합니다. 사용량이 많은 경우에만 두 개 이상의 노드가 필요합니다. 필요에 따라 확장합니다.

## <a name="sql-server-reporting-services"></a>SQL Server 보고 서비스

일반 공급 릴리스의 경우 하나의 SSRS 노드만 배포할 수 있습니다. 테스트하는 동안 SSRS 노드를 모니터링하고 필요에 따라 SSRS에 사용할 수 있는 코어 수를 늘립니다. SSRS VM과 다른 가상 호스트에서 사용할 수 있는 미리 구성된 보조 노드가 있는지 확인합니다. 이는 SSRS 또는 가상 호스트를 호스팅하는 가상 머신에 문제가 있는 경우 중요합니다. 이 경우 교체해야 합니다.

버전 10.0.17부터 추가 SSRS 노드를 구성하여 고가용성을 달성할 수 있습니다. 자세한 내용은 [SSRS(SQL Server Reporting Services) 노드에 대한 고가용성 구성](../../dev-itpro/deployment/onprem-ssrsha.md)을 참조하세요.

## <a name="environment-orchestrator"></a>환경 오케스트레이터

Orchestrator 서비스는 배포 및 LCS와의 관련 통신을 관리하는 서비스입니다. 이 서비스는 기본 Service Fabric 서비스로 배포되며 최소 3개의 VM이 필요합니다. 이 서비스는 Service Fabric 오케스트레이션 서비스와 함께 배치됩니다. 이것은 클러스터의 최대 로드에 맞게 크기를 조정해야 합니다. 자세한 내용은 [Service Fabric 독립 실행형 클러스터 배포 계획 및 준비](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation)를 참조하세요.

## <a name="virtualization-and-oversubscription"></a>가상화 및 초과 구독

AOS와 같은 미션 크리티컬 서비스는 코어, 메모리 및 디스크와 같은 전용 리소스가 있는 가상 호스트에서 호스팅되어야 합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
