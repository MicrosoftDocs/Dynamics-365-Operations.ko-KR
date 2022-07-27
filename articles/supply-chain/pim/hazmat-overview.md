---
title: 위험 물질 개요
description: 이 토픽에서는 제품 정보 관리 및 창고 관리 중 위험 물질 취급 및 기록과 관련된 기능에 대한 개요를 제공합니다.
author: t-benebo
ms.date: 06/10/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: cfea2cd6a2699bdf2a14de72a8bdeb3e8cd32a17
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449776"
---
# <a name="hazardous-materials-overview"></a>위험 물질 개요

[!include [banner](../includes/banner.md)]

운송 및 운송 규정을 계속 준수하기 위해 위험물로 분류된 자재를 운송하는 조직은 운송 시 추가 서류 작업을 포함해야 합니다. 위험 물질 기능을 통해 고객은 출시 품목과 관련된 정보를 저장할 수 있습니다. 그런 다음 이 정보를 사용하여 배송 문서를 준비할 수 있습니다. 위험 물질을 운송하는 조직은 운송 프로세스를 관리하기 위한 자체 프로세스와 절차를 가지고 있어야 합니다. Microsoft Dynamics 365 Supply Chain Management는 필요한 문서를 생성하는 데 도움이 되는 도구일 뿐입니다.

다음 다이어그램은 위험 물질 기능을 설정하고 사용하는 데 필요한 단계를 보여줍니다.

![위험 물질 기능을 설정하고 사용합니다.](media/hazmat-overview.png "위험 물질 기능 설정 및 사용")

위험 물질 기능은 제품 정보 관리에서 설정되며, 창고 관리를 통해 출력 가능한 문서를 제공합니다. 따라서 일반적으로 해당 영역은 이 기능의 기능을 검토, 설정 및 사용할 두 가지 주요 영역입니다.

- **상품 정보 관리** – 출고된 제품에 적용될 코드를 설정합니다.
- **창고 관리** – 배송을 위해 인쇄될 추가 배송 문서를 작업합니다.

> [!IMPORTANT]
> Supply Chain Management의 위험 물질 기능은 유해 제품과 관련된 정보를 기록하고 참조하는 데 도움이 되는 유용한 제품 정보 필드 및 관련 기능 모음을 제공합니다. 이러한 기능은 또한 배송하는 모든 위험 물질에 대한 동일한 정보가 포함된 배송 문서를 디자인하고 인쇄하는 데 도움이 될 수 있습니다. 그러나 시스템이 자동으로 해당 국가 또는 지역의 모든 관련 규정을 준수하도록 유도하지는 않습니다. 이러한 도구는 일반적인 규정을 준수하는 데 도움을 주기 위한 것이지만 그 자체로는 충분하지도 않고 보장되지도 않습니다. 귀하의 조직은 모든 해당 규정을 인지하고 이를 준수하기 위해 필요한 모든 조치를 취할 책임이 있습니다.

## <a name="product-information-management"></a>제품 정보 관리

제품 정보 관리는 육로, 항공, 해상 화물에 대한 다양한 위험물 목록에 대한 참조 정보를 입력할 수 있는 다양한 설정 테이블을 제공합니다.

이 기능이 개발될 때 다음과 같은 공통 규정이 참조되었습니다.

- **ADR** – 육로를 통한 위험물의 국제 운송과 관련된 규정
- **CFR 49** – 위험물 운송에 대한 미국 규정
- **IMDG** – 국제 해양 위험물(IMDG) 코드
- **IATA** – 국제항공운송협회(IATA) 위험물 규정

각 규정 집합은 위험 물질 및 참조 코드의 표준화된 목록을 제공합니다. 따라서 Supply Chain Management는 해당 목록의 공통 코드에 대한 참조 테이블을 제공합니다. 각 목록에는 정의할 수 있는 고유 코드도 있습니다.

유해 물질에 대한 규정 및 값을 설정하는 방법과 관련 제품에 값을 할당하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

- [위험 물질 설정](hazmat-setup.md)
- [제품, 주문, 배송 및 화물 내 위험 물질](hazmat-items.md)

## <a name="warehouse-management"></a>창고 관리

창고 관리에서 배송을 준비할 때 제품 정보 관리에서 설정한 정보를 사용하는 몇 가지 새로운 보고서를 인쇄할 수 있습니다. 사용 가능한 보고서 및 사용 방법에 대한 자세한 내용은 [위험 물질 문의 및 보고서](hazmat-reports.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]