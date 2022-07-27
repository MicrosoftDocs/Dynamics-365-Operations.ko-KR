---
title: 등록 자격 처리
description: 이 항목에서는 등록 자격 프로세스를 실행하는 방법을 설명합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8997cf24bf24097e46a05acffef8b3839056c57
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452377"
---
# <a name="process-enrollment-eligibility"></a>등록 자격 처리


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 등록 자격 프로세스를 실행하는 방법을 설명합니다.

1. **복리후생 관리** 작업 영역의 **처리** 에서 **등록 자격 처리** 를 선택합니다.

2. **복리후생 등록 자격 프로세스 실행** 대화 상자에서 다음 필드의 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **등록 기간** | 등록 자격을 처리하는 등록 기간. |
   | **법인** | 등록 자격을 처리하는 법인. |
   | **작업자** | 등록 자격을 처리하는 작업자. 이 필드를 비워두면 모든 작업자의 등록 자격이 처리됩니다. |
   | **복리후생 계획** | 등록 자격을 처리하는 복리후생 계획.

3. 백그라운드에서 프로세스를 실행하려면 **백그라운드에서 실행** 을 선택하고 다음 작업을 수행합니다.

   1. 프로세스에 대한 정보를 입력합니다.

   2. 되풀이 작업을 설정하려면 **되풀이** 를 선택하고 되풀이 정보를 입력한 다음 **확인** 을 선택합니다.

   3. 작업 알림을 설정하려면 **알림** 을 선택하고 수신할 알림을 선택한 다음 **확인** 을 선택합니다.

   4. **확인** 을 선택합니다. 프로세스는 설정한 매개 변수로 실행됩니다.

4. **확인** 을 선택합니다.

## <a name="view-process-results"></a>프로세스 결과 보기

이 항목에서는 자격 프로세스 결과를 보는 방법을 설명합니다.

1.  **복리후생 관리** 작업 영역의 **처리** 에서 **처리 결과** 를 선택합니다.

2.  **프로세스 결과** 페이지에 다음 필드가 지정됩니다.

   | 필드 | 설명 |
   | --- | --- |
   | **프로세스 ID** | 작업자, 법인 및 프로세스 실행 조합의 고유 ID. |
   | **프로세스 유형** | 이는 실행된 프로세스를 식별합니다. 예: 등록. |
   | **타임스탬프** | 자격 프로세스가 실행된 시간. |
   | **법인** | 등록 프로세스 중에 지정된 법인. |
   | **작업자** | 처리된 작업자. |
   | **계획** | 등록을 시도한 복리후생 계획. |
   | **자격 규칙** | 처리된 자격 규칙. 자격이 실행되기 전에 오류가 발생한 경우 공백이 됩니다. 예: 작업자에 대한 보상이 정의되지 않은 경우 자격 프로세스가 실행되지 않고 이 필드는 공백으로 남습니다. |
   | **결과 상태** | 적격 또는 부적격입니다. 작업자가 자격 규칙 기준을 충족하지 못하거나, 작업자가 지불 빈도 또는 고정 보상과 같은 필수 정보를 누락하거나, 복리후생 계획에 작업자를 등록할 수 없게 하는 정보 누락이 있는 경우 결과 상태는 부적격이 됩니다 |
   | **결과 메시지** | 작업자가 복리후생 계획에 부적격인 이유 또는 자격 규칙이 통과되었는지를 나타냅니다. |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
