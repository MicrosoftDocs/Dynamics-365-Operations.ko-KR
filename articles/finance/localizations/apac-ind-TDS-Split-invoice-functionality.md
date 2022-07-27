---
title: 인보이스 분할 기능
description: 이 토픽에서는 배송 주소 및 세금 계정 번호(TAN)별로 송장을 분할하기 위한 설정 및 기능에 대해 설명합니다.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f9bb4db14cbb7c9abb33ccee532ed73b378317bb
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451846"
---
# <a name="split-invoice-functionality"></a>인보이스 분할 기능

[!include [banner](../includes/banner.md)]

이 토픽에서는 배송 주소 및 세금 계정 번호(TAN)별로 송장을 분할하기 위한 설정 및 기능에 대해 설명합니다.

**지급 계정 매개 변수** 페이지의 **일반** 탭에서 **제품 영수증** 또는 **송장** 확인란을 선택하여 **구매 주문** 페이지에서 서로 다른 배송 주소와 TAN을 가진 제품 영수증이나 송장을 전기하고 분할합니다. 전기된 송장은 배송 주소와 TAN에 따라 나뉩니다.

**요약 업데이트** 탭의 **분할 기준** 빠른 탭, **배송 정보** 행에서 **확인**, **불출 목록**, **포장 전표** 또는 **송장** 옵션을 **예** 로 설정하여 **판매 주문** 페이지의 다른 송장 라인에 대해 다른 배송 주소와 TAN이 정의된 확인, 불출 목록, 포장 전표 또는 송장을 전기하고 분할합니다. 송장은 먼저 배송 주소별로 분할된 다음 TAN별로 분할됩니다.

> [!IMPORTANT]
> - **배송 정보** 옵션이 **예** 로 설정되지 않은 경우 송장은 단일 송장으로 전기됩니다. 송장 분할이 발생하지 않습니다.
> - 송장 라인에 배송 주소와 TAN이 다른 포장 전표를 분할하여 전기하려면 **배송 정보** 에 대한 **포장 전표** 옵션을 **예** 로 설정해야 합니다.
> - 송장 라인에 배송 주소와 TAN이 다른 송장을 분할하여 전기하려면 **배송 정보** 에 대한 **송장** 옵션을 **예** 로 설정해야 합니다.
> - 송장 라인의 배송 주소는 다르지만 TAN은 동일한 송장을 전기하려면 **배송 정보** 에 대한 **송장** 옵션을 **아니요** 로 설정합니다. 송장은 배송 주소로 분할됩니다.

## <a name="example"></a>예

이 예에서 **배송 정보** 에 대한 **송장** 옵션은 **지급 계정 매개 변수** 페이지의 **요약 업데이트** 탭에서 **예** 로 설정됩니다. 라인의 배송 주소 및 TAN에 대해 다음 설정이 포함된 구매 송장이 전기됩니다.

- **품목 라인 1:** 배송 주소 1, TAN-ABCD12345A
- **품목 라인 2:** 배송 주소 1, TAN-ABCD12345A
- **품목 라인 3:** 배송 주소 2, TAN-ABCE12345B
- **품목 라인 4:** 배송 주소 3, TAN-ABCD12345A

이 경우 원본 송장은 두 개의 송장으로 분할되어 다음과 같은 방식으로 전기됩니다.

- 두 라인 모두 동일한 납품 주소와 TAN을 갖고 있기 때문에 송장 1은 품목 라인 1과 품목 라인 2에 대해 전기됩니다.
- 송장 2는 품목 라인 3에 대해 전기됩니다.
- 송장 3는 품목 라인 4에 대해 전기됩니다.
