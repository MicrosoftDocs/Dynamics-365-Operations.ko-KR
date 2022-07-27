---
title: 유지 관리 일정
description: 이 토픽에서는 자산 관리의 유지 관리 일정에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 40df8e6cba824f90e13b46cc258c76bef993a3e2dd9c35566d8c6a622ce4eb09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446854"
---
# <a name="maintenance-schedule"></a>유지 관리 일정

[!include [banner](../../includes/banner.md)]

 

유지 관리 일정에는 예상되는 모든 예방적 유지 관리 계획, 유지 관리 요청 및 수행할 유지 관리 라운드의 목록이 포함됩니다. 일부 일정 라인은 작업 주문으로 변환되었을 수 있습니다.

4개의 유지 관리 일정 보기는 보고자 하는 유지 관리 일정 라인에 따라 약간 다릅니다.

| 메뉴 항목                  | 콘텐츠 설명                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 모든 유지 관리 일정       | 모든 유지 관리 일정 라인이 표시됩니다.     |
| 내 자산 일정        | 작업자와 관련된 기능 위치에 설치된 자산을 포함하는 모든 유지 관리 일정 라인([유지 관리 작업자 및 작업자 그룹](../setup-for-objects/workers-and-worker-groups.md)에서 설정)이 이 목록에 표시됩니다. |
| 공개 유지 관리 일정 라인 | 상태가 "생성됨"인 유지 관리 일정 라인(아직 작업 주문으로 변환되지 않았거나 폐기됨을 의미)이 이 목록에 표시됩니다.                                            |
| 공개 유지 관리 일정 풀 | 작업 주문 풀과 관련된 유지 관리 일정 라인이 이 목록에 표시됩니다.                                                                                                                  |

>[!NOTE]
>유지 관리 일정 라인이 여러 작업 주문 풀([작업 주문 풀](../work-orders/work-order-pools.md) 참조)에 포함된 경우 **공개 유지 관리 일정 풀** 의 각 풀에 대해 하나의 레코드가 표시됩니다. 이는 작업 주문 풀에 대한 필터링 옵션을 최적화하기 위해 수행됩니다.

유지 관리 일정을 열려면:

1. **자산 관리** > **공통** > **유지 관리 일정** > **모든 유지 관리 일정** 또는 **유지 관리 일정 라인 열기** 또는 **유지 관리 일정 풀 열기** 를 클릭합니다.

2. 유지 관리 일정을 업데이트하려면 **유지 관리 계획** 또는 **유지 관리 라운드** 를 클릭합니다. 

3. 유지 관리 일정 라인을 선택하고 **편집** 을 클릭하여 편집할 수 있습니다. 예를 들어 서비스 수준이나 작업을 담당하는 작업자를 쉽게 업데이트할 수 있습니다. 아직 작업 주문에 연결되지 않은 유지 관리 일정 라인만 편집할 수 있습니다.

4. 목록 페이지에서 유지 관리 일정 라인을 선택하고 **삭제** 를 클릭하여 삭제할 수 있습니다.

5. 목록 페이지에서 유지 관리 일정 라인을 선택하고 **폐기** 를 클릭하여 폐기할 수 있습니다. 이 기능은 예를 들어 자산에 2,000km 유지 관리 계획과 10,000km 유지 관리 계획이 있는 경우에 유용합니다. 그런 다음 10,000km, 20,000km, 30,000km 등과 일치하는 경우 2,000km 유지 관리 계획에서 생성된 선을 버릴 수 있습니다. 유지 관리 계획과 관련된 유지 관리 일정 라인을 버리면 해당 유지 관리 계획이 예약될 때 해당 라인은 다시는 나타나지 않습니다.

6. 선택한 모든 라인을 동일한 작업 주문 풀에 포함시키려면 **모든 유지 관리 일정** 에서 여러 유지 관리 일정 라인을 선택하고 **작업 주문 풀** 을 클릭할 수 있습니다.

7. **모든 유지 관리 일정** 또는 **유지 관리 일정 라인 열기** 또는 **유지 관리 일정 풀 열기** 에서 여러 유지 관리 일정 줄을 선택하고 여러 줄에 대해 동일한 조정을 수행하려는 경우 **일정 조정** 을 클릭할 수 있습니다. 선택한 유지 관리 일정 라인과 관련된 예상 시작 및 종료 일자, 서비스 수준, 책임 유지 관리 작업자 그룹 또는 담당 유지 관리 작업자를 변경할 수 있습니다.

- 유지 관리 일정 라인이 작업 주문과 관련된 경우 작업 주문 ID가 **작업 주문** 필드에 표시됩니다.  
- **모든 자산** 세부 정보 보기 > **자산 유지 관리 계획** 빠른 탭에서 자산에 대한 유지 관리 계획을 선택할 수 있습니다. 나중에 **모든 자산** 에서 자산과 관련된 유지 관리 계획 라인을 삭제하는 경우 해당 유지 관리 계획을 기반으로 생성된 상태가 "생성됨"인 모든 유지 관리 일정 라인도 자동으로 삭제됩니다. [자산 생성](../objects/create-an-object.md)도 참조하세요.

아래 그림은 모든 **유지 관리 일정** 목록 페이지를 보여줍니다.

![자료 1.](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]