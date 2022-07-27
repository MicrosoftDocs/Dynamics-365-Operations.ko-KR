---
title: 인벤토리 가시성 추가 기능 설치
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management용 인벤토리 가시성 추가 기능을 설치하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a49f35211f30cdb76104cc5be78f5b114320a228
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449848"
---
# <a name="install-and-set-up-inventory-visibility"></a>인벤토리 가시성 설치 및 설정

[!include [banner](../includes/banner.md)]


이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management용 인벤토리 가시성 추가 기능을 설치하는 방법에 대해 설명합니다.

인벤토리 가시성 추가 기능을 설치하려면 Microsoft Dynamics LCS(Lifecycle Services)를 사용해야 합니다. LCS는 재무 및 운영 앱의 애플리케이션 수명 주기를 관리하는 데 도움이 되는 환경과 정기적으로 업데이트되는 서비스 세트를 제공하는 협업 포털입니다.

자세한 내용은 [Lifecycle Services 리소스](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)를 참조하세요.

## <a name="inventory-visibility-prerequisites"></a>인벤토리 가시성 전제 조건

인벤토리 가시성을 설치하기 전에 다음 작업을 완료해야 합니다.

- 하나 이상의 환경이 배포된 LCS 구현 프로젝트를 가져옵니다.
- 추가 기능 설정을 위한 전제 조건이 완료되었는지 확인합니다. 이러한 필수 구성 요소에 대한 자세한 내용은 [추가 기능 개요](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md)를 참조하세요. 인벤토리 가시성은 이중 쓰기 연결이 필요하지 않습니다.

> [!NOTE]
> 현재 지원되는 국가 및 지역은 캐나다(CCA, ECA), 미국(WUS, EUS), 유럽 연합(NEU, WEU), 영국(SUK, WUK), 호주(EAU, SEAU), 일본(EJP, WJP) 및 브라질(SBR, SCUS)입니다.

이러한 전제 조건에 대해 질문이 있는 경우 인벤토리 가시성 제품 팀([inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com))에 문의하세요.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>인벤토리 가시성 추가 기능 설치

추가 기능을 설치하기 전에 애플리케이션을 등록하고 Azure 구독에서 Azure Active Directory(Azure AD)에 클라이언트 암호를 추가합니다. 지침은 [애플리케이션 등록](/azure/active-directory/develop/quickstart-register-app) 및 [클라이언트 암호 추가](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)를 참조하세요. 나중에 필요하므로 **애플리케이션(클라이언트) ID**, **클라이언트 암호** 및 **테넌트 ID** 값을 기록해 두세요.

애플리케이션을 등록하고 Azure AD에 클라이언트 암호를 추가한 후 다음 단계에 따라 인벤토리 가시성 추가 기능을 설치합니다.

1. [LCS](https://lcs.dynamics.com/Logon/Index)에 로그인합니다.
1. 홈 페이지에서 환경이 배포된 프로젝트를 선택합니다.
1. 프로젝트 페이지에서 추가 기능을 설치할 환경을 선택합니다.
1. 환경 페이지에서 **Power Platform 통합** 섹션의 **환경 추가 기능** 섹션을 찾을 때까지 아래로 스크롤합니다. 거기에서 Dataverse 환경 이름을 찾을 수 있습니다. Dataverse 환경 이름이 인벤토리 가시성에 사용하려는 이름인지 확인합니다.

    > [!NOTE]
    > 현재 LCS를 사용하여 만든 Dataverse 환경만 지원됩니다. Dataverse 환경이 다른 방식으로 생성된 경우(예: Power Apps 관리 센터를 사용하여) Supply Chain Management 환경에 연결된 경우 먼저 인벤토리 가시성 제품 팀([inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com))에 연락하여 매핑 문제를 수정합니다. 그런 다음 인벤토리 가시성을 설치할 수 있습니다.

1. **환경 추가 기능** 섹션에서 **새 추가 기능 설치** 를 선택합니다.

    ![LCS의 환경 페이지](media/inventory-visibility-environment.png "LCS의 환경 페이지")

1. **새 추가 기능 설치** 링크를 선택합니다. 사용 가능한 추가 기능 목록이 나타납니다.
1. 목록에서 **인벤토리 가시성** 을 선택합니다.
1. 환경에 대해 다음 필드를 설정합니다.

    - **AAD 애플리케이션(클라이언트) ID** – 이전에 만들고 메모해 둔 Azure AD 애플리케이션 ID를 입력합니다.
    - **AAD 테넌트 ID** – 이전에 기록해 둔 테넌트 ID를 입력합니다.

    ![추가 기능 페이지 설정](media/inventory-visibility-setup.png "추가 기능 페이지 설정")

1. **계약조건** 확인란을 선택하여 이용약관에 동의합니다.
1. **설치** 를 선택합니다. 추가 기능의 상태는 **설치 중** 으로 표시됩니다. 설치가 완료되면 페이지를 새로 고칩니다. 상태가 **설치됨** 으로 변경되어야 합니다.
1. Dataverse의 왼쪽 탐색에서 **앱** 섹션을 선택하고 **인벤토리 가시성** Power Apps가 성공적으로 설치되었는지 확인합니다. **앱** 섹션이 없으면 인벤토리 가시성 제품 팀[(inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com))에 문의하세요.

> [!TIP]
> 인벤토리 가시성 추가 기능 사용자 그룹에 가입하는 것이 좋습니다. 여기에서 유용한 가이드를 찾고, 최신 업데이트를 받고, 인벤토리 가시성 사용에 대한 질문을 게시할 수 있습니다. 가입하려면 인벤토리 가시성 제품 팀([inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com))으로 이메일을 보내고 Supply Chain Management ID를 포함하세요.

> [!IMPORTANT]
> 둘 이상의 LCS 환경이 있는 경우 각 환경에 대해 다른 Azure AD 애플리케이션을 만듭니다. 동일한 애플리케이션 ID와 테넌트 ID를 사용하여 다른 환경에 인벤토리 가시성 추가 기능을 설치하면 이전 환경에서 토큰 문제가 발생합니다. 마지막으로 설치된 것만 유효합니다.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>인벤토리 가시성 추가 기능 제거

인벤토리 가시성 추가 기능을 제거하려면 LCS 페이지에서 **제거** 를 선택합니다. 제거 프로세스는 인벤토리 가시성 추가 기능을 종료하고 LCS에서 추가 기능을 등록 취소하며 인벤토리 가시성 추가 기능 데이터 캐시에 저장된 모든 임시 데이터를 삭제합니다. 그러나 Dataverse 구독에 저장된 기본 인벤토리 데이터는 삭제되지 않습니다.

Dataverse 구독에 저장된 인벤토리 데이터를 제거하려면 [Power Apps](https://make.powerapps.com)를 열고 탐색 모음에서 **환경** 을 선택한 다음 LCS 환경과 연결된 Dataverse 환경을 선택합니다. 그런 다음 **솔루션** 으로 이동하여 다음 5가지 솔루션을 순서대로 삭제합니다.

1. Dynamics 365 솔루션의 Inventory Visibility 애플리케이션용 앵커 솔루션
1. Dynamics 365 FNO SCM Inventory Visibility 애플리케이션 솔루션
1. 인벤토리 서비스 구성
1. Inventory Visibility 독립 실행형
1. Dynamics 365 FNO SCM Inventory Visibility 기본 솔루션

이러한 솔루션을 삭제하면 테이블에 저장된 데이터도 삭제됩니다.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Supply Chain Management에서 인벤토리 가시성 설정

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>인벤토리 가시성 통합 패키지 배포

Supply Chain Management 버전 10.0.17 이하를 실행 중인 경우 인벤토리 가시성 온보드 지원 팀([inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com))에 문의하여 패키지 파일을 받으십시오. 그런 다음 LCS에 패키지를 배포합니다.

> [!NOTE]
> 배포 중 버전 불일치 오류가 발생하면 X++ 프로젝트를 개발 환경으로 수동으로 가져와야 합니다. 그런 다음 개발 환경에서 배포 가능한 패키지를 만들고 프로덕션 환경에 배포합니다.
>
> 이 코드는 Supply Chain Management 버전 10.0.18에 포함되어 있습니다. 해당 버전 이상을 실행하는 경우 배포가 필요하지 않습니다.

Supply Chain Management 환경에서 다음 기능이 켜져 있는지 확인하세요. (기본적으로 켜져 있습니다.)

| 기능 설명 | 코드 버전 | 토글 클래스 |
|---|---|---|
| InventSum 테이블에서 인벤토리 차원 사용 활성화 또는 비활성화      | 10.0.11 | InventUseDimOfInventSumToggle      |
| InventSumDelta 테이블에서 인벤토리 차원 사용 활성화 또는 비활성화 | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>인벤토리 가시성 통합 설정

추가 기능을 설치했으면 다음 단계를 수행하여 Supply Chain Management 시스템이 작동하도록 준비합니다.

1. Supply Chain Management에서 **[기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** 작업 영역을 열고 다음 기능을 켭니다.
    - *인벤토리 가시성 통합* - 필수.
    - *예약 상쇄와 인벤토리 가시성 통합* – 권장되지만 선택 사항입니다. 버전 10.0.22 이상이 필요합니다. 자세한 내용은 [인벤토리 가시성 예약](inventory-visibility-reservations.md)을 참조하세요.

1. **재고 관리 \> 설정 \> 인벤토리 가시성 통합 매개 변수** 로 이동합니다.
1. **일반** 탭을 열고 다음 설정을 지정합니다.
    - **인벤토리 가시성 엔드포인트** – 인벤토리 가시성을 실행 중인 환경의 URL을 입력합니다. 자세한 내용은 [서비스 엔드포인트 찾기](inventory-visibility-configuration.md#get-service-endpoint)를 참조하세요.
    - **단일 요청의 최대 레코드 수** – 단일 요청에 포함할 최대 레코드 수로 설정합니다. 1000 이하의 양의 정수를 입력해야 합니다. 기본값은 512입니다. Microsoft 지원에서 조언을 받았거나 변경해야 한다고 확신하지 않는 한 기본값을 유지하는 것이 좋습니다.

1. *예약 상쇄와 인벤토리 가시성 통합 기능*(선택 사항)을 활성화한 경우 **예약 상쇄** 탭을 열고 다음 설정을 지정합니다.
    - **예약 상쇄 사용** – 이 기능을 활성화하려면 *예* 로 설정합니다.
    - **예약 상쇄 수정자** – 인벤토리 가시성에서 이루어진 예약을 상쇄할 재고 트랜잭션 상태를 선택합니다. 이 설정은 상쇄를 트리거하는 주문 처리 단계를 결정합니다. 단계는 주문의 재고 트랜잭션 상태로 추적됩니다. 다음 중 하나를 선택합니다.
        - *주문 시* – *주문 시* 상태의 경우 주문이 생성될 때 상쇄 요청을 보냅니다. 상쇄 수량은 생성된 주문의 수량입니다.
        - *예약* – *예약 주문 거래* 상태의 경우 예약, 피킹, 포장 명세서 게시 또는 송장 발행 시 주문에서 상쇄 요청을 보냅니다. 요청은 언급된 프로세스가 발생하는 첫 번째 단계에 대해 한 번만 트리거됩니다. 상쇄 수량은 해당 주문 라인에서 재고 트랜잭션 상태가 *주문 시* 에서 *주문 예약*(또는 이후 상태)으로 변경된 수량입니다.

1. **재고 관리 \> 정기 \> 인벤토리 가시성 통합** 으로 이동하여 작업을 활성화합니다. 이제 Supply Chain Management의 모든 재고 변경 이벤트가 인벤토리 가시성에 전기됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
