---
title: 작업 ID에 대한 통합 번호 시퀀스
description: 이 기능은 생산 제어, 제조 실행 및 근태 모듈에 대한 작업 ID를 생성하는 단일 통합 번호 시퀀스를 제공합니다.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8ff8fae0bb20b11b15c7520fbb14727ff0372ca0255adc82599c6680a64671af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446962"
---
# <a name="unified-number-sequence-for-job-ids"></a>작업 ID에 대한 통합 번호 시퀀스

[!include [banner](../includes/banner.md)]

이 기능은 생산 제어, 제조 실행 및 근태 모듈에 대한 작업 ID를 생성하는 단일 통합 번호 시퀀스를 제공합니다. 이전에는 이러한 모듈 각각에 대해 다른 번호 시퀀스를 선택할 수 있었는데, 이러한 시퀀스 중 둘 이상이 동일한 형식을 사용하는 경우 충돌하는 작업 ID가 발생할 수 있었습니다. 이러한 충돌로 인해 데이터가 손상될 수 있습니다.

## <a name="turn-on-this-feature-for-your-system"></a>시스템에 이 기능 사용 설정

시스템에 이 항목에서 설명하는 기능이 아직 포함되어 있지 않으면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)로 이동하여 *작업 ID에 대한 통합 번호 시퀀스* 기능을 켭니다.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>작업 ID에 대한 통합 번호 시퀀스 설정

이 기능을 활성화하면 생산 제어, 제조 실행, 근태 모듈에 대한 매개 변수 페이지에 있는 기존 **작업 식별** 번호 시퀀스 설정이 더 이상 사용되지 않으며 새로운 **통합 작업 ID** 필드가 추가됩니다. **통합 작업 ID** 값은 세 모듈 모두에서 공유하므로 모든 모듈이 동일한 번호 시퀀스를 참조하도록 합니다. 따라서 작업 ID는 세 모듈 모두에서 고유하며 충돌이 발생하지 않습니다.

작업 ID에 대한 통합 번호 시퀀스를 설정하려면:

1. 이전 섹션에서 설명한 대로 기능을 켭니다.
1. 통합 작업 ID에 사용할 번호 시퀀스를 식별하거나 새 번호를 만드세요. 자세한 내용은 [번호 시퀀스 개요](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)를 참조하세요.
1. **생산 제어 매개 변수**, **제조 실행 매개 변수** 또는 **근태 매개 변수** 페이지로 이동합니다. 해당 페이지 중 하나에서 이 설정을 지정하면 다른 모든 페이지가 자동으로 업데이트되기 때문에 어느 것을 선택하든 상관 없습니다.
1. 선택한 매개 변수 페이지에서 **번호 시퀀스** 탭을 엽니다.
1. 그리드의 **통합 작업 ID** 행에 이전에 식별한 **번호 시퀀스 코드** 를 할당합니다.
