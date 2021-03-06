---
title: 생산 현장 실행 인터페이스를 실행하는 장치 설정
description: 생산 현장 실행 인터페이스는 생산 현장의 모든 장치에 대해 설정됩니다. 회사는 일반적으로 장치가 제공하는 목적에 따라 각 장치를 다르게 설정합니다. 예를 들어 회사에서 직원이 출근하고 퇴근하는 리셉션 구역에 장치가 있고 작업자가 작업을 관리하는 작업 현장에 다른 장치가 있을 수 있습니다.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f0be79b54a279893f93d41981342e42c8880f059
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "8449413"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>생산 현장 실행 인터페이스를 실행하는 장치 설정

[!include [banner](../includes/banner.md)]

생산 현장 실행 인터페이스는 생산 현장의 모든 장치에 대해 설정됩니다. 회사는 일반적으로 장치가 제공하는 목적에 따라 각 장치를 다르게 설정합니다. 예를 들어 회사에서 직원이 출근하고 퇴근하는 리셉션 구역에 장치가 있고 작업자가 작업을 관리하는 작업 현장에 다른 장치가 있을 수 있습니다.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>특정 장치에 대한 구성 및 필터 설정

장치에 대한 구성 및 작업 필터를 설정하려면 *시간 감독 유지* 직무를 포함하는 보안 역할이 있는 계정을 사용하여 **생산 현장 실행** 페이지에 로그인합니다. (기본 보안 역할 중 *작업 현장 감독자* 만 이 직무를 가집니다.) 그런 다음 다음 단계를 따르세요.

1. 설정하려는 장치로 이동하고 작업 현장 감독자로 Microsoft Dynamics 365 Supply Chain Management에 로그인합니다. (*시간 감독 유지* 직무가 포함된 계정을 사용하세요.)
1. 설정 중인 장치에 구성을 사용할 수 있는지 확인하세요. 구성이 이미 존재하지 않으면 기본 구성이 제공됩니다. 구성을 설정하는 방법에 대한 자세한 내용은 [생산 현장 실행 인터페이스 구성](production-floor-execution-configure.md)을 참조하세요.
1. **생산 제어 \> 제조 실행 \> 생산 현장 실행** 으로 이동합니다.

    현재 장치에서 생산 현장 실행 인터페이스가 이미 한 번 이상 구성된 경우 로그인 페이지가 나타납니다. 그렇지 않으면 시작 페이지가 나타납니다.

1. 로그인 페이지 또는 시작 페이지에서 **구성** 을 선택합니다.
1. 목록에서 구성을 선택합니다.
1. **다음** 을 선택합니다.
1. 현재 장치에 적용할 필터를 하나 이상 선택하세요. 이러한 필터는 관련 작업만 장치에 표시되도록 합니다. 필터를 설정하려면 필터 유형을 선택하여 값 목록을 연 다음 필터링할 값을 선택합니다. 다음 필터를 사용할 수 있습니다.

    - **생산 단위** – 이 필터는 최고 수준의 필터입니다. 일반적으로 여러 리소스 그룹 및 개별 리소스가 있는 대규모 작업 영역을 나타냅니다.
    - **리소스 그룹** – 이 필터는 중간 수준의 필터입니다. 일반적으로 작업 영역의 제한된 영역에 있는 관련 리소스 모음을 나타냅니다. **생산 단위** 필터를 먼저 선택하면 리소스 그룹 목록에 해당 단위의 그룹만 표시됩니다. 그렇지 않으면 사용 가능한 모든 리소스 그룹이 표시됩니다.
    - **리소스** – 이 필터는 가장 구체적인 필터입니다. 일반적으로 특정 시스템 또는 기타 단일 리소스를 나타냅니다. **리소스 그룹** 및/또는 **생산 단위** 필터를 먼저 선택하면 리소스 목록에 해당 그룹 및/또는 단위의 리소스만 표시됩니다. 그렇지 않으면 사용 가능한 모든 리소스가 표시됩니다.

1. **확인** 을 선택합니다.
1. 로그인 페이지가 나타나고 장치를 사용할 준비가 되었습니다.

## <a name="allow-a-worker-to-override-the-default-filters"></a>작업자가 기본 필터를 재정의하도록 허용

특정 작업자에게 그들이 사용하는 모든 장치에서 필터 설정을 변경할 수 있는 권한을 부여할 수 있습니다. 이 권한이 있는 작업자의 경우 생산 현장 실행 인터페이스는 **모든 작업** 및 **활성 작업** 페이지에 **필터** 단추를 제공합니다.

> [!NOTE]
> 작업자가 필터를 변경하면 해당 시점부터 장치에 로그인하는 모든 사용자에게 새 필터가 적용됩니다.

작업자가 장치에 대해 설정된 기본 작업 필터를 재정의하도록 허용하려면 다음 단계를 따르십시오.

1. **근태 \> 설정 \> 시간 등록 작업자** 로 이동합니다.
1. 목록에서 작업자를 선택하여 해당 작업자의 **시간 등록 작업자** 페이지를 엽니다.
1. **시간 등록** 탭에서 **필터 설정** 옵션을 *예* 로 설정합니다.

## <a name="run-the-interface-in-full-screen-mode"></a>전체 화면 모드에서 인터페이스 실행

종종 해당 용도로만 사용되는 장치에서 생산 현장 실행 인터페이스를 실행합니다. 따라서 탐색 및/또는 브라우저 크롬을 표시하지 않고 전체 화면 모드에서 인터페이스를 실행하는 것이 적합할 수 있습니다.

- Supply Chain Management에 표시되는 탐색 창을 숨기려면 브라우저 주소 표시줄의 URL 끝에 `\&limitednav=true`라는 텍스트를 추가합니다.
- 브라우저의 주소 표시줄도 숨기려면 브라우저의 기본 전체 화면 모드를 사용하세요. (지침은 브라우저의 문서를 참조하세요.)

다음 그림의 상단은 기본적으로 인터페이스가 어떻게 보이는지 보여줍니다. 하단은 탐색 창이 숨겨져 있을 때 전체 화면 모드에서 어떻게 보이는지 보여줍니다.

![표준 대 전체 화면 인터페이스.](media/pfei-full-screen.png "표준 대 전체 화면 인터페이스")

## <a name="extend-the-session-past-12-hours"></a>세션을 12시간 이상 연장

기본적으로 생산 현장 실행 인터페이스는 12시간 동안 아무도 사용하지 않으면 자동으로 로그아웃됩니다. 그런 다음 Supply Chain Management 사용자는 다시 로그인해야 합니다. 그러나 타임아웃 제한을 최대 90일까지 연장할 수 있습니다.

타임아웃 제한을 연장하려면 Supply Chain Management에 로그인하고 **시스템 관리 \> 사용자 \> 세션 확장** 으로 이동합니다. 장치에 로그인하는 데 사용되는 Supply Chain Management 사용자 계정 및 세션이 활성 상태를 유지해야 하는 시간을 지정합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
