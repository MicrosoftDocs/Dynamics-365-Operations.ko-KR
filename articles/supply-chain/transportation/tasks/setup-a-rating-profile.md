---
title: 평가 프로필
description: 이 토픽에서는 평가 프로필에 대한 데이터를 설정하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af9051c6bbaed311f1f841a82dfd145633acab2c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448756"
---
# <a name="rating-profiles"></a>평가 프로필

[!include [banner](../../includes/banner.md)]

평가 프로필은 물류 계약과 유사하지만 법적 계약은 아닙니다. 화물에 대한 운송 요금을 결정하는 데 사용됩니다. 

각 등급 프로필은 운송업체마다 다릅니다. 프로필에서 운송업체를 요율 마스터와 연결합니다. 요율 마스터는 요율 기준 지정 및 요율 기준을 정의합니다. 요율 기준은 운송업체의 요율을 결정합니다.

모든 기존 평가 프로필의 개요를 표시하는 일반 페이지를 사용하여 평가 프로필을 설정할 수 있습니다. 또는 운송업체에서 직접 평가 프로필을 설정할 수 있습니다. 두 경우 모두 평가 프로필에 대해 설정한 정보는 동일합니다.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>등급 프로필 페이지에서 등급 프로필 생성 또는 편집

**등급 프로필** 페이지에서 사용 가능한 모든 등급 프로필을 검토할 수 있습니다. 기존 프로필을 편집하고 새 프로필을 만들 수도 있습니다.

1. **운송 관리 \> 설정 \> 등급 \> 등급 프로필** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 새 등급 프로필을 추가하거나 **편집** 을 선택하여 기존 프로필을 편집합니다.
1. 신규 또는 기존 평가 프로필 행에서 다음 필드를 설정합니다.

    - **평가 프로필** – 등급 프로필의 고유 식별자(ID)를 입력합니다.
    - **이름** – 등급 프로필을 설명하는 이름을 입력합니다.
    - **배송사** – 배송사를 선택합니다. 설정 중인 등급 프로필은 선택한 운송업체의 **운송업체** 페이지에도 표시됩니다.
    - **사이트** 및 **창고** – 사이트 및 창고를 선택합니다.
    - **요금 엔진** – 등급 프로필에 대한 요금 엔진을 선택합니다.
    - **요금 마스터** – 등급 프로필에 대한 요금 마스터를 선택합니다. 요율 마스터를 사용하여 요율 기준 유형 및 요율 기준을 정의할 수 있습니다. 자세한 내용은 [요율 마스터 설정](set-up-rate-masters.md)을 참조하세요.
    - **운송 시간 엔진** – 등급 프로필에 대한 운송 시간 엔진을 선택합니다.
    - **운송업체 연료 지수** – 등급 프로필에 대한 운송업체 연료 지수를 선택합니다.
    - **효과 시작 날짜 및 시간** 및 **효과 종료 날짜 및 시간** – 등급 프로필이 활성화되어야 하는 기간을 정의합니다.

1. 작업 창에서 **저장** 을 선택합니다.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>운송업체 페이지에서 직접 등급 프로필 생성

1. **운송 관리 \> 설정 \> 운송업체 \> 운송업체** 로 이동합니다.
1. 목록에서 운송업체를 선택합니다.
1. **등급 프로필** 빠른 탭에서 **새로 만들기** 를 선택하여 등급 프로필을 만듭니다.
1. 새 등급 프로필에 대한 필드를 설정합니다. 이 필드는 이 토픽의 이전 섹션에서 설명한 대로 **등급 프로필** 페이지의 필드에 해당합니다.

> [!NOTE]
> **운송업체** 페이지에서 생성된 프로필은 **등급 프로필** 페이지에도 표시됩니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]