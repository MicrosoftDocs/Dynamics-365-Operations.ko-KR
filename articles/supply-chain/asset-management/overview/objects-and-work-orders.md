---
title: 자산 및 작업 주문
description: 이 항목에서는 자산 관리의 자산 및 작업 주문에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a2872dc84ec11ae7fad9fd5b225b9207f13280db334cc0d010a3d6749a591ee2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446677"
---
# <a name="assets-and-work-orders"></a>자산 및 작업 주문

[!include [banner](../../includes/banner.md)]

 

이 항목에서는 자산 관리의 자산 및 작업 주문에 대해 설명합니다. 자산 및 작업 주문은 자산 관리의 핵심 부분입니다. *자산* 은 지속적인 유지 보수 및 서비스가 필요한 기계 또는 기계 부품입니다. 자산은 계층 구조로 생성될 수 있으며 기능적 위치와 관련될 수 있습니다. 자산 구조의 모든 수준에서 유지 관리 작업을 계획할 수 있습니다.

제품 정보, 자산 사양 등 다양한 데이터와 필요한 유지 관리 계획이 자산별로 설정됩니다. 다음 그림은 자산 데이터의 개요와 작업 유형에 대한 자산의 제휴를 보여줍니다. 빨간색 텍스트는 상속 및 종속성을 보여주는 예에 사용됩니다.

![작업 유형과 관련된 자산 데이터를 보여주는 다이어그램.](media/05-overview-image.png)

모든 작업 주문에는 예방 유지 관리, 수정 유지 관리 또는 검사와 같은 작업 주문 유형이 있습니다. 작업 주문에는 하나 이상의 작업 주문 작업이 포함되어 있습니다. 모든 작업 주문 작업은 자산 및 관련 작업 유형에 대해 수행해야 하는 작업을 정의합니다. 관련 직무 유형의 예로는 10,000km, 50,000km, 1년 오버홀, 안전 점검 등이 있습니다. 하나의 작업 주문은 여러 자산과 관련될 수 있습니다.

다음 그림은 작업 주문의 주요 데이터에 대한 개요를 보여줍니다.

![작업 주문의 주요 데이터를 보여주는 다이어그램.](media/06-overview-image.png)

작업 주문은 다른 작업 주문과 관련될 수 있으며 작업 유형에는 작업 주문을 생성하는 후속 작업이 포함될 수 있습니다. 일반적으로 작업 주문 간에는 종속성이 없습니다. 따라서 작업 주문 수명 주기 상태를 변경할 수 있고 서로 독립적으로 예약할 수 있습니다.

작업 주문은 수정, 예방 또는 사후 유지 관리와 관련된 다양한 방법으로 생성할 수 있습니다. 작업 주문을 수동으로 생성할 수도 있습니다. 다음 그림은 작업 주문의 자동 또는 수동 생성 프로세스에 대한 개요를 보여줍니다.

![작업 주문의 자동 또는 수동 생성을 보여주는 다이어그램.](media/07-overview-image.png)

작업 주문에 대한 유지 관리 작업을 예약하고 실행하려면 여러 단계를 완료해야 합니다. 다음 그림은 작업 주문 처리의 개요를 보여줍니다.

![작업 주문 처리 개요를 보여주는 다이어그램.](media/08-overview-image.png)

> [!NOTE]
> 일반적으로 Dynamics 365 Supply Chain Management 및 **자산 관리 모듈** 에서 작업할 때 **새로 만들기** 를 선택하여 새 레코드를 만들고 **편집** 을 선택하여 기존 레코드를 업데이트하고 **저장** 을 선택하여 새 데이터나 편집된 데이터를 저장합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]