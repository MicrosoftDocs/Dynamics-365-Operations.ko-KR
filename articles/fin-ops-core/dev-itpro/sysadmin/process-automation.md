---
title: 프로세스 자동화
description: 이 항목에서는 프로세스 자동화를 통해 일괄 처리 서버에서 실행할 프로세스를 간단하게 예약할 수 있는 방법에 대해 자세히 설명합니다.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: b69fa378539e39053b6f7066ba4b6ae9984157c9bdc4f38b78de4c062c04ad09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460908"
---
# <a name="process-automation"></a>프로세스 자동화

[!include[banner](../includes/banner.md)]

프로세스 자동화를 사용하면 일괄 처리 서버에서 실행할 프로세스를 간단하게 예약할 수 있습니다. 예약된 작업의 업데이트된 일정 보기를 통해 최종 사용자는 예약 및 완료된 작업을 보고 조치를 취할 수 있습니다.

## <a name="administration"></a>관리

모든 프로세스 자동화에 대한 중앙 관리 페이지는 **설정** 메뉴 아래의 시스템 관리 모듈에 있습니다. 이 페이지에는 시스템에 설정된 모든 자동화된 프로세스(시리즈)가 나열됩니다. 또한 이 페이지에서 직접 새로운 프로세스 자동화를 추가할 수 있습니다. 시리즈를 설정한 후 이 목록에서 각 시리즈를 관리할 수 있습니다. 전체 시리즈를 편집하거나 삭제하거나 목록 보기에서 모든 항목을 보거나 예약된 작업을 잠시 일시 중지하려는 경우 시리즈를 비활성화하도록 선택할 수 있습니다. 

기능이 비활성화되면 기능 관리에서 비활성화된 프로세스가 표시되지 않습니다. 또한 프로세스 자동화 스케줄링 엔진은 비활성화된 기능에 대한 발생 또는 백그라운드 프로세스를 스케줄링하지 않습니다. 기능을 다시 활성화하면 과거에 예약된 모든 발생 또는 백그라운드 프로세스가 즉시 실행됩니다. 프로세스 자동화 스케줄링 엔진은 시스템 배치 작업에 의존하며 실행할 **프로세스 자동화 폴링 시스템 작업** 입니다. 작업은 언제든지 변경되거나 변조되어서는 안 됩니다. 

## <a name="calendar-view"></a>캘린더 보기

프로세스 자동화의 주요 이점 중 하나는 간단한 일정 보기에서 예약된 작업을 볼 수 있다는 것입니다.  이 보기를 사용하면 한 번에 일주일 동안의 작업을 볼 수 있습니다. **프로세스 자동화** 페이지의 오른쪽에 이 보기가 표시됩니다. 선택한 시리즈의 예정된 작업으로 채워집니다. 

[![프로세스 자동화 캘린더.](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>발생 변화

각 발생은 해당 발생을 시작한 시리즈에서 정의한 다른 발생에 영향을 주지 않고 수정할 수 있습니다. 예약된 작업의 발생은 캘린더 보기에서 **보기/편집** 버튼을 선택하고 **발생** 을 선택하여 편집할 수 있습니다. 이 페이지에서는 시리즈 설정 마법사에 원래 표시된 모든 설정에 액세스할 수 있으며 선택한 항목에 대해 일회성 변경을 수행할 수 있는 기능을 제공합니다. 예약된 작업의 발생은 캘린더 보기의 **비활성화** 버튼을 선택하여 끌 수도 있습니다.

## <a name="developer-documentation"></a>개발자 문서

프로세스 자동화 프레임워크를 통해 개발자는 프로세스 자동화 프레임워크를 확장할 수 있습니다. [프로세스 자동화 프레임워크](../process-automation/process-automation-framework.md) 문서는 프로세스 자동화 마법사로 예약된 배치 서버에서 실행해야 하고 일정 보기에 자동으로 나타나는 사용자 지정 프로세스를 생성하는 방법에 대한 정보를 제공합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
