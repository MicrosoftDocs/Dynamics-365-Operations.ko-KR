---
title: Warehouse Management 모바일 앱의 단계에 대한 승격 필드 구성
description: 이 토픽에서는 Warehouse Management 모바일 앱에 대한 작업 흐름의 모든 단계에 대한 특정 정보를 승격하고 강조 표시하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 0ce3fb829d349a35c6c2f29838a2c725f7b61c55
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449575"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱의 단계에 대한 승격 필드 구성

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> 이 토픽에서 설명하는 기능은 새 Warehouse Management 모바일 앱에만 적용됩니다. 더 이상 사용되지 않는 이전 창고 앱에는 영향을 주지 않습니다.

이 토픽에서는 Warehouse Management 모바일 앱에 대한 작업 흐름의 모든 단계에 대한 특정 정보를 승격하고 강조 표시하는 방법에 대해 설명합니다. 이 기능은 작업자가 흐름을 따라 작업할 때 가장 중요한 필드에 주의를 집중하는 데 도움이 될 수 있습니다. 모든 프로세스의 각 단계에서 관리자는 승격할 필드와 강조 표시할 필드를 선택할 수 있습니다.

## <a name="enable-promoted-fields-in-your-system"></a>시스템에서 승격된 필드 활성화

승격 필드를 설정하기 전에 다음 절차를 완료하여 필수 기능을 활성화하고 Warehouse Management 모바일 앱에서 필수 필드 이름을 생성해야 합니다.

1. **시스템 관리 \> 작업 영역 \> 기능 관리** 로 이동합니다.
1. [**기능 관리** 작업 영역](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 다음과 같은 방식으로 나열된 기능을 활성화합니다.

    - **모듈:** *창고 관리*
    - **기능 이름:** *창고 앱 단계 지침*

    *창고 앱 단계 지침* 기능에 대한 자세한 정보는 [Warehouse Management 모바일 앱에 대한 단계 제목 및 지침 사용자 정의](mobile-app-titles-instructions.md)를 참조하세요. 이 기능은 *창고 앱 승격 필드* 기능의 전제 조건입니다.

1. 기능은 다음과 같은 방식으로 활성화됩니다.

    - **모듈:** *창고 관리*
    - **기능 이름:** *창고 앱 승격 필드*

    이 기능은 이 토픽에서 설명하는 기능입니다.

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 창고 앱 필드 이름** 으로 이동하고 **기본 설정 만들기** 를 선택하여 Warehouse Management 모바일 앱에서 필드 이름을 업데이트하세요. 자세한 정보는 [Warehouse Management 모바일 앱의 필드 구성](configure-app-field-names-priorities-warehouse.md)을 참조하세요.
1. Warehouse Management 모바일 앱을 사용하는 각 법인(회사)에 대해 이전 단계를 반복합니다.

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>메뉴별 재정의에서 승격된 필드 구성

다음 절차에 따라 승격된 필드를 설정합니다.

1. [Warehouse Management 모바일 앱에 대한 단계 제목 및 지침 사용자 설정](mobile-app-titles-instructions.md)에 설명된 대로 관련 메뉴 및 단계에 대한 메뉴별 대체를 작성합니다.
1. 편집할 **단계 ID** 와 **메뉴 항목 이름** 값의 조합을 찾은 다음 **단계 ID** 열에서 값을 선택합니다.
1. 표시되는 페이지의 **승격 필드 선택** 빠른 탭에서 도구 모음의 **필드 선택** 을 선택합니다.
1. **승격된 필드** 대화 상자에서 승격할 필드를 선택합니다. 선택한 필드를 최대 2개까지 강조 표시할 수도 있습니다. 강조 표시된 필드는 Warehouse Management 모바일 앱에서 굵게 표시됩니다. 필드를 선택할 때 일부 화면은 상위 1개 또는 2개의 승격된 필드만 표시하기에 충분히 클 수 있다는 사실을 고려하세요. 이러한 설정을 사용하는 방법을 보여주는 예는 이 토픽의 뒷부분에 나오는 시나리오를 참조하세요.

    > [!NOTE]
    > **사용 가능한 필드** 목록은 메뉴 항목에 대해 나타날 수 있는 필드로 제한됩니다. 그러나 항목 구성과 같은 다른 요소에 따라 해당 필드가 Warehouse Management 모바일 앱에 실제로 표시되는지 여부가 결정됩니다. 승격 필드를 구성한 경우 선택한 필드만 Warehouse Management 모바일 앱의 기본 페이지에 나타납니다. 그러나 작업자는 세부 정보 페이지를 탭하여 나머지 필드를 계속 볼 수 있습니다.

1. **확인** 을 선택하여 설정을 적용합니다. 선택한 필드가 이제 **승격 필드 선택** 빠른 탭에 나열됩니다.

## <a name="example-scenario"></a>예시 시나리오

### <a name="enable-sample-data"></a>샘플 데이터 활성화

지정된 샘플 레코드 및 값을 사용하여 이 시나리오를 진행하려면 표준 데모 데이터가 설치된 시스템을 사용해야 합니다. 또한 시작하기 전에 **USMF** 법인을 선택해야 합니다.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>번호판 단계에서 승격된 단계로 판매 피킹 구성

이 절차에서는 번호판 단계에서 **판매 선택** 메뉴 항목에 대해 승격되고 강조 표시된 필드를 설정합니다.

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 단계** 로 이동합니다.
1. *LicensePlateId* 라는 단계 ID를 찾아 선택합니다.
1. 작업 창에서 **단계 구성 추가** 를 선택합니다.
1. 드롭다운 대화 상자에서 **메뉴 항목** 필드를 사용하여 *판매 선택* 을 찾아 선택합니다.
1. **확인** 을 선택합니다.
1. 방금 생성한 재정의에 대한 세부 정보 페이지가 나타납니다. **승격 필드 선택** 빠른 탭에서 도구 모음의 **필드 선택** 을 선택합니다.
1. **승격 필드** 대화 상자에서 승격 및 강조 표시할 필드를 선택할 수 있습니다. **사용 가능한 필드** 목록에서 다음 필드를 찾아 선택하고 단추를 사용하여 **선택한 필드** 목록으로 이동합니다.

    - 위치
    - 항목
    - 제품 이름
    - 재고 상태

1. 위쪽 화살표 및 아래쪽 화살표 버튼을 사용하여 **선택한 필드** 목록에서 필드의 순서를 사용자 정의합니다. Warehouse Management 모바일 앱에서 필드는 여기에서 설정한 순서대로 나타납니다.
1. **위치** 필드를 선택한 다음 **강조 표시** 를 선택합니다.
1. **확인** 을 선택하여 구성을 저장합니다.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Warehouse Management 모바일 앱에서 승격 필드 보기

이 절차에서는 Warehouse Management 모바일 앱을 열고 이전 절차에서 승격 및 강조 표시한 필드를 보기 위한 단계를 진행합니다.

1. Microsoft Dynamics 365 Supply Chain Management에서 번호판 추적 위치에서 선택하려면 선택 단계가 필요한 판매 주문을 만듭니다. 그런 다음 판매 주문을 창고로 릴리즈합니다. 생성된 작업 ID를 기록해 둡니다.
1. Warehouse Management 모바일 앱을 열고 창고 24에 로그인합니다. (표준 데모 데이터에서는 사용자 ID로 *24*, 암호로 *1* 을 사용하여 로그인합니다.)
1. **아웃바운드** 메뉴를 선택한 다음 **판매 피킹** 메뉴 항목을 선택합니다.
1. 화면의 데이터 입력 지침에 따라 1단계에서 생성한 작업 ID를 입력합니다.
1. **번호판 스캔** 텍스트가 포함된 단계에서 세부 정보 페이지에서 변경한 내용을 확인해야 합니다. 필드는 승격된 필드에 대해 설정한 순서대로 표시되고 **위치** 필드는 굵게 표시됩니다.
