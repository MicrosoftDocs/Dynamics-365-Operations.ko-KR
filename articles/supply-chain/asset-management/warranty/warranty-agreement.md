---
title: 보증 계약
description: 이 토픽에서는 자산 관리의 보증 계약에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8269b9f2084ddd0f69039044c29978ce7940270d5b569456f7a0bfca0a6f1f0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446839"
---
# <a name="warranty-agreements"></a>보증 계약

[!include [banner](../../includes/banner.md)]

 


자산 관리에서 자산 또는 자산 유형에 연결할 수 있는 보증 조건을 설정할 수 있습니다. 보증 기간은 특정 기간 동안 생성됩니다. 보증은 전체 보장 또는 부분 보장을 제공하도록 설정할 수 있으며 시간, 비용 및 항목과 관련된 조건을 설정할 수 있습니다.

첫 번째 단계는 장비에 대한 공급업체 보증 계약을 작성하는 것입니다. 그런 다음 자산 또는 자산 유형에 보증 계약을 첨부합니다. 공급업체 보증 계약은 정보 제공의 목적으로만 사용됩니다. 자산에 공급업체 보증이 설정된 경우 자산에 대한 보증 적용 기간을 볼 수 있습니다.

## <a name="create-a-warranty-agreement"></a>보증 계약 생성

보증 계약에는 작업 시간, 비용 및 항목에 대한 보증을 포함하는 여러 계약 라인이 포함될 수 있습니다.

1. **자산 관리** \> **설정** \> **자산** \> **보증** 을 선택합니다.
2. **새로 만들기** 를 선택하여 제품을 만듭니다.
3. **보증** 필드에서 보증 ID를 입력합니다. 
4. **이름** 필드에 설명을 입력합니다.

    **세부 정보** 빠른 탭에서 **자산** 필드는 보증 계약을 사용하는 활성 자산의 수를 표시합니다.

5. **보증 라인** 빠른 탭에서 다음 단계에 따라 보증 계약에 포함되어야 하는 라인을 추가합니다.

    1. **라인 추가** 를 선택하여 보증에 새 조건을 추가합니다. 순차적인 라인 번호가 **라인** 필드에 자동으로 입력됩니다.
    2. **기간** 필드에서 보증 기간 유형을 선택합니다.
    3. **간격** 필드에 숫자를 입력합니다. 이 필드는 보증이 유효한 기간 수를 정의합니다.
    4. **비율** 필드에 보증 라인에 대한 적용 비율을 입력합니다. 백분율은 회사에서 얼마를 커버하는지 나타냅니다.

![보증 페이지.](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]