---
title: 통합 원장
description: 이 항목에서는 Dataverse를 사용하는 재무 및 운영과 기타 Dynamics 365 응용 프로그램 간의 원장 데이터 통합에 대해 설명합니다.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 0deb4198acb59b90bf06e4050889d028df2223e3
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460684"
---
# <a name="integrated-ledger"></a>통합 원장

[!include [banner](../../includes/banner.md)]



비즈니스 애플리케이션에서 원장 데이터는 회사가 비즈니스를 수행하는 방법에 대한 핵심 설정을 정의합니다. 예를 들어, 원장 데이터는 회사가 따르는 회계 연도, 거래하는 통화 및 사용하는 계정을 설명합니다. 이 항목에서는 이 핵심 재무 데이터의 통합에 대해 설명합니다.

## <a name="templates"></a>템플릿

원장 데이터에는 다음 표와 같이 데이터 상호 작용 중에 함께 작동하는 핵심 재무 테이블 맵 모음이 포함됩니다.

금융 및 운영 앱 | Customer Engagement 앱     | 설명
---------------------------------|----------------------------------|------------
[CDS 환율](mapping-reference.md#123) | msdyn_currencyexchangerates |
[계정 차트](mapping-reference.md#121) | msdyn_chartofaccountses |
[통화](mapping-reference.md#218) | transactioncurrencies |
[환율 통화 쌍](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[환율 유형](mapping-reference.md#129) | msdyn_exchangeratetypes |
[재무 차원 형식](mapping-reference.md#130) | msdyn_financialdimensionformats |
[재무 차원](mapping-reference.md#128) | msdyn_dimensionattributes |
[회계 캘린더 통합 엔터티](mapping-reference.md#132) | msdyn_fiscalcalendars |
[회계 달력 기간](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[회계 캘린더 연도 통합 엔터티](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[원장](mapping-reference.md#148) | msdyn_ledgers |
[주 계정](mapping-reference.md#152) | msdyn_mainaccounts |
[주 계정 카테고리](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
