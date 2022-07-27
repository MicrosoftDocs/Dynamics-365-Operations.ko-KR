---
title: 자산 서비스 수준
description: 이 항목에서는 자산 관리의 자산 서비스 수준에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/26/2019
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
ms.openlocfilehash: 5e4f7daa10931ce406a5d2bdbbc1dced067e3de5065cdb61cce369d617709d67
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446725"
---
# <a name="asset-service-levels"></a>자산 서비스 수준

[!include [banner](../../includes/banner.md)]

 

이 항목에서는 자산 관리의 자산 서비스 수준에 대해 설명합니다. 자산 서비스 수준은 자산과 관련되며 유지 관리 요청 및 작업 주문으로 전송됩니다. 작업 주문 예약 중에 작업 주문의 우선 순위를 계산하는 데 사용됩니다. 변경이 필요한 경우 자산 서비스 수준을 변경할 수 있습니다.

작업 주문 일정에 대한 평가 점수 계산과 관련된 설정에 대한 자세한 내용은 [자산 관리 매개 변수](../setup-for-objects/enterprise-asset-management-parameters.md)를 참조하세요. 자산 서비스 수준에 대해 하나 이상의 기본 레코드를 설정해야 합니다. 이 기본 레코드는 작업 주문 예약 중에 일치하는 다른 항목이 없는 경우 사용됩니다.

**예시 1:** 일치하는 다른 항목이 없는 경우 사용되는 기본 서비스 수준입니다. 이 레코드에서는 서비스 수준만 선택합니다.

**예시 2:** 볼보 트럭 엔진의 작업을 예약하는 데 사용되는 높은 서비스 수준입니다. 이 레코드에서 관련 자산 유형(예:**트럭 엔진**), 제조업체(**볼보**) 및 서비스 수준을 선택합니다.

## <a name="set-up-asset-service-levels"></a>자산 서비스 수준 설정

1. **자산 관리** \> **설정** \> **자산 서비스 수준** 을 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. 자산 서비스 수준에 필요한 세부 정보 수준에 따라 **기능 위치**, **자산 유형**, **제조업체**, **모델**, **자산**, **작업 주문 유형** 및 **서비스 수준** 필드에서 관련 항목을 선택합니다.

    > [!NOTE]
    > 자산 서비스 수준이 유지 관리 요청 및 작업 주문에 사용되는 경우 자산 관리는 모든 자산 서비스 수준 레코드를 검토하여 가능한 일치를 확인합니다. 항상 가장 구체적인 조합을 먼저 확인합니다. 즉, 자산 관리는 먼저 **작업 주문 유형** 필드와 일치하는지 확인합니다. 일치하는 항목이 없으면 **자산** 필드 등의 일치 항목이 있는지 확인합니다. **자산 서비스 수준** 페이지 레이아웃에서 볼 수 있듯이 이 동작은 가장 구체적인 조합을 찾기 위해 자산 관리가 각 레코드를 오른쪽에서 왼쪽으로 확인하여 일치하는지를 의미합니다. 일치하는 항목이 없으면 해당 필드에 선택 항목이 없는 기본 레코드가 사용됩니다.

4. **서비스 수준** 필드에서 서비스 수준(우선 순위)을 나타내는 숫자를 선택합니다.


> [!NOTE]
> 작업 주문에서 이미 사용한 후에 **자산 서비스 수준** 페이지에서 자산 서비스 수준 레코드를 변경하는 경우 유지 관리 요청 및 작업 주문에 대한 서비스 수준이 그에 따라 업데이트되지 않습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]