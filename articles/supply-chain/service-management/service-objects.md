---
title: 서비스 개체 개요
description: 이 토픽에서는 서비스 개체 작업 방법에 대한 개요를 제공합니다.
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad758d32c6e9de0758c6fddb57a7dea886ab73d4
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449782"
---
# <a name="service-objects-overview"></a>서비스 개체 개요

[!include [banner](../includes/banner.md)]

서비스 개체는 서비스를 수행할 수 있는 고객의 자산 및 제품입니다. 제공하는 서비스 유형에 따라 대상은 유형 또는 무형일 수 있습니다.

-  유형 개체는 물리적 서비스 작업을 수행할 수 있는 기계나 건물과 같은 것입니다.

    유형 서비스 개체는 출시된 제품 세부 정보 양식에서 생성하는 재고 항목일 수도 있습니다. 항목에 연결하는 재고 차원 그룹에 따라 항목 일련 번호를 포함하는 세부 정보 수준으로 서비스 개체를 생성할 수 있습니다. 이는 서비스 개체가 나타내는 정확한 항목을 추적해야 할 때 유용합니다.

    유형 서비스 개체는 회사의 직접 생산 또는 공급망과 직접 관련이 없는 항목일 수도 있습니다. 예를 들어 서비스 주문의 수리에 사용되는 도구 키트는 재고에 포함되지 않은 서비스 개체일 수 있습니다. 이 경우 재고 항목으로 등록하지 않습니다.

-  무형의 개체는 서비스 작업을 수행할 수 있는 계정 집합이나 법적 문서와 같은 비물리적 사물입니다.

## <a name="example-of-an-intangible-service-object"></a>무형 서비스 개체의 예

회사 A는 여러 소규모 회사의 재무 기록을 유지 관리합니다. A사의 고객 중 하나는 지역 축구팀이며 A사는 클럽 계정에 대한 주간 부기 및 연간 감사를 수행합니다. 클럽의 계정은 서비스 개체 양식으로 설정되고 서비스 계약의 개체로 지정됩니다. 개체에 대한 두 개의 서비스 계약 라인이 있습니다. 라인 1은 라인에 주간 간격이 할당된 주간 부기이고, 라인 2는 연간 간격이 할당된 연간 감사입니다.

## <a name="related-topics"></a>관련 토픽

[서비스 개체 생성](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]