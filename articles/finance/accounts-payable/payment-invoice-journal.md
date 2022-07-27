---
title: 송장 분개장에 지불 일정 적용
description: 이 항목에서는 공급업체 송장 분개장에 지불을 추가하는 방법을 설명합니다.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f6481c3fc033acf4bb563bf1716789216646b60b
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8451651"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>송장 분개장에 지불 일정 적용

[!include [banner](../includes/preview-banner.md)]

Microsoft Dynamics 365 Finance 릴리스 10.0.25에서는 이제 **공급업체 송장 분개장** 에 지불 일정이 지원됩니다.

이 기능을 사용하려면 기능 관리에서 **송장 분개장에 지불 일정 적용** 기능을 활성화해야 합니다.

기능이 활성화되면 **송장 분개장** 페이지에 새로운 **지불 일정** 필드가 추가됩니다. 송장 분개장 라인을 만들 때 공급업체에서 지불 조건이 유지되고 지불 일정에서 지불 조건이 선택되면 **송장 분개장** 페이지에서 **지불 일정** 필드가 업데이트됩니다.

비즈니스 요구 사항에 따라 사용되는 지불 일정을 변경할 수 있습니다. 공급업체 송장 분개장을 게시하는 동안 지불 일정에 따라 공급업체 미결 거래가 생성됩니다.

 - 지불 일정에서 생성된 여러 공급업체 미결 거래를 검토하려면 **지급 계정 \> 송장 \> 공급업체 송장 열기** 로 이동하여 송장 번호 또는 공급업체 계정을 입력합니다.
 - 지불 일정을 검토하거나 구성하려면 **지급 계정 \> 지불 설정 \> 지불 일정** 으로 이동합니다.
 - 지불 조건을 구성하고 지불 일정을 지정하려면 **지급 계정 \> 지불 설정 \> 지불 조건** 으로 이동합니다.
 - 공급업체에 대한 지불 조건을 유지하려면 **지급 계정 \> 모든 공급업체** 로 이동하여 공급업체 계정을 선택한 다음 **지불** 탭에서 **지불 조건** 필드를 설정합니다.

지불 일정 기능은 **공급업체 송장 등록** 프로세스에서도 사용할 수 있습니다. 송장 등록부 분개장에서 지불 일정을 선택한 경우 송장 등록부가 게시될 때 여러 공급업체 지불 라인이 생성되지 **않습니다**. 송장이 승인되면 공급업체 지불 라인이 생성됩니다.

## <a name="limitation"></a>제한 사항

보류 중인 공급업체 송장의 경우 지불 일정이 송장 헤더에 있는 경우 사용자가 지불 라인을 편집할 수 있는 고급 페이지가 있습니다. (예를 들어, 사용자는 각 지불 라인의 만기 날짜와 값을 편집할 수 있습니다.) 송장 분개장에서 생성된 지불 라인은 지불 일정의 값을 가집니다.

이 기능은 향후 릴리스에서 **공급업체 송장 분개장** 및 **보류 중인 송장** 에 사용할 수 있습니다.
