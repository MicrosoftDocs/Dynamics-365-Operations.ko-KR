---
title: 자산 중요도 유형
description: 이 항목에서는 자산 관리의 자산 중요도 유형에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9edf55c22375a66fda04ae7ff76d7a0a191140e5ffb3a377b9ac1a7ba604a8d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447277"
---
# <a name="asset-criticality-types"></a>자산 중요도 유형

[!include [banner](../../includes/banner.md)]

 

이 항목에서는 자산 관리의 자산 중요도 유형에 대해 설명합니다. 자산 중요도는 자산과 관련되며 작업 주문으로 전송됩니다. 작업 주문에서는 변경할 수 없습니다. 자산 중요도는 작업 주문 일정 중 작업 주문 중요도를 계산하는 데 사용됩니다. 즉, 자산의 유지 관리 작업이 회사의 생산 일정과 생산성에 영향을 미치는 정도를 계산하는 데 사용됩니다. 작업 주문 일정에 대한 평가 점수 계산과 관련된 설정에 대한 자세한 내용은 [자산 관리 매개 변수](../setup-for-objects/enterprise-asset-management-parameters.md)를 참조하세요.

중요도를 설정하려면 먼저 자산 설정에 사용해야 하는 중요도 유형을 생성합니다. 그런 다음 자산 중요도를 설정합니다.

## <a name="set-up-criticality-types"></a>중요도 유형 설정

1. **자산 관리** \> **설정** \> **자산** \> **중요도 유형** 을 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. **중요도** 필드에 중요도를 나타내는 숫자를 입력합니다.
4. **이름** 필드에 중요도 유형의 이름을 입력합니다.
5. **계수** 필드에서 계수를 입력합니다. 이 요소는 작업 주문 일정을 계산하는 동안 사용해야 하는 중요도 레코드를 결정하는 데 사용됩니다. (요소가 가장 높은 레코드가 항상 사용됩니다.) 이 설정은 다음 그림과 같이 동일한 중요도 값을 갖는 중요도 라인이 생성되는 경우에 적합합니다.

    ![중요도 유형 페이지.](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>자산 중요도 설정

1. **자산 관리** \> **설정** \> **자산 중요도** 를 선택합니다.
2. **새로 만들기** 를 선택하여 레코드를 만듭니다.
3. 자산 중요도에 필요한 세부 정보 수준에 따라 **기능 위치**, **자산 유형**, **제조업체**, **모델**, **자산**, **작업 유형 범주**, **작업 유형**, **작업 유형 변형** 및 **작업 요구 사항** 필드에서 관련 항목을 선택합니다.

    > [!NOTE]
    > 자산 중요도가 선택되면 자산 관리는 모든 자산 중요도 레코드를 검토하여 가능한 일치를 확인합니다. 항상 가장 구체적인 조합을 먼저 확인합니다. 즉, 자산 관리는 먼저 **작업 요구 사항** 을 확인합니다. 일치하는 항목이 없으면 **작업 유형 변형** 을 확인합니다. 일치하는 항목이 없으면 **작업 유형** 등을 확인합니다. 페이지 레이아웃에서 볼 수 있듯이 이 동작은 가장 구체적인 조합을 찾기 위해 자산 관리가 각 레코드를 오른쪽에서 왼쪽으로 확인하여 일치하는지를 의미합니다. 일치하는 항목이 없으면 선택 항목이 없는 "기본" 레코드가 사용됩니다.

4. **중요도** 필드에서 이전 절차에서 생성한 중요도 값 중 하나를 선택합니다.

### <a name="notes-about-criticality-setup"></a>중요도 설정에 대한 참고 사항

- 작업 주문에서 이미 자산을 사용한 후 이 설정에서 자산 중요도를 변경하면 작업 주문의 중요도가 그에 따라 업데이트되지 않습니다.
- 작업 주문에 대한 중요도는 작업 주문 라인이 작업 주문에 추가되거나 삭제될 때마다 다시 계산됩니다.
- 작업 주문이 여러 작업 주문 작업을 포함하는 경우 **중요도 유형** 페이지의 **계수** 필드에 따라 가장 높은 중요도가 항상 작업 주문에 사용됩니다.
- 일반적으로 자산 중요도는 일정 기간 동안 변경될 수 있습니다. 중요도는 새 장비 구입, 수리 등의 영향을 받을 수 있습니다. 자산 중요도를 정기적으로(예: 1년에 한 번 또는 격년으로) 재평가하여 중요도 정의가 현재 프로덕션 설정과 일치하는지 확인하세요.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]