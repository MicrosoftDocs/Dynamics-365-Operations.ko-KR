---
title: 분개장 및 라인 설정 취소
description: 이 항목에서는 게시된 거래에 일반 분개장에 입력된 반대 기입이 포함되지 않는 이유를 설명합니다.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d0659fbd814d3fb86b2f4a1ecb6162614ab8a4f125029fbb04f08cc5fb52b45c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452878"
---
# <a name="reverse-settings-on-journals-and-lines"></a>분개장 및 라인 설정 취소

[!include [banner](../includes/banner.md)]

이 항목에서는 게시된 거래에 일반 분개장에 입력된 반대 기입이 포함되지 않는 이유를 설명합니다.  

## <a name="symptom"></a>증상

일반 분개장에는 분개장의 반대 기입과 반전 날짜가 포함됩니다. 분개장을 게시해도 쿠폰이 반전되지 않습니다. 왜 이런 일이 발생합니까?

## <a name="resolution"></a>해결책

분개장이 공시될 때 취소 프로세스는 쿠폰의 **라인** 섹션에 있는 **반대 기입** 과 **반전 날짜** 설정만 살펴봅니다. 이 접근 방식을 사용하면 분개장에 반전 표시가 있는 일부 쿠폰과 그렇지 않은 쿠폰이 포함될 수 있습니다.

분개장의 값은 *새* 라인을 추가할 때 기본값으로만 사용됩니다. 분개장의 값을 변경해도 기존 라인은 영향을 받지 않습니다. 이 예에서는 쿠폰 라인이 먼저 입력되었습니다. 분개장을 역으로 지정하기 전에 라인 상세 내역을 입력하면 반대 기입 및 반전 날짜가 기존 라인에 적용되지 않습니다.

기존 라인의 반대 기입 또는 반전 날짜를 변경하면 동일한 쿠폰의 다른 라인으로 변경한 내용이 전파됩니다. 성능을 최적화하기 위해 다른 라인에 변경 사항을 전파한 후에 그리드를 새로 고치지 않습니다. 그리드를 새로 고쳐 업데이트된 값을 표시할 수 있습니다.


