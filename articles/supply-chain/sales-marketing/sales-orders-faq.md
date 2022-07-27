---
title: 판매 주문에 대해 자주 묻는 질문
description: 이 페이지는 Dynamics 365 Supply Chain Management에서 판매 주문을 처리할 때 나오는 자주 묻는 질문을 다룹니다.
author: Henrikan
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cee75b1d740e7cb414c674157dde0146e8faa50
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448438"
---
# <a name="sales-order-faqs"></a>판매 주문 FAQ

이 페이지는 Dynamics 365 Supply Chain Management에서 판매 주문을 처리할 때 나오는 자주 묻는 질문을 다룹니다.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>수요를 충족시키기 위해 구매 주문을 판매 주문에 연결할 수 있습니까?

판매 주문에서 구매 주문을 생성할 수 있습니다. 자세한 내용은 [판매 주문에서 구매 주문 만들기](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order)를 참조하세요.

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>판매 주문 또는 반품 주문을 취소하거나 삭제할 수 있나요?

*생성됨* 상태인 판매 주문 및 반품 주문만 취소할 수 있습니다. 자세한 내용은 [반품 주문 취소](/dynamics365/supply-chain/service-management/cancel-return-order)를 참조하세요.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>삭제된 송장 청구된 판매 주문을 복원할 수 있습니까?

송장 발행된 판매 주문이 실수로 삭제된 경우 복원하거나 세부 정보를 볼 수 있습니다.

**고객 계정 \> 거래 \> 원본 문서 \> 세부 정보 보기** 로 이동합니다. 찾고 있는 송장을 찾고 선택하여 세부 정보를 봅니다. 이러한 세부 정보에는 판매 주문 참조가 포함됩니다. 또한 해당 페이지에서 판매 주문 세부 정보에 액세스할 수 있어야 합니다.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>분리된 판매 주문 레코드를 삭제하려면 어떻게 하나요?

분리된 판매 주문 레코드를 정리하려면 다음 위치 중 하나로 이동하여 *판매 주문 삭제* 정기 작업을 실행합니다.

- 영업 및 마케팅 \> 정기 작업 \> 정리 \> 판매 주문 삭제
- 소매 및 상거래 \> 소매 및 상거래 IT \> 정리 \> 판매 주문 삭제

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>이미 게시된 송장에 대한 수수료를 계산하는 방법이 있습니까?

Supply Chain Management는 현재 게시된 송장에 대한 수수료 계산을 지원하지 않습니다.
