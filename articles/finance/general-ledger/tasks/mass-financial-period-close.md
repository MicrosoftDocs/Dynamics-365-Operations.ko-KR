---
title: 대규모 재무 기간 마감
description: 이 항목에서는 기간을 보류하거나 한 번에 둘 이상의 법인을 영구적으로 마감하는 방법을 보여줍니다.
author: aprilolson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dac267d2d4ce0824bc47b63b8d07913a8dd7f02bcccc025880701cb4d0bdd3d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450538"
---
# <a name="mass-financial-period-close"></a>대규모 재무 기간 마감

[!include [banner](../../includes/banner.md)]

이 항목에서는 기간을 보류하거나 한 번에 둘 이상의 법인을 영구적으로 마감하는 방법을 보여줍니다. 또한 이 작업은 사용자 그룹 게시를 특정 모듈로 제한하는 방법을 보여줍니다.

1. 탐색 창에서 **모듈 > 총계정원장 > 기간 마감 > 원장 일정** 으로 이동합니다. 표시되는 법인 목록은 페이지에서 선택한 회계 일정에 따라 다릅니다. 선택한 회계 일정을 사용하는 법인만 표시됩니다.
2. **편집** 을 선택합니다.
3. 상태를 수정할 기간을 선택합니다.
4. 상태를 업데이트할 법인을 선택합니다. 그리드의 왼쪽 상단에 있는 확인 표시를 선택하여 모든 법인을 빠르게 선택할 수 있습니다.  
5. **모듈 액세스 업데이트** 를 선택하여 선택한 모듈에 대한 게시 액세스 권한을 정의합니다. 모듈 상태는 그리드의 레코드를 편집하여 하나씩 업데이트할 수도 있습니다. 이 버튼은 여러 법인 레코드를 빠르게 업데이트하려는 경우에 유용합니다.  
6. **애플리케이션** 모듈에서 상태를 업데이트할 모듈을 선택합니다. **선택** 을 클릭합니다.
7. **액세스** 수준에서 **모두**, **없음** 또는 특정 사용자 그룹을 선택합니다. **선택** 을 클릭합니다. 모두는 기간이 열려 있으면 모듈에 대한 편집 액세스 권한이 있는 모든 사용자가 게시할 수 있음을 나타냅니다. 없음은 기간이 열려 있어도 사용자가 모듈에 게시할 수 없음을 나타냅니다. 특정 사용자 그룹은 기간이 열려 있으면 그룹의 사용자만 모듈에 게시할 수 있음을 나타냅니다.  
8. **업데이트** 를 선택합니다.
9. 상태를 업데이트하려면 다른 기간을 선택합니다.
10. 기간 상태를 업데이트할 법인을 선택합니다.
11. **업데이트 기간 상태** 를 선택하고 **보류 중**, **열림** 또는 **영구 마감** 상태를 설정합니다. **열림** 은 사용자에게 액세스 권한이 있는 경우 기간을 게시할 수 있음을 나타냅니다. **보류 중** 은 기간을 게시할 수 없지만 기간을 다시 열 수 있음을 의미합니다. **영구 마감** 은 기간이 마감되었으며 열 수 없음을 의미합니다. 조정을 게시할 수 없습니다. 모든 조정 및 감사가 완료될 때까지 기간을 **영구 마감** 으로 설정하지 않는 것이 좋습니다.  
12. **업데이트** 를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]