---
title: 예외 처리를 위한 창고 작업 취소
description: 이 항목에서는 창고 감독자가 차단된 작업을 처리할 수 있도록 하는 작업 취소 기능에 대해 설명합니다.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: af0c147eefbfe22cb6b6d531f514e6f293d66689
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448519"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>예외 처리를 위한 창고 작업 취소

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management의 작업 취소 기능을 사용하여 관리자는 현재 진행 중인 특정 창고 작업을 취소할 수 있지만 시스템에 의해 차단되거나 예외적인 상황으로 인해 완료할 수 없습니다. 이 기능은 일관성 없는 데이터를 수정하는 SQL 수정 스크립트에 대한 매력적이고 안전한 대안입니다. 그러나 이러한 스크립트는 일반적으로 IT 전문가에게 요청되는 반면 작업 취소 기능은 관리자 권한이 있는 회사 사용자가 사용할 수 있습니다.

**창고 관리** \> **정기 작업** \> **청소 \> 작업 취소** 에서 작업 취소 기능에 액세스할 수 있습니다. **작업 취소** 대화 상자에서 취소할 작업의 작업 ID를 지정한 다음 **확인** 을 선택합니다.

## <a name="warehouse-work-that-can-be-canceled"></a>취소 가능한 창고 작업

창고 피킹 작업 중에 작업자는 보관 위치에서 사용자 위치로 피킹된 수량을 등록했지만 넣기 작업을 등록할 수 없는 상황이 발생할 수 있습니다. 일관되지 않은 웨어하우스 데이터는 항상 그런 것은 아니지만 작업이 차단되는 이유입니다.

작업 헤더의 **취소** 단추를 사용하여 액세스할 수 있는 일반 취소 기능과 달리 작업 취소 기능은 마지막으로 완료된 작업 라인이 **풋** 유형의 작업 라인일 필요가 없습니다. 즉, 작업 취소 기능의 경우 작업 라인의 품목 수량이 사용자 위치에 있더라도 취소 로직이 실행될 수 있습니다.

> [!NOTE]
> 운영상의 이유로 취소해야 하는 작업의 경우 창고 사용자는 작업 페이지에서 일반 취소 기능을 계속 사용해야 합니다.

**판매**, **전송 문제**, **원자재 피킹** 또는 **보충** 유형의 작업만 작업 취소 기능을 사용하여 취소할 수 있습니다. 동결된 원자재 피킹 작업이나 일반 취소 기능을 사용하여 취소할 수 있는 작업에 대해서는 취소 로직이 실행되지 않습니다(이전 참고 사항 참조).

작업 차단을 해제하기 위해 시스템은 나머지 작업 라인을 취소하고 사용자가 지정한 작업 ID와 연결된 창고 데이터를 수정합니다. 그러면 영향을 받는 품목 수량과 관련된 모든 정규 창고 처리 작업이 재개될 수 있습니다.

작업 취소 후 해당 아이템을 특정 위치에 놓기 위해서는 사용자가 모바일 기기에서 재고 이동이나 수량 조정 조작을 해야 한다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]