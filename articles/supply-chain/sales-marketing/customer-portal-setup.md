---
title: 고객 포털 설치, 설정 및 업데이트
description: 이 토픽에서는 고객 포털에 대한 라이선스 세부 정보 및 설정 지침을 제공합니다.
author: Henrikan
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 187efe1372bf2400241f3d65751189247c001447
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449800"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>고객 포털 설치, 설정 및 업데이트

[!include [banner](../includes/banner.md)]


## <a name="licensing-requirements"></a>라이선싱 요구 사항

고객 포털을 구현하려면 다음 라이선스가 있어야 합니다.

- **Power Apps 포털** – 이 라이선스는 고객 포털을 호스팅하는 데 필요합니다. 포털은 사용량에 따라 라이선스가 부여됩니다. 자세한 내용은 [Power Apps 포털 라이선스 요구 사항](/power-platform/admin/powerapps-flow-licensing-faq#portals)을 참조하세요.
- **이중 쓰기** – Supply Chain Management 테이블에 대해 이중 쓰기를 활성화하려면 필요한 라이선스가 있어야 합니다. 자세한 내용은 [이중 쓰기에 대한 시스템 요구 사항](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md)을 참조하세요.

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>이중 쓰기 및 Power Apps 포털에 대한 종속성

고객 포털은 다음 그림과 같이 Power Apps 포털 및 이중 쓰기에 따라 다릅니다.

![고객 포털 종속성.](media/customer-portal-elements.png "고객 포털 종속성")

Supply Chain Management의 다른 기능과 달리 고객 포털 템플릿은 Power Apps 포털에 있습니다. 따라서 고객 포털은 Power Apps 포털과 이중 쓰기 테이블에서 제공하는 기능으로 제한됩니다.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>고객 포털을 사용하는 데 필요한 설정

필요한 라이선스가 있는지 확인한 후 [이중 쓰기 초기 동기화 지침](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-entity-map.md)에 설명된 대로 이중 쓰기를 설정할 수 있습니다.

이중 쓰기에서 다음 테이블 매핑을 사용해야 합니다.

- 판매 주문 헤더
- 판매 주문 세부 정보
- 어카운트
- 연락처
- 제품

이 설정이 완료되면 고객 포털 템플릿을 프로비저닝할 수 있습니다.

## <a name="provision-the-customer-portal"></a>고객 포털 프로비전

시작하기 전에 [필요한 설정](#required-setup)을 이미 완료했는지 확인하세요. 이후 다음 단계에 따라 고객 포털을 프로비전합니다.

1. [make.powerapps.com](https://make.powerapps.com/)으로 이동합니다.
2. 이중 쓰기를 사용 설정 환경을 사용하고 있는지 확인하세요.
3. **만들기** 탭에서 **템플릿에서 시작** 섹션까지 아래로 스크롤하고 **고객 포털** 이라는 템플릿을 선택합니다.
4. 화면의 지시를 따릅니다.

프로비전이 완료되면 **홈** 페이지의 **내 앱** 섹션에서 고객 포털에 액세스할 수 있습니다.

> [!NOTE]
> 이중 쓰기 솔루션이 작업 중인 환경에 설치되어 있지 않으면 오류 메시지가 표시되고 고객 포털이 프로비전되지 않습니다.

## <a name="update-the-customer-portal"></a>고객 포털 업데이트

나중에 고객 포털에 더 많은 기능이 추가될 수 있습니다. 기본 솔루션 구성 요소에 대한 Microsoft의 모든 변경 내용은 사용자 환경에 자동으로 나타납니다. 그러나 환경에 프로비전된 웹 사이트는 구성 데이터에 대한 변경 사항을 자동으로 반영하지 않습니다. 새 템플릿에서 코드를 가져와 프로비전된 웹 사이트와 병합하여 이러한 변경 내용을 수동으로 적용해야 합니다.

## <a name="additional-resources"></a>추가 리소스

고객 포털을 설정하고 사용자 지정하는 방법을 배우려면 먼저 기본 기술에 대한 다음 문서를 검토해야 합니다.

- [Power Apps 포털 문서](/powerapps/maker/portals/overview)
- [이중 쓰기 문서](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

포털을 효과적으로 관리하려면 Power Apps 포털과 Microsoft Dataverse 수명 주기를 이해해야 합니다. 자세한 내용은 다음 리소스를 참조하세요.

- [포털 수명 주기 정보](/powerapps/maker/portals/admin/portal-lifecycle)
- [포털 업그레이드](/powerapps/maker/portals/admin/upgrade-portal)
- [포털 구성 마이그레이션](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [솔루션 수명 주기 관리: Dynamics 365 for Customer Engagement 앱](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]