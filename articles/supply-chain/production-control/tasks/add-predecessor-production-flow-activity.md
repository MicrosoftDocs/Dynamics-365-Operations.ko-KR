---
title: 생산 흐름 활동에 선행 작업 추가
description: 생산 흐름 버전에서 모든 활동은 순서가 지정되어야 합니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc1aa742013faeeb545d746f9715c639a5b66b9b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448786"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>생산 흐름 활동에 선행 작업 추가

[!include [banner](../../includes/banner.md)]

생산 흐름 버전에서 모든 활동은 순서가 지정되어야 합니다. 활동에는 하나 이상의 선행 작업 또는 후속 작업이 있을 수 있습니다. 

이 절차는 선행 작업을 활동에 연결하는 방법을 보여줍니다. 

이 작업을 수행하려면 연결할 수 있는 활동이 두 개 이상 있는 초안 버전이 있는 생산 흐름이 필요합니다. 

자세한 내용은 백서 "린 제고의 생산 흐름 및 활동"을 참조하세요.


## <a name="find-the-production-flow-and-version"></a>생산 흐름 및 버전 찾기
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. 활동을 클릭합니다.

## <a name="select-an-activity-and-add-a-predecessor"></a>활동 선택 및 선행 작업 추가
1. 목록에서 원하는 레코드를 찾아 선택합니다.
2. 선행 작업 추가를 클릭합니다.
3. 활동 필드에서 값을 입력하거나 선택합니다.
4. 주기 시간 비율 필드에 숫자를 입력합니다.
    * 활동 관계의 기본 주기 시간 비율은 1입니다. 이는 두 활동이 동일한 페이스 또는 작업 단위당 소요 시간으로 실행된다고 가정합니다. 선행자가 더 높은 페이스(낮은 작업 단위당 소요 시간)로 달리는 경우 비율은 1보다 작아야 하고, 선행자가 더 느린 페이스(높은 작업 단위당 소요 시간)에서 달리는 경우 주기 시간 비율은 1보다 커야 합니다.  
5. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]