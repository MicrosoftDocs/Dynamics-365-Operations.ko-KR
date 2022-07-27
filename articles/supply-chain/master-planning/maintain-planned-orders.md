---
title: 계획된 주문 유지 관리
description: 이 토픽에서는 계획된 주문을 관리하는 방법에 대한 정보를 제공합니다. 계획된 주문의 상태를 업데이트하고 확정하고 선택한 계획 주문과 상태가 동일한 계획 주문을 필터링하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4ec4e50d37403107b31117912423b8bbc8ebb35
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448837"
---
# <a name="maintain-planned-orders"></a>계획된 주문 유지 관리

[!include [banner](../includes/banner.md)]

이 토픽에서는 계획된 주문을 관리하는 방법에 대한 정보를 제공합니다. 계획된 주문의 상태를 업데이트하고 확정하고 선택한 계획 주문과 상태가 동일한 계획 주문을 필터링하는 방법에 대해 설명합니다.

**기준 계획** 작업 영역, **계획된 주문** 목록 또는 **계획된 생산 주문**, **계획된 구매 주문** 및 **계획된 이전** 목록에서 계획된 주문을 관리할 수 있습니다. 

## <a name="planned-order-status"></a>계획된 주문 상태
**상태** 필드를 사용하여 진행 상황을 추적할 수 있습니다. 다음과 같은 값이 사용됩니다.

-   기준 계획이 계획 주문을 생성할 때 계획 주문의 상태는 **미처리** 입니다.
-   계획 주문을 확정하지 않기로 결정한 경우 **완료** 상태를 지정할 수 있습니다.
-   계획 주문을 확정하려는 경우 상태를 **승인됨** 으로 변경할 수 있습니다. **승인됨** 상태의 계획 주문은 기준 계획에서 준수하므로 이후 기준 계획 실행 중에 수정되거나 삭제되지 않습니다. 이를 달성하기 위해 계획 논리는 기준 계획 중에 이전 계획 버전에서 새 계획 버전으로 **승인된** 계획 주문을 복사합니다.

## <a name="firming-planned-orders"></a>계획 주문 확정 
계획 주문을 확정하면 실제 주문이 생성됩니다. *해제* 또는 *공개 주문* 이라고도 합니다. 계획 주문이 확정되면 해당 모듈의 주문 섹션으로 이동합니다.

**계획된 주문** 페이지에서 두 가지 확정 옵션을 선택할 수 있습니다.

-   **확정** - 하나 또는 여러 개의 선택된 계획 주문을 확정합니다.
-   **모두 확정** – 이렇게 하면 필터의 모든 계획 주문이 확정됩니다. **모두 확정** 을 사용하면 계획 주문을 선택할 필요가 없으며 필터 내의 모든 계획 주문이 확정됩니다. 이 옵션은 많은 수의 계획 주문을 확정하는 경우에 유용할 수 있습니다.

> [!NOTE]
> **계획된 주문 양식 > 보기 > 확정 내역** 의 **확정 내역** 에서 확정된 계획 주문을 추적할 수 있습니다.

## <a name="parallelize-firming"></a>병렬화 확정
동시에 많은 주문을 확정하려는 경우실행을 병렬화하면 실행 시간이 단축되고 성능이 향상될 수 있습니다. 이 옵션은 **확정** 또는 **모두 확정** 으로 여러 계획 주문을 확정할 때 사용할 수 있습니다. 다음과 같은 매개 변수를 사용할 수 있습니다.

-   **퍼밍 병렬화** – **예** 인 경우, 퍼밍 프로세스는 스레드 수에 정의된 **스레드 수** 와 병렬화됩니다.
-   **스레드 수** – 퍼밍 프로세스를 병렬화하는 데 사용되는 스레드 수를 제어합니다. 매개 변수는 **평행화 퍼밍** 이 **예** 로 설정된 경우에만 표시됩니다.

> [!NOTE]
> **확정 병렬화** 옵션은 확정을 위해 둘 이상의 계획 주문을 선택한 경우에만 표시됩니다.

## <a name="additional-resources"></a>추가 리소스

[마스터 플랜 개요](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]