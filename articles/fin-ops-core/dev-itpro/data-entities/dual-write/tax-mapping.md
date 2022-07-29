---
title: 통합 세금
description: 이 항목에서는 재무 및 운영과 Dataverse 간의 세금 데이터 통합에 대해 설명합니다.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 532e6603b74ad0293d65684d2d6858ef31fbc496
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460899"
---
# <a name="integrated-tax"></a>통합 세금

[!include [banner](../../includes/banner.md)]



세금 설정 데이터는 간접세(VAT, GST, 판매세) 및 원천세 모두에 대한 설정을 정의합니다. 세금 계산 규칙, 세율, 세무 회계, 결산 및 기타 개념에 대해 설명합니다.

## <a name="templates"></a>템플릿

세금 데이터에는 다음 표와 같이 데이터 상호 작용 중에 함께 작동하는 테이블 맵 모음이 포함됩니다.

| 금융 및 운영 앱 | Customer Engagement 앱 | 설명 |
|-----------------------------|-----------------------------------|-------------|
[품목 판매세 그룹](mapping-reference.md#196) | msdyn_taxitemgroups | |
[판매세 당국](mapping-reference.md#193) | msdyn_taxauthorities | |
[판매 면세 코드 엔터티 CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[판매세 그룹](mapping-reference.md#195) | msdyn_taxgroups | |
[판매세 원장 기장 그룹 V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[원천징수세 코드](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[원천징수세 그룹](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
