---
title: 제품 수명 주기 상태 및 트랜잭션
description: 이 항목에서는 엔지니어링 제품이 수명 주기를 거치면서 각 수명 주기 상태에 대해 허용되는 트랜잭션을 제어하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1e9b8a9f25edfa654a57e0ab4071cd93c8033d85
ms.sourcegitcommit: d375ef4138e898621416754c40770d8ccca4d271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8450058"
---
# <a name="product-lifecycle-states-and-transactions"></a>제품 수명 주기 상태 및 트랜잭션

[!include [banner](../includes/banner.md)]

엔지니어링 제품이 수명 주기를 거치면서 각 수명 주기 상태에 대해 허용되는 트랜잭션을 제어할 수 있는 것이 중요합니다. 예를 들어, 아직 완전하지 않은 제품은 판매 주문을 해서는 안 됩니다. 또는 제품이 수명 종료 상태에 도달하면 해당 제품의 유입을 제어할 수 있습니다.

엔지니어링 제품의 경우 수명 주기 상태에 대한 변경 사항은 제품의 엔지니어링 버전에 연결됩니다. 따라서 제품의 수명 주기 상태는 제품의 엔지니어링 버전에도 연결할 수 있습니다. 제품 수명 주기 상태가 엔지니어링 버전에 연결되면 수명 주기 상태를 사용하여 엔지니어링 버전에 허용되는 트랜잭션을 제어할 수 있습니다.

## <a name="create-and-manage-product-lifecycle-states"></a>제품 수명 주기 상태 생성 및 관리

제품 수명 주기 상태를 사용하려면 **엔지니어링 변경 관리 \> 설정 \> 제품 수명 주기 상태** 으로 이동하세요. 그런 다음 다음 단계 중 하나를 따릅니다.

- 새 수명 주기 상태를 만들려면 작업 창에서 **새로 만들기** 를 선택한 후 다음 하위 섹션에 설명된 대로 필드를 설정합니다.
- 기존 수명 주기 상태를 편집하려면 목록 창에서 정책을 선택하고 작업 창에서 **편집** 을 선택한 후 다음 하위 섹션에 설명된 대로 필드를 설정합니다.
- 기존 수명 주기 상태를 삭제하려면 목록 창에서 선택한 다음 작업 창에서 **삭제** 를 선택합니다.

> [!NOTE]
> 엔지니어링 제품은 표준(비엔지니어링) 제품과 동일한 제품 수명 주기 상태를 사용합니다. **제품 정보 관리 \> 설정 \> 제품 수명 주기 상태** 로 이동하여 이 항목에서 설명하는 **제품 수명 주기 상태** 페이지를 열 수도 있습니다. 엔지니어링 제품 및 표준 제품 모두에 대한 제품 수명 주기 상태에 대한 자세한 내용은 [제품 수명 주기 상태 개요](../pim/product-lifecycle.md)를 참조하세요.

### <a name="header"></a>머리글

제품 수명 주기 상태 헤더에 다음 필드를 설정합니다.

| 필드 | 설명 |
|---|---|
| 상태 | 제품 수명 주기 상태의 이름을 입력합니다. |
| 설명 | 제품 수명 주기 상태에 대한 설명을 입력합니다. |

### <a name="general-fasttab"></a>일반 빠른 탭

**일반** 빠른 탭에서 다음 필드를 설정합니다.

| 필드 | 설명 |
|---|---|
| 법인으로 출시될 때의 기본값 | 표준 제품의 경우 이 수명 주기 상태가 처음 출시될 때 기본적으로 모든 제품에 적용되어야 하는 경우 이 옵션을 *예* 로 설정합니다. 이 수명 주기 상태가 나중에 수동으로 적용되는 경우 *아니요* 로 설정합니다.<p>이 설정은 엔지니어링 제품에 적용할 수 없습니다. 엔지니어링 회사에서 생성된 엔지니어링 제품 버전의 수명 주기 상태는 해당 엔지니어링 변경 범주에 지정됩니다. 제품이 운영 회사에 출시되면 제품의 수명 주기 상태가 복사됩니다. 즉, 엔지니어링 제품이 운영 회사에 출시되면 엔지니어링 회사에서와 동일한 수명 주기 상태를 갖습니다. 수명 주기 상태는 운영 회사에서 덮어쓸 수 있습니다.</p> |
| 계획에 대해 활성 | 이 옵션을 *예* 로 설정하면 기준 계획 및 BOM(자재 명세서) 수준에서 이 수명 주기 상태에 있는 제품을 계산에 포함할 수 있습니다. 이 수명 주기 상태에 있는 제품을 계산에서 제외하려면 *아니요* 로 설정합니다. |

### <a name="enabled-business-processes-fasttab"></a>활성화된 비즈니스 프로세스 빠른 탭

**사용 설정된 비즈니스 프로세스** 빠른 탭을 사용하여 현재 수명 주기 상태의 제품과 함께 사용할 수 있는 비즈니스 프로세스를 제어합니다. 이 빠른 탭에 나열된 프로세스는 다음과 같은 방식으로 자동으로 검색됩니다.

- 새 수명 주기 상태를 처음 저장하면 페이지에 현재 사용 가능한 비즈니스 프로세스가 로드됩니다.
- 시스템에 새 비즈니스 프로세스를 추가하는 경우 작업 창에서 **업데이트 확인** 을 선택하여 기존 수명 주기 상태에 대한 **활성화된 비즈니스 프로세스** 빠른 탭의 목록을 업데이트할 수 있습니다.

**사용 설정된 비즈니스 프로세스** 빠른 탭에 나열된 각 프로세스에 대해 다음 필드를 사용할 수 있습니다.

| 필드 | 설명 |
|---|---|
| 프로세스 | 이 읽기 전용 필드에는 기존 비즈니스 프로세스의 이름이 표시됩니다. |
| 프로세스 영역 | 이 읽기 전용 필드에는 기존 프로세스 영역의 이름이 표시됩니다. |
| 정책 | 다음 값 중 하나를 선택하여 이 수명 주기 상태에 있는 제품에 대해 현재 프로세스를 허용할지 여부와 방법을 제어합니다.<ul><li>**활성화됨** – 비즈니스 프로세스가 허용됩니다.</li><li>**차단됨** – 프로세스가 허용되지 않습니다. 사용자가 이 수명 주기 상태에 있는 제품에서 프로세스를 사용하려고 하면 시스템이 시도를 차단하고 대신 오류를 표시합니다. 예를 들어 수명이 다한 제품의 구매를 차단할 수 있습니다.</li><li>**경고와 함께 사용** – 프로세스는 허용되지만 경고가 표시됩니다. 예를 들어, 연구 개발 부서에서 생성한 생산 주문에 프로토타입 제품을 넣을 수 있습니다. 그러나 다른 부서에서는 아직 제품을 생산하지 않아야 함을 알아야 합니다.</li></ul> |

수명 주기 상태 규칙을 사용자 지정으로 추가하는 경우 상단 창에서 **프로세스 새로 고침** 을 선택하여 사용자 인터페이스(UI)에서 해당 규칙을 볼 수 있습니다. **프로세스 새로 고침** 버튼은 관리자만 사용할 수 있습니다.

## <a name="lifecycle-states-for-released-products-and-product-variants"></a>출시된 제품 및 제품 변형의 수명 주기 상태

변형(마스터 및 변형)이 있는 제품의 경우 제품(마스터)은 수명 주기 상태를 가지며 각 변형도 다른 수명 주기 상태를 가질 수 있습니다.

특정 프로세스의 경우 변형 또는 제품이 차단되면 해당 프로세스도 차단됩니다. 특히 프로세스가 차단되었는지 여부를 확인하기 위해 시스템은 다음을 확인합니다.

- 엔지니어링 제어 제품의 경우:
  - 현재 엔지니어링 버전이 차단된 경우 프로세스를 차단합니다.
  - 현재 변형이 차단된 경우 프로세스를 차단합니다.
  - 출시된 제품이 차단된 경우 프로세스를 차단합니다.
- 표준 제품의 경우:
  - 현재 변형이 차단된 경우 프로세스를 차단합니다.
  - 출시된 제품이 차단된 경우 프로세스를 차단합니다.

예를 들어 주어진 제품(티셔츠)의 한 변형(빨간색)만 판매하고 현재 다른 모든 변형의 판매를 차단한다고 가정합니다. 다음 설정을 사용하여 이를 구현할 수 있습니다.

- 프로세스를 허용하는 제품 수명 주기 상태를 지정합니다. 예를 들어, 티셔츠 제품에 *판매 주문* 비즈니스 프로세스를 허용하는 *판매 가능* 의 수명 주기 상태를 할당합니다.
- 프로세스를 허용하는 판매 가능한 변형 수명 주기 상태를 지정합니다. 예를 들어 *판매 가능* 이라는 빨간색 변형 수명 주기 상태도 할당합니다.
- 다른 모든 변형에는 프로세스가 차단된 다른 수명 주기 상태가 할당됩니다. 예를 들어 흰색 변형(및 기타 모든 변형)에 *판매 불가* 의 수명 주기 상태를 할당하여 *판매 주문* 비즈니스 프로세스를 차단합니다.

## <a name="default-product-lifecycle-states"></a>기본 제품 수명 주기 상태

엔지니어링 버전의 기본 수명 주기 상태는 해당 엔지니어링 범주로 지정됩니다. 새 제품의 첫 번째 버전을 포함하여 새 엔지니어링 버전을 만들 때 상태가 기본값으로 설정됩니다.

새 제품 또는 엔지니어링 제품을 생성할 때 제품에 할당된 릴리스 정책의 템플릿 릴리스 제품에 지정하여 기본 수명 주기 상태를 설정할 수도 있습니다.

이 경우 새 엔지니어링 제품을 생성할 때 제품의 수명 주기 상태가 버전과 다를 수 있습니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
