---
title: 회사 간 배치 및 일련 번호
description: 이 토픽에서는 회사 간 주문에 대한 배치 번호 및 일련 번호를 등록할 때 발생하는 상황에 대해 설명합니다.
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447775"
---
# <a name="intercompany-batch-and-serial-numbers"></a>회사 간 배치 및 일련 번호

[!include [banner](../../includes/banner.md)]

일련 번호 또는 배치 번호를 사용하여 항목을 추적하는 회사는 피킹된 항목의 일련 번호와 배치 번호도 추적해야 합니다. 회사 간 기능은 한 회사에서 다른 회사로 일련 번호 및 배치 번호의 푸시/풀을 자동화합니다. 회사 간 판매 주문의 항목에 대한 배치 번호와 일련 번호를 등록할 때 이 번호를 회사 간 구매 주문 및 최초 판매 주문에 자동으로 푸시하도록 프로그램을 설정할 수 있습니다. 판매 주문에 대한 **회사 간** 페이지에서 관련 매개 변수를 설정합니다.

- **판매 주문 정책** 페이지에서 **배치 번호** 필드를 선택하면 회사 간 판매 주문의 포장 전표를 전기할 때 배치 번호가 회사 간 구매 주문 라인의 재고 트랜잭션과 동기화됩니다.
- **일련 번호** 필드를 선택하면 회사 간 판매 주문의 포장 전표를 전기할 때 회사 간 구매 주문 라인의 재고 트랜잭션에 일련 번호가 동기화됩니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
