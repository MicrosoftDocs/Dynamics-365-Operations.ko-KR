---
title: 모바일 디바이스 사용자 계정
description: 이 주제에서는 작업자가 창고 앱에 로그인하여 사용할 수 있도록 하는 사용자 계정을 설정하고 관리하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f3a930814a1fb98e3b1611adf309c10e66b49b9d
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2021
ms.locfileid: "8449533"
---
# <a name="mobile-device-user-accounts"></a>모바일 디바이스 사용자 계정

[!include [banner](../includes/banner.md)]

작업자는 창고 앱을 사용할 때마다 사용자 이름과 암호를 사용하여 로그인해야 합니다. 임의의 수의 창고 앱 사용자가 시스템의 각 작업자와 연관될 수 있으며 창고는 일반적으로 각 창고 앱 사용자와 연관됩니다. 기본 설정 및 창고 앱 사용과 관련된 기타 설정을 구성하기 위해 각 작업자에 대해 다양한 옵션도 구성되어 있습니다.

## <a name="set-up-the-required-worker-and-employee-records"></a>필수 근로자 및 직원 기록 설정

창고 앱 사용자를 설정하려면 먼저 각 작업자가 이미 Supply Chain Management 직원 또는 **인사** 모듈의 작업자로 존재해야 합니다.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>모바일 디바이스 사용자 계정 설정

인적 자원에서 필수 작업자 및 직원을 설정한 후 각각에 창고 앱 사용자를 할당하고 앱 사용 방법에 영향을 미치는 기타 옵션을 설정할 수 있습니다.

1. **창고 관리 \> 설정 \> 작업자** 로 이동합니다.
1. 기존 작업자를 편집하려면 목록 창에서 선택합니다. 새 레코드를 추가하려면 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 작업자를 설정하는 경우 다음 단계를 따르십시오.

    1. **작업자** 필드의 직원 목록에서 대상 사용자를 선택합니다.
    1. **선택** 을 선택합니다.
    1. 작업 창에서 **저장** 을 선택합니다.

1. 기본 프로필을 사용하여 포장 스테이션의 창고 작업자에게 필요한 프로세스를 안내할 수 있습니다. 또는 기본 프로필을 사용하여 작업자의 기본 프로필 설정을 저장할 수 있습니다. **프로필** 빠른 탭에서 다음 필드를 설정합니다.

    - **컨테이너 포장 정책** – 포장 스테이션에서 컨테이너를 처리하는 방법을 정의하는 컨테이너 포장 정책을 선택합니다. 여기에서 선택한 컨테이너 포장 정책은 작업자가 포장 스테이션을 열 때 미리 선택됩니다. 자세한 내용은 [향상된 포장 기능](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611) 블로그 게시물을 참조하세요.
    - **포장 프로필 ID** – 사용되는 포장 정책 및 컨테이너 설정을 정의하는 포장 프로필 ID를 선택합니다. 선택한 포장 프로필 ID가 컨테이너 포장 정책과 연결된 경우 이 페이지에서 **컨테이너 포장 정책** 설정을 변경할 수 없습니다.

1. **기본 포장 스테이션** 빠른 탭에서 다음 필드를 설정하여 작업자가 로그인할 때 적용되는 기본 포장 스테이션을 정의합니다. 작업자는 필요에 따라 다른 포장 스테이션을 선택할 수 있습니다.

    - **사이트** – 기본 포장 스테이션이 있는 사이트를 선택합니다.
    - **창고** – 기본 포장 스테이션이 있는 창고를 선택합니다.
    - **위치** – 기본 포장 스테이션의 위치를 선택합니다.

1. **사용자** 빠른 탭을 사용하면 선택한 작업자에 대한 창고 앱 사용자 계정을 원하는 수만큼 생성할 수 있습니다. 각 계정은 특정 창고와 연결됩니다. 도구 모음을 사용하여 사용자 계정을 추가 또는 제거하고 선택한 계정의 암호를 재설정하거나 선택한 계정에 창고를 할당합니다. 각 사용자 계정에 대해 다음 필드를 설정할 수 있습니다.

    - **사용자 ID** – 고유 ID를 입력합니다.
    - **사용자 이름** – ID의 이름을 입력합니다.
    - **기본 창고** – 작업자가 주로 일하는 기본 창고를 설정합니다. 도구 모음을 사용하여 추가 창고를 지정할 수 있으며 작업자는 모바일 디바이스 메뉴 항목의 **창고 변경** 간접 활동을 사용하여 창고 간에 전환할 수 있습니다.
    - **메뉴 이름** – 작업자의 시작 페이지가 될 루트 메뉴를 선택합니다. 각 작업자에 대한 루트 메뉴를 설정하는 기능은 각 작업자가 사용할 수 있는 메뉴 구조를 제어할 수 있기 때문에 유용합니다. 예를 들어 아웃바운드 영역에서만 활동하는 작업자를 위한 메뉴는 해당 영역의 아웃바운드 작업과 관련된 작업에 맞게 조정할 수 있습니다.
    - **비활성** – 선택된 확인란은 사용자 계정이 비활성화되었음을 나타냅니다. 창고 앱에서 작업자가 잘못된 암호를 5회 연속 입력하면 사용자 계정이 자동으로 비활성화됩니다. 그러나 이 확인란을 수동으로 선택할 수도 있습니다. 사용자를 다시 활성화하려면 확인란의 선택을 취소합니다.

1. **작업** 빠른 탭에서 다음 필드를 설정합니다.

    - **선택 위치 재정의 허용** – 이 옵션을 *예* 로 설정하면 작업자가 피킹 단계를 위한 위치를 재정의할 수 있습니다. 이 기능은 실제 재고가 시스템 제안 위치와 일치하지 않는 경우에 유용할 수 있습니다.
    - **배치 위치 재정의 허용** – 이 옵션을 *예* 로 설정하면 작업자가 배치 단계를 위한 위치를 재정의할 수 있습니다. 이 기능은 제안된 배치 위치가 현재 가득 찼거나 사용할 수 없는 경우 또는 준비 위치가 변경된 경우에 유용할 수 있습니다.
    - **판매 초과 피킹 허용** – 이 옵션을 *예* 로 설정하면 판매 주문이 피킹될 때 작업자가 초과 피킹할 수 있습니다. 자세한 내용은 [판매 주문 및 이전 주문에 대한 초과 피킹](over-picking-for-sales-and-transfer-orders.md)을 참조하세요.
    - **이전 주문 초과 피킹 허용** – 이 옵션을 *예* 로 설정하면 이전 주문이 피킹될 때 작업자가 초과 피킹할 수 있습니다. 자세한 내용은 [판매 주문 및 이전 주문에 대한 초과 피킹](over-picking-for-sales-and-transfer-orders.md)을 참조하세요.
    - **관련 작업과 함께 재고 이동 허용** – 이 옵션을 *예* 로 설정하면 작업자가 이미 예약되었거나 다른 작업과 이미 연결된 재고를 이동할 수 있습니다. 자세한 내용은 [Warehouse Management에서 관련 업무에 따른 재고 이동](move-inventory-associated-work.md)을 참조하세요.
    - **수동 항목 재할당 허용** – 이 옵션을 *예* 로 설정하여 단기 피킹 동안 작업자에 대한 수동 재할당을 활성화합니다. 항목 재할당은 작업자가 다른 위치에서 재고를 선택하도록 안내합니다. 모든 작업자가 자동 재할당을 사용할 수 있지만 수동 재할당은 작업자에 대한 명시적 설정이 필요합니다. 각 작업자에 대한 수동 재할당을 제어하는 기능은 예를 들어 검역소 또는 벌크 영역에서 항목 선택이 신뢰할 수 있는 작업자로 제한될 때 각 작업자의 가시성을 제어할 수 있기 때문에 유용할 수 있습니다. 자세한 내용은 [단기 피킹 중 자동 및 수동 항목 재할당](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/) 블로그 게시물을 참조하세요.
    - **순환 재고 감독자임** – 이 옵션을 *예* 로 설정하여 작업자를 순환 재고 감독자로 만듭니다. 이 경우 작업자가 창고 앱에서 수행하는 모든 준환 재고가 즉시 승인됩니다. 이 옵션이 *예* 로 설정된 작업자의 경우 **최대 비율 제한**, **최대 수량 제한** 및 **최대값 제한** 필드가 고려되지 않습니다.
    - **최대 비율 제한** – 순환 재고 감독자의 승인 없이 순환 재고가 예상 개수와 다를 수 있는 최고 비율 제한을 입력합니다.
    - **최대 수량 제한** – 순환 재고 감독자의 승인 없이 입력된 수량이 예상 수량(단위)과 다를 수 있는 총 수량을 입력합니다.
    - **최대값 제한** – 순환 재고 감독자의 승인 없이 재고 비용이 예상 비용과 다를 수 있는 최대 금액을 입력합니다.

1. 작업 창에서 **저장** 을 선택합니다.
1. 새 사용자 계정을 추가한 경우 사용자가 모바일 앱에 로그인하는 데 사용할 수 있는 간단한 암호를 만들 수 있는 **암호 설정** 대화 상자가 나타납니다. 간단한 암호를 2번 입력 후 **암호 저장** 을 선택하여 계속합니다.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>각 창고 앱 사용자의 언어, 숫자 형식 및 시간대 설정

작업자가 Warehouse Management 모바일 앱에 로그인하면 언어, 숫자 형식 및 시간대가 해당 작업자의 기본 설정에 맞게 변경됩니다. [모바일 디바이스 사용자 계정 설정](#set-wma-users) 섹션의 3단계에서 선택한 작업자의 계정 설정에 따라 사용되는 설정이 결정됩니다. 각 사용자에 대해 별도의 설정이 필요한 경우 다른 작업자 계정을 사용하세요. 다음 절차는 각 창고 앱 사용자의 언어, 숫자 형식 및 시간대를 변경하는 방법을 보여줍니다.

1. **창고 관리 \> 설정 \> 작업자** 로 이동합니다.
1. 설정하려는 작업자의 이름을 찾습니다. 작업자에게 **사용자** 빠른 탭에 나열된 모든 필수 창고 앱 사용자 계정이 있는지 확인하세요. [모바일 디바이스 사용자 계정 설정](#set-wma-users) 섹션의 단계에 따라 새 작업자를 생성하거나 필요에 따라 창고 앱 사용자 계정을 추가합니다.
1. **시스템 관리 \> 사용자 \> 사용자** 로 이동합니다.
1. **사람** 열에 2단계에서 찾은 작업자의 이름이 표시되는 사용자 계정을 선택합니다.

    > [!IMPORTANT]
    > **사용자** 페이지에 나열된 **사용자 ID** 값은 1단계에서 연 **작업자** 페이지의 **사용자** 빠른 탭에 표시된 값과 관련이 *없습니다*.

1. 작업 창에서 **사용자 옵션** 을 선택합니다.
1. **환경 설정** 탭에서 다음 필드를 설정합니다.

    - **언어** – 작업자가 선호하는 언어를 선택합니다. 이 필드는 또한 창고 앱에 표시되는 날짜 형식을 제어합니다.
    - **날짜, 시간 및 숫자 형식** – 창고 앱에 표시되는 숫자 형식을 결정할 언어를 선택합니다. 창고 앱에 표시되는 날짜 및 시간 형식은 실제로 이 필드가 아니라 **언어** 필드입니다.
    - **시간대** – 작업자가 근무하는 시간대를 선택합니다. 이 필드는 작업자가 앱을 사용하여 만드는 모든 등록에 대한 타임스탬프에 영향을 줍니다.

> [!NOTE]
> 어떤 경우에는 창고 앱이 언어, 숫자 형식 및 시간대를 설정하는 특정 작업자 설정을 찾을 수 없습니다. 다음 규칙이 적용됩니다.
>
> - 앱이 Supply Chain Management 환경에 연결되지 않은 경우(예: 앱을 설치한 후 처음으로 앱을 시작할 때) 로컬 장치의 언어가 사용됩니다. 디바이스 언어가 변경되면 앱 언어도 변경됩니다. 로컬 디바이스의 언어를 구성하는 방법에 대한 자세한 내용은 디바이스 및/또는 운영 체제 설명서를 참조하세요.
> - 앱이 Supply Chain Management 환경에 연결되어 있지만 로그인한 작업자에 대한 기본 설정이 지정되지 않은 경우 디바이스가 Supply Chain Management에 연결하는 데 사용하는 클라이언트 ID와 연결된 계정을 기반으로 언어, 숫자 형식 및 시간대가 선택됩니다. 자세한 내용은 [Supply Chain Management에서 사용자 계정 생성 및 구성](install-configure-warehouse-management-app.md#user-azure-ad)을 참조하세요.

> [!TIP]
> 창고 앱을 사용한 등록에 대해 잘못된 타임스탬프가 표시되는 경우 작업자가 Supply Chain Management에 로그인 및/또는 인증하는 데 사용하는 사용자 계정에 대해 설정된 시간대를 조정해야 할 수 있습니다. 이전에 언급했듯이 시간대 설정은 **작업자** 페이지에서 설정했듯이 창고 앱에 로그인하는 데 사용되는 사용자 계정에서 가져올 수 있습니다. 또는 **작업자** 페이지에서 사용자 계정이 설정되지 않은 경우 **[Azure Active Directory 애플리케이션](install-configure-warehouse-management-app.md)** 페이지에서 설정한 대로 인증에 사용되는 클라이언트 ID와 연결된 사용자 계정에서 표준 시간대를 가져옵니다.
