---
title: 고객 포털 사용자 생성 및 관리(비디오 포함)
description: 이 항목에서는 고객 포털 사용자 계정을 만들고 권한을 설정하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4615182e6c3341a376e8e55a1417480e3e3f5ea7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449842"
---
# <a name="create-and-manage-customer-portal-users"></a>고객 포털 사용자 생성 및 관리

[!include [banner](../includes/banner.md)]


기본 구현에서는 사용자가 고객 포털을 사용하여 만든 웹 사이트에 자체 등록할 수 있는 방법이 없습니다. 웹 사이트에 로그인하여 사용하려면 관리자의 초대를 받아야 합니다. Microsoft는 사용자가 자체 등록하는 기능을 의도적으로 차단했습니다.

사용자가 웹 사이트를 사용하려면 먼저 해당 사용자에 대한 연락처 레코드를 만들어야 합니다. 이 레코드는 사용자가 속한 고객 계정 및 법인을 나타냅니다. 이 정보는 사용자가 판매 주문을 생성하고 볼 수 있도록 하는 데 필수적입니다.

사용자가 자체 등록하면 연락처 레코드가 자동으로 생성됩니다. 따라서 사용자가 올바른 고객 계정 및 법인을 선택했는지 확인할 수 없습니다. 반면에 초대 절차를 통해 관리자는 초대가 전송되기 전에 연락처 레코드에 올바른 고객 계정과 법인을 할당할 수 있습니다. 사용자가 자체 등록할 수 있도록 솔루션을 사용자 지정하려는 경우 가능한 결과를 고려해야 합니다.

## <a name="video"></a>비디오
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

[고객 포털을 등록하고 사용하도록 고객 초대](https://youtu.be/drGUYHX9QIQ) 비디오(위 참조)는 YouTube에서 제공되는 [금융 및 운영 재생 목록](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)에 포함되어 있습니다.

## <a name="prerequisite-setup"></a>전제 조건 설정

Power Apps 포털의 연락처는 Microsoft Dataverse의 **연락처** 테이블에 레코드로 저장됩니다. 그런 다음 이중 쓰기는 필요에 따라 이러한 레코드를 Microsoft Dynamics 365 Supply Chain Management에 동기화합니다.

![고객 포털 연락처에 대한 시스템 다이어그램.](media/customer-portal-contacts.png "고객 포털 연락처에 대한 시스템 다이어그램")

새 고객 초대를 시작하기 전에 이중 쓰기에서 **연락처** 테이블 매핑을 활성화했는지 확인하세요.

## <a name="the-invitation-process"></a>초대 절차

기존 연락처를 고객 포털에 초대하려면 Power Apps 포털 설명서의 [포털에 연락처 초대](/powerapps/maker/portals/configure/invite-contacts)의 단계를 따르세요.

고객 포털에 가입하도록 고객을 초대하기 전에 고객의 [연락처 레코드](/powerapps/maker/portals/configure/configure-contacts)가 사용 가능하고 다음과 같은 방식으로 설정되어 있는지 확인하세요.

1. **회사** 필드를 Supply Chain Management에서 고객이 속하게 하려는 법인으로 설정합니다.
2. **계정 번호** 필드를 사용자가 Supply Chain Management에서 갖게 하려는 고객 계정 번호로 설정합니다.

연락처가 생성되면 Supply Chain Management에서 볼 수 있어야 합니다.

자세한 내용은 Power Apps 포털 설명서의 [포털에서 사용할 연락처 구성](/powerapps/maker/portals/configure/configure-contacts)을 참조하세요.

## <a name="out-of-box-web-roles-and-table-permissions"></a>기본 웹 역할 및 테이블 권한

Power Apps 포털의 사용자 역할은 [웹 역할](/powerapps/maker/portals/configure/create-web-roles) 및 [테이블 권한](/powerapps/maker/portals/configure/assign-entity-permissions)으로 정의됩니다. 기본적으로 고객 포털에 대해 몇 가지 역할이 정의됩니다. 새 역할을 만들고 기존 역할을 수정하거나 제거할 수 있습니다.

### <a name="out-of-box-web-roles"></a>기본 웹 역할

이 섹션에서는 고객 포털과 함께 제공되는 웹 역할에 대해 설명합니다.

기본 사용자 역할을 수정하는 방법에 대한 자세한 내용은 Power Apps 포털 설명서의 [포털에 대한 웹 역할 생성](/powerapps/maker/portals/configure/create-web-roles) 및 [포털에 대한 테이블 권한을 사용하여 레코드 기반 보안 추가](/powerapps/maker/portals/configure/assign-entity-permissions)를 참조하세요.

#### <a name="administrator"></a>관리자

관리자는 웹 사이트를 감독하고 유지 관리합니다. 이 사람은 고객 포털을 프로비전하고 설정합니다. 관리자는 포털의 IT 및 보안 측면을 유지 관리하고 모든 것이 원활하게 실행되는지 확인합니다. 관리자는 새 기능을 추가하고 새 역할을 만드는 등의 방법으로 포털을 사용자 지정 및/또는 변경도 할 수 있습니다.

#### <a name="customer-representative"></a>고객 담당자

고객 담당자는 고객 회사에서 일하며 회사가 발주하는 주문을 관리하는 책임이 있습니다. 고객 담당자는 회사와 주문한 사용자에 대한 모든 주문을 볼 수 있습니다. 또한 고객 담당자는 전체 계정 및 해당 계정을 대신하여 주문할 수 있는 연락처 정보를 볼 수 있습니다.

#### <a name="authorized-users"></a>권한 있는 사용자

권한 있는 사용자는 주문을 하고 주문 상태를 볼 수 있습니다. 그러나 회사의 다른 사용자가 주문한 상태는 볼 수 없습니다.

#### <a name="unauthorized-users"></a>권한 없는 사용자

권한 없는 사용자는 데이터를 볼 수 없습니다. 이용 약관과 같은 공개 정보와 고객 포털을 실행하는 회사에 대한 세부 정보만 볼 수 있습니다.

#### <a name="example"></a>예제

다음 테이블은 각 웹 역할의 사용자가 시스템에서 볼 수 있는 판매 주문을 보여줍니다.

| 판매 주문 | 관리자 | 고객 X의&nbsp;고객 담당자 | 권한 있는 사용자: Jane | 권한 있는 사용자: Sam | 권한 없는 사용자: May |
|---|---|---|---|---|---|
| 고객&nbsp;X&nbsp;주문자: Jane | 예 | 예 | 예 | 아니요 | 아니요 |
| 고객&nbsp;X&nbsp;주문자: Sam | 예 | 예 | 아니요 | 예 | 아니요 |
| 고객&nbsp;Y 주문자:&nbsp;May | 예 | 아니요 | 아니요 | 아니요 | 아니요 |

> [!NOTE]
> Sam과 Jane은 모두 고객 X를 위해 일하는 연락처지만 자신이 발주한 주문만 볼 수 있고 다른 것은 볼 수 없습니다. May는 시스템에 주문이 있지만 권한 없는 사용자이기 때문에 고객 포털에서 해당 주문을 볼 수 없습니다. (또한 그녀는 고객 포털이 아닌 다른 채널을 통해 주문해야 합니다.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]