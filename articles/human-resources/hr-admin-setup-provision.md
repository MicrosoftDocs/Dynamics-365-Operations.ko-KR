---
title: Human Resources 프로비전
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources의 새 프로덕션 환경을 프로비저닝하는 프로세스에 관해 설명합니다.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c856bca32c3dee44469c098961d85b4d8cb70a6
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451987"
---
# <a name="provision-human-resources"></a>Human Resources 프로비전

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Microsoft Dynamics 365 Human Resources의 새 프로덕션 환경을 프로비저닝하는 프로세스에 관해 설명합니다. 

## <a name="prerequisites"></a>전제 조건

새 프로덕션 환경 프로비저닝을 시작하기 전에 다음 전제 조건이 충족되어야 합니다.

- 클라우드 솔루션 공급자(CSP) 또는 엔터프라이즈 아키텍처(EA) 계약을 통해 Human Resources를 구매했습니다. Human Resources 서비스 계획이 이미 포함된 기존 Microsoft Dynamics 365 라이선스가 있고 이 항목의 단계를 완료할 수 없는 경우 고객 지원팀에 문의하세요.

- 전역 관리자가 [Microsoft Dynamics Lifecycle Services(LCS)](https://lcs.dynamics.com)에 로그인하여 새 Human Resources 프로젝트를 만들었습니다. 

## <a name="provision-a-human-resources-trial-environment"></a>Human Resources 평가판 환경 프로비전

첫 번째 샌드박스 또는 프로덕션 환경을 프로비저닝하기 전에 [Human Resources 평가판 환경](https://go.microsoft.com/fwlink/p/?LinkId=2115962)을 프로비저닝하여 Human Resources 기능을 검증할 수 있습니다. 평가판 환경에는 안전한 방식으로 프로그램을 살펴보는 데 사용할 수 있는 가상 데이터가 포함되어 있습니다. 평가판 환경은 요청한 사용자가 소유하지만 Human Resources의 시스템 관리 환경을 통해 다른 사용자를 초대할 수 있습니다. 

평가판 환경은 아직 Human Resources 환경에 대한 액세스 권한이 없는 사용자에게 Human Resources 기능을 평가할 수 있는 기능을 제공합니다. 평가판 환경을 프로비저닝하고 인증된 사용자가 이미 하나 이상의 기존 Human Resources 환경에 액세스할 수 있는 경우 사용자는 기존 환경 또는 환경 목록으로 리디렉션됩니다.

평가판 환경은 프로덕션 환경으로 사용하기 위한 것이 아닙니다. 30일 평가판 기간으로 제한됩니다. 평가판 기간이 만료되면 환경과 그 안에 있는 모든 데이터가 삭제되고 복구할 수 없습니다. 환경을 샌드박스 또는 프로덕션 환경으로 변환할 수 없습니다. 기존 환경이 만료된 후 새 평가판 환경에 등록할 수 있습니다.

Human Resources 평가판 환경을 만들 때 Power Apps 평가판 환경도 테넌트에 생성되고 Human Resources 환경에 연결됩니다. Power Apps 환경의 이름은 "TestDrive"이고 평가판 기간은 Human Resources 환경과 같습니다.

> [!NOTE]
> 인증된 사용자에게 Power Apps 평가판 환경을 만들 수 있는 권한이 없는 경우 Human Resources 평가판 환경 프로비저닝이 실패합니다. 사용자는 Power Platform 관리 센터에서 평가판 환경을 만들 수 있는 사용자 그룹에 포함되어야 합니다. 자세한 내용은 [Power Platform 관리 센터에서 환경을 만들고 관리할 수 있는 사용자 제어](/power-platform/admin/control-environment-creation)를 참조하세요.

## <a name="plan-human-resources-environments"></a>Human Resources 환경 계획

첫 번째 Human Resources 환경을 만들기 전에 프로젝트에 필요한 환경을 신중하게 계획해야 합니다. Human Resources의 기본 구독에는 프로덕션 환경과 샌드박스 환경의 두 가지 환경이 포함됩니다. 프로젝트의 복잡성에 따라 프로젝트 활동을 지원하기 위해 추가 샌드박스 환경을 구매해야 할 수도 있습니다. 

추가 환경에 대한 고려 사항:

- **데이터 마이그레이션**: 프로젝트 전체에서 테스트 목적의 샌드박스 환경을 사용하려면 데이터 마이그레이션 활동을 위한 추가 환경을 고려해야 할 수도 있습니다. 추가 환경이 있으면 테스트 및 구성 활동을 다른 환경에서 동시에 수행하면서 데이터 마이그레이션 활동을 계속할 수 있습니다.
- **통합**: 통합을 구성하고 테스트하기 위해 추가 환경을 고려해야 할 수 있습니다. 여기에는 Ceridian Dayforce LinkedIn Talent Hub 통합과 같은 기본 통합 또는 급여, 지원자 추적 시스템 또는 복리후생 시스템 및 공급자를 위한 통합과 같은 사용자 지정 통합이 포함될 수 있습니다.
- **학습**: 새 시스템 사용에 대한 직원 교육을 위해 교육 데이터의 집합으로 구성된 별도의 환경이 필요할 수 있습니다. 
- **다단계 프로젝트**: 프로젝트의 초기 가동 후 계획된 프로젝트 단계에서 구성, 데이터 마이그레이션, 테스트 또는 기타 활동을 지원하기 위해 추가 환경이 필요할 수 있습니다.

 > [!IMPORTANT]
 > 환경을 고려할 때 다음 사항을 권장합니다.
 > - 프로젝트 전체에서 프로덕션 환경을 골드 구성 환경으로 사용합니다. 샌드박스 환경을 프로덕션 환경으로 복사할 수 없으므로 이는 중요합니다. 따라서 라이브 전환할 때 골드 환경이 프로덕션 환경이며 이 환경에서 전환 활동을 완료합니다.</br></br>
 > - 라이브 전환 전에 샌드박스 또는 다른 환경을 사용하여 모의 전환을 수행합니다. 골드 구성이 있는 프로덕션 환경을 샌드박스 환경으로 새로 고쳐서 이 작업을 수행할 수 있습니다.</br></br>
 > - 라이브 전환 중에 최종 데이터를 프로덕션 환경으로 마이그레이션하는 데 필요한 각 데이터 패키지를 포함하는 상세한 전환 체크리스트를 유지합니다.</br></br>
 > - 프로젝트 전체에서 샌드박스 환경을 테스트 환경으로 사용합니다. 추가 환경이 필요한 경우 조직에서 추가 비용을 지불하고 구매할 수 있습니다.</br></br>

## <a name="create-an-lcs-project"></a>LCS 프로젝트 만들기

LCS를 사용하여 Human Resources 환경을 관리하려면 먼저 LCS 프로젝트를 만들어야 합니다.

1. Human Resources에 가입할 때 사용한 계정으로 [LCS](https://lcs.dynamics.com/Logon/Index)에 로그인합니다.

   > [!NOTE]
   > 프로비저닝을 위해서는 Human Resources 환경을 프로비저닝하는 데 사용되는 계정이 Human Resources 환경과 연결된 Power Apps 환경에서 **시스템 관리자** 또는 **시스템 사용자 지정자** 역할에 할당되어야 합니다. Power Platform에서 사용자에게 보안 역할을 할당하는 방법에 대한 자세한 내용은 [리소스에 대한 사용자 보안 구성](/power-platform/admin/database-security)을 참조하세요.

2. 더하기 기호(**+**)를 선택하여 프로젝트를 만듭니다.

3. 제품 이름과 제품 버전으로 **Microsoft Dynamics 365 Human Resources** 를 선택합니다.

4. **Dynamics 365 Human Resources** 방법론을 선택합니다.

5. **만들기** 를 선택합니다.

Human Resources를 시작하는 방법은 새 프로젝트에서 만든 **Human Resources** 방법론을 참조하세요. 프로젝트 만들기를 완료한 후 다음 절차를 수행하여 Human Resources 환경을 프로비저닝합니다.

## <a name="provision-a-human-resources-project"></a>Human Resources 프로젝트 프로비전

LCS 프로젝트를 만든 후 환경에 Human Resources를 프로비저닝할 수 있습니다.

1. LCS 프로젝트에서 **Human Resources 앱 관리** 타일을 선택합니다.

2. 이 환경이 Human Resources의 샌드박스 또는 프로덕션 인스턴스인지 나타냅니다. 조기 피드백 및 테스트를 위해 샌드박스 인스턴스에서 조기 미리 보기 기능을 사용할 수 있습니다.
   
    > [!NOTE]
    > Human Resources 인스턴스 유형은 일단 설정되면 변경할 수 없습니다. 계속하기 전에 올바른 인스턴스 유형을 선택했는지 확인하세요.</br></br>
    > Human Resources 인스턴스 유형은 Power Apps 관리 센터에서 설정한 Microsoft Power Apps 환경의 인스턴스 유형과 별개입니다.
    
3. Human Resources 평가판 환경에서 사용된 것과 같은 데모 데이터 세트를 환경에 포함하려면 **데모 데이터 포함** 옵션을 선택합니다. 데모 데이터는 장기 데모 또는 교육 환경에 유용하지만 프로덕션 환경에는 절대 사용해서는 안 됩니다. 초기 배포 시 이 옵션을 선택해야 합니다. 나중에 기존 배포를 업데이트할 수 없습니다.

4. Human Resources는 Power Apps 통합 및 확장성을 활성화하기 위해 항상 Microsoft Power Apps 환경에 프로비저닝됩니다. 계속하기 전에 이 문서의 "Power Apps 환경 선택" 섹션을 참조하세요 Power Apps 환경이 아직 없는 경우 LCS에서 환경 관리를 선택하거나 Power Apps 관리 센터로 이동합니다. 그런 다음 [Power Apps 환경 만들기](/powerapps/administrator/create-environment)의 단계를 따릅니다.

5. Human Resources를 프로비저닝할 환경을 선택합니다.

6. **예** 를 선택하여 약관에 동의하고 배포를 시작합니다.

   왼쪽 탐색 창의 환경 목록에 새 환경이 나타납니다. 그러나 배포 상태가 **배포됨** 으로 업데이트될 때까지 환경 사용을 시작할 수 없습니다. 이 프로세스는 일반적으로 몇 분 정도 걸립니다. 프로비저닝 프로세스가 실패하면 고객 지원팀에 문의해야 합니다.

7. 새 환경을 사용하려면 **Human Resources에 로그온** 을 선택합니다.

    > [!NOTE]
    > 아직 최종 요구 사항에 서명하지 않은 경우 프로젝트에 Human Resources의 테스트 인스턴스를 배포할 수 있습니다. 그런 다음 이 인스턴스를 사용하여 승인할 때까지 솔루션을 테스트할 수 있습니다. 새 환경을 테스트용으로 사용하는 경우 이 절차를 반복하여 프로덕션 환경을 만들어야 합니다.

## <a name="select-a-power-apps-environment"></a>Power Apps 환경 선택

Power Apps 도구를 사용하여 Human Resources 데이터의 사용을 통합하고 확장할 수 있습니다. 환경 범위, 환경 액세스, 환경 만들기 및 선택을 비롯한 Power Apps 환경에 대한 자세한 내용은 [Power Apps 환경 발표](https://powerapps.microsoft.com/blog/powerapps-environments/)를 참조하세요. 

Human Resources를 배포할 Power Apps 환경을 결정할 때 다음 지침을 사용하세요. 

1. LCS에서 **환경 관리** 를 선택합니다. 기존 환경을 보고 새 환경을 만들 수 있는 Power Apps 관리 센터로 직접 이동할 수도 있습니다.

2. 단일 Human Resources 환경은 단일 Power Apps 환경에 매핑됩니다.

3. Power Apps 환경에는 해당하는 Power Apps, Power Automate 및 Dataverse 애플리케이션과 함께 Human Resources가 포함됩니다. Power Apps 환경이 삭제되면 그 안에 있는 앱도 삭제됩니다. Human Resources 환경을 프로비저닝할 때는 **평가판** 또는 **프로덕션** 환경을 프로비저닝할 수 있습니다. 환경이 사용되는 방식에 따라 환경 유형을 선택하세요. 

4. 샌드박스, UAT 또는 프로덕션과 같은 데이터 통합 및 테스트 전략을 고려해야 합니다. Power Apps 환경에 매핑되는 Human Resources 환경을 변경하기는 쉽지 않으므로 배포에 대한 영향을 신중하게 고려하세요.

5. 다음 Power Apps 환경은 Human Resources에 사용할 수 없습니다. LCS 내의 선택 목록에서 필터링됩니다.
 
    - **기본 Power Apps 환경** - 각 테넌트가 기본 Power Apps 환경으로 자동으로 프로비저닝되지만 Human Resources와 함께 사용하지 않는 것이 좋습니다. 모든 테넌트 사용자는 Power Apps 환경에 액세스할 수 있으며 Power Apps 또는 Power Automate 통합으로 테스트 및 탐색할 때 의도하지 않게 프로덕션 데이터를 손상할 수 있습니다.
   
    - **평가판 환경** - 이러한 환경은 생성될 때 만료 날짜가 지정됩니다. 만료되면 환경과 그 안에 포함된 모든 Human Resources 인스턴스가 자동으로 제거됩니다.
   
    - **지원되지 않는 지리** - 환경은 지원되는 지리에 있어야 합니다. 자세한 내용은 [지원되는 지리](hr-admin-setup-provision.md#supported-geographies)를 참조하세요.

6. Human Resources 데이터를 Power Apps 환경과 통합하기 위한 이중 쓰기 기능은 환경에 **Dynamics 365 앱 사용** 옵션이 선택된 경우에만 사용할 수 있습니다. 이중 쓰기에 대한 자세한 내용은 [이중 쓰기 홈페이지](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)를 참조하세요.

    > [!NOTE]
    > **Dynamics 365 앱 사용** 옵션은 Power Apps 환경이 생성될 때 선택해야 합니다. 프로비저닝할 때 이 옵션을 선택하지 않으면 Dynamics 365 Human Resources와 Power Apps 환경 간에 데이터를 통합할 때 이중 쓰기를 사용하거나 환경에 Dynamics 365 Sales 및 Field Service와 같은 Dynamics 365 앱을 설치할 수 없습니다. 이 옵션은 되돌릴 수 없습니다. 자세한 내용은 Power Platform 설명서 사이트에서 [새 환경을 만들 때 몇 가지 중요한 고려 사항](//power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment)을 참조하세요.

7. 사용할 올바른 환경을 결정했으면 프로비저닝 프로세스를 계속할 수 있습니다. 

### <a name="supported-geographies"></a>지원되는 지리

Human Resources는 현재 다음 지리를 지원합니다.

- 미국
- 유럽
- 영국
- 오스트레일리아
- 캐나다
- 아시아 

Human Resources 환경을 만들 때 Human Resources 환경과 연결할 Power Apps 환경을 선택합니다. 그런 다음 Human Resources 환경은 선택한 Power Apps 환경과 같은 Azure 지리에 프로비저닝됩니다. Human Resources 환경과 연결될 Power Apps 환경을 생성할 때 지리를 선택하여 Human Resources 환경 및 데이터베이스가 물리적으로 상주하는 위치를 선택할 수 있습니다.

환경이 프로비저닝되는 Azure *지리* 를 선택할 수 있지만 특정 Azure *지역* 을 선택할 수는 없습니다. 로드 밸런싱 및 성능을 최적화하기 위해 환경이 생성되는 지리 내의 특정 지역은 자동화로 결정됩니다. Azure 지리 및 지역에 대한 정보는 [Azure 지리](https://azure.microsoft.com/global-infrastructure/geographies) 설명서에서 찾을 수 있습니다.

Human Resources 환경에 대한 데이터는 항상 환경이 생성된 Azure 지리 내에 포함됩니다. 그러나 항상 같은 Azure 지역 내에 포함되지는 않습니다. 데이터는 재해 복구를 위해 지리 내의 기본 Azure 지역과 보조 장애 조치(failover) 지역 모두에 복제됩니다.

 > [!NOTE]
 > 한 Azure 지역에서 다른 지역으로 Human Resources 환경을 마이그레이션하는 것은 지원되지 않습니다.

## <a name="grant-access-to-the-environment"></a>환경에 대한 액세스 권한 부여

기본적으로 환경을 만든 전역 관리자가 액세스할 수 있습니다. 추가 애플리케이션 사용자에게는 명시적으로 액세스 권한을 부여해야 합니다. Human Resources 환경에서 사용자를 추가하고 적절한 역할을 할당해야 합니다. 자세한 내용은 [새 사용자 만들기](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) 및 [보안 역할에 사용자 할당](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles)을 참조하세요. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
