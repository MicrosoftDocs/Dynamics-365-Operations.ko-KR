---
title: 분산 하이브리드 토폴로지의 확장 단위
description: 이 주제에서는 제조 및 창고 관리 워크로드를 위한 클라우드 및 에지 스케일 장치에 대한 정보를 제공합니다.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30f455f37b5161878cf9c864b92966aa74da051f
ms.sourcegitcommit: b52ff5dfd32580121f74a5f262e5c2495e39d578
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8450070"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>분산 하이브리드 토폴로지의 확장 단위

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Microsoft Dynamics 365 Supply Chain Management용 배율 단위 용량은 서비스 사용에 적용되는 조건에 따라 제공됩니다. 자세한 내용은 [Microsoft Dynamics 법률 정보](https://go.microsoft.com/fwlink/?LinkID=290927)를 참조하세요.
>
> 클라우드 및 에지 규모 단위를 활성화하면 클라우드 및 에지 규모 단위의 구성 및 처리와 관련된 일부 데이터가 미국에 있는 데이터 센터에 저장될 수 있다는 점을 이해했음을 확인하라는 메시지가 표시됩니다. 클라우드 및 에지 스케일 단위의 데이터 처리에 대해 자세히 알아보려면 이 토픽 후반부의 [스케일 단위 관리 중 데이터 처리](#data-processing-management)를 참조하세요.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>분산 하이브리드 토폴로지의 핵심 가치 제안

제조 및 유통과 협력하는 회사는 중단 없이 대규모로 주요 비즈니스 프로세스를 연중무휴로 실행할 수 있어야 합니다. 분산 하이브리드 토폴로지를 통해 기업은 간헐적인 네트워크 연결 또는 대기 시간 문제에 직면하더라도 중단 없이 핵심 미션 크리티컬 제조 및 창고 프로세스를 실행할 수 있습니다.

분산 하이브리드 토폴로지는 *스케일 단위* 의 개념을 도입하며, 다양한 환경 간에 작업 현장 및 창고 실행 워크로드를 분산할 수 있습니다. 이 기능은 성능을 개선하고 서비스 중단을 방지하며 가동 시간을 최대화하는 데 도움이 될 수 있습니다. 배율 단위는 Supply Chain Management 구독에 대해 다음 추가 기능을 통해 제공됩니다.

- Dynamics 365 Supply Chain Management용 Cloud 배율 단위 추가 기능
- Dynamics 365 Supply Chain Management용 Edge 배율 단위 추가 기능

워크로드 기능은 점진적 개선을 통해 지속적으로 릴리스됩니다.

## <a name="scale-units-and-dedicated-workloads"></a>확장 단위 및 전용 워크로드

스케일 유닛은 전용 처리 용량을 추가하여 중앙 Supply Chain Management 허브 환경을 확장합니다. 스케일 단위는 클라우드에서 실행할 수 있습니다. 또는 로컬 시설의 [에지](cloud-edge-edge-scale-units-lbd.md), 온-프레미스에서 실행할 수 있습니다.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="배율 단위가 있는 Dynamics 365.":::

배율 단위는 할당된 워크로드에 대한 탄력성, 안정성 및 규모를 제공합니다. 에지 스케일 장치는 클라우드 허브 환경에서 일시적으로 연결이 끊길 수 있으며 작업자는 에지에 할당된 워크로드에서 계속 작업합니다.

*워크로드* 는 팩토링 및 배율 단위에 위임할 수 있는 정의된 비즈니스 기능 집합입니다. 창고 관리를 위한 워크로드는 해제되었지만 제조 실행을 위한 워크로드는 아직 프리뷰입니다.

[Scale Unit Manager 포털](https://sum.dynamics.com)을 사용하여 선택한 워크로드에 대해 허브 환경 및 클라우드 규모 단위를 구성할 수 있습니다. 배율 단위당 여러 워크로드를 할당할 수도 있습니다. 현재 릴리스의 클라우드 규모 단위에 대한 전제 조건 및 제한 사항에 대한 정보는 이 토픽 후반부의 [클라우드 규모 단위에 대한 전제 조건 및 제한 사항](#cloud-scale-unit-prerequisites)을 참조하세요.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>스케일 유닛의 전용 창고 관리 워크로드 기능

창고 관리 워크로드를 사용하면 격리된 유지 관리 기간을 사용하여 탄력적인 환경에서 창고 운영을 확장하고 실행할 수 있습니다. 창고 관리 워크로드는 대부분의 엔터프라이즈 허브 창고 관리 프로세스를 지원합니다. 자세한 내용은 [클라우드 및 에지 스케일 유닛을 위한 창고 관리 워크로드](cloud-edge-workload-warehousing.md)를 참조하세요.

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>스케일 유닛의 전용 제조 실행 워크로드 기능

제조 워크로드는 다음 기능을 제공합니다.

- 기계 운영자와 작업 현장 감독자는 운영 생산 계획에 액세스할 수 있습니다.
- 기계 운영자는 개별 및 공정 제조 작업을 실행하여 계획을 최신 상태로 유지할 수 있습니다.
- 작업 현장 감독자는 운영 계획을 조정할 수 있습니다.
- 근로자는 정확한 근로자 급여 계산을 위해 에지에서 출퇴근 시간과 출퇴근 시간에 액세스할 수 있습니다.

자세한 내용은 [클라우드 및 에지 스케일 유닛을 위한 제조 실행 워크로드](cloud-edge-workload-manufacturing.md)를 참조하세요.

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Supply Chain Management에 대해 분산 하이브리드 토폴로지를 활성화하기 전 고려 사항

분산 하이브리드 토폴로지를 활성화하면 Supply Chain Management 클라우드 환경이 허브로 작동하도록 전환됩니다. 클라우드 또는 에지에서 배율 단위로 구성된 추가 환경을 연결할 수도 있습니다.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>클라우드 규모 단위에 대한 전제 조건 및 제한 사항

배율 단위에 대한 현재 릴리스에서는 일부 기능을 아직 사용할 수 없지만 시간이 지남에 따라 증분 릴리스에 추가될 수 있습니다.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Supply Chain Management의 라이선스 고객이어야 합니다.

분산 토폴로지에 온보딩하려면 Supply Chain Management 라이선스가 있어야 합니다. 기존 클라우드 환경이 하이브리드 토폴로지의 허브가 됩니다. 샌드박스 환경과 프로덕션 환경을 모두 허브 환경으로 선언할 수 있으며 획득한 추가 기능에 따라 확장 단위를 추가할 수 있습니다.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>기존 프로젝트는 LCS의 글로벌 상용 버전을 통해 관리되어야 합니다.

기존 Microsoft Dynamics 수명 주기 서비스(LCS) 프로젝트는 다음 버전 요구 사항을 충족해야 합니다.

- 프로젝트는 [lcs.dynamics.com](https://lcs.dynamics.com)에서 LCS의 글로벌 상용 버전을 통해 관리되어야 합니다.
- LCS의 로컬 버전(예: [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) 및 [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com))은 지원되지 않습니다.
- 정부 클라우드 버전의 LCS는 지원되지 않습니다.
- LCS의 Mooncake 버전은 지원되지 않습니다.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>현재 프로덕션 환경은 LCS의 셀프 서비스 유형이어야 합니다.

현재 프로덕션 환경은 LCS의 **셀프 서비스** 유형으로 태그되어야 합니다. 이 유형은 LCS 프로젝트의 테넌트가 이미 변환되어 Azure Service Fabric 호스팅 모델을 지원함을 나타냅니다.

> [!IMPORTANT]
> IaaS(서비스 제공 인프라)로 실행되는 환경 유형은 지원되지 않습니다. 이러한 환경에는 일반적으로 LCS의 **Microsoft 관리** 로 태그가 지정됩니다. 이러한 유형의 환경이 있는 경우 Microsoft 담당자와 협력하여 **셀프 서비스** 유형으로의 마이그레이션 일정을 알아보세요.

Microsoft는 Supply Chain Management의 모든 클라우드 환경을 IaaS 모델에서 Service Fabric에서 호스팅되는 토폴로지로 전환하는 과정에 있습니다. 이러한 이동은 더 나은 확장성을 가져오고 서비스 관리를 더 쉽게 만드는 데 도움이 됩니다. 따라서 배포 및 유지 관리 작업이 더 빠릅니다. 마찬가지로 서비스 구성 요소는 마이크로 서비스 개념으로 마이그레이션되고 있으며 서비스 호스팅 모델은 가상 머신(VM) 모델에서 경량 컨테이너화된 아키텍처로 [전환](/virtualization/windowscontainers/about/containers-vs-vm)됩니다.

궁극적으로 동일한 Service Fabric 기반의 컨테이너화된 서비스 인프라는 인스턴스가 클라우드의 허브인지, 클라우드 또는 에지의 확장 단위인지에 관계없이 서비스의 클라우드 및 에지 인스턴스를 모두 지원합니다.

배율 단위를 지원하는 하이브리드 토폴로지에 온보딩하려면 먼저 프로젝트 테넌트를 Service Fabric 호스팅 모델로 전환해야 합니다. 또한 허브 역할을 하는 모든 환경을 변환해야 합니다.

> [!TIP]
> LCS 프로젝트 테넌트의 상태를 문의하려면 [LCS](https://lcs.dynamics.com/)에서 환경 유형을 조회하거나 파트너 또는 Microsoft 담당자에게 문의하세요.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>로컬 비즈니스 데이터(온-프레미스) 환경은 확장 단위의 허브로 지원되지 않습니다.

온-프레미스 환경은 배율 단위의 허브로 작동할 수 없습니다. 허브 환경은 항상 클라우드 호스팅되어야 합니다.

#### <a name="scale-unit-management-capabilities-are-limited"></a>스케일 유닛 관리 기능이 제한됨

워크로드 이동에 도움이 될 수 있는 관리 기능은 제한적입니다. 일부 관리 작업은 셀프 서비스 방식으로 지원되지 않으며 파트너 또는 Microsoft 담당자를 통해 지원을 요청해야 할 수 있습니다. 예를 들어 규모 단위 간의 일부 워크로드 이동과 재해 시나리오의 임시 애드혹 이동이 있습니다.

#### <a name="metrics-and-measurements-arent-yet-available"></a>메트릭 및 측정은 아직 사용할 수 없습니다.

스케일 단위에 가장 적합한 애플리케이션을 선택하는 데 도움이 될 수 있는 메트릭 및 측정값은 아직 사용할 수 없습니다. Microsoft 담당자 또는 구현 파트너와 협력하여 가장 유익한 응용 프로그램을 선택합니다.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>스케일 단위 관리 중 데이터 처리

Dynamics 365 환경에서 클라우드 및 에지 확장 장치에 대한 분산 하이브리드 토폴로지를 지원하도록 설정하면 일부 관리 서비스는 LCS와 마찬가지로 미국에서만 호스팅됩니다. 이 동작은 [Scale Unit Manager 포털](https://sum.dynamics.com)에서 사용하는 일부 관리 및 구성 정보의 전송 및 저장에 영향을 줍니다. 여기 예시들이 있습니다 :

- 테넌트 이름 및 ID
- LCS 프로젝트 ID
- 로그인에 사용되는 관리자 및 프로젝트 소유자 이메일 주소
- 허브 및 배율 단위에 대한 환경 ID
- 토폴로지가 지리적 맵에 표시될 수 있도록 법인 및 시설의 이름 및 물리적 주소를 포함한 워크로드 구성
- 지도 분석 페이지에 표시되는 수집된 지표(예: 대기 시간 및 처리량)는 축척 단위의 가장 유익한 사용을 선택하는 데 도움이 됩니다

미국 데이터 센터로 전송 및 저장되는 데이터는 Microsoft 데이터 보존 정책에 따라 삭제됩니다. 귀하의 개인 정보는 Microsoft에 중요합니다. 자세히 알아보려면 [개인정보처리방침](https://go.microsoft.com/fwlink/?LinkId=521839)을 읽어보세요.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Supply Chain Management용 분산 하이브리드 토폴로지에 온보딩

### <a name="try-out-the-distributed-hybrid-topology"></a>분산 하이브리드 토폴로지 사용해 보기

분산 하이브리드 토폴로지에 온보딩하는 프로세스에는 두 단계가 있습니다. 첫 번째 단계에서 솔루션을 [사용해 보고](cloud-edge-try-out.md) 확장 단위를 포함하는 분산 토폴로지에서 작동하는지 확인하기 위해 사용자 정의를 검증하해야 합니다. (기존 개발 환경을 사용하여 검증을 수행할 수 있습니다.) 그런 다음 프로덕션 환경을 확보하는 두 번째 단계로 계속 진행할 수 있습니다.

## <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>LCS 프로젝트 테넌트 및 자세한 온보딩 프로세스 선택

스케일 단위는 여러 SKU(재고 보관 단위) 및 가격 옵션으로 제공됩니다. 따라서 계획된 월간 거래량 및 성능 요구 사항에 가장 적합한 옵션을 선택할 수 있습니다.

> [!TIP]
> 요구 사항에 가장 적합한 크기 조정을 식별하려면 구현 파트너 및 Microsoft와 협력하여 필요한 월별 트랜잭션 크기를 파악합니다.

엔트리 레벨 SKU는 *기본* 이라고 하며 더 성능이 좋은 SKU는 *표준* 이라고 합니다. 각 SKU에는 특정 수의 월별 트랜잭션이 미리 로드되어 있습니다. 그러나 각 SKU에 대한 초과 추가 기능을 추가하여 월간 거래 예산을 늘릴 수 있습니다.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="클라우드 배율 단위의 추가 기능.":::

> [!NOTE]
> 배율 단위 추가 기능은 제한된 수의 사용자와 연결되지 않습니다. 기존 구독의 모든 사용자가 사용할 수 있습니다(관리자가 필요한 사용자 역할을 할당한 경우).

각 확장 장치 추가 기능을 구입하면 월별 트랜잭션 볼륨을 제공할 뿐만 아니라 LCS에서 특정 수의 환경 슬롯을 사용할 수 있습니다. 각 Cloud Scale Unit Add-in에 대해 하나의 새 프로덕션 슬롯과 하나의 새 샌드박스 슬롯을 사용할 수 있습니다. 온보딩 프로세스 중에 이러한 슬롯이 있는 새 LCS 프로젝트가 추가됩니다. 슬롯에 대한 사용 권한은 클라우드 허브가 있는 스케일 단위로 슬롯을 사용해야 하도록 바인딩됩니다.

초과 추가 기능은 새 환경 슬롯에 대한 권한을 부여하지 않습니다.

더 많은 샌드박스 환경을 확보하려면 일반 샌드박스 슬롯을 추가로 구매할 수 있습니다. 그런 다음 Microsoft는 이러한 슬롯을 하이브리드 토폴로지에 대한 샌드박스 배율 단위로 활성화하는 데 도움을 줄 수 있습니다.


Supply Chain Management를 위해 분산 하이브리드 토폴로지에 온보딩하는 방법을 계획한 후 [Scale Unit Manager 포털](https://aka.ms/SCMSUM)을 사용하여 온보딩 프로세스를 시작합니다. 포털에서 **Dynamics 365 테넌트** 탭을 선택합니다. 이 탭에는 귀하의 계정이 속한 테넌트 목록과 귀하가 LCS 프로젝트의 소유자 또는 환경 관리자인 위치가 표시됩니다.

찾고 있는 세입자가 목록에 없으면 [LCS](https://lcs.dynamics.com/v2)로 이동하고, 환경 관리자 또는 해당 테넌트에 대한 LCS 프로젝트의 프로젝트 소유자인지 확인합니다. 선택한 테넌트의 Azure Active Directory(Azure AD) 계정만 등록 환경을 완료할 수 있는 권한이 있습니다.

> [!NOTE]
> LCS에 변경 사항을 적용한 후 테넌트 목록에 변경 사항을 반영하는 데 최대 30분이 소요될 수 있습니다.

각 테넌트에 대해 목록에 온보딩 상태가 표시됩니다.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Dynamics 365 테넌트 탭의 테넌트 목록입니다.":::

**시작하려면 여기를 클릭** 을 선택하여 LCS 테넌트에 대한 온보딩을 요청합니다. 약관에 동의해야 합니다. 또한 Microsoft가 온보딩 프로세스와 관련된 커뮤니케이션을 보낼 수 있는 비즈니스 이메일 주소를 제공해야 합니다.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="테넌트에 대한 등록 제출.":::

Microsoft는 귀하의 요청을 검토하고 귀하가 등록 양식에 제공한 주소로 이메일을 보내 다음 단계에 대해 알려드릴 것입니다. Microsoft는 귀하의 비즈니스 시나리오에 대한 하이브리드 토폴로지의 확장 단위를 활성화하기 위해 귀하와 긴밀히 협력할 것입니다.

온보딩이 완료되면 포트를 사용하여 배율 단위 및 워크로드를 구성할 수 있습니다.

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Scale Unit Manager 포털을 사용하여 Scale Unit 및 워크로드 관리

[Scale Unit Manager 포털](https://aka.ms/SCMSUM)로 이동하고 테넌트 계정을 사용하여 로그인합니다. **배율 단위 구성** 페이지에서 아직 나열되지 않은 경우 허브 환경을 추가할 수 있습니다. 그런 다음 배율 단위 및 워크로드로 구성할 허브를 선택할 수 있습니다.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="배율 단위 관리자 포털, 배율 단위 구성 페이지.":::

구독에서 사용할 수 있는 하나 이상의 배율 단위를 추가하려면 **배율 단위 추가** 을 선택합니다.

**정의된 워크로드** 탭에서 **워크로드 생성** 버튼을 사용하여 창고 관리 워크로드를 스케일 단위 중 하나에 추가합니다. 각 워크로드에 대해 워크로드가 소유할 프로세스의 컨텍스트를 지정해야 합니다. 창고 관리 워크로드의 경우 컨텍스트는 특정 사이트 및 법인의 특정 창고입니다.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="워크로드 정의 대화 상자.":::

#### <a name="manage-workloads"></a><a name="manage-workloads"></a>워크로드 관리

하나 이상의 워크로드가 활성화되면 **워크로드 관리** 옵션을 사용하여 다음 표에 나열된 것과 같은 프로세스를 시작하고 관리합니다.

| 프로세스 | 설명 |
|---|---|
| 저울 단위 통신 일시 중지 | 허브와 배율 단위 간의 파이프라인 메시지를 일시 중지합니다. 이 프로세스는 통신을 중지하고 허브와 스케일 장치 간의 데이터 파이프라인을 비웁니다. 허브 또는 저울 장치에서 Supply Chain Management 서비스 작업을 실행하기 전에 이 프로세스를 실행해야 하지만 다른 상황에서도 이를 사용할 수 있습니다. |
| 배율 단위 통신 재개 | 허브와 배율 단위 간의 파이프라인 메시지를 재개합니다. 예를 들어 허브 또는 배율 단위에서 Supply Chain Management 서비스 작업을 실행한 후 이 프로세스를 사용해야 할 수 있습니다. |
| 워크로드 업그레이드 | 허브와 확장 단위 워크로드 간에 새로운 기능을 동기화합니다. 예를 들어 서비스로 인해 데이터 교환 쿼리가 변경되거나 새 테이블이나 필드가 워크로드에 추가된 경우 이 프로세스를 사용해야 할 수 있습니다. |
| 확장 단위로 워크로드 전송 | 현재 허브에서 실행 중인 워크로드를 배율 단위로 이동하도록 예약합니다. 이 프로세스가 실행되면 데이터 동기화가 진행되고 허브와 스케일 유닛이 모두 워크로드의 소유권을 변경하도록 설정됩니다. |
| 스케일 유닛을 허브로 전송 | 현재 배율 단위에서 실행 중인 워크로드를 허브로 이동하도록 예약합니다. 이 프로세스가 실행되면 데이터 동기화가 진행되고 허브와 스케일 유닛이 모두 워크로드의 소유권을 변경하도록 설정됩니다.
| 허브로 비상 전환 | <p>기존 워크로드를 즉시 허브로 전송합니다. *이 프로세스는 현재 허브에서 사용할 수 있는 데이터의 소유권만 변경합니다.*</p><p><strong>경고:</strong> 이 프로세스는 동기화되지 않은 데이터에 대한 데이터 손실 및 비즈니스 처리 실패를 유발할 수 있습니다. 따라서 스케일 장치에 합리적인 시간 내에 완화할 수 없는 중단이 있기 때문에 비즈니스 프로세스를 허브에서 처리해야 하는 비상 상황에서만 사용해야 합니다.</p> |
| 분산 토폴로지 해제 | 확장 단위 배포를 제거하고 워크로드 처리 없이 허브에서만 실행합니다. |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="배율 단위 및 워크로드 관리 경험.":::

> [!TIP]
> 시간이 지남에 따라 Scale Unit Manager 환경에 점진적 개선 사항이 추가되어 수명 주기 관리 작업을 더 쉽게 수행할 수 있습니다. 현재 릴리스의 특정 기능은 Supply Chain Management를 위해 분산 하이브리드 토폴로지에 온보딩하는 과정에 있는 고객이 사용할 수 있는 온보딩 핸드북에 문서화되어 있습니다. <!-- KFM: Add a link to the handbook when it is published -->

## <a name="feature-management-considerations-for-workloads"></a>워크로드에 대한 기능 관리 고려 사항

이 섹션에서는 워크로드를 설치하거나, 기능을 추가하거나, 분산 하이브리드 토폴로지 배포에서 기능을 제거할 때 고려해야 하는 몇 가지 중요한 측면에 대해 설명합니다. 변경 후에 여러 시나리오가 [워크로드 업그레이드](#manage-workloads) 실행 여부에 영향을 줄 수 있습니다. 그러나 일반적으로 새 데이터 교환 쿼리를 업데이트하거나 추가할 때 및/또는 이전에 설치된 작업 부하에 새 테이블이나 필드를 추가할 때 그렇게 해야 합니다.

### <a name="mandatory-features-for-installing-a-workload"></a>워크로드 설치를 위한 필수 기능

워크로드를 설치할 때 설치 프로세스는 두 배포 간에 데이터를 동기화할 때 사용되는 데이터 테이블에 대한 정보가 포함된 워크로드 정의를 만듭니다. 워크로드 정의 생성은 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 현재 활성화된 기능을 기반으로 자동 처리됩니다. 다음 표에는 창고 또는 제조 워크로드를 실행하는 데 필요한 워크로드 정의를 생성하기 위해 활성화해야 하는 기능이 나열되어 있습니다.

| 필수 기능 | 워크로드 |
|---|---|
| WHS 사용자 생성 시 가이드 자동 할당 | 창고 |
| 조직 전체 작업 차단 | 창고 |
| 배송 웨이브 라벨 세부정보 | 창고 |
| 창고 앱 작업 목록에 대한 배율 단위 지원 | 창고 |
| 생산 현장 실행 | 제조 |

[원박스 개발 환경을 위한 스케일 유닛 배포 도구](https://github.com/microsoft/SCMScaleUnitDevTools) 또는 [배율 단위 관리자 포털](https://sum.dynamics.com)을 사용하여 워크로드를 배포하는 경우, 모든 필수 기능이 자동으로 활성화됩니다. 그러나 하나 이상의 필수 기능이 누락된 수동 테스트 배포를 수행하는 경우 워크로드 설치가 실패하고 누락된 기능을 나열하는 메시지를 받게 됩니다. 그런 다음 해당 기능을 수동으로 활성화하고 워크로드 설치를 다시 트리거해야 합니다.

### <a name="enabling-or-disabling-features-that-have-data-synchronization-dependencies"></a>데이터 동기화 종속성이 있는 기능 활성화 또는 비활성화

허브와 해당 배율 단위 간에 동기화되는 데이터 선택에 영향을 주는 기능은 워크로드 정의가 생성되는 방식에도 영향을 줍니다. 따라서 워크로드를 설치하기 전에 이러한 기능을 활성화하는 것이 중요합니다. 워크로드를 실행하는 동안 이러한 유형의 기능을 활성화하는 경우 기능을 활성화한 후 [워크로드 업그레이드](#manage-workloads)을 실행하여 워크로드 정의를 다시 생성해야 합니다. 마찬가지로 워크로드를 실행하는 동안 데이터 동기화 종속성이 있는 기능을 비활성화하는 경우 [워크로드 업그레이드](#manage-workloads)를 실행하여 워크로드 정의에서 관련 데이터 동기화 정보를 제거해야 합니다.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
