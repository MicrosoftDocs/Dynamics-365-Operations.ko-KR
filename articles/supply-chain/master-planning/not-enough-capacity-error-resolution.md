---
title: "'충분한 용량을 찾을 수 없습니다' 스케줄링 엔진 오류 및 한정된 용량 수정"
description: 이 항목에서는 '생산 주문 %1을(를) 예약할 수 없습니다. 용량이 충분하지 않습니다' 스케줄링 엔진 오류에 대한 이유와 해결에 대한 정보를 제공합니다.
author: ChristianRytt
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: becd537d37a8ba8931f2598dccbae8554a4d168e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449728"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>"용량이 충분하지 않습니다." 스케줄링 엔진 오류를 해결합니다.

[!include [banner](../includes/banner.md)]

예약을 실행할 때 다음 오류 메시지가 나타날 수 있습니다.

> 생산 주문 %1의 예약을 할 수 없습니다. 용량이 충분하지 않습니다.

스케줄링 엔진이 실패하고 이 오류 메시지가 표시되는 데에는 몇 가지 이유가 있습니다. 이 항목에서는 오류의 근본 원인을 찾아 완화하는 데 도움이 되는 지침을 제공합니다.

## <a name="review-the-applicable-resources"></a>해당 리소스 검토

생산 주문 사이트에서 작업 요구 사항을 충족하는 해당 리소스가 없는 경우 오류가 발생할 수 있습니다.

해당 리소스를 검토하려면 다음 단계를 따르십시오.

1. **생산 관리 \> 생산 주문 \> 모든 생산 주문** 으로 이동하고 예약할 수 없는 생산 주문을 열거나 선택합니다.
1. 작업 창의 **생산 주문** 탭에서 **생산 세부 정보** 그룹에 있는 **경로** 를 선택합니다.
1. **생산 경로** 페이지에서 작업을 선택한 다음 작업 창에서 **적용 가능한 리소스** 를 선택합니다.
1. **적용 가능한 리소스** 대화 상자에서 사용 중인 일정 유형에 따라 **요구 사항 사용** 필드를 *작업 예약* 또는 *작업 예약* 으로 설정합니다.
1. 생산 주문 사이트에 해당 리소스가 있는지 확인합니다.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>리소스와 연결된 캘린더 검토

리소스 또는 리소스 그룹과 연결된 캘린더가 없거나 연결된 캘린더가 올바르게 설정되지 않은 경우(예: 작업 시간이 없거나 백분율로 나타낸 효율성이 0\[영\]인 경우) 오류가 발생할 수 있습니다.

캘린더가 리소스 또는 리소스 그룹과 연결되어 있는지 확인하려면 다음 단계를 따르십시오.

1. **생산 관리 \> 생산 주문 \> 모든 생산 주문** 으로 이동하고 예약할 수 없는 생산 주문을 열거나 선택합니다.
1. 작업 창의 **생산 주문** 탭에서 **생산 세부 정보** 그룹에 있는 **경로** 를 선택합니다.
1. **생산 경로** 페이지에서 작업을 선택한 다음 작업 창에서 **적용 가능한 리소스** 를 선택합니다.
1. **적용 가능한 리소스** 대화 상자에서 리소스를 선택한 다음 **리소스 보기** 를 선택합니다. 또는 **리소스 그룹** 필드를 길게 선택하고(또는 오른쪽 버튼으로 클릭) **세부 정보 보기** 를 선택합니다.
1. **리소스** 페이지 또는 **리소스 그룹** 페이지의 **캘린더** 빠른 탭에서 캘린더가 리소스 또는 리소스 그룹과 연결되어 있는지 확인하세요.

> [!NOTE]
> 작업 예약 중에 오류가 발생하면 캘린더가 해당하는 모든 리소스 그룹과 연결되어 있는지 확인해야 합니다.

캘린더 설정을 검토하려면 다음 단계를 따르십시오.

1. **조직 관리 \> 설정 \> 캘린더 \> 캘린더** 로 이동하고 리소스 또는 리소스 그룹과 연결된 캘린더를 선택합니다.
1. 작업 창에서 **작업 시간** 을 선택합니다.
1. **작업 시간** 페이지에서 페이지가 비어 있지 않은지 확인하세요. 또한 관심 있는 날짜에 대해 **제어** 필드가 *닫힘* 으로 설정되지 않았고 작업 시간이 존재하고 **효율성이 백분율임** 필드가 *0*(영)으로 설정되지 않았는지 확인하세요.

캘린더가 기본 캘린더와 연결된 경우 기본 캘린더의 설정도 검토해야 합니다.

> [!NOTE]
> 작업 예약에서 리소스 그룹의 캘린더는 각 작업의 시작 및 종료 시간과 날짜를 결정하는 데 사용됩니다. 또한 시스템이 특정 리소스 그룹의 특정 날짜에 대해 하나의 특정 작업을 예약할 수 있는 시간을 제한합니다. 예를 들어, 특정 요일의 리소스 그룹 작업 시간이 오전 8시부터 오후 4시인 경우 한 작업이 리소스 그룹에 가하는 로드는 해당 날짜의 리소스 그룹에 있는 사용 가능한 용량에 관계없이 8시간에 맞을 수 있는 로드를 초과할 수 없습니다. 그러나 사용 가능한 용량으로 인해 로드가 더 제한될 수 있습니다.

## <a name="review-the-scheduling-parameters"></a>예약 매개 변수 검토

좋은 성능을 보장하기 위해 일정 엔진은 특정 시간과 일정 충돌 횟수에 대해서만 리소스를 검색합니다.

예약 매개 변수를 검토하려면 다음 단계를 따르십시오.

1. **조직 관리 \> 설정 \> 예약 매개 변수** 로 이동합니다.
1. 다음 단계 중 하나를 따르십시오.

    - **예약 시간 초과 활성화됨** 옵션이 *아니요* 로 설정된 경우 3단계로 이동합니다.
    - **예약 시간 초과 활성화됨** 옵션이 *예* 로 설정된 경우 **시퀀스당 최대 스케줄링 시간** 필드의 값을 높여 처리를 완료하는 데 더 많은 시간을 제공합니다.

1. 다음 단계 중 하나를 따르십시오.

    - **예약 최적화 시간 초과 활성화됨** 옵션이 *아니요* 로 설정된 경우 4단계로 이동합니다.
    - **예약 최적화 시간 초과 활성화됨** 옵션이 *예* 로 설정된 경우 **최적화 시도 시간 초과** 필드의 값을 높여 처리를 완료하는 데 더 많은 시간을 제공합니다.

1. 페이지의 설정을 변경한 경우 주문을 다시 예약하여 다시 시도하세요.

## <a name="review-capacity"></a>용량 검토

유한 스케줄링을 수행하지만 여유 용량이 없을 때 오류가 발생할 수 있습니다.

무한 용량 스케줄링을 수행하려면 다음 단계를 따르십시오.

1. **생산 관리 \> 생산 주문 \> 모든 생산 주문** 으로 이동하고 예약할 수 없는 생산 주문을 선택하거나 엽니다.
1. 작업 창의 **일정** 탭에 있는 **생산 주문** 그룹에서 **작업 예약** 또는 **작업 예약** 을 선택합니다.
1. **작업 예약** 또는 **작업 예약** 대화 상자에서 **유한 용량** 옵션을 *아니요* 로 설정합니다.
1. **확인** 을 선택하여 주문을 예약합니다.

리소스에서 사용 가능한 용량을 검토하려면 다음 단계를 따르십시오.

1. **조직 관리 \> 리소스 \> 리소스** 로 이동하고 예약할 수 없는 주문에 적용할 수 있는 리소스를 선택합니다.
1. 작업 창의 **리소스** 탭에 있는 **보기** 그룹에서 **최대 수용 작업량** 또는 **최대 수용 작업량, 그래픽** 을 사용하여 사용 가능한 용량이 있는지 확인합니다.

리소스 그룹에서 사용 가능한 용량을 검토하려면 다음 단계를 따르십시오.

1. **조직 관리 \> 리소스 \> 리소스 그룹** 으로 이동하고 예약할 수 없는 주문에 적용할 수 있는 리소스 그룹을 선택합니다.
1. 작업 창의 **리소스 그룹** 탭에 있는 **보기** 그룹에서 **최대 수용 작업량** 또는 **최대 수용 작업량, 그래픽** 을 사용하여 사용 가능한 용량이 있는지 확인합니다.

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>기준 계획은 리소스 캘린더가 마감될 때 리소스를 예약합니다.

작업 예약을 사용할 때 기준 계획은 기본 리소스 그룹의 캘린더에 따라 능력을 계획합니다. 기본 작업과 동시에 보조 작업을 예약하고 보조 작업의 일정이나 용량을 고려하지 않습니다. 이로 인해 생산 주문이 마감된 일정에 예약되거나 2차 작업을 사용할 수 없는 시간에 예약될 수 있습니다(일정 마감, 용량 없음).

작업 예약을 사용할 때 기준 계획은 주문을 스케줄링할 때 기본 및 보조 작업 모두의 용량과 일정을 고려합니다. 주문을 예약하려면 두 작업의 리소스에 대한 캘린더가 열려 있어야 하고 사용 가능한 용량이 있어야 합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]