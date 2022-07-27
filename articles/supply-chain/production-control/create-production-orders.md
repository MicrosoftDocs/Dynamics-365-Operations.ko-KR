---
title: 생산 주문 수명 주기 개요
description: 생산 오더가 생성되면 품목 생산을 시작하기 위한 요청이 시작됩니다. 생산 오더에는 생산할 제품, 생산 수량 및 계획된 완료 날짜에 대한 정보가 포함됩니다. 또한 소비할 재료와 품목을 생산하기 위해 따라야 할 프로세스에 대한 정보도 포함되어 있습니다.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19741"
- intro-internal
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4c3632d644070f064ec70d3dd7c0d480927eafe
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449671"
---
# <a name="production-order-lifecycle-overview"></a>생산 주문 수명 주기 개요

[!include [banner](../includes/banner.md)]

생산 오더가 생성되면 품목 생산을 시작하기 위한 요청이 시작됩니다. 생산 오더에는 생산할 제품, 생산 수량 및 계획된 완료 날짜에 대한 정보가 포함됩니다. 또한 소비할 재료와 품목을 생산하기 위해 따라야 할 프로세스에 대한 정보도 포함되어 있습니다.

생산 오더는 생산 라이프 사이클의 단계를 거칩니다. 주문이 생성되면 **생성됨** 상태가 할당됩니다. 주문이 완료되면 **종료됨** 상태가 할당됩니다. 각 단계의 매개 변수 설정을 통해 사용자는 각 단계를 구성할 수 있습니다. 단일 사용자 또는 모든 사용자에 대해 설정을 지정할 수 있습니다.

생산 BOM과 생산 경로는 생산 오더의 주요 요소입니다. 선택한 품목과 생산할 수량을 기준으로 생산 오더에 복사됩니다. 생산 오더가 시작되기 전에 생산 BOM 및 경로를 편집할 수 있습니다.

다음 시나리오에서 생산 오더를 생성할 수 있습니다.

-   자재 수요를 기반으로 기준 계획 실행에 의해 생성됩니다.
-   판매 주문 라인에서 직접 생성되거나 더 높은 수준의 생산 주문이 생성 및 추정될 때 생성됩니다(공급 페깅).
-   수동으로 생성되었습니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]