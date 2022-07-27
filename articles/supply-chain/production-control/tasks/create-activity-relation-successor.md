---
title: 활동 관계 생성 - 후임자
description: 린 생산 흐름에서 활동의 흐름은 활동 관계를 통해 문서화됩니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8cee0c75de1fee24cfb6df018de62ece102c96cc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449191"
---
# <a name="create-activity-relation---successor"></a>활동 관계 생성 - 후임자

[!include [banner](../../includes/banner.md)]

린 생산 흐름에서 활동의 흐름은 활동 관계를 통해 문서화됩니다. 이 기록은 활동 관계를 만드는 방법을 보여줍니다.

전제 조건:

- 초안 모드의 프로덕션 흐름 및 버전. 

- 생산 흐름에서 서로 뒤따르는 두 가지 활동이 생성되지만 관련되지는 않습니다.


## <a name="find-the-production-flow-version"></a>생산 흐름 버전 찾기 
1. 생산 제어 > 설정 > 린 생산 흐름 > 생산 흐름으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. 목록에서 선택한 행을 표시합니다.
5. 목록에서 초안 버전을 선택합니다.
    * 활동 관계는 생산 흐름의 초안 또는 활성 버전 모두에 추가할 수 있습니다.  

## <a name="open-the-activity-overview"></a>활동 개요 열기
1. 활동을 클릭합니다.
    * 양식에는 작업 중인 생산 흐름의 버전에 할당된 생산 흐름의 모든 활동이 표시됩니다.  

## <a name="add-a-successor"></a>후임자 추가
1. 후속 작업 추가를 클릭합니다.
2. 활동 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 제약 조건 확인란을 선택합니다.
6. 제약 조건 값 필드에 숫자를 입력합니다.
    * 제약 시간은 선행 작업의 예정된 종료(기한 날짜 및 시간)와 후속 작업의 예정된 시작 사이에 예정된 시간입니다.  
7. 단위 필드에 값을 입력합니다.
8. 주기 시간 비율 필드에 숫자를 입력합니다.
    * 두 활동이 동일한 택트에서 실행되는 경우 주기 시간 비율은 1이어야 합니다. 선행 작업이 후속 작업의 두 배 속도로 실행되는 경우 비율은 2여야 합니다.   주기 시간 비율은 생산 흐름 활동의 개별 주기 시간을 계산하는 데 사용됩니다.  
9. 확인을 클릭합니다.
10. 페이지를 닫습니다.
11. GridPanel 탭을 클릭합니다.
12. 페이지를 닫습니다.
13. 페이지를 새로 고칩니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]