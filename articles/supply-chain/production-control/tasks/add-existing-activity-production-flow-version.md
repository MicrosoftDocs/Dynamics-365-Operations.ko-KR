---
title: 생산 흐름 버전에 기존 활동 추가
description: 생산 흐름의 새 버전을 생성할 때 이전 버전용으로 생성된 활동을 새 버전에 추가하도록 선택할 수 있습니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f73274c6e102df3007793e027587793d87c4f83
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449203"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>생산 흐름 버전에 기존 활동 추가

[!include [banner](../../includes/banner.md)]

생산 흐름의 새 버전을 생성할 때 이전 버전용으로 생성된 활동을 새 버전에 추가하도록 선택할 수 있습니다. 이 절차는 활동을 복사하지 않고 기존 생산 흐름에 대해 새 버전을 만드는 방법을 보여줍니다. 다음 단계에서 기존 활동이 새 버전에 추가됩니다. 

이 작업에는 이미 생성된 버전 및 활동이 있는 생산 흐름이 필요합니다.


## <a name="create-a-new-production-flow-version"></a>새로운 생산 흐름 버전 만들기
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 편집을 클릭합니다.
5. 목록에서 선택한 행을 표시합니다.
6. 만료 날짜 필드에 날짜와 시간을 입력합니다.
    * 새 생산 흐름 버전을 생성하기 전에 활성 버전의 만료 날짜와 시간을 확인합니다. 선택한 버전의 만료 날짜에 연결되는 유효 시작 날짜로 새 버전이 생성됩니다.  
7. 추가를 클릭합니다.
8. 버전에서 복사 필드에서 아니요를 선택합니다.
    * 복사된 버전의 활동 대부분이 새 활동으로 대체될 경우 빈 버전으로 시작하려면 아니요를 선택합니다. 변경되지 않은 활동을 활동 양식의 기존 기능 추가에 수동으로 추가합니다.  
9. 칸반 규칙 복제 필드에서 아니요를 선택합니다.
    * 활동이 새 버전으로 복사되지 않으면 새 버전 생성 시 칸반 규칙을 복사할 수 없습니다.   대신 나중에 칸반 규칙 양식에서 대체 칸반 생성 기능을 사용하여 새 버전의 활동을 사용하여 이전 생산 흐름 버전의 칸반 규칙을 칸반 규칙으로 교체합니다.  
10. 확인을 클릭합니다.
11. 목록에서 원하는 레코드를 찾아 선택합니다.

## <a name="add-an-existing-activity"></a>기존 활동 추가
1. 활동을 클릭합니다.
2. 기존 항목 추가를 클릭하여 드롭 대화 상자를 엽니다.
    * 새 생산 흐름 버전에 추가할 기존 활동을 찾아 선택합니다.  목록에는 흐름의 모든 이전 버전에 대해 이 생산 흐름에 대해 생성된 모든 활동이 표시됩니다.  
3. 활동 필드에서 값을 입력하거나 선택합니다.
4. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]