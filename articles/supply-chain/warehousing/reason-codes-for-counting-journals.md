---
title: 재고 집계 사유 코드
description: 이번에는 작업 계산을 위한 사유 코드를 설정하고 적용하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4c178ddf342b13a0ef8fee8b8b958554a9a31069
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2021
ms.locfileid: "8447709"
---
# <a name="reason-codes-for-inventory-counting"></a>재고 집계 사유 코드

[!include [banner](../includes/banner.md)]

사유 코드를 사용하면 계산 프로세스의 결과와 해당 프로세스 중에 발생하는 불일치를 분석할 수 있습니다. 파손된 팔레트 또는 재고 샘플을 기반으로 하는 재고 조정과 같이 카운트를 수행하는 사유를 지정할 수 있습니다. 동시에 조정 기능을 사용하여 각 재고 조정 사유에 따라 현 재고 조정 값을 적절한 상계 계정에 전기할 수 있습니다.

## <a name="recommendation"></a>추천

시스템을 설정하기 전에 사유 코드 작업을 위한 전략을 정의하는 것이 좋습니다. 예를 들어 다음 질문에 답해 보십시오.

- 사유 코드는 창고에 필수이어야 합니까?
- 사유 코드는 일부 품목에 필수 또는 선택 사항이어야 합니까?
- 몇 개의 사유 코드가 필요합니까?
- 조정을 위해 제한된 사유 코드 목록을 미리 선택해야 합니까?
- 바코드 스캐너 사용자는 사유 코드를 어떻게 사용해야 합니까? 사유 코드를 미리 선택해야 합니까, 필수로 해야 합니까, 편집할 수 없습니까?
- 창고 작업자는 모바일 스캐너에서 다른 사유 코드 동작을 요구합니까? 답변이 예인 경우 더 많은 메뉴 품목을 만들고 다른 사람들에게 할당할 수 있습니다.
- 사유 코드가 재정 상계 계정 전기를 유도해야 합니까?

## <a name="turn-on-reason-code-features-in-your-system"></a>시스템에서 사유 코드 기능 켜기

이 품목에 설명된 모든 기능이 시스템에 표시되지 않는 경우 *상계 계정 기능에 연결된 구성 가능한 사유 코드를 사용하여 현 재고 조정 전기* 를 켜야 할 수 있습니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 설정을 사용하여 기능의 상태를 확인하고 필요한 경우 켤 수 있습니다. **기능 관리** 작업 영역에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈:** *창고 관리*
- **기능 이름:** *상계 계정에 연결된 구성 가능한 사유 코드를 사용하여 현 재고 조정 전기*

## <a name="set-up-reason-codes"></a>사유 코드 설정

### <a name="set-up-reason-code-policies"></a>사유 코드 정책 설정

사유 코드 계산이 적용되는 시기와 방법을 제어하기 위해 여러 사유 코드 정책을 생성할 수 있습니다. 각 사유 코드 정책에는 두 가지 계산 사유 코드 유형(*선택 사항* 또는 *필수*) 중 하나가 있을 수 있습니다. 계산 사유 코드 정책은 창고 수준 또는 품목 수준에서 사용할 수 있습니다.

사유 코드 정책을 만들려면 다음 단계를 따르십시오.

1. **재고 관리** \> **설정** \> **재고** \> **집계 사유 코드 정책** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 정책을 추가합니다.
1. 새 정책의 **이름** 필드를 설정합니다.
1. **집계 사유 코드 유형** 필드에서 *필수* 또는 *선택 사항* 을 선택하여 다음 재고 조정 프로세스 중 하나에서 사유 코드 선택이 선택적이어야 하는지 아니면 필수인지 지정합니다.

    - 주기 수(모바일 디바이스)
    - 스팟 수(모바일 디바이스)
    - 임계값 수(모바일 디바이스)
    - 조정 입력(모바일 디바이스)
    - 조정 출력(모바일 디바이스)
    - 카운팅 원장(리치 클라이언트)
    - 수량 조정/온라인 카운팅(리치 클라이언트)

개별 창고 및 제품 모두에 대해 사유 코드 정책을 설정할 수 있습니다. 제품에 대한 사유 코드 설정이 제품 창고에 대한 설정보다 우선할 수 있습니다.

> [!NOTE]
> **집계 사유 코드 정책 필드** 가 *필수* 로 설정된 창고 및 품목의 경우 사유 코드가 제공될 때까지 집계 원장을 완료하고 닫을 수 없습니다. 자세한 내용은 다음 섹션을 참조하세요.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>창고에 계산 사유 코드 정책 할당

계산 사유 코드 정책을 창고에 지정하려면 다음 단계를 따르십시오.

1. **재고 관리** \> **설정** \> **재고 분석** \> **창고** 로 이동합니다.
1. 목록 창에서 창고를 선택합니다.
1. 작업 창의 **창고** 탭에 있는 **설정** 그룹에서 **집계 사유 코드 정책** 을 선택합니다. 이후 **집계 사유 코드 정책 할당** 드롭다운 대화 상자에서 다음 단계 중 하나를 수행합니다.

    - 각 품목에 대한 정책 설정을 사용하여 계산 원장이 품목에 대해 필수인지를 결정하려면 값을 입력하지 않거나 기존 값을 삭제합니다.
    - 창고에 대한 집계 원장에 사유 코드를 요구하려면 **집계 사유 코드 유형** 필드가 *필수* 로 설정된 사유 정책을 선택하세요.
    - 창고에 대한 집계 원장에서 사유 코드가 선택 사항인 경우 **집계 사유 코드 유형** 필드가 *선택 사항* 으로 설정된 사유 정책을 선택하세요.

### <a name="assign-counting-reason-code-policies-to-products"></a>제품에 계산 사유 코드 정책 할당

계산 사유 코드 정책을 제품에 할당하려면 다음 단계를 따르십시오.

1. **제품 정보 관리** \> **제품** \> **출시 제품** 으로 이동합니다.
1. 그리드에서 제품을 선택합니다.
1. 작업 창의 **제품** 탭에 있는 **설정** 그룹에서 **집계 사유 코드 정책** 을 선택합니다. 이후 **집계 사유 코드 정책 할당** 드롭다운 대화 상자에서 다음 단계 중 하나를 수행합니다.

    - 창고에 대한 정책 설정을 사용하여 집계 원장이 제품에 대해 필수인지를 결정하려면 값을 입력하지 않거나 기존 값을 삭제하세요.
    - 제품의 집계 원장에 사유 코드를 요구하려면 **집계 사유 코드 유형** 필드가 *필수* 로 설정된 사유 정책을 선택하세요. 이 설정은 창고 수준에서 모든 사유 코드 설정을 대체합니다.
    - 사유 코드가 제품에 대한 집계 원장에서 선택 사항인 경우 **집계 사유 코드 유형** 필드가 *선택 사항* 으로 설정된 사유 정책을 선택합니다. 이 설정은 창고 수준에서 모든 사유 코드 설정을 대체합니다.

### <a name="set-up-counting-reason-codes"></a>계산 사유 코드 설정

계산 사유 코드를 설정하려면 다음 단계를 따르십시오.

1. **재고 관리** \> **설정** \> **재고** \> **집계 사유 코드** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다.
1. 새 행에 대한 **집계 사유 코드** 및 **설명** 필드를 설정합니다.
1. 상계 계정을 지정하려면 **상계 계정** 필드에 값을 입력하거나 선택합니다.

    > [!NOTE]
    > 상계 계정이 집계 사유 코드에 지정된 경우, 집계 원장을 전기할 때 해당 집계 사유 코드가 있는 경우 값은 기본 재고 전기 프로필 계정 대신 지정된 상계 계정에 대해 전기됩니다.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>계산 사유 코드 그룹 설정

*집계 사유 코드 그룹* 은 Warehouse Management 모바일 앱에서 *조정 입력* 및 *조정 출력* 메뉴 품목의 일부로 사용하여 계수 사유 코드 목록을 제한할 수 있습니다. (사유 코드 그룹 집계에 대한 자세한 내용은 이 항목 뒷부분의 [조정 및 조정을 위한 모바일 디바이스 메뉴 품목 설정](#setup-adjustment-in-out) 섹션을 참조하세요.)

1. **재고 관리** \> **설정** \> **재고** \> **집계 사유 코드 그룹** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그룹을 추가합니다.
1. 새 그룹에 대한 **집계 사유 그룹** 및 **그룹 설명** 필드를 설정합니다.
1. 작업 창에서 **저장** 을 선택합니다.
1. **세부 정보** 섹션의 도구 모음에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대한 **집계 사유 코드** 필드를 설정합니다. 
1. 필요에 따라 더 많은 코드를 할당하려면 이전 단계를 반복합니다. 그룹에서 코드를 제거해야 하는 경우 해당 코드를 선택한 후, 도구 모음에서 **삭제** 를 선택합니다.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>모바일 디바이스 메뉴 품목에 대한 사유 코드 설정

다음 현 재고 조정 유형에 대한 사유 코드를 구성할 수 있습니다.

- 순환 재고
- 스팟 카운트
- 임계값 수
- 조정
- 조정 아웃

대부분의 경우 각 관련 모바일 디바이스 메뉴 품목에 대해 다음 정보를 정의할 수 있습니다.

- 계산하는 동안 모바일 디바이스 작업자에게 사유 코드를 표시할지입니다.
- 모바일 디바이스 메뉴 품목에 표시되는 기본 사유 코드입니다.
- 사용자가 사유 코드를 편집할 수 있는지입니다.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>계산 프로세스를 위한 모바일 디바이스 메뉴 품목 설정

계산 프로세스를 위한 모바일 디바이스 메뉴 품목을 설정하려면 다음 단계를 따르십시오.

1. **창고 관리** \> **설정** \> **모바일 디바이스** \> **모바일 디바이스 메뉴 항목** 으로 이동합니다.
1. 목록 창에서 해당 메뉴 품목을 선택하거나 새 메뉴 품목을 만듭니다.
1. 작업 창에서 **주기 집계** 을 선택합니다.
1. **기본 집계 사유 코드** 필드에서 모바일 디바이스 메뉴 품목을 사용하여 집계할 때 기록되어야 하는 기본 사유 코드를 설정합니다.
1. **집계 사유 코드 표시** 필드에서 다음 값 중 하나를 선택합니다.

    - *라인* – 각 분산이 기록된 후 사유 코드를 표시합니다.
    - *숨기기* – 사유 코드를 표시하지 않습니다.

1. **집계 사유 코드 편집** 을 *예* 로 설정하면 집계하는 동안 모바일 디바이스에 표시될 때 작업자가 사유 코드를 편집할 수 있습니다. 작업자가 코드를 편집하지 못하도록 하려면 *아니요* 로 설정합니다.

> [!NOTE]
> **주기 집계** 버튼은 집계를 수행할 수 있는 모든 모바일 디바이스 메뉴 항목에서 활성화할 수 있습니다. 예를 들면 스팟 카운트, 사용자 지시 작업 및 시스템 지시 작업에 대한 메뉴 품목이 포함됩니다.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>조정 입력 및 조정 출력을 위한 모바일 디바이스 메뉴 품목 설정

조정 또는 조정을 위해 모바일 디바이스 메뉴 품목을 설정하려면 다음 단계를 따르십시오.

1. **창고 관리** \> **설정** \> **모바일 디바이스** \> **모바일 디바이스 메뉴 항목** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 메뉴 품목을 만듭니다.
1. 새 메뉴 항목에 대한 **모바일 항목 이름** 및 **제목** 필드를 설정합니다.
1. **모드** 필드를 *작업* 으로 설정합니다.
1. **기존 작업 사용** 옵션을 *아니요* 로 설정합니다.
1. **작업 생성 프로세스** 필드에서 *조정 입력* 또는 *조정 출력* 을 선택합니다.
1. **일반** 빠른 탭에서 다음 필드를 설정하세요. (이 모든 필드는 **작업 생성 프로세스** 필드에서 *조정 입력* 또는 *조정 출력* 을 선택하면 추가됩니다.)

    - **프로세스 가이드 사용** – *조정 출력* 프로세스를 생성하는 경우 이 옵션을 *예* 로 설정해야 합니다. *조정 출력* 프로세스를 생성하는 경우 이 옵션은 항상 *예* 로 설정됩니다.
    - **기본 집계 사유 코드** – 모바일 디바이스 메뉴 항목을 사용하여 집계을 수행할 때 기록되어야 하는 기본 사유 코드를 설정합니다.
    - **집계 사유 코드 표시** – 다음 값 중 하나를 선택합니다.

        - *라인* – 각 분산이 기록된 후 사유 코드를 표시합니다.
        - *숨기기* – 사유 코드를 표시하지 않습니다.

    - **집계 사유 코드 편집** – 집계 중에 모바일 디바이스에 표시될 때 작업자가 사유 코드를 편집할 수 있도록 하려면 이 옵션을 *예* 로 설정합니다. 작업자가 코드를 편집하지 못하도록 하려면 *아니요* 로 설정합니다.
    - **집계 사유 코드 그룹** – 작업자에게 표시되는 옵션 목록을 제한하려면 사유 코드 그룹을 선택합니다. 사유 코드 그룹을 설정하는 방법에 대한 자세한 내용은 이 항목 앞부분의 [집계 사유 코드 그룹 설정](#reason-groups) 섹션을 참조하세요. 

> [!NOTE]
> **프로세스 가이드 사용** 옵션이 *예* 로 설정된 *조정 입력* 및 *조정 출력* 메뉴 항목에 집계 사유 코드 그룹을 할당하면 Warehouse Management 모바일 앱에서 처리의 일부로 집계 사유 코드의 제한된 목록을 얻을 수 있습니다.
>
> **프로세스 가이드 사용** 옵션은 또한, 실수로 많은 조정량이 발생하는 것을 방지하는 데 도움이 될 수 있습니다. (예를 들어 작업자가 실수로 수량 값 대신 품목 번호의 바코드를 스캔할 수 있습니다.) 이 기능을 설정하려면 각 관련 메뉴 항목에 대해 **프로세스 가이드 사용** 옵션을 *예* 로 설정하세요. 이후 **창고 관리 \> 설정 \> 작업자** 으로 이동하여 해당 창고 작업자별로 **조정 수량 제한** 필드를 설정하여 작업자가 등록할 수 있는 최대 조정 수량을 지정합니다.

## <a name="processing-that-uses-counting-reason-codes"></a>계수 사유 코드를 사용하는 처리

작업자가 Warehouse Management 모바일 앱을 사용하면 사유 코드가 기록됩니다. 집계 승인 프로세스가 정의되지 않은 한 기록된 사유 코드는 다음 집계 원장 전기의 일부로 즉시 사용됩니다.

### <a name="cycle-count-approvals"></a>주기 집계 승인

개수가 승인되기 전에 작업자는 개수와 연결된 사유 코드를 변경할 수 있습니다. 집계가 승인되면 집계 원장 라인에 사유 코드가 입력됩니다.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>주기 집계 승인에 대한 사유 코드 수정

주기 집계 승인을 수정하려면 다음 단계를 따르십시오.

1. **창고 관리** \> **주기 집계** \> **주기 집계 작업 검토 대기 중** 으로 이동합니다.
1. 그리드에서 주기 집계를 선택합니다.
1. 작업 창의 **작업** 탭에서 **주기 집계** 를 선택합니다. 이후 **사유 코드** 필드에서 새 사유 코드를 선택합니다.

집계 원장 유형의 *집계 원장* 에서 사유 코드가 원장 라인에 추가됩니다.

1. **재고 관리** \> **원장 입력** \> **항목 집계** \> **집계** 로 이동합니다.
2. 집계 원장의 라인 세부 정보에서 **집계 사유 코드** 필드에서 현재 상황과 일치하는 사유 코드를 선택합니다.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>카운팅 이력에 기록된 사유 코드 보기

계수 기록에 기록된 원인 코드를 보려면 다음 단계를 따르십시오.

1. **재고 관리** \> **문의 및 신고** \> **집계 내역** 으로 이동합니다.
1. 목록 창에서 품목 수 기록를 선택합니다.
1. **집계 사유 코드** 필드에서 사유 코드를 통해 기록된 집계 내역을 확인합니다.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>수량 조정 또는 온라인 집계에 사유 코드 사용

수량 조정 또는 온라인 집계에 사유 코드를 사용하려면 다음 단계를 따르십시오.

1. **재고 관리 \> 문의 및 보고 \> 보유 목록** 으로 이동합니다.
1. 작업 창에서 **수량 조정** 을 선택합니다.
1. **수량 조정** 을 선택한 후, **집계 사유 코드** 필드에서 사유 코드를 선택합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
