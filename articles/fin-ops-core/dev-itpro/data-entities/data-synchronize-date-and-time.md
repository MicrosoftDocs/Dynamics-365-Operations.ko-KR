---
title: 가져오기 작업에서 날짜 및 시간 동기화
description: 표준 시간대 변환 문제를 방지하려면 가져오기 작업에서 UTC 표준 시간대를 사용합니다.
author: peakerbl
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c76eadc5839785ba1624ee3894ef1d0872369aa9
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2021
ms.locfileid: "8461004"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>가져오기 작업에서 날짜 및 시간 동기화

[!include [banner](../includes/banner.md)]

가져오기 작업의 시간대를 표준 시간대(UTC)로 설정하는 것이 중요합니다. 다른 설정을 사용하면 가져온 데이터에 예기치 않은 날짜와 시간이 표시될 수 있습니다. 올바른 설정이 없으면 가져오기 프로세스에서 UTC 날짜를 로컬 형식으로 변환한 다음 시스템 설정에서 다시 변환합니다.

이 이중 변환으로 인해 애플리케이션 간에 날짜가 변경됩니다. 예를 들어 이중 변환으로 인해 직원의 시작 날짜가 Dynamics 365 Human Resources 현지 시간대와 Dynamics 365 Finance 현지 시간대의 차이로 인해 달라질 수 있습니다. 가져오기 작업을 UTC로 설정하면 이 문제가 해결됩니다.

1. Dynamics 365 Finance 및 작업에서 **데이터 관리** 를 선택합니다.

2. **프로젝트 가져오기** 를 선택한 다음 프로젝트를 선택합니다.

3. **원본 날짜 형식** 에서 **CSV-유니코드** 를 선택합니다.

   [![소스 날짜 형식을 UTC로 변경합니다.](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. **Timezone** 을 **Coordinated Universal Timezone** 으로 변경하고 **Language** 를 **En-US** 로 변경합니다.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
