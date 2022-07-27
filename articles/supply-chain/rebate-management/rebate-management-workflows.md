---
title: 리베이트 관리 거래 워크플로
description: 이번에는 거래를 승인하고 활성화하기 위해 리베이트 관리 거래 워크플로를 설정하는 방법에 대해 설명합니다.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f18c3bd95901303379c460d026bc944cee809b7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448927"
---
# <a name="rebate-management-deal-workflows"></a>리베이트 관리 거래 워크플로

[!include [banner](../includes/banner.md)]

리베이트 거래를 승인하기 위해 리베이트 관리는 다른 재무 및 운영 앱과 동일한 워크플로 플랫폼을 사용합니다. 모든 워크플로에는 두 가지 작업 프로세스가 연결됩니다.

- 워크플로의 한 요소가 거래를 승인합니다.
- 워크플로의 한 요소는 사용자 또는 워크플로 프로세스가 거래를 승인할 수 있도록 거래를 활성화합니다.

리베이트 거래를 사용하려면 **리베이트 관리** 모듈에서 활성화되어 있어야 합니다. 거래를 활성화하려면 먼저 *리베이트 관리 거래 워크플로* 를 만들고 구성해야 합니다.

사용자는 수동으로 거래를 승인할 수 없습니다. 워크플로는 항상 사용해야 합니다.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>리베이트 관리 거래 워크플로 생성 및 관리

리베이트 관리 거래 워크플로를 사용하려면 **리베이트 관리 \> 설정 \> 리베이트 관리 워크플로** 로 이동하세요. 여기에서 필요에 따라 워크플로를 보고, 만들며 업데이트할 수 있습니다. 이 유형의 워크플로는 한 번에 하나만 활성화할 수 있습니다. 워크플로, **리베이트 관리 워크플로** 페이지 작업 방법 및 워크플로 생성 방법에 대한 자세한 내용은 [워크플로 시스템 개요](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) 및 관련 항목을 참조하세요.

## <a name="use-a-workflow-to-activate-a-deal"></a>워크플로를 사용하여 거래 활성화

워크플로를 통해 거래를 활성화하려면 거래를 엽니다(**모든 리베이트 관리 거래 페이지** 등에서). 이후 작업 창에서 **워크플로 \> 제출** 을 선택합니다. 새 거래가 처리되고 워크플로를 통해 승인되면 활성화되어 사용할 준비가 됩니다.

거래가 활성화된 후에는 대부분의 설정을 변경할 수 없습니다. 활성 거래를 변경해야 하는 경우 먼저 비활성화한 후, 새 거래를 만드십시오. 새 거래가 이전 거래와 유사할 경우 이전 거래를 복사하여 생성할 수 있습니다.

거래가 활성화된 후 거래에 대해 다음 설정을 변경할 수 있습니다.

- 조정자
- 누적 보증
- 프로필 전기
- 보증을 위한 프로필 전기
- 문서 메모
- 통화
- 시작일
- 종료일

또한 리베이트 라인을 제거할 수 있습니다.
