---
title: 회사 간 주문을 게시하기 위한 매개 변수 설정
description: 이 토픽에서는 회사 간 주문을 게시하기 위해 매개 변수를 설정하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: c728f2f491948ae1c8550396ba4d72f76f46fe85
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "8447739"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>회사 간 주문을 게시하기 위한 매개 변수 설정

[!include [banner](../../includes/banner.md)]

회사 간 고객 송장이 전기되면 회사 간 구매 주문과 최초 고객 송장을 모두 자동으로 전기하도록 설정할 수 있습니다.

> [!NOTE]
> 이 절차를 수행하기 전에 올바른 송장 프린터를 가리키도록 조직의 인쇄 관리를 설정하세요. 이렇게 하면 원래 판매 주문에 대한 송장이 올바른 프린터로 인쇄됩니다.

다음 매개 변수를 설정해야 합니다.

1. **영업 및 마케팅 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다. 작업할 판매 주문을 선택합니다.
1. 판매 주문의 작업 창에서 **헤더 보기** 를 선택한 다음 **회사 간 설정** 빠른 탭을 선택하고 엽니다.
1. 작업 창의 **판매 주문** 탭으로 이동한 다음 **편집** 을 선택합니다.
1. **회사 간 설정** 빠른 탭으로 돌아가서 **직접 배송** 을 선택하여 회사 간 체인(모든 주문) 전체에 직접 배송을 활성화합니다.
1. **저장** 을 선택하여 새 설정으로 판매 주문을 저장합니다. 그런 다음 **닫기** 를 선택하여 판매 주문을 마감합니다.
1. **조달 및 소싱 \> 공급업체 \> 공급업체 검색** 으로 이동합니다. **일반** 탭에서 **회사 간** 을 선택합니다.
1. **회사 간** 페이지에서 **구매 주문 정책** 링크를 선택합니다. **회사 간 구매 주문(직접 배송)** 필드 그룹에서 **자동으로 송장 전기** 를 선택하고 **자동으로 송장 인쇄** 필드에서 확인 표시를 제거합니다.
1. **원래 판매 주문(직접 배송)** 필드 그룹에서 **자동으로 송장 전기** 필드와 **자동으로 송장 인쇄** 필드를 선택합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
