---
title: 상태 평가
description: 이 항목에서는 자산 관리에서 자산에 대한 상태 평가 템플릿 및 등록을 생성하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cced322dd2f213d8e6025d853edc8472618989b61de7139b28ba1c6bffd3ad2a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446845"
---
# <a name="condition-assessment"></a>상태 평가

[!include [banner](../../includes/banner.md)]

 

이 항목에서는 자산 관리에서 자산에 대한 상태 평가 템플릿 및 등록을 생성하는 방법에 대해 설명합니다. 상태 평가는 정기적으로 수행되며 주요 목표는 자산에 대한 상태 데이터를 생성하고 유지하는 것입니다. 예방 정비의 관점에서 볼 때 현재 상태, 남은 수명 등의 핵심 정보를 모니터링하는 것이 중요합니다. 또한 정기적으로 상태 평가를 수행하면 공장의 기계 상태를 모니터링하고 비교할 수 있습니다.

상태 평가는 장비의 여러 상태를 측정하고 모니터링하는 데 사용할 수 있습니다. 예: 기계의 진동을 측정할 수 있습니다. 다양한 유형의 장비에 대해 자산 관리에 진동 측정을 등록한 후 최근에 등록된 평가를 검색하고 진동 측정을 볼 수 있습니다.

상태 평가는 자산에 대해 생성됩니다. 상태 평가 절차를 수행하기 전에 자산 유형에 대한 상태 평가 템플릿을 설정합니다. 상태 평가에 템플릿을 사용하는 이유는 유사한 자산에 대한 상태 데이터의 변동을 피하기 위함입니다. 자산 관리에서 조건 평가를 설정하고 사용하는 순서는 다음과 같습니다. 먼저 필요한 조건 평가 템플릿을 설정합니다. 다음으로 **자산 유형** 양식에서 템플릿을 자산 유형과 연결합니다. 마지막으로 **자산** 양식에서 자산에 대한 상태 평가 등록을 생성할 수 있습니다.

## <a name="create-a-condition-assessment-template"></a>상태 평가 템플릿 만들기

1. **자산 관리** > **설정** > **자산 유형** > **상태 평가** 를 선택합니다.
2. **새로 만들기** 를 선택하여 새 템플릿을 생성합니다.
3. **템플릿** 필드에서 템플릿의 ID를 삽입합니다.
4. **이름** 필드에 템플릿의 이름을 삽입합니다.
5. **상태 평가 라인** 빠른 탭에서 적절한 조건 유형 및 측정 단위 선택을 포함하여 조건 평가에 필요한 라인을 추가합니다.
6. **자산 유형** 빠른 탭에서 상태 평가 템플릿을 사용해야 하는 자산 유형을 추가합니다.
7. 화면 상단의 **세부 정보** 그룹에 있는 **라인** 및 **자산 유형** 필드에서 선택한 상태 평가 템플릿과 관련된 평가 라인 및 자산 유형의 수를 볼 수 있습니다.


## <a name="create-condition-assessment-registration-on-an-asset"></a>자산에 대한 상태 평가 등록 생성

1. **자산 관리** > **공통** > **자산** > **모든 자산** 을 선택합니다.
2. 목록에서 상태 평가 등록을 생성할 자산을 선택합니다.
3. **일반** 탭에서 **상태 평가** 를 클릭합니다.
4. **새로 만들기** 를 클릭하여 새로운 등록을 만듭니다.
5. **날짜** 필드에서 상태 평가의 날짜를 선택합니다.
6. **작업자** 필드에서 평가 등록을 수행한 작업자의 이름을 선택합니다.
7. **라인** 필드에 상태 평가에 설정된 평가 라인 수가 표시됩니다.
8. **템플릿** 필드에서 상태 평가의 템플릿을 선택합니다. **이름** 필드에 템플릿 이름이 자동으로 삽입되며 관련 등록 라인이 **상태 평가 라인** 빠른 탭에 삽입됩니다.
9. **메모** 빠른 탭에서 선택한 상태 평가와 관련된 메모를 에 삽입할 수 있습니다.
10. **값** 필드에서 각 상태 평가 라인에 대해 측정 데이터를 삽입합니다.
11. **상태 평가 라인** 빠른 탭 > **댓글** 필드에서 선택한 등록 라인과 관련된 설명을 입력할 수 있습니다. 한 줄에 주석을 추가하면 **댓글** 확인란이 자동으로 선택됩니다.

자산에 상태 평가를 등록한 후 상태 평가 보고서를 인쇄할 수 있습니다.

>[!NOTE]
>작업 주문에 상태 평가를 등록할 수도 있습니다(**자산 관리** > **공통** > **작업 주문** > **모든 작업 주문** > **상태 평가** 단추.)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]