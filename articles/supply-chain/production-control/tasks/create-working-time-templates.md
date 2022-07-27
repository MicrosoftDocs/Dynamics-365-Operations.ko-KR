---
title: 근무 시간 템플릿 만들기
description: 근무 시간 템플릿은 한 주의 근무 시간을 정의하고 일정 기간 동안의 근무 시간을 생성하는 데 사용됩니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130a21d08e4e720f8bf803a5d4b03d315cefc26f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449338"
---
# <a name="create-working-time-templates"></a>근무 시간 템플릿 만들기

[!include [banner](../../includes/banner.md)]

근무 시간 템플릿은 한 주의 근무 시간을 정의하고 일정 기간 동안의 근무 시간을 생성하는 데 사용됩니다. 이 절차에서는 근무 시간 간격을 분류하기 위해 근무 시간 예약 속성을 사용하여 근무 시간 템플릿을 정의하는 방법을 보여줍니다. 데모 데이터 회사 USMF에서 이 절차를 수행하거나 자신의 데이터를 사용할 수 있습니다.

1. **작업 영역 > 리소스 수명 주기 관리** 로 이동합니다.
1. **근무 시간 템플릿** 을 만듭니다.

## <a name="create-working-time-template"></a>근무 시간 템플릿 만들기

1. **새로 만들기** 를 선택합니다.
1. **근무 시간 템플릿** 필드에 값을 입력합니다.
1. **이름** 필드에 값을 입력합니다.
1. **월요일** 섹션을 확장합니다.
1. **추가** 를 선택합니다.
1. **시작** 필드에 시간을 입력합니다.
    * 근무가 시작되는 오전 시간을 지정합니다.  
1. **종료** 필드에 시간을 입력합니다.
    * 작업자가 점심을 먹기 위해 쉬는 시간을 지정합니다.  
1. **추가** 를 선택합니다.
1. **시작** 필드에 시간을 입력합니다.
    * 점심 식사 후 작업이 재개되는 시간을 지정합니다.  
1. **종료** 필드에 시간을 입력합니다.
    * 근무일의 끝을 지정합니다.  

## <a name="replicate-working-times-to-all-week-days"></a>모든 요일에 근무 시간 복제

1. **요일 복사** 를 선택합니다.
    * 근무 시간 정의를 월요일에서 화요일로 복사합니다.  
1. **확인** 을 선택합니다.
1. **요일 복사** 를 선택합니다.
    * 근무 시간 정의를 월요일에서 수요일로 복사합니다.  
1. **종료 요일** 필드에서 옵션을 선택합니다.
1. **확인** 을 선택합니다.
1. **요일 복사** 를 선택합니다.
    * 근무 시간 정의를 월요일에서 목요일로 복사합니다.  
1. **종료 요일** 필드에서 옵션을 선택합니다.
1. **확인** 을 선택합니다.
1. **요일 복사** 를 선택합니다.
    * 근무 시간 정의를 월요일에서 금요일로 복사합니다.  
1. **종료 요일** 필드에서 옵션을 선택합니다.
1. **확인** 을 선택합니다.

## <a name="define-time-slots-for-special-operations"></a>특수 작업을 위한 시간 슬롯 정의

1. **금요일** 섹션을 확장합니다.
1. 목록에서 원하는 레코드를 찾아 선택합니다.
1. **속성** 필드에서 값을 입력하거나 선택합니다.
1. 목록에서 원하는 레코드를 찾아 선택합니다.
1. **속성** 필드에서 값을 입력하거나 선택합니다.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>픽업을 위해 주말을 휴무로 표시

1. **토요일** 섹션을 펼칩니다.
1. **픽업 마감** 필드에서 *예* 를 선택합니다.
1. **일요일** 섹션을 확장합니다.
1. **픽업 마감** 필드에서 *예* 를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]