---
title: 생산 또는 조달할 수 있는 제품 설정
description: 제품은 다양한 방식으로 소싱될 수 있습니다. 즉, 생산(제조)하거나 조달(구매)할 수 있습니다. 이 문서에서는 다중 소싱을 지원하도록 제품을 구성할 때 고려해야 할 몇 가지 일반적인 사항에 대해 설명합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 344a022561fa425747e7674bd600c65d70229557
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448093"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a>생산 또는 조달할 수 있는 제품 설정

[!include [banner](../includes/banner.md)]

제품은 다양한 방식으로 소싱될 수 있습니다. 즉, 생산(제조)하거나 조달(구매)할 수 있습니다. 이 문서에서는 다중 소싱을 지원하도록 제품을 구성할 때 고려해야 할 몇 가지 일반적인 사항에 대해 설명합니다. 

다중 소싱은 일반적으로 가끔 제조되는 구매 품목에 사용되거나 주로 제조 품목이었던 품목이 이제 주로 구매 품목이 되도록 변경될 때 사용됩니다. 먼저 품목을 제조 품목으로 지정하여 BOM(자재 명세서) 및 경로 정보를 정의하고 품목에 대한 생산 오더를 지원합니다. 생산 유형은 **BOM**(또는 공정 제조의 경우 **수식** 또는 **연산품**)으로 설정되어야 합니다.

표준 원가를 사용하면 제조된 품목에 대한 품목원가 기록을 계산할 수 있습니다. 그러나 품목 비용 레코드가 구매 목적으로 원하는 표준 비용과 일치하지 않을 수 있습니다. 이 경우 품목 원가 레코드에 대해 표준 원가를 수동으로 입력하고 활성화해야 합니다. 비용 계산을 위해 시간 경과에 따른 편차를 최소화하기 위해 회계 기간 동안 제품의 공급 구성을 나타내는 특수 BOM 및 경로를 사용하는 것이 좋습니다. 또한 한 사이트에서 제조된 품목을 다른 사이트로 이전할 수 있습니다. 따라서 항목의 비용을 수동으로 입력하고 항목이 이전되는 사이트에 대해 활성화해야 합니다. 제조된 품목을 상위 제품의 구성품으로 사용할 경우 구성품의 비용은 구매 품목으로 처리해야 합니다. 이 지침은 구성 요소의 비용이 계산되었거나 수동으로 입력되었는지 여부에 관계없이 적용됩니다. 즉, BOM 계산은 품목의 BOM 및 경로 정보를 사용하여 비용을 계산하는 대신 품목의 비용을 구매한 구성 요소로 처리해야 합니다. 

계산이 발생하지 않도록 하려면 항목에 할당된 BOM 계산 그룹에 포함된 **폭발 중지** 플래그를 선택합니다. 기준 일정 계획 계산이 품목을 통해 소요량을 확장하지 않도록 하려면 품목 적용 범위 또는 적용 범위 그룹에서 확장 펜스를 0(영)일로 설정합니다. 그러면 기준 일정 계획은 항목을 구매한 항목으로 처리하고 항목의 BOM 및 경로 정보에 대해 더 이상 계산을 수행하지 않습니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]