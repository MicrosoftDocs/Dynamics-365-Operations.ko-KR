---
title: 회사 개념 Dataverse
description: 이번에는 재무 및 운영 Dataverse 간의 회사 데이터 통합 및 에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3657e41363ca6c1ce8eabfeaf3ba6da9b93f5e2a
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460818"
---
# <a name="company-concept-in-dataverse"></a>회사 개념 Dataverse

[!include [banner](../../includes/banner.md)]




재무 및 운영에서 *회사* 의 개념은 법적 구성 요소이자 비즈니스 구성 요소입니다. 데이터에 대한 보안 및 가시성 경계이기도 합니다. 사용자는 항상 단일 회사의 컨텍스트에서 작업하며 대부분의 데이터는 회사별로 스트라이프됩니다.

Dataverse 동등한 개념이 없습니다. 가장 가까운 개념은 주로 사용자 데이터에 대한 보안 및 가시성 경계인 *사업부* 입니다. 이 개념은 회사 개념과 동일한 법적 또는 비즈니스 의미를 갖지 않습니다.

사업부와 회사는 동등한 개념이 아니기 때문에 Dataverse 통합을 위해 일대일(1:1) 매핑을 강제할 수 없습니다. 그러나 기본적으로 사용자는 애플리케이션 및 Dataverse에서 동일한 행을 볼 수 있어야 하므로 Microsoft는 cdm\_Company라는 Dataverse 새 테이블을 도입했습니다. 이 테이블은 애플리케이션의 Company 테이블과 동일합니다. 애플리케이션과 기본 제공 Dataverse 간에 행의 가시성이 동일하도록 하려면 Dataverse의 데이터에 대해 다음 설정을 권장합니다.

+ 이중 쓰기가 활성화된 각 재무 및 운영 회사 행에 대해 연결된 cdm\_Company 행이 생성됩니다.
+ cdm\_Company 행이 생성되고 이중 쓰기가 활성화되면 동일한 이름을 가진 기본 비즈니스 단위가 생성됩니다. 해당 사업부에 대해 기본 팀이 자동으로 생성되지만 사업부가 사용되지는 않습니다.
+ 동일한 이름을 가진 별도의 소유자 팀이 생성됩니다. 사업부와도 연결됩니다.
+ 기본적으로 생성되고 이중 기록되는 모든 행의 소유자는 연결된 비즈니스 단위에 Dataverse 연결된 'DW 소유자' 팀으로 설정됩니다.

다음 그림은 Dataverse에서 이 데이터 설정의 예를 보여줍니다.

![Dataverse에서 데이터 설정.](media/dual-write-company-1.png)

이 구성으로 인해 USMF 회사와 관련된 모든 행은 Dataverse의 USMF 사업부에 연결된 팀이 소유합니다. 따라서 사업부 수준 가시성으로 설정된 보안 역할을 통해 해당 사업부에 액세스할 수 있는 모든 사용자는 이제 해당 행을 볼 수 있습니다. 다음 예는 팀을 사용하여 해당 행에 대한 올바른 액세스를 제공하는 방법을 보여줍니다.

+ '영업 관리자' 역할은 'USMF 영업' 팀 구성원에게 할당됩니다.
+ '영업 관리자' 역할이 있는 사용자는 자신이 속한 동일한 사업부의 구성원인 모든 계정 행에 액세스할 수 있습니다.
+ 'USMF 영업'팀은 앞서 언급한 USMF 사업부와 연결되어 있습니다.
+ 따라서 'USMF 영업' 팀의 구성원은 'USMF DW' 사용자가 소유한 모든 계정을 볼 수 있습니다. 이 계정은 재무 및 운영의 USMF 회사 테이블에 있습니다.

![팀을 사용할 수 있는 방법.](media/dual-write-company-2.png)

앞의 그림에서 알 수 있듯이 사업부, 회사 및 팀 간의 1:1 매핑은 시작점일 뿐입니다. 이 예시에서 새 '유럽' 비즈니스 단위는 DEMF 및 ESMF 모두에 대한 상위로 Dataverse 수동으로 생성됩니다. 이 새로운 루트 비즈니스 단위는 이중 쓰기와 관련이 없습니다. 그러나 관련 보안 역할에서 데이터 가시성을 **상위/하위 BU** 로 설정하여 'EUR 영업' 팀 구성원에게 DEMF 및 ESMF 모두의 계정 데이터에 대한 액세스 권한을 부여하는 데 사용할 수 있습니다.

논의할 마지막 주제는 이중 쓰기가 행을 할당해야 하는 소유자 팀을 결정하는 방법입니다. 이 동작은 cdm\_Company 행의 **기본 소유 팀** 열에 의해 제어됩니다. cdm\_Company 행이 이중 쓰기에 대해 활성화되면 플러그인은 연결된 사업부 및 소유자 팀(아직 없는 경우)을 자동으로 만들고 **기본 소유 팀** 열을 설정합니다. 관리자는 이 열을 다른 값으로 변경할 수 있습니다. 그러나 테이블이 이중 쓰기에 대해 활성화되어 있는 한 관리자는 열을 지울 수 없습니다.

> [!div class="mx-imgBorder"]
![기본 소유 팀 열입니다.](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>회사 스트라이핑 및 부트스트랩

Dataverse 통합은 회사 식별자를 사용하여 데이터를 스트라이프함으로써 회사 패리티를 제공합니다. 다음 그림에서 볼 수 있듯이 모든 회사별 테이블은 cdm\_Company 테이블과 다대일(N:1) 관계를 갖도록 확장됩니다.

> [!div class="mx-imgBorder"]
![회사별 테이블과 cdm_Company 테이블 간의 N:1 관계.](media/dual-write-bootstrapping.png)

+ 행의 경우 회사를 추가하고 저장한 후 값이 읽기 전용이 됩니다. 따라서 사용자는 올바른 회사를 선택했는지 확인해야 합니다.
+ 회사 데이터가 있는 행만 애플리케이션과 Dataverse.
+ 기존 Dataverse 데이터의 경우 관리자 주도 부트스트래핑 환경이 곧 제공될 예정입니다.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>고객 참여 앱에서 회사 이름 자동 채우기

고객 참여 앱에서 회사 이름을 자동으로 채우는 방법에는 여러 가지가 있습니다.

+ 시스템 관리자인 경우 **고급 설정 > 시스템 > 보안 > 사용자** 로 이동하여 기본 회사를 설정할 수 있습니다. **사용자** 양식을 열고 **조직 정보** 섹션에서 **회사를 양식 값의 기본값** 으로 설정합니다.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="조직 정보 섹션에서 기본 회사를 설정합니다.":::

+ **사업부** 수준의 **SystemUser** 테이블에 대한 **쓰기** 액세스 권한이 있는 경우 **회사** 드롭다운 메뉴에서 회사를 선택하여 모든 양식에서 기본 회사를 변경할 수 있습니다.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="새 계정에서 회사 이름을 변경합니다.":::

+ 둘 이상의 회사에 있는 데이터에 대한 **쓰기** 액세스 권한이 있는 경우 다른 회사에 속한 행을 선택하여 기본 회사를 변경할 수 있습니다.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="행을 선택하면 기본 회사가 변경됩니다.":::

+ 시스템 구성자 또는 관리자이고 사용자 지정 양식에 회사 데이터를 자동으로 채우려는 경우 [양식 이벤트](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids)를 사용할 수 있습니다. **msdyn_/DefaultCompany.js** 에 JavaScript 참조를 추가하고 다음 이벤트를 사용하십시오. **계정** 양식과 같은 기본 양식을 사용할 수 있습니다.

    + 양식에 대한 **OnLoad** 이벤트: **defaultCompany** 열을 설정합니다.
    + **회사** 열에 대한 **OnChange** 이벤트: **updateDefaultCompany** 열을 설정합니다.

## <a name="apply-filtering-based-on-the-company-context"></a>회사 컨텍스트에 따라 필터링 적용

사용자 지정 양식 또는 표준 양식에 추가된 사용자 지정 조회 열의 회사 컨텍스트를 기반으로 필터링을 적용하려면 양식을 열고 **관련 기록 필터링** 섹션을 사용하여 회사 필터를 적용하십시오. 지정된 행의 기본 회사를 기반으로 필터링이 필요한 각 조회 열에 대해 이를 설정해야 합니다. 다음 그림에서 **계정** 에 대한 설정이 표시됩니다.

:::image type="content" source="media/apply-company-context.png" alt-text="회사 컨텍스트를 적용합니다.":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]