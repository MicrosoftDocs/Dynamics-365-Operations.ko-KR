---
title: 계정 구조 활성화 성능 향상
description: 이 문서에서는 계정 구조 활성화 프로세스의 새로운 성능 향상에 대해 설명합니다.
author: RyanCCarlson2
ms.date: 10/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-10-08
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 42f8fcebba6465261489f74a9bb1dd46c2d5fa16
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2022
ms.locfileid: "9714004"
---
# <a name="account-structure-activation-performance-enhancement"></a>계정 구조 활성화 성능 향상

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

이 성능 향상을 통해 동시에 여러 거래 업데이트를 실행하여 계정 구조를 더 빠르게 활성화할 수 있습니다. 또한 구조 자체는 유효성이 검사된 후 활성으로 표시되며 기존의 기장되지 않은 거래가 새 구조로 업데이트되는 동안 거래 처리를 계속할 수 있습니다. 거래 업데이트에는 시간이 걸릴 수 있으므로 **계정 구조** 페이지의 그리드 위에 있는 **활성화 상태 보기** 를 선택하여 활성화 상태를 추적할 수 있습니다. 작업 창에서 **보기** 를 선택한 다음 드롭다운 메뉴에서 **활성화 상태** 를 선택하여 활성화 상태를 볼 수도 있습니다.

[![계정 구조 페이지.](./media/AccountStructure1.png)](./media/AccountStructure1.png)

**활성화 상태 보기** 를 선택하면 활성화 프로세스의 일부로 실행 중인 개별 작업을 보여주는 대화 상자가 나타납니다. 각 작업의 상태를 볼 수 있으며 작업이 완료된 후 완료 날짜 및 시간을 볼 수 있습니다.

[![계정 구조 활성화 타임라인.](./media/AccountStructureTimeline.png)](./media/AccountStructureTimeline.png)

## <a name="account-structure-activation-tips"></a>계정 구조 활성화 팁

초안 계정 구조에 대해 **활성화** 를 선택할 때 나타나는 계정 구조 활성화 대화 상자에는 **기장되지 않은 거래 업데이트** 라는 탭 섹션이 있습니다. 이 섹션에는 **강제 업데이트** 라는 옵션이 포함되어 있습니다. 이 옵션을 선택하여 기장되지 않은 모든 거래를 현재 구조로 업데이트할 수 있습니다. 그러나 오류가 발생했거나 Microsoft 지원에서 사용하도록 지시한 경우에만 이 옵션을 사용해야 합니다.

활성화 프로세스의 성능에 영향을 줄 수 있는 몇 가지 요소는 다음과 같습니다.

- 게시되지 않은 많은 분개장 기록
- 자유 형식 텍스트 송장, 공급업체 송장 및 소스 문서 프레임워크를 사용하고 공개 회계 분포가 있는 관련 문서와 같은 많은 수의 오픈 소스 문서 레코드
- TaxUncommitted의 데이터 양
- 미결 예산 데이터의 양
- 활성화 작업이 계속 실행되는 동안 분개장 데이터 가져오기

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
