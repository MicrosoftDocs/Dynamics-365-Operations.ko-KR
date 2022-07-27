---
title: 회사 간 고객 송장에 대한 지급 자동 등록
description: 이 토픽에서는 회사 간 고객 송장에 대한 지급을 자동으로 등록하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: ffc5c7bf44989fbcc18e940b5a7c9df81260d770
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447760"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>회사 간 고객 송장에 대한 지급 자동 등록

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management는 회사 간 고객 송장이 전기될 때 고객 트랜잭션을 생성합니다. 이 고객 거래는 결제가 완료될 때까지 열려 있습니다. 해당 회사 간 구매 주문이 송장 업데이트되면 고객 트랜잭션과 일치하는 공급업체 트랜잭션이 생성됩니다. 이 공급업체 거래도 결제될 때까지 열려 있습니다. 차액의 위험을 줄이기 위해 지급 계정 결제 분개가 전기될 때 지급 계정 지급 분개가 자동으로 생성되고 전기될 수 있습니다.

1. **영업 및 마케팅 \> 고객 \> 모든 고객** 으로 이동합니다.
1. 작업 창의 **일반** 탭에서 **회사 간** 을 선택합니다.
1. 판매 주문에 대한 **회사 간** 거래 페이지에서 회사 간 AR 지급을 설정하려면 **판매 주문 정책** 링크를 선택합니다.
1. **지급 분개** 필드에서 회사 간 공급업체 지급을 등록할 수취 계정 지급 분개를 선택합니다. **수취 계정 매개 변수** 페이지에서 설정합니다.
1. 이 분개장에 자동으로 전기하려면 **자동으로 분개장 전기** 확인란을 선택합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
