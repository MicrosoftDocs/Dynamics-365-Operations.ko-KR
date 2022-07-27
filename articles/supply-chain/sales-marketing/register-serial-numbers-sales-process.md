---
title: 직렬화된 품목 작업
description: 이번에는 판매 절차 중 소포 명세서 또는 송장에 일련 번호를 등록하는 방법에 대해 설명합니다. 이 기능은 회사에서 서비스 및 보증 목적으로 일련 번호를 캡처하려고 하지만 입고에서 발행할 때까지 재고의 일련 번호를 유지할 필요가 없는 경우에 유용합니다.
author: Henrikan
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable, InventSerial
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62e53ec57a8d5c5c922f580219e4bde5338d0707
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448444"
---
# <a name="working-with-serialized-items"></a>직렬화된 품목 작업

[!include [banner](../includes/banner.md)]

이번에는 판매 절차 중 소포 명세서 또는 송장에 일련 번호를 등록하는 방법에 대해 설명합니다. 이 기능은 회사에서 서비스 및 보증 목적으로 일련 번호를 캡처하려고 하지만 입고에서 발행할 때까지 재고의 일련 번호를 유지할 필요가 없는 경우에 유용합니다.

많은 회사는 서비스 및 보증 목적으로 일련 번호를 캡처하기를 원하며 입고에서 발행할 때까지 재고의 일련 번호를 유지할 필요가 없습니다. 이러한 시나리오에서는 제품이 판매될 때 소포 명세서 또는 송장에 일련 번호를 등록할 수 있습니다. 나중에 제품이 반품된 경우 각 제품을 송장으로 추적하여 제품을 판매했는지와 서비스 또는 보증 의무가 유효한지를 확인할 수 있습니다.

**추적 치수 그룹** 페이지에서 **판매 절차에서 활성** 옵션을 선택하여 판매 절차에 대한 일련 번호를 활성화해야 합니다. 이후 Supply Chain Management에서 다음 이벤트가 발생합니다.
-   **일련 번호** 빠른 탭에서 **일련 번호 제어** 옵션이 선택됩니다. 이 옵션을 선택하면 소포 전표나 송장에 있는 각 품목에 대해 하나의 일련 번호를 등록해야 합니다.
-   **공백 문제 허용** 옵션을 제외하고 일련 번호에 대한 추적 치수 그룹의 모든 선택이 지워집니다. **공백 문제 허용** 옵션을 선택하여 일련 번호 제어를 무시하고 일련 번호를 등록하지 않고도 제품을 포장하고 송장 발행할 수 있습니다.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>판매 과정에서 일련 번호는 언제 등록합니까?
판매 주문의 소포 명세서 또는 송장에 일련 번호를 등록할 수 있습니다. 소포 명세서와 함께 배송된 일련 번호가 지정된 품목에 대한 송장을 준비할 때 송장을 작성할 소포 명세서의 일련 번호를 선택할 수 있습니다. 등록된 일련 번호의 수는 배송된 품목의 수량을 초과할 수 없습니다. 부분 송장을 생성하는 경우 소포 명세서에 등록된 것보다 적은 수의 일련 번호 품목을 선택할 수 있습니다. 소포 전표 또는 송장을 인쇄할 때 등록된 일련 번호가 포함됩니다.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>일련 번호를 스캔하여 입력할 수 있습니까, 아니면 직접 입력해야 합니까?
일련 번호를 스캔하거나 입력할 수 있습니다. 스캐너를 사용할 때 스캔 모드는 일련 번호가 송장 또는 소포 명세서의 일련 번호 목록에 추가 또는 제거되는지를 결정합니다. 예를 들어 휴대용 바코드 스캐너를 사용하여 일련 번호를 스캔하려면 일련 번호 뒤에 Enter 또는 TAB 명령을 보내도록 스캐너를 구성하세요. 이 명령은 데이터 스트림의 끝을 나타냅니다. 그렇지 않으면 각 일련 번호를 스캔한 후 키보드에서 Enter 또는 TAB 키를 눌러야 합니다.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>판매 절차에 대해 일련 번호를 활성화하면 모든 품목에 대해 모든 일련 번호를 등록해야 합니까?
제품에 할당된 추적 치수 그룹의 설정에 따라 소포 명세서 또는 송장의 모든 품목에 대해 일련 번호를 등록해야 하는지가 결정됩니다. 판매 절차에 대해 일련 번호를 활성화하면 **일련 번호 제어** 옵션이 자동으로 선택됩니다. 이후 소포 명세서 또는 송장의 각 품목에 대해 하나의 일련 번호를 등록하거나 읽을 수 없는 번호에 대해 공백 등록을 등록해야 합니다. 각 품목에 대한 일련 번호를 요구하지 않으려면 품목에 할당된 추적 치수 그룹에서 **공백 문제 허용** 옵션을 선택합니다. 이후 배송 중인 품목의 수량보다 적은 수의 일련 번호를 등록할 수 있습니다. 배송되는 품목의 수량보다 많은 일련 번호를 등록하면 소포 명세서 또는 송장을 전기할 수 없습니다.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>부분 송장 및 부분 배송에 대한 일련 번호를 등록할 수 있습니까?
판매 주문에 대한 부분 송장 및 소포 명세서를 생성하고 해당 송장 및 소포 명세서에 포함된 품목의 일련 번호만 등록할 수 있습니다. 부분 송장을 생성하고 판매 주문에 대해 둘 이상의 소포 명세서가 있는 경우 둘 이상의 소포 명세서에서 일련 번호를 포함할 수 있습니다. 그러나 모든 일련 번호가 포함되지 않은 소포 명세서는 하나만 있을 수 있습니다. 예를 들어, 3개의 소포 명세서가 있고 각 소포 명세서에 2개의 직렬화된 품목이 포함되어 있는 경우 각 소포 명세서에서 한 품목에 대한 부분 송장을 생성할 수 없습니다.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>일련 번호를 읽을 수 없는 경우 어떻게 해야 합니까?
일련 번호를 읽거나 스캔할 수 없는 경우 **일련 번호** 페이지에서 **읽을 수 없음** 을 클릭하여 품목에 대한 빈 줄을 만들 수 있습니다. 나중에 일련 번호를 사용할 수 있게 되면 송장 또는 소포 명세서를 업데이트할 수 있습니다. 자세한 내용은 다음 섹션 '판매 주문에 등록한 일련 번호를 수정하거나 변경할 수 있습니까?'를 참조하세요.

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>판매 주문에 등록한 일련 번호를 수정하거나 변경할 수 있습니까?
예, 다음 조건이 충족되는 경우 일련 번호를 수정할 수 있습니다.
-   **송장** – 아직 송장을 발행하지 않은 품목의 일련 번호를 변경할 수 있습니다. 이후 소포 명세서도 업데이트됩니다. 단, 판매 주문 라인이 음수 등록으로 수정된 경우 판매 주문 라인의 일련 번호를 변경할 수 없습니다.
-   **포장 명세서** – 일련번호가 지정된 품목이 포함된 포장 명세서 라인을 부분적으로 수정할 수 없습니다. 라인의 전체 수량을 취소해야 합니다. 소포 전표가 취소 또는 수정된 경우 동일한 일련 번호 품목에 대해 새 소포 전표를 만들 때 반전된 일련 번호를 다시 등록할 필요가 없습니다. 등록된 번호가 사용됩니다.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>특정 소포 명세서와 함께 배송되었거나 송장에 포함된 일련 번호를 볼 수 있습니까?
예, 소포 명세서 분개 라인 또는 송장 분개 라인에서 조회를 실행하여 문서에 포함된 모든 일련 번호 목록을 볼 수 있습니다.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>보유하고 있는 일련 번호를 확인할 수 있습니까?
아니요, 일련 번호는 품목이 판매될 때까지 품목에 등록되지 않기 때문에 보유하고 있는 일련 번호가 지정된 품목을 볼 수 없습니다.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>캐치웨이트 품목의 일련 번호를 등록할 수 있습니까?
아니요, 판매 절차 중에는 중량 품목에 대한 일련 번호를 등록할 수 없습니다. 또한 제품이 캐치-웨이트 품목으로 설정된 경우 판매 절차 중에만 일련 번호를 사용하도록 설정된 추적 치수 그룹에 제품을 할당할 수 없습니다.

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>소매 POS에서 일련 번호를 등록할 수 있습니까?

예, 소매 POS(판매 시점)는 사용자가 판매 절차 중에만 일련 번호를 사용하도록 설정된 추적 치수 그룹이 할당된 품목을 판매할 때 일련 번호를 입력하라는 메시지를 표시합니다.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>판매 과정에서 일련 번호를 등록하려면 어떤 보안 역할이 필요합니까?
이 기능은 판매 소포 명세서 및 판매 송장을 관리할 수 있는 모든 역할에 사용할 수 있습니다. 다음 임무를 통해 작업자는 일련 번호를 수정하고 읽거나 스캔할 수 없는 일련 번호에 대해 빈 품목을 등록할 수 있습니다.
-   일련 번호 수정 유지
-   읽을 수 없는 일련 번호의 등록 유지







[!INCLUDE[footer-include](../../includes/footer-banner.md)]