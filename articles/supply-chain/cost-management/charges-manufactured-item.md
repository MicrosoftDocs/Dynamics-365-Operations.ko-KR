---
title: 제조 품목에 대한 표시 요금
description: 제조 품목의 일정 비용은 작업 설정 시간과 일정 수량 또는 일정 스크랩 양이 있는 구성품을 반영합니다.
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: dbce06f554a5c2cf3a52d1a508c1391882af44b8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448861"
---
# <a name="display-charges-for-a-manufactured-item"></a>제조 품목에 대한 표시 요금

[!include [banner](../includes/banner.md)]

제조 품목의 일정 비용은 작업 설정 시간과 일정 수량 또는 일정 스크랩 양이 있는 구성품을 반영합니다.

계산된 아이템 비용은 아이템의 단가와 함께 표시될 수 있습니다. 그러나 요금이 별도의 필드로 표시되는 경우가 있으며 항목의 단가에 포함되지 않습니다. 비용이 별도의 필드로 표시되는 경우 한 필드에는 총 비용 금액이 표시되고 다른 필드에는 금액을 상각하는 데 사용되는 원가 계산 로트 크기가 표시됩니다. 예를 들어 항목 가격 페이지에는 두 개의 개별 필드로 요금이 표시됩니다. 그러나 완료 페이지에는 항목의 단위당 총 비용이 표시되고 상각된 비용은 단위 비용에 포함됩니다.

제조된 품목에 대한 비용은 표준 원가 목적으로 항상 품목의 단가에 포함됩니다. 계획된 비용 목적으로 선택적으로 포함될 수 있습니다. 원가 계산 버전의 정책은 제조 품목의 원가에 비용을 포함하도록 강제합니다. 항목의 비용 레코드를 활성화하면 항목 가격 페이지에 표시되는 항목의 기본 비용 정보에 대한 요금을 업데이트합니다. 요금이 두 가지 별도의 필드로 표시되는 경우가 있으며 항목의 단가에 포함되지 않습니다. 활성화할 때마다 다른 사이트가 반영되더라도 항목의 기본 비용 정보가 업데이트됩니다. 따라서 기본 비용 정보를 참조 정보로 보아야 합니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]