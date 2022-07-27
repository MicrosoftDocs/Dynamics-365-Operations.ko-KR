---
title: 생산 주문 상태 되돌리기
description: 이 토픽에서는 생산 주문 상태를 되돌리는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmStatusDecrease, ProdSetupStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0dd17bc48bfb6c78e1baca4faf78d6bc5b3ce426c5f0530174eccd95536a5859
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447124"
---
# <a name="reverse-the-production-order-status"></a>생산 주문 상태 되돌리기

[!include [banner](../includes/banner.md)]

이 토픽에서는 생산 주문 상태를 되돌리는 방법에 대해 설명합니다. 

생산 주문의 상태를 되돌리면 해당 경로와 연관된 주문 및 모든 작업이 생산 라이프 사이클의 이전 단계로 되돌아갑니다. 예를 들어 생산 주문의 상태가 **예약됨** 이고 상태를 다시 **생성됨** 으로 변경합니다. 이 경우 시스템은 먼저 상태를 **예정됨** 으로 변경해야 합니다. 이 상태는 **예약됨** 바로 앞의 상태입니다. 그런 다음 상태를 원하는 상태인 **생성됨** 으로 변경할 수 있습니다. **참고:** 주문이 **완료로 보고됨** 상태인 경우에도 이전 상태로 되돌릴 수 있습니다. 그러나 주문에 대한 정보를 업데이트하려면 견적 및 작업 예약, 작업 예약 또는 두 가지 예약 유형을 모두 다시 실행해야 합니다. 이 단계는 남은 품목 소비 및 작업 리소스 소비에 대한 모든 예약도 재설정해야 하기 때문에 필요합니다. 이 문서의 나머지 부분에서는 다음과 같은 방법으로 생산 주문 상태를 취소할 때 발생하는 상황에 대해 설명합니다.

-   **예상됨** 에서 **생성됨** 까지
-   **예약됨** 에서 **예상됨** 까지
-   **릴리스됨** 에서 **예약됨** 까지
-   **시작됨** 에서 **릴리스됨** 까지

## <a name="from-estimated-to-created"></a>예상됨에서 생성됨까지
생산 주문의 상태를 **예상됨** 에서 **생성됨** 으로 되돌리면 BOM(자재 명세서)의 품목에 대해 계산된 품목 소비가 제거됩니다. 생산 라인의 재고 트랜잭션이 삭제되고 생산 주문의 BOM 라인에 있는 **남은 상태** 필드가 **종료됨** 으로 재설정됩니다. **파생 구매** 및 **파생 생산** 옵션을 선택하면 기본 구매 주문 또는 생산 주문이 삭제됩니다. 생산 주문의 비용을 추정했거나 생산에 사용할 수 있도록 항목을 수동으로 예약한 경우 해당 트랜잭션이 제거됩니다.

## <a name="from-scheduled-to-estimated"></a>예약됨에서 예상됨까지
생산 주문의 상태를 **예약됨** 에서 **예상됨** 으로 되돌리면 예약된 시작 및 종료 날짜와 시간이 제거됩니다. 스케줄링 중에 예약된 용량이 제거되고 작업 예약 중에 생성된 작업이 삭제됩니다. **생산 주문 세부 정보** 페이지에 작업 일정 및 작업 일정에 대해 기록된 모든 정보가 재설정됩니다.

## <a name="from-released-to-scheduled"></a>릴리스됨에서 예약됨까지
생산 주문의 상태를 **릴리스됨** 에서 **예약됨** 으로 되돌릴 때 발생하는 유일한 변경 사항은 상태 필드의 값입니다.

## <a name="from-started-to-released"></a>시작됨에서 릴리스됨까지
생산 주문의 상태를 **시작됨** 에서 **릴리스됨** 으로 되돌리면 완료된 것으로 보고된 모든 항목이 되돌려집니다. 자재가 피킹되었거나 인바운드 및 아웃바운드 납품이 생산으로 이루어진 경우 해당 설정이 되돌려집니다. 생산 주문의 BOM 라인에 있는 **남은 상태** 필드가 **종료됨** 에서 **자재 소비** 로 변경됩니다. 시간이 등록되었거나 생산 경로의 작업이 완료된 것으로 수량이 보고된 경우 해당 설정이 반대로 됩니다. **남은 상태** 필드는 생산 경로에서 **완료됨** 에서 **경로 소비** 로 변경됩니다. 재공품 또는 재공품으로 게시된 모든 항목에 대한 설정이 반전됩니다. **생산 주문 세부 정보** 페이지에서 시작되었거나 완료된 것으로 보고된 수량을 표시하는 필드가 재설정됩니다. 해당 거래의 날짜도 재설정됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]