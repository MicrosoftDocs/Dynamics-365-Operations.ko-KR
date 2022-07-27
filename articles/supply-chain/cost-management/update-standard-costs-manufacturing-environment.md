---
title: 제조 환경에서 표준 비용 업데이트
description: 이 문서에서는 제조 환경에서 표준 비용을 업데이트하는 방법에 대한 지침을 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0c8cae65ef95e299f9b774c4fa18dbdc615dd169138835f1852ee21a54cba69
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446836"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>제조 환경에서 표준 비용 업데이트

[!include [banner](../includes/banner.md)]

이 문서에서는 제조 환경에서 표준 비용을 업데이트하는 방법에 대한 지침을 제공합니다. 

업데이트는 새 항목, 비용 범주 또는 간접비 계산 공식을 반영할 수 있습니다. 또한 수정 및 비용 변경을 반영할 수 있습니다. 업데이트 유형은 다음 경우와 같이 표준 비용을 업데이트하기 위해 완료해야 하는 단계에 영향을 줍니다.

-   구매 품목에 대한 예상 표준 원가 변경을 입력한 다음 해당 일자에 품목 원가 레코드의 상태를 **활성** 으로 변경합니다. 그러나 구매한 품목을 사용하는 제조 품목의 비용을 다시 계산하지 마세요.
-   신규 구매 품목에 대한 표준 원가를 입력하되 신규 구매 품목을 구성요소로 포함하는 BOM(자재 명세서) 버전이 있는 제조 품목의 원가는 재계산하지 마세요.
-   구매 품목의 비용을 수정 또는 변경하거나 구매 품목에 지정된 비용 그룹을 변경하고 구매 품목을 구성요소로 포함하는 BOM 버전이 있는 모든 제조 품목의 비용을 계산합니다.
-   비용 범주에 대한 비용을 변경하고 비용 범주를 사용하는 공정순서 작업이 포함된 경로 버전이 있는 모든 제조 품목의 비용을 계산합니다.
-   공정순서 작업에 지정된 비용 범주 또는 비용 범주에 지정된 비용 그룹을 변경합니다. 그런 다음 비용 범주를 사용하는 공정순서 작업이 포함된 경로 버전이 있는 모든 제조 품목의 비용을 계산합니다.
-   간접비 계산 공식을 변경하고, 변경의 영향을 받는 모든 제조 품목에 대한 원가를 계산합니다.
-   제조 품목에 대한 제조 사이트를 변경하거나 추가하고 해당 사이트에 대한 품목 제조 비용을 계산합니다.
-   제조 품목의 비용을 계산하거나 재계산하고, 제조 품목을 구성요소로 포함하는 BOM 버전이 있는 모든 제조 품목의 비용을 재계산합니다.
-   정의, 승인 및 활성 BOM 및 경로 정보를 기반으로 새로운 제조 품목의 비용을 계산합니다.

각 경우에는 표준 비용을 업데이트하는 방법에 대한 신중한 고려가 필요합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]