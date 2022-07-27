---
title: 고객 신용 그룹
description: 이 토픽에서는 고객 신용 그룹에 대한 정보를 제공합니다.
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: c8a007dcaaa9e10ab36dd3a7d0f80dd49b8e4d63
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451159"
---
# <a name="customer-credit-groups"></a>고객 신용 그룹

[!include [banner](../includes/banner.md)]

공유 신용 한도가 있는 고객 그룹을 정의할 수 있습니다. 고객 송장 계정에 정의된 개별 신용 한도도 고려됩니다.

고객 신용 그룹의 구성원은 다른 법인에서 선택할 수 있습니다. 고객 신용 그룹의 고객 목록에 고객을 추가하면 각 고객의 신용 한도 만료 날짜가 그룹에 할당된 만료 날짜로 변경됩니다.

**고객 신용 그룹** 페이지(**신용 관리 \> 고객 신용 그룹 \> 고객 신용 그룹**)에서 고객 신용 그룹을 설정할 수 있습니다.

1. **그룹 번호** 및 **설명** 필드에 그룹의 식별자와 설명을 입력합니다.
2. **신용 한도** 및 **통화** 필드에 시스템이 그룹 구성원의 신용 한도를 확인할 때 사용할 신용 한도 및 통화를 입력합니다.
3. **신용 한도 종료 날짜** 필드에 신용 한도가 만료되는 날짜를 입력합니다. 고객 신용 그룹에는 만료 날짜가 있어야 합니다.

고객 신용 그룹 설정을 완료한 후 법인 및 고객 계정 ID를 지정하여 고객을 추가할 수 있습니다. 고객 신용 그룹에 새 고객을 추가하면 시스템은 모든 법인에서 동일한 고객 계정을 검색하고 이를 고객 신용 그룹에 추가하라는 메시지를 표시합니다.

**에이징 잔액** 메뉴를 사용하여 고객 신용 그룹의 모든 송장 고객에 대한 에이징 잔액 세부 정보를 봅니다. **에이징 잔액** 페이지에는 송장 고객 계정에 대한 에이징 잔액의 요약이 표시됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
